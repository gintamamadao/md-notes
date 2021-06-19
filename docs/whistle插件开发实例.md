# Parent Node

- [ROOT](./root.md)
- [whistle 学习杂记](./whistle学习杂记.md)

# Child Node

# whistle 插件开发实例


```ts
/* eslint-disable import/no-dynamic-require */
import { join, extname } from 'path'
import { createReadStream } from 'fs'
import { fsUtil, cache } from '@credit/cli-helper'
import mime from 'mime-types'

const RULE_JSON = 'rules.js'

export const getMockJson = (fileDir: string, pathname: string, rules: any) => {
  let truePathname = pathname
  if (pathname.indexOf('?')) {
    truePathname = pathname.split('?')[0]
  }
  const routeArr = truePathname.split('/').filter((v) => v)

  const map = rules.map || {}
  let key = ''
  let fileName = ''
  for (let i = 0; i < routeArr.length; i++) {
    const route = routeArr[routeArr.length - i - 1]
    if (key) {
      key = `${route}/${key}`
    } else {
      key = route
    }
    fileName = map[key]
    if (fileName) {
      break
    }
  }
  if (!fileName) {
    return
  }
  const filePath = join(fileDir, fileName)
  const mimeType = mime.lookup(filePath)
  const ext = extname(filePath)

  if (!fsUtil.exist(filePath)) {
    return
  }
  const stream = createReadStream(filePath)

  return {
    contentType: mimeType,
    stream,
    data: ext === '.json' ? fsUtil.read(filePath) : undefined,
  }
}

export default (server /* , options */) => {
  // handle http request
  server.on('request', async (req, res) => {
    try {
      const originalReq = req.originalReq
      const { ruleValue, relativeUrl } = originalReq
      const rulesFile = join(ruleValue, RULE_JSON)
      if (!fsUtil.exist(rulesFile)) {
        res.end('rules no found')
        return
      }
      const rules = require(rulesFile)
      cache.write(rules, 'json')
      const json = getMockJson(join(ruleValue, rules.dir), relativeUrl, rules)
      if (!json) {
        req.passThrough(`${rules.host}${relativeUrl}`)
        return
      }
      cache.write(json, 'json')
      res.setHeader('content-type', json.contentType)
      if (json.data) {
        res.end(json.data)
        return
      }
      const responseData: any = [] // 存储文件流
      if (json.stream) {
        json.stream.on('data', function (chunk) {
          responseData.push(chunk)
        })
        json.stream.on('end', function () {
          const finalData = Buffer.concat(responseData)
          res.end(finalData)
        })
      }
    } catch (e) {
      console.log(e, 'response')
      res.end(e)
    }
  })

  // handle websocket request
  server.on('upgrade', (req /* , socket */) => {
    // 修改 websocket 请求用，
    req.passThrough() // 直接透传
  })

  // handle tunnel request
  server.on('connect', (req /* , socket */) => {
    // 修改普通 tcp 请求用
    req.passThrough() // 直接透传
  })
}

```
# Parent Node

- [ROOT](./root.md)
- [git 学习杂记](./git学习杂记.md)

# Child Node

# git 批量删除 tag

- 删除所有远程标签

```sh
git show-ref --tag | awk '{print ":" $2}' | xargs git push origin
```

- 删除所有本地标签

```sh
git tag -l | xargs git tag -d
```

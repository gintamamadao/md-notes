# Parent Node

- [ROOT](./root.md)
- [git 学习杂记](./git学习杂记.md)

# Child Node

# git config 例子

```sh
[core]
	repositoryformatversion = 0
	filemode = false
	bare = false
	logallrefupdates = true
	symlinks = false
	ignorecase = true
[remote "origin"]
	url = git@github.com:gintamamadao/blog.git
	fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
	remote = origin
	merge = refs/heads/master
[user]
	name = gintamamadao
	email = gintamaginsan@126.com
[alias]
    blog = !git add . && git commit -m 'article' && git push
	dcommit = "!f(){ git add . && git commit -m $1; }; f"
    cppush = "!f(){ git commit -m $1 && git pull --rebase && git push; }; f"
    ppush = !git pull --rebase && git push
    acheckout = "!f(){ git submodule foreach 'git checkout '$1; }; f"
    rpull = !git pull --rebase
    apull = !git submodule foreach 'git pull --rebase'
```

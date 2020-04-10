> 前提 :
>
> 1. 会Git和GitHub
> 2. 安装Git
> 3. 安装hugo

## 使用hugo

1. 创建个人博客 : `hugo new site cryptoyc.github.io`

2. 进入该目录 : `cd cryptoyc.github.io`

3. 新建第一篇文章 : `hugo new post/使用Hugo搭建个人博客.md`

## 安装主题

1. 在[官方主题](https://themes.gohugo.io/)选择一个主题，如[beautifulhugo](https://github.com/halogenica/beautifulhugo)

2. 下载主题，并把该主题加到themes目录下
```shell
git init
git submodule add https://github.com/halogenica/beautifulhugo.git themes/beautifulhugo
```

3. 进入themes目录，把exampleSite下的config.toml覆盖到cryptoyc.github.io下的config.toml

4. 修改config.toml，如下

```shell
baseurl = "https://cryptoyc.github.io"
DefaultContentLanguage = "en"
title = "cryptoyc"
# 编译静态文件到cryptoyc.github.io下的docs目录
publishDir = "docs"
theme = "beautifulhugo"


[Params]
  subtitle = "I am what I am"
  # 在themes/static/img中替换logo
  logo = "img/avatar-icon.png" 
  # 在themes/static/img中替换favicon
  favicon = "img/favicon.ico"
  dateFormat = "January 1, 2000"
  commit = true
  rss = true
  comments = true
  readingTime = true
  wordCount = true
  useHLJS = true
  socialShare = true
  delayDisqus = true
  showRelatedPosts = true


[Author]
  name = "cryptoyc"
  website = ""
  email = ""
  github = ""
  linkedin = ""
  telegram = ""


[[menu.main]]
    name = "Blog"
    url = ""
    weight = 1

[[menu.main]]
    name = "About"
    url = "page/about/"
    weight = 2

[[menu.main]]
    name = "Tags"
    url = "tags"
    weight = 3
```

## 发布到GitHub

1. 先在本地预览一下，`hugo server -D`

2. 编译静态文件, `hugo -t beautifulhugo`

3. 在GitHub创建一个项目，名字为`example.github.io`

4. 进入docs，把docs上传到Github

```
git init
git add --all
git commit -m "first commit"
git push -u origin master
```

5. 最后，打开[https://cryptoyc.github.io](https://cryptoyc.github.io)

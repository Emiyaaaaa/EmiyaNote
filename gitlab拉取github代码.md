# gitlab拉取github代码


1. `cd ./.git`
2. `code config`
3. ```
    [remote "origin-github"]
      url = git@github.com:realsee-developer/dnalogel.git
      fetch = +refs/heads/*:refs/remotes/origin/*
    [branch "lhz/github"]
      remote = origin-github
      merge = refs/heads/main
    ```
  1. 会将gitlab中本地`lhz/github`分支指向 [remote "origin-github"] 中的配置，即远程仓库为 git@github.com:realsee-developer/dnalogel.git，分支为 main
  2. git pull origin-github main 即可拉取 github 上的代码
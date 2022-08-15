# github ssh连接


1. `cd ~/.ssh/`
1. `ssh-keygen -t rsa -f 'xxx'`
1. `cat xxx.pub`
1. 复制到github
1. `ssh -v git@github.com`
1. `ssh-agent -s`
1. `ssh-agent bash`
1. `ssh add 'xxx'`
1. `ssh -v git@github.com` 成功
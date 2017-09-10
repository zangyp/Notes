* `git version` 查看git版本信息  
* `git config -l` 查看当前git环境详细配置  
* `git config --system --list` 查看系统配置  
* `git config --global --list` 查看当前用户的全局配置  
* `git config --local --list` 查看当前仓库配置信息  
* `git config --global user.name <user.name>` 配置全局用户名称  
* `git config --global user.email <user.email>` 配置全局邮箱  
* `git init` 在当前目录新建一个git代码库  
* `git clone <url>` 克隆一个项目和它的整个代码历史（版本信息）  
* `git status .` 查看所有文件状态  
* `git status <filename>` 查看指定文件状态  
* `git add <file1> <file2>` 添加指定文件到暂存区  
* `git add <dir>` 添加指定目录到暂存区  
* `git add .` 添加当前目录所有文件到暂存区  
* `git diff <filename>` 查看工作区和暂存区文件的差异  
* `git log` 查看提交日志  
* `git log -l <num>` 查看最近的num次修改  
* `git branch` 列出所有本地分支  
* `git branch -r` 列出所有远程分支  
* `git branch -a` 列出所有本地分支和远程分支  
* `git branch <branch.name>` 新建一个分支，但依然停留在当前分支  
* `git checkout -b <branch.name>` 新建一个分支，并切换到该分支  
* `git checkout <branch.name>` 切换到指定分支并更新工作区  
* `git merge <branch.name>` 合并指定分支到当前分支  
* `git branch -d <branch.name>` 删除分支  
* `git push orign --delete <branch.name>` 删除远程分支  
* `git branch -dr <remote/branch>` 删除远程分支  

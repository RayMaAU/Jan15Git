# Lecture2 Git

## - 为什么要使用 Git?
   - 如何设置 Git?
   - Git 的基本使用方法
   - 使用 Git branch 进行日常协作
   - 使用 merge 和 rebase 合并分支
   - 使用 GitHub 进行团队协作

# NOTE

## Version Control System
 - Snapshot
 - 回溯历史 每一步的改变
  - 稳定性测试 beta 内测
  - candidate 公测
 - 协同合作 查看知道谁写的 为哪个ticket去写的
 - 备份 

## Glossary
 - Repository
 : repo对应一个project

 - Diff 版本之间的差异
 - Commit 代码提交的动作
 - Branch 分支 从最初版本到后来的改变 linear
 : 使用多条线的结构 每个人产生属于自己的历史记录（树状结构）

 - Merge 合并到另一个分支
 - Clone code + history
 - Fork

## Centralized & Distributed
 - SUBVERSION
 : SVN TFS TFVC
 - Distributed
 冲突解决 没有区别
 代码合并历史
 本地拥有完整仓库 

## Waht is Git
 - Speed
 - Data intergrity
 - Support and sitributed

## Git workflow
IMPORTANT
2 steps
git local repo

每天的文件目录在本地目录下
1 stage 把它放到一个暂存区域 告诉git修改了哪些文件 哪些我打算提交
2 commit 真正的提交动作
ABC才会以版本的形式（snapshot） git抓取文件作为版本保存期里

### Git branch
CLI - Command LineInterface

## git和github的区别
 - Local Repo -- IP, firewall, port
 - 需要一台Server取放Repo 提供Server的平台 最流行的就是Github

### Github和Local的关系
 - 本地和远程
 Github Remote Repo
 Local Repo
 Sync 同步 <- - -> 关系PULL和PUSH)

### PULL vs PUSH
想要在本机看到修改 pull
本地修改了 Stage commit

### PR pull request
: 代码合并

## Git Global Setup
 - git config --global user.name "<your-full-name>"
 - git config --global user.email "<your-email-address>"
 - git config --global color.ui auto
 - git config --global merge.conflictstyle diff3
 - git config --global core.editor "code --wait"

### 在每个repo下面设置属于这个的setup
 - git config --global --list

## Hands-on—_1
 - create a new blank folder 某个位置文件夹
 - `git init` .git -> local git repo
 - inclu. code history branch metadata `shift+command+.`
 - 文件夹下面 建立`index.html`  working diretory
 - `git status

 - vsc + added or `git add./styole.css` or `git add .`
 - those file already in stage
 - vsc can automatically freshed
 - 做一个版本快照 snapshot `git commit -m "WI108-Create Homepage"`
 - ! + return 自动生成html

修改的话 如何操作
 - 比如在body里一点东西
 - stage + commit

## Git Ignore的文件 写上哪些文件可以自动忽略掉
 - blah.exe blah.lib 不用的文件 不需要进行版本跟踪

## Undoing things
 - undoing the last commit/comment: git commit --amend
 This is a H2 title

 - `commit -> commit staged (amend)`
 - git history  - Git: View History (git log)
 git history extention 安装我们就可以显示图形化的历史记录
 : check pervous cersion vs current version
 
 - git rm test.txt
 - git clearn remove untracked files form the workin tree
 - git stash stash the changes in a dirty working directory away
 JAN15GIT     
 - CRAT A REPO - Setting - Colaborators - Manage access - add people

 choose the line - Git: View Line History  View history

## Git stash
 - Feature A做到一半 需要去做fix bug
 - 缓存 `git stash` - `git stash list` or vscode (... - stash / apply stash / pop stash 把最轻的提取出来) 不确定哪个方法最好的时候 方法A做好可以先缓存 再开始做方法B

## Git Cloud Repository
  - 创建repo的时候如果是java的项目 add .gitignore - java
  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

### repo点击commits 可以查询commits历史

## Fetch做一个remote和local repo的检查 但是不会push/pull
### commit message 一定要有意义 区分每次做的是什么 不能随意写

## 回滚操作 `git revert`
 - 用一个新的commit对历史记录进行回滚 revert
 - revert操作流程 git history - more - `X Revert this (xxxxxxx) commit`
 - 用命令行就需要copy hash to clipboard

### `git reset`
: 从历史记录中删除commit  soft/hard

### git clean
 - 删除创建的文件

### git checkout
 - 对现有的文件做还原

### git log
 - 查看git历史 q退出

### git diff
 - 查看两个版本之间的差异

## Gith with Branching
 - create a branch `git branch`
 - checkout a branch `git checkout`
 - merge a branch `git merge`
 - rebasea a branch `git rebase`

### `git branch`
 - `git checkout -b branchname`
 : -b - branch
 - e.g., create a feat1(feature1) branch - `git checkout -b feat1`
 - create `.md` file to add and commit ...

### switch to other branch
 - `git branch master` or 左下角切换分支
 - 可以查看不同文件之间版本的差异

### create a new branch
 - `git checkout -b testBranch`
### delete that branch
 - 需要先切换到别的branch - `git branch master`
 - `git branch -d testBranch`

## check branch at Github
 - branch - `View all branches`
 - `active branch` - 现在所在的branch
 - test

## Semanticbranch names - branch的命名规则
 - `<tpye>/<ticet-number>-<title>`
 - featuer
 - fix/bugfix/hotfix
 - chore
 - e.g. create a new branch: `bugfix-101-update-dan remove-some-wordings`-  change a bit content in feature.html - add - commint - add in the first line  bugfix 101 - update and remove some wordings - then can check on github
 : 有很多commit，因为此feature branch是基于master branch发展的，所以过去master branch过去的内容历史都会继承下来，但是此branch还会有自己的history

## merge
 - bugfix merge back to feature 1 - merge back to - master
 - git visualization
 
## rebase two line-one line
### Merge conflicts
 - 在两个branch里面分别修改标题 然后切换到master branch 之后合并 `git merge feat1`
 - 处理冲突保存到stage之后add - commit
 - `git merge <branch name> --abort`
 - `git merge <branch name> --overwrite-ignore`
 - `git merge <branch name> --no-overwrite-ignore`

后进来的人 合并的人去 解决冲突


## pull request (PR)
如果是自己的repo可以做的
如果是公司 是没有办法push的

## How to do it
 - new pull requiest
 - feat 1 to master
 ... after push... feat1
 - create pull request
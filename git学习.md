# git学习

1. 简介

2. 安装

   linux : sudo apt-get install git

   git config --global user.name "linuxidc"
   git config --global user.email "root@linuxidc.net"

3. 创建版本库

   1.简介：文件目录，目录中的所有文件都可以被git管理起来，每个文件的修改删除，git都能跟踪，任何时刻都可以追踪历史，或者在某一个时刻还原

   版本库目录 /Users/git/learngit

   2.创建

   创建目录  sudo  mkdir 

   转变为git可以管理的仓库  sudo git init

   3.测试

   创建测试文件readme.txt (放到仓库目录下)

   文件添加到仓库 git add realme.txt

   提交到仓库 git commit 

   （sudo git commit  -m '提交的说明'）
   [master (root-commit) 1de2f6c] wrote a readme file   # 文件被改动
    1 file changed, 2 insertions(+)   # 添加了两行
    create mode 100755 readme.txt  

   注意：commit命令可以一次提交多个任务，git命令必须在仓库目录下

   

2. 修改回退

   修改文件后查看结果命令  git status

   修改文件后查看具体修改内容 git diff

   修改文件后提交 git add readme.txt

   再次查看文件 git status

   没问题后提交 git commit 

   注意：

   - 要随时掌握工作区的状态，使用`git status`命令。
   - 如果`git status`告诉你有文件被修改过，用`git diff`可以查看修改内容。

   查看修改记录 git log 提交日志   git log  --pretty=oneline

   回退版本 git reset --hard HEAD^

   (上上一个版本就是`HEAD^^`，当然往上100个版本写100个`^`比较容易数不过来，所以写成`HEAD~100`)

   恢复回退的版本 sudo git reset --hard 896d6 （版本号）

   记录历史命令  sudo git reflog

   

   - `HEAD`指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令`git reset --hard commit_id`。
   - 穿梭前，用`git log`可以查看提交历史，以便确定要回退到哪个版本。
   - 要重返未来，用`git reflog`查看命令历史，以便确定要回到未来的哪个版本

3. 工作区和暂存区

   ![git-stage](https://www.liaoxuefeng.com/files/attachments/919020074026336/0)

4. 查看工作区和版本库里面最新版本的区别  sudo git diff HEAD -- readme.txt

5. 撤销修改

   在add 和 commit 之前可以撤销修改  git checkout -- file

   在已经add 之后，还没有commit之前 可以撤销修改  git reset HEAD file,回退到add之前，然后再删除 .

   

   场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令`git checkout -- file`。

   场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令`git reset HEAD <file>`，就回到了场景1，第二步按场景1操作。

   场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考[版本回退](https://www.liaoxuefeng.com/wiki/896043488029600/897013573512192)一节，不过前提是没有推送到远程库。

6. 删除文件

   1.版本库中删除文件  git rm file      git commit -m 'illustrate '

   2.如果删除错了，恢复 git checkout -- file

9. 远程仓库

    github 添加key 创建新的仓库 

   创建成功后，可以添加一个新的，也可以推送一个已有的本地库

   关联本地库 git remote add 远程库的名字 git@github.com:github用户名/learngit.git

   本地库的内容推送到远程库上 git push -u 远程库的名字 master

   查询git用户名邮箱  sudo git config --global --list

   查询远程库信息 sudo git remote -v

   删除远程库信息 sudo git remote rm 远程库名字

   分支名字修改，分支重命名  git branch -m oldName  newName

   推送命令 git push -u origin master （第一次）

   推送命令 git push origin master  （之后）

   拉取远程仓库内容到本地仓库：git pull origin master

   

9. 远程库克隆

  克隆  git clone git@github.com:renchang110/gitclone.git

9. 分支管理

  

9. 

   

   

   




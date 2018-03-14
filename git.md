```javascript
1.版本控制器 --> git
2.GIT 之所以优秀是因为Git 跟踪并管理的是修改，而非文件。
3.安装，默认流程安装后配置全局设置,代表这台机器的身份证
    $ git config --global user.name "Your Name"
    $ git config --global user.email "email@example.com"
4.本地仓库
  1. 你的文件夹（工作区）
  2. 隐藏文件夹 .git 就是版本库
  3. 版本库里有 暂存区和本地仓库的分支(master....)

5.远程仓库(例如github)
    1.生成SSH key
        在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，
        如果已经有了，可直接跳到下一步。如果没有，打开 Shell（Windows 下打开 Git Bash），创建 SSH Key：
        ssh-keygen -t rsa -C "youremail@example.com"

    2.你需要把邮件地址换成你自己的邮件地址，然后一路回车，使用默认值即可，无需设置密码
      如果一切顺利的话，可以在用户主目录里找到.ssh目录，里面有 id_rsa 和 id_rsa.pub 两个文件，
      这两个就是 SSH Key 的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。
    
    3.登陆 GitHub，打开“Account settings”，“SSH Keys”页面：
      然后，点“Add SSH Key”，填上任意 Title，在 Key 文本框里粘贴id_rsa.pub文件的内容：
6.命令汇总: 
    git add ./-u/fileName.ext
    git status 
    git commit -m "des"
    git push origin master(远程库的分支)
    git clone SSH/HTTPS 
    git pull 
    
    git init 初始化本地git版本库
    git diff filename.ext 比较该文件和之前版本的不同
    git log    查看commit版本历史记录
    git reflog 记录你的每一次命令
    git reset --hard commitID   回退到哪个commit id 的版本
    git reset --hard HEAD^  回退到上一个版本
                            HEAD表示当前版本，回退版本其实就只将HEAD的指针改变了
    git rm filename.ext  在版本库中删除文件，然后记得commit
    git checkout --filename.ext  用版本库的版本替换工作区的版本（你的乱删或者胡乱修改都不怕了）
    cat filename.ext  查看文件的内容

    git branch 查看分支
    git branch branchName 创建分支
    git checkout branchName 切换分支
    git checkout -b branchNAme 创建并切换分支
    git branch -d branchName  删除分支
    git merge dev  比如说当前在master分支，那么这条这令的意思就是将分支Dev合并到master分支
                   如果合并起了冲突，可以用git status 查看，也可以直接查看 合并之后的冲突文件cat filename.ext，
                   修改好之后再提交
    git remote 查看远程库信息一般为origin
    git remote -v 查看远程库详细信息
    git config --list  查看配置信息
    git config user.name
    git config user.email
```
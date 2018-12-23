 1、mkdir file --创建文件夹

 2、ls --查看目录
 
 3、git init --初始化

 4、ls --查看目录

 5、ls -a --查看所有目录

 6、echo "helloworld" > index.txt --写“helloworld”到index文本文件中

 7、ls --查看目录

 8、git status--显示工作目录和暂存区的状态

 9、git add .--（.）点表示当前目录下的所有内容，交给git管理，也就是提交到了git的本地仓库

 10、git status--显示工作目录和暂存区的状态

 11、git commit -m "This is first Git" --对你更新或修改了哪些内容做一个描述

 12、git log--查看提交历史
 
 13、git push--命令用于将本地分支的更新，推送到远程主机
 
 14、git remote add origin https://xxxxxxx  --
 
 15、git status--显示工作目录和暂存区的状态

 16、git push -u origin master--将本地的项目提交到远程仓库中

 .gitignore 设置git快捷键




＃从github将我们的项目下载下来
git clone https://github.com/nf147/nf147.github.io

＃切换到项目目录
cd nf147.github.io

＃在项目里添加，修改一系列文件
记事本index.html ....

＃如果要查看项目下的文件修改情况
git状态

＃如果要将修改保存，并同步到服务器，分三步：
git add .
git commit -m '我是注释信息'
git push

＃当然，如果是第一次使用，可能需要先告诉git工具你是谁，执行下面两条命令 
git config --global user.email “你的邮箱地址” 
git config --global user.name “你的名字。这个随便填，只是为了方便混帐区分不同用户”

＃后续，如果想将服务器的代码同步到本地 
git pull   ＃pull拉推推

如里有报错误：

To git@git.oschina.net:yangzhi/hello.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'git@git.oschina.net:yangzhi/hello.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushin
hint: to the same ref. You may want to first merge the remote changes (e.g.
hint: 'git pull') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
 
可以输入：

git push -f

 
 	
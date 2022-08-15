![QQ截图20210815234508](D:\git截图\QQ截图20210815234508.png)

![QQ截图20210816000131](D:\git截图\QQ截图20210816000131.png)

![QQ截图20210816004956](D:\git截图\QQ截图20210816004956.png)

![QQ截图20210816121824](D:\git截图\QQ截图20210816121824.png)

![QQ截图20210816122353](D:\git截图\QQ截图20210816122353.png)

![QQ截图20210816132819](D:\git截图\QQ截图20210816132819.png)

所有的配置文件都保存在本地



查看不同级别的配置文件：

git config --system --list		#查看系统config

git config --global --list		#查看当前用户(global)配置



配置文件：

git config --global user.name "名字"

git config --global user.name "邮箱"



git init : 生成.git文件夹



git的工作流程：

1.在工作目录中添加、修改文件；

2、将需要进行版本管理的文件放入暂存区域；	git add .

3、将暂存区域的文件提交到git仓库		git commit



![image-20220217223024237](C:\Users\000\AppData\Roaming\Typora\typora-user-images\image-20220217223024237.png)

创建本地仓库的方法有两种：一种是创建全新的仓库，另一种是克隆远程仓库

创建全新的仓库：在项目文件夹下执行命令：`git init`

克隆：`git clone 仓库链接`



`git status` : 查看文件是否被跟踪

`git status 文件名 `: 查看指定文件是否被跟踪

`git add .` : 添加所有文件到暂存区

`git commit -m "信息(自定义内容)"` : 提交暂存区的内容到本地仓库

`git push -u origin master` : 将文件提交个远程仓库

`git remote add origin 仓库地址 `: 将本地仓库与远程仓库绑定





设置本机绑定SSH公钥，可以实现免密码登录
-----------------------------------------------------------------------------------------------------------
git 安装我就不说了  一直next (注意配置git环境变量)
注册github 我也不说了
-----------------------------------------------------------------------------------------------------------
（一）检查  ssh-key
       cd ~/.ssh (提示No such file or directory 则表示没有key)
-----------------------------------------------------------------------------------------------------------
（二）生成新的ssh key。
      ssh-keygen -t rsa -C "xxxxxx@yy.com"  自己真实邮箱 一路回车
      Your identification has been saved in /c/Users/xxxx_000/.ssh/id_rsa.   #生成的密钥
      Your public key has been saved in /c/Users/xxxx_000/.ssh/id_rsa.pub.  #生成的公钥
      *本机已完成ssh key设置，其存放路径为：c:/Users/xxxx_000/.ssh/下。
-----------------------------------------------------------------------------------------------------------
 (三)  添加ssh key到GItHub
       登录GitHub系统；点击右上角账号头像的“▼”→Settings→SSH kyes→Add SSH key。
       进入c:/Users/xxxx_000/.ssh/目录下，打开id_rsa.pub文件，全选复制公钥内容。
       Title自定义，将公钥粘贴到GitHub中Add an SSH key的key输入框，最后“Add Key”。
-----------------------------------------------------------------------------------------------------------
	   
（四）配置账户
      git config --global user.name “your_username”  #设置用户名
      git config --global user.email “your_registered_github_Email”  #设置邮箱地址(建议用注册giuhub的邮箱
	-----------------------------------------------------------------------------------------------------------  
	  
（五）测试ssh keys是否设置成功  一路回车吧（前面私钥不要设置密码）
      ssh -T git@github.com
      The authenticity of host 'github.com (192.30.252.129)' can't be established.
      RSA key fingerprint is 16:27:xx:xx:xx:xx:xx:4d:eb:df:a6:48.
      Are you sure you want to continue connecting (yes/no)? yes #确认你是否继续联系，输入yes
      Hi xxx! You've successfully authenticated, but GitHub does not provide shell access. #出现词句话，说明设置成功。

	-----------------------------------------------------------------------------------------------------------  
（六）  本地项目通过SSH push到GitHub  或者 将GitHub 项目Clone 下来

     1、github上创建一个示例仓库，复制仓库ssh路径。
	 
	 2、创建本地文件夹 cd  到文件夹下
	 
	     （1）、如果是上传本地项目到github 上 步骤如下：
		 
		        创建好本地项目 test  cd test文件夹下
	                git init   初始化
		        git add .  提交当前文件夹下所以文件
		        git status  查看当前修改文件状态
		        git commit -m "add  msg" 更新信息描述（提交记录说明 ）
 	                git remote add origin ‘GitHub 的 ssh路径’ 
			git push -u origin master  （推送到GitHub 仓库）
				
			刷新仓库就可以看见项目已经上传到github了
-----------------------------------------------------------------------------------------------------------
		（2）、更新仓库项目到本地
		        创建好本地项目 test  cd test文件夹下
	                git init   初始化
			git remote add origin git@github.com:wylk/wxapps.git
                        
		        git pull --rebase origin  master   （pull 仓库项目最新版）（很重要 以后每次提交前都要执行的命令）				
			然后修改其中的某个文件后 提交：git push -u origin master  （推送到GitHub 仓库）
		
		（3）
		
		（4）
		
		
		（5）
	
	 

1、


git init


git add .


git commit -m "add  HBuilder"


git remote  add origin git@github.com:zhan520/HBuilder.git


git pull --rebase origin  master 


git push -u origin master

git reset --hard 这里是commit id，也就是我上面说的xxxx


-------------------创建与合并分支--------------------------------
Git鼓励大量使用分支：

查看分支：git branch

创建分支：git branch <name>

切换分支：git checkout <name>

创建+切换分支：git checkout -b <name>

合并某分支到当前分支：git merge <name>

删除分支：git branch -d <name>

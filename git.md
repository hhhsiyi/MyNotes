## git

### 1第一步，得先把字符集设置好， option -text-charXX-utf-8-重启gitbash

### 0如何使用git把本地的代码或者什么 东西上传到github上呢

### 2建立git仓库

- 新建一个本地仓库，其实也就是新建一个文件夹。最简单的创建方式就是直接在桌面鼠标右键，新建文件夹(test)，然后进去该文件夹。鼠标右键，打开git -> Git Bash Here -> git init。执行命令后目录下创建一个.git文件夹。
- git inti

### 3添加需要上传的代码到本地仓库

- 如何添加，首先将需要上传的代码复制粘贴到本地仓库，也就是test文件夹。

  然后git status，这时候会发现多了一些东西，这些东西就是你刚刚复制进来的文件，显示为红色，就是待添加到本地仓库的意思，就像图片这样

  ![image-20200715093330865](C:\Users\Hewen\AppData\Roaming\Typora\typora-user-images\image-20200715093330865.png)

### 4将所有的项目文件都添加到仓库中

- 既然待添加，下一步自然就是添加了，如何添加，git add + 需要添加的文件名 或者git add --all 将所有的文件全部添加，我这里是git add test.txt，然后再次git status 查看状态，可以发现test.txt变成了绿色，这时候文件就已经添加到本地仓库了，这样那些待添加的就变绿了![image-20200715093611669](C:\Users\Hewen\AppData\Roaming\Typora\typora-user-images\image-20200715093611669.png)

### 5将add添加的文件commit提交到仓库

- 添加之后，最后提交就行，git commit -m “修改说明”。-m后面添加的是对本次操作的说明，加入你修改了代码或者重新上传了什么东西都做个简单说明，别人看了就知道是怎么回事了。然后再次git status查看状态，如下，已经添加成功：

  git commit -m "第一次提交"![img](https://ss2.baidu.com/6ONYsjip0QIZ8tyhnq/it/u=3435262181,321403109&fm=173&app=49&f=JPEG?w=595&h=376&s=C562BB403BAEB74D0EFDCD0F020080C3)

- 本来想直接提交的，但是因为我之前没有配置自己的个人信息，因此提示我重新配置![image-20200715093953654](C:\Users\Hewen\AppData\Roaming\Typora\typora-user-images\image-20200715093953654.png)

### 6去github上面创建自己的Respository

- 点击Create repository，一步一步执行下去即可，创建成功后拿到创建的仓库的https地址，最后选择ssh地址
- 将本地的仓库关联到github上 git remote add origin git@github.com:hhhsiyi/MyNotes.git

### 7上传代码或者自己的文档到github的远程仓库

- 执行完后，如果没有异常，等待执行完就上传成功了，中间可能会让你输入Username和Password，你只要输入github的账号和密码就行了。但是在这一步很多人执行会报错，报类似failed to push some refs to......的错误，那是因为本地代码目录缺失README.md文件。我们只需要先

  通过如下命令进行代码合并【注：pull=fetch+merge]

  git pull --rebase origin master 打钩

### 8报错处理

- fatal: pathspec 'REAMDE.md' did not match any files
- 选择git push -u origin master

-   ~~~ xml
  The authenticity of host 'github.com (52.74.223.119)' can't be established.
  RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
  Are you sure you want to continue connecting (yes/no/[fingerprint])? y
  Please type 'yes', 'no' or the fingerprint: yes
  Warning: Permanently added 'github.com,52.74.223.119' (RSA) to the list of known hosts.
  git@github.com: Permission denied (publickey).
  fatal: Could not read from remote repository.
  
  Please make sure you have the correct access rights
  and the repository exists.
  如果报错是这样的，是因为没有对应公钥，需要生成一个公钥才行呢
    ~~~

## 如果所有全部配置完成，下一次是如何提交的呢

1. 拖文件，检查git status
2. 添加文件，git add --all或者git add 某一个文件，检查git status
3. 提交文件，git commit -m “描述这次提交的概要”，检查git status
4. 往仓库提交（push），git push -u grigin master，当然之后也可以简化流程，直接写git push也可以！
5. 去github上面去检查！

git add 

git commit

git push

我再改一下试试，行吧还是会乱码的
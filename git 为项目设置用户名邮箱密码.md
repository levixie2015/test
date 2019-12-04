###  git 为项目设置用户名邮箱密码

下面介绍对特定项目设置用户名/邮箱/密码的方法

1.找到项目所在目录下的 .git，进入.git文件夹，然后执行如下命令分别设置用户名和邮箱

    git config user.name "Affandi"

    git config user.email "123333333@qq.com"
    
 然后执行命令查看config文件：cat config
 
        cat config
        
 发现里面多了刚才配置的用户名和邮箱信息user，即成功为该项目单独设置了用户名和邮箱
    
    ...
    [branch "master"]
        remote = origin
        merge = refs/heads/master
    [user]
        name = Affandi
        email = 123333333@qq.com
 
2.如果git pull 每次都要求输入用户名和密码，则可以执行如下配置
 
    git config credential.helper store
 
 执行后， cat config查看，则多了credential的内容：
 
    [user]
        name = Affandi
        email = 123333333@qq.com
    [credential]
            helper = store

然后再回到项目目录下执行git pull/push，根据提示输入用户名和密码，输入正确后，以后再执行git pull/push 就不用输入用户名和密码了
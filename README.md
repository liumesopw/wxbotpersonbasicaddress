# wxbotpersonbasicaddress
wxbot,PC微信机器人接口api之找微信个人数据基址,windows版微信Hook开发SDK之C#版-微信二次开发，PC个人企业微信机器人之实战分析微信发送xml文章消息call，微信机器人开发sdk，个人微信机器人开发API，淘宝客微信发单机器人开发sdk，导购返利机器人研发SDK、微信群管理机器人开发SDK， 微信二次开发SDK，微信个人号开发API接口协议企业微信SDK、企业微信开发API、,企业微信第三方开发接口适用于企业微信营销软件研发、企业微信工作手机研发、企业微信云控系统研发、企业微信客服系统研发、企业微信营销系统研发、 企业微信客微商营销工具研发、企业微信scrm客服系统研发、企业微信聊天机器人、企业微信群管理机器人研发企业微信协议API接口开发
今天主要讲一下，找微信个人数据的基址，用到的软件有vs2017，OD（主要用来调试程序，找程序内部call的），CE（用来辅助我们找call的，找数据修改数据），DLL注入工具、内存修改工具 这两个我们后边自己实现。
先打开微信，然后在任务管理器里面找到微信进程名字，然后打开OD，搜索这个进程名字，附加微信，
![image](https://user-images.githubusercontent.com/96330669/175482295-f5e28ca3-de4d-4bc7-a499-7d141cde66d9.png)
附加之后，点击运行，运行之后，这个微信才能操作它。然后打开CE，搜一下自己的微信号，然后左边有黑色和绿色的结果，黑色的是动态地址，绿色的就是基址，动态地址就是在微信从新启动后，这个地址就会完全变了，基址是不会变的，就是一个模块加上一个偏移地址。
找到这个基址之后，可以在OD里面，最下面输入命令：dc 后面跟上刚才的地址，然后就看到这个地址对应的你的微信号了。然后再找一下这个头像的基址，他这个头像的基址可能是个指针，这个指针怎么理解呢，就是地址里面又装了一个地址，就是指针。
根据这些方法，可以找到每个字段的基址，比如头像，昵称，微信号等，记录下来，以备下次用。
![image](https://user-images.githubusercontent.com/96330669/175482466-a6036d3b-efc5-455d-aa89-e8e9dff5cc98.png)
目前已经实现了大部分功能，运行稳定，比如：发各种消息，
接收各种消息，群管，下载文件，加好友，检测僵尸粉，发送朋友圈，获取朋友圈，点赞发评论等等功能，
可提供接口，方便各种语言二次开发，欢迎技术交流。

企业微信：
目前已经实现了大部分功能，运行稳定，比如：发各种消息，
接收各种消息，外部群内部群管理，下载文件，加好友等等功能，
可提供接口，方便各种语言二次开发，欢迎技术交流。
请勿用于商业用途。

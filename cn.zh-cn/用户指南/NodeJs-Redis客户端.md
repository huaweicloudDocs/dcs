# NodeJs Redis客户端<a name="ZH-CN_TOPIC_0148195323"></a>

介绍使用同一VPC内弹性云服务器ECS上的NodeJs Redis客户端连接Redis实例的方法。更多的客户端的使用方法，请参考[https://redis.io/clients](https://redis.io/clients)

## 前提条件<a name="section1502270695932"></a>

-   已成功申请Redis实例，且状态为“运行中”。
-   已创建弹性云服务器，创建弹性云服务器的方法，请参见《弹性云服务器用户指南》。
-   如果弹性云服务器为Linux系统，该弹性云服务器必须已经安装gcc编译环境。

## 操作步骤<a name="section195273281212"></a>

-   **客户端服务器为Ubuntu\(debian系列\)**

1.  <a name="li5233248151213"></a>查看并获取待连接Redis实例的IP地址/域名和端口。

    具体步骤请参见[查看缓存实例信息](查看缓存实例信息.md)。

2.  登录弹性云服务器。
3.  安装NodeJs。

    **apt install nodejs-legacy**

    如果以上命令安装不了，备选方式如下：

    **wget https://nodejs.org/dist/v0.12.4/node-v0.12.4.tar.gz --no-check-certificate ;**

    **tar -xvf node-v0.12.4.tar.gz;**

    **cd node-v0.12.4;**

    **./configure;**

    **make;**

    **make install;**

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >安装完成后，可执行**node --version**查看NodeJs的版本号，确认NodeJs已安装成功。  

4.  安装js包管理工具npm。

    **apt install npm**

5.  安装NodeJs redis客户端 ioredis。

    **npm install ioredis**

6.  编辑连接Redis实例的示例脚本。

    编辑连接示例脚本ioredisdemo.js。示例脚本中增加以下内容，包括连接以及数据读取。

    ```
    var Redis = require('ioredis');
    var redis = new Redis({
      port: 6379,          // Redis port
      host: '192.168.0.196',   // Redis host
      family: 4,           // 4 (IPv4) or 6 (IPv6)
      password: '******',
      db: 0
    }); 
    redis.set('foo', 'bar');
    redis.get('foo', function (err, result) {
      console.log(result);
    }); 
    // Or using a promise if the last argument isn't a function
    redis.get('foo').then(function (result) {
      console.log(result);
    });
    // Arguments to commands are flattened, so the following are the same:
    redis.sadd('set', 1, 3, 5, 7);
    redis.sadd('set', [1, 3, 5, 7]);
    // All arguments are passed directly to the redis server:
    redis.set('key', 100, 'EX', 10);
    ```

    其中，**host**为Redis实例的IP地址/域名，**port**为Redis实例的端口。IP地址/域名和端口获取见步骤[1](#li5233248151213)，请按实际情况修改后执行。**\*\*\*\*\*\***为创建Redis实例时自定义的密码，请按实际情况修改后执行。

7.  运行示例脚本，连接Redis实例。

    **node ioredisdemo.js**


-   **客户端服务器为centos\(redhat系列\)**

1.  <a name="li11511175651212"></a>查看并获取待连接Redis实例的IP地址/域名和端口。

    具体步骤请参见[查看缓存实例信息](查看缓存实例信息.md)。

2.  登录弹性云服务器。
3.  安装NodeJs。

    **yum install nodejs**

    如果以上命令安装不了，备选方式如下：

    **wget https://nodejs.org/dist/v0.12.4/node-v0.12.4.tar.gz --no-check-certificate ;**

    **tar -xvf node-v0.12.4.tar.gz;**

    **cd node-v0.12.4;**

    **./configure;**

    **make;**

    **make install;**

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >安装完成后，可执行**node -v**查看NodeJs的版本号，确认NodeJs已安装成功。  

4.  安装js包管理工具npm。

    **yum install npm**

5.  安装NodeJs redis客户端 ioredis。

    **npm install ioredis**

6.  编辑连接Redis实例的示例脚本。

    编辑连接示例脚本ioredisdemo.js。示例脚本中增加以下内容，包括连接以及数据读取。

    ```
    var Redis = require('ioredis');
    var redis = new Redis({
      port: 6379,          // Redis port
      host: '192.168.0.196',   // Redis host
      family: 4,           // 4 (IPv4) or 6 (IPv6)
      password: '******',
      db: 0
    });
    redis.set('foo', 'bar');
    redis.get('foo', function (err, result) {
      console.log(result);
    });
    // Or using a promise if the last argument isn't a function
    redis.get('foo').then(function (result) {
      console.log(result);
    }); 
    // Arguments to commands are flattened, so the following are the same:
    redis.sadd('set', 1, 3, 5, 7);
    redis.sadd('set', [1, 3, 5, 7]); 
    // All arguments are passed directly to the redis server:
    redis.set('key', 100, 'EX', 10);
    ```

    其中，**host**为Redis实例的IP地址/域名，**port**为Redis实例的端口。IP地址/域名和端口获取见步骤[1](#li11511175651212)，请按实际情况修改后执行。**\*\*\*\*\*\***为创建Redis实例时自定义的密码，请按实际情况修改后执行。

7.  运行示例脚本，连接Redis实例。

    **node ioredisdemo.js**


## 连接Redis实例操作视频<a name="section116961735182016"></a>

如果需要详细了解连接Reids实例的操作，请单击以下链接观看视频。

[访问缓存实例操作视频](https://support.huaweicloud.com/dcs_video/index.html)


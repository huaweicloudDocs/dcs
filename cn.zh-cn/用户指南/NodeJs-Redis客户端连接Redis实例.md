# NodeJs Redis客户端连接Redis实例<a name="ZH-CN_TOPIC_0126076986"></a>

介绍使用同一VPC内弹性云服务器ECS上的NodeJs Redis客户端连接Redis实例的方法。更多的客户端的使用方法，请参考https://redis.io/clients。

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


## 相关产品及文档<a name="section152613113129"></a>

<a name="zh-cn_topic_0046844820_table1073594361220"></a>
<table><thead align="left"><tr id="zh-cn_topic_0046844820_row197372430123"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0046844820_p4737243111216"><a name="zh-cn_topic_0046844820_p4737243111216"></a><a name="zh-cn_topic_0046844820_p4737243111216"></a>相关产品</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0046844820_p18737144301214"><a name="zh-cn_topic_0046844820_p18737144301214"></a><a name="zh-cn_topic_0046844820_p18737144301214"></a>相关文档</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0046844820_row17371443131210"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0046844820_p13372054101419"><a name="zh-cn_topic_0046844820_p13372054101419"></a><a name="zh-cn_topic_0046844820_p13372054101419"></a><a href="https://www.huaweicloud.com/product/dcs.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Redis</a></p>
<p id="zh-cn_topic_0046844820_p19548105714519"><a name="zh-cn_topic_0046844820_p19548105714519"></a><a name="zh-cn_topic_0046844820_p19548105714519"></a><a href="https://www.huaweicloud.com/product/dcsmem.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Memcached</a></p>
<p id="zh-cn_topic_0046844820_p8862161219564"><a name="zh-cn_topic_0046844820_p8862161219564"></a><a name="zh-cn_topic_0046844820_p8862161219564"></a><a href="https://www.huaweicloud.com/product/ecs.html?infodocbz" target="_blank" rel="noopener noreferrer">弹性云服务器 ECS</a></p>
<p id="zh-cn_topic_0046844820_p841193941416"><a name="zh-cn_topic_0046844820_p841193941416"></a><a name="zh-cn_topic_0046844820_p841193941416"></a><a href="http://www.huaweicloud.com/product/vpc.html?infodocbz" target="_blank" rel="noopener noreferrer">虚拟私有云 VPC</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0046844820_p1381695711471"><a name="zh-cn_topic_0046844820_p1381695711471"></a><a name="zh-cn_topic_0046844820_p1381695711471"></a><a href="https://support.huaweicloud.com/usermanual-dcs/dcs-zh-ug-180315001.html?infodocbz" target="_blank" rel="noopener noreferrer">购买Redis实例</a></p>
<p id="zh-cn_topic_0046844820_p682916370595"><a name="zh-cn_topic_0046844820_p682916370595"></a><a name="zh-cn_topic_0046844820_p682916370595"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0082114847.html?infodocbz" target="_blank" rel="noopener noreferrer">连接Redis实例</a></p>
<p id="zh-cn_topic_0046844820_p16726748155912"><a name="zh-cn_topic_0046844820_p16726748155912"></a><a name="zh-cn_topic_0046844820_p16726748155912"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0061845451.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例扩容</a></p>
<p id="zh-cn_topic_0046844820_p12250886517"><a name="zh-cn_topic_0046844820_p12250886517"></a><a name="zh-cn_topic_0046844820_p12250886517"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0079545637.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例备份恢复</a></p>
<p id="zh-cn_topic_0046844820_p143616360517"><a name="zh-cn_topic_0046844820_p143616360517"></a><a name="zh-cn_topic_0046844820_p143616360517"></a><a href="https://support.huaweicloud.com/migration-dcs/zh-cn_topic_0078784423.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例数据迁移</a></p>
</td>
</tr>
</tbody>
</table>


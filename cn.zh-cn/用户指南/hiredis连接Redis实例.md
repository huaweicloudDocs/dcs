# hiredis连接Redis实例<a name="dcs-zh-ug-180814003"></a>

介绍使用同一VPC内弹性云服务器ECS上的C++  hiredis连接Redis实例的方法。更多的客户端的使用方法，请参考[https://redis.io/clients](https://redis.io/clients)

## 前提条件<a name="section1502270695932"></a>

-   已成功申请Redis实例，且状态为“运行中”。
-   已创建弹性云服务器，创建弹性云服务器的方法，请参见《弹性云服务器用户指南》。
-   如果弹性云服务器为Linux系统，该弹性云服务器必须已经安装gcc编译环境。

## 操作步骤<a name="section6715101110310"></a>

1.  <a name="li1655151054317"></a>查看并获取待连接Redis实例的IP地址/域名和端口。

    具体步骤请参见[查看缓存实例信息](查看缓存实例信息.md)。

2.  登录弹性云服务器。
3.  安装gcc、make和hiredis。

    如果系统没有自带编译环境，可以使用yum方式安装。

    **yum install gcc make**

4.  下载并解压hiredis。

    **wget https://github.com/redis/hiredis/archive/master.zip;**

5.  进入到解压目录后编译安装。

    **make**

    **make install**

6.  使用hiredis客户端连接Redis实例。

    关于hiredis的使用，请参考redis官网的使用介绍。这里举一个简单的例子，介绍连接、密码鉴权等的使用。

    1.  编辑连接Redis实例的demo示例，然后保存退出。

        vim connRedis.c

        示例内容如下：

        ```
        #include <stdio.h>
        #include <stdlib.h>
        #include <string.h>
        #include <hiredis.h>
        int main(int argc, char **argv) {
             unsigned int j;
             redisContext *conn;
             redisReply *reply;
             if (argc < 3) {
                     printf("Usage: example {instance_ip_address} 6379 {password}\n");
                     exit(0);
             }
             const char *hostname = argv[1];
             const int port = atoi(argv[2]);
             const char *password = argv[3];
             struct timeval timeout = { 1, 500000 }; // 1.5 seconds
             conn = redisConnectWithTimeout(hostname, port, timeout);
             if (conn == NULL || conn->err) {
        		if (conn) {
                     printf("Connection error: %s\n", conn->errstr);
                     redisFree(conn);
        		} else {
                     printf("Connection error: can't allocate redis context\n");
        		}
             exit(1);
             }
             /* AUTH */
             reply = redisCommand(conn, "AUTH %s", password);
             printf("AUTH: %s\n", reply->str);
             freeReplyObject(reply);
        
             /* Set */
             reply = redisCommand(conn,"SET %s %s", "welcome", "Hello, DCS for Redis!");
             printf("SET: %s\n", reply->str);
             freeReplyObject(reply);
        
             /* Get */
             reply = redisCommand(conn,"GET welcome");
             printf("GET welcome: %s\n", reply->str);
             freeReplyObject(reply);
        
             /* Disconnects and frees the context */
             redisFree(conn);
             return 0;
        }
        ```

    2.  执行以下命令进行编译。

        **gcc connRedis.c -o connRedis  -I /usr/local/include/hiredis -lhiredis**

        如果有报错，可查找hiredis.h文件路径，并修改编译命令。

        编译完后得到一个可执行文件connRedis。

    3.  执行以下命令，连接Redis实例。

        **./connRedis** **_\{redis\_ip\_address\}_** **6379** **_\{password\}_**

        其中，\{redis\_instance\_address\}为Redis实例的IP地址/域名，“6379“为Redis实例的端口。IP地址/域名和端口获取见步骤[1](#li1655151054317)，请按实际情况修改后执行。\{password\}为创建Redis实例时自定义的密码，请按实际情况修改后执行。

        返回以下回显信息，表示成功连接Redis实例。

        ```
        AUTH: OK
        SET: OK
        GET welcome: Hello, DCS for Redis!
        ```


    >![](public_sys-resources/icon-notice.gif) **注意：**   
    >如果运行报错找不到hiredis库文件，可参考如下命令，将相关文件拷贝到系统目录，并增加动态链接。  
    >**mkdir /usr/lib/hiredis**  
    >**cp /usr/local/lib/libhiredis.so.0.13 /usr/lib/hiredis/**  
    >**mkdir /usr/include/hiredis**  
    >**cp /usr/local/include/hiredis/hiredis.h /usr/include/hiredis/**  
    >**echo '/usr/local/lib' &gt;&gt;/etc/ld.so.conf**  
    >**ldconfig**  
    >以上so文件与.h文件的位置，需要替换成实际文件位置。  


## 连接Redis实例操作视频<a name="section2045018233194"></a>

如果需要详细了解连接Reids实例的操作，请单击以下链接观看视频。

[访问缓存实例操作视频](https://support.huaweicloud.com/dcs_video/index.html)

## 连接Redis实例的常见问题<a name="section17508471113"></a>

-   [如何使用Redis-cli访问Redis实例？](https://support.huaweicloud.com/dcs_faq/dcs-zh-ug-190131020.html)
-   [客户端出现概率性超时错误](https://support.huaweicloud.com/dcs_faq/zh-cn_topic_0052790071.html)
-   [客户使用Redis版本和DCS Redis版本不同是否存在兼容问题？](https://support.huaweicloud.com/dcs_faq/dcs-zh-ug-190131010.html)
-   [客户端访问Redis实例出现“ERR unknown command”的原因是什么？](https://support.huaweicloud.com/dcs_faq/dcs-zh-ug-190131011.html)
-   [为什么我的DCS缓存实例支持域名访问后，客户端无法使用域名连接DCS缓存实例？](https://support.huaweicloud.com/dcs_faq/dcs-zh-ug-180312004.html)
-   [Redis命令执行是否有超时时间？超时了会出现什么结果？](https://support.huaweicloud.com/dcs_faq/dcs-zh-ug-180718002.html)

## 相关产品及文档<a name="section152613113129"></a>

<a name="td475c361406b4841ba0faa98fc782ed5"></a>
<table><thead align="left"><tr id="rb27d733848ce4e7a9386965803595f1b"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="a5cc8ae3032d8416f9696b6f2a50d82d4"><a name="a5cc8ae3032d8416f9696b6f2a50d82d4"></a><a name="a5cc8ae3032d8416f9696b6f2a50d82d4"></a>相关产品</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="ad3b8309045294369bdb9a006daef8f00"><a name="ad3b8309045294369bdb9a006daef8f00"></a><a name="ad3b8309045294369bdb9a006daef8f00"></a>相关文档</p>
</th>
</tr>
</thead>
<tbody><tr id="re4588baf45714b4f80c021cca1290879"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="a8c37acc50b884e0b9a71051bcb9179b4"><a name="a8c37acc50b884e0b9a71051bcb9179b4"></a><a name="a8c37acc50b884e0b9a71051bcb9179b4"></a><a href="https://www.huaweicloud.com/product/dcs.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Redis</a></p>
<p id="a11d9314698354304b9a9e9cb1270b5c9"><a name="a11d9314698354304b9a9e9cb1270b5c9"></a><a name="a11d9314698354304b9a9e9cb1270b5c9"></a><a href="https://www.huaweicloud.com/product/dcsmem.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Memcached</a></p>
<p id="abeaed75bd99c4aeeb5ef850c82a274f2"><a name="abeaed75bd99c4aeeb5ef850c82a274f2"></a><a name="abeaed75bd99c4aeeb5ef850c82a274f2"></a><a href="https://www.huaweicloud.com/product/ecs.html?infodocbz" target="_blank" rel="noopener noreferrer">弹性云服务器 ECS</a></p>
<p id="zh-cn_topic_0046844820_p841193941416"><a name="zh-cn_topic_0046844820_p841193941416"></a><a name="zh-cn_topic_0046844820_p841193941416"></a><a href="http://www.huaweicloud.com/product/vpc.html?infodocbz" target="_blank" rel="noopener noreferrer">虚拟私有云 VPC</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a0c4ea7b976b745079231aeb676430680"><a name="a0c4ea7b976b745079231aeb676430680"></a><a name="a0c4ea7b976b745079231aeb676430680"></a><a href="https://support.huaweicloud.com/usermanual-dcs/dcs-zh-ug-180315001.html?infodocbz" target="_blank" rel="noopener noreferrer">购买Redis实例</a></p>
<p id="zh-cn_topic_0046844820_p682916370595"><a name="zh-cn_topic_0046844820_p682916370595"></a><a name="zh-cn_topic_0046844820_p682916370595"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0082114847.html?infodocbz" target="_blank" rel="noopener noreferrer">连接Redis实例</a></p>
<p id="a3d146c9e41904a09b098cc34a53b5652"><a name="a3d146c9e41904a09b098cc34a53b5652"></a><a name="a3d146c9e41904a09b098cc34a53b5652"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0061845451.html?infodocbz" target="_blank" rel="noopener noreferrer">变更缓存实例规格</a></p>
<p id="zh-cn_topic_0046844820_p12250886517"><a name="zh-cn_topic_0046844820_p12250886517"></a><a name="zh-cn_topic_0046844820_p12250886517"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0079545637.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例备份恢复</a></p>
<p id="zh-cn_topic_0046844820_p143616360517"><a name="zh-cn_topic_0046844820_p143616360517"></a><a name="zh-cn_topic_0046844820_p143616360517"></a><a href="https://support.huaweicloud.com/migration-dcs/zh-cn_topic_0078784423.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例数据迁移</a></p>
</td>
</tr>
</tbody>
</table>


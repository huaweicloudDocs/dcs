# C++Redis客户端（hiredis）<a name="dcs-ug-0312010"></a>

介绍使用同一VPC内弹性云服务器ECS上的C++  hiredis连接Redis实例的方法。更多的客户端的使用方法请参考[Redis客户端](https://redis.io/clients)。

>![](public_sys-resources/icon-note.gif) **说明：** 
>本章节操作，仅适用于连接单机、主备、Proxy集群实例，如果是使用C++ Redis客户端连接Cluster集群，请参考[C++ Redis客户端](https://github.com/sewenew/redis-plus-plus?_ga=2.64990636.268662337.1603553558-977760105.1588733325#redis-cluster)。

## 前提条件<a name="section1502270695932"></a>

-   已成功申请Redis实例，且状态为“运行中”。
-   已创建弹性云服务器，创建弹性云服务器的方法，请参见[创建弹性云服务器](https://support.huaweicloud.com/qs-ecs/ecs_02_0005.html)  。
-   如果弹性云服务器为Linux系统，该弹性云服务器必须已经安装gcc编译环境。

## 操作步骤<a name="section6715101110310"></a>

1.  <a name="li1655151054317"></a>查看并获取待连接Redis实例的IP地址/域名和端口。

    具体步骤请参见[查看实例信息](查看实例信息.md)。

2.  登录弹性云服务器。

    本章节以弹性云服务器操作系统为centos为例介绍通过C++ redis客户端连接实例。

3.  安装gcc、make和hiredis。

    如果系统没有自带编译环境，可以使用yum方式安装。

    **yum install gcc make**

4.  下载并解压hiredis。

    **wget https://github.com/redis/hiredis/archive/master.zip**

    **unzip** **master.zip**

5.  进入到解压目录后编译安装。

    **make**

    **make install**

6.  使用hiredis客户端连接Redis实例。

    关于hiredis的使用，请参考redis官网的使用介绍。这里举一个简单的例子，介绍连接、密码鉴权等的使用。

    1.  编辑连接Redis实例的demo示例，然后保存退出。

        **vim connRedis.c**

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

        其中，\{redis\_instance\_address\}为Redis实例的IP地址/域名，“6379“为Redis实例的端口。IP地址/域名和端口获取见[1](#li1655151054317)，请按实际情况修改后执行。\{password\}为创建Redis实例时自定义的密码，请按实际情况修改后执行。

        返回以下回显信息，表示成功连接Redis实例。

        ```
        AUTH: OK
        SET: OK
        GET welcome: Hello, DCS for Redis!
        ```

    >![](public_sys-resources/icon-notice.gif) **须知：** 
    >如果运行报错找不到hiredis库文件，可参考如下命令，将相关文件复制到系统目录，并增加动态链接。
    >**mkdir /usr/lib/hiredis**
    >**cp /usr/local/lib/libhiredis.so.0.13 /usr/lib/hiredis/**
    >**mkdir /usr/include/hiredis**
    >**cp /usr/local/include/hiredis/hiredis.h /usr/include/hiredis/**
    >**echo '/usr/local/lib' \>\>;\>\>;/etc/ld.so.conf**
    >**ldconfig**
    >以上so文件与.h文件的位置，需要替换成实际文件位置。


## 连接Redis实例操作视频<a name="section2045018233194"></a>

如果需要详细了解连接redis实例的操作，请单击以下链接观看视频。

[访问缓存实例操作视频](https://support.huaweicloud.com/dcs_video/index.html)


# phpredis客户端<a name="ZH-CN_TOPIC_0148195315"></a>

介绍使用同一VPC内弹性云服务器ECS上的phpredis连接Redis的方法。更多的客户端的使用方法，请参考[https://redis.io/clients](https://redis.io/clients)

## 前提条件<a name="section1502270695932"></a>

-   已成功申请Redis实例，且状态为“运行中”。
-   已创建弹性云服务器，创建弹性云服务器的方法，请参见《弹性云服务器用户指南》。
-   如果弹性云服务器为Linux系统，该弹性云服务器必须已经安装gcc编译环境。

## 操作步骤<a name="section418118191507"></a>

1.  <a name="li8233164074413"></a>查看并获取待连接Redis实例的IP地址/域名和端口。

    具体步骤请参见[查看缓存实例信息](查看缓存实例信息.md)。

2.  登录弹性云服务器。
3.  安装gcc-c++及make等编译组件。

    **yum install gcc-c++ make**

4.  安装php开发包与命令行工具。

    执行如下命令，使用yum方式直接安装。

    **yum install php-devel php-common php-cli**

    安装完后可查看版本号，确认成功安装：

    **php --version**

5.  安装php redis客户端。
    1.  下载php redis源文件。

        **wget http://pecl.php.net/get/redis-4.1.0RC3.tgz**

        以上是当前最新版本。还可以去redis官网或者php官网下载其他版本的phpredis客户端。

    2.  解压php redis源文件包。

        **tar -zxvf redis-4.1.0RC3.tgz**

        **cd redis-4.1.0RC3**

    3.  编译前先执行扩展命令。

        **phpize**

    4.  配置php-config文件。

        **./configure --with-php-config=/usr/bin/php-config**

        不同操作系统，不同的php安装方式，该文件位置不一样。建议在配置前，先查找和确认该文件的目录：

        **find / -name php-config**

    5.  编译和安装php redis客户端。

        **make && make install**

    6.  安装完后在php.ini文件中增加extension配置项，用于增加redis模块的引用配置。

        **vim /usr/local/php/etc/php.ini**

        增加如下配置项：

        ```
        extension = "/usr/lib64/php/modules/redis.so"
        ```

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >php.ini和redis.so两个文件的目录可能不同，需要先查找确认。  
        >例如：**find / -name php.ini**  

    7.  保存退出后确认扩展生效。

        **php -m |grep redis**

        如果以上命令返回了 redis，表示php redis客户端环境搭建好了。

6.  使用php redis客户端连接Redis实例。
    1.  编辑一个redis.php文件：

        ```
        <?php
            $redis_host = "{redis_instance_address}";
            $redis_port = 6379;
            $user_pwd = "{password}";
            $redis = new Redis();
            if ($redis->connect($redis_host, $redis_port) == false) {
               die($redis->getLastError());
            }
            if ($redis->auth($user_pwd) == false) {
                die($redis->getLastError());
            }
            if ($redis->set("welcome", "Hello, DCS for Redis!") == false) {
                die($redis->getLastError());
            }
            $value = $redis->get("welcome");
            echo $value;
            $redis->close();
        ?>
        ```

        其中，**\{redis\_instance\_address\}**为Redis实例的IP地址/域名，“6379“为Redis实例的端口。IP地址/域名和端口获取见步骤[1](#li8233164074413)，请按实际情况修改后执行。\{password\}为创建Redis实例时自定义的密码，请按实际情况修改后执行。如果免密访问，请将密码认证的if语句屏蔽。

    2.  执行 php redis.php，连接Redis实例。


## 连接Redis实例操作视频<a name="section1424883115181"></a>

如果需要详细了解连接Reids实例的操作，请单击以下链接观看视频。

[访问缓存实例操作视频](https://support.huaweicloud.com/dcs_video/index.html)


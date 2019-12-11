# Python Redis客户端<a name="ZH-CN_TOPIC_0148195287"></a>

介绍使用同一VPC内弹性云服务器ECS上的Python Redis客户端Redis-py连接Redis实例的方法。更多的客户端的使用方法，请参考[https://redis.io/clients](https://redis.io/clients)

## 前提条件<a name="section1502270695932"></a>

-   已成功申请Redis实例，且状态为“运行中”。
-   已创建弹性云服务器，创建弹性云服务器的方法，请参见《弹性云服务器用户指南》。
-   如果弹性云服务器为Linux系统，该弹性云服务器必须已经安装gcc编译环境。

## 操作步骤<a name="section886785613318"></a>

1.  <a name="li450593110588"></a>查看并获取待连接Redis实例的IP地址/域名和端口。

    具体步骤请参见[查看缓存实例信息](查看缓存实例信息.md)。

2.  登录弹性云服务器。
3.  安装Python和Python Redis客户端Redis-py。
    1.  如果系统没有自带Python，可以使用yum方式安装。

        **yum install python**

    2.  下载并解压redis-py。

        **wget https://github.com/andymccurdy/redis-py/archive/master.zip;**

    3.  进入到解压目录后安装Python Redis客户端Redis-py。

        **python setup.py install**

        安装后执行**python**命令，返回如下信息说明成功安装Redis-py：

        ```
        Python 2.6.6 (r266:84292, Aug 18 2016, 15:13:37) 
        [GCC 4.4.7 20120313 (Red Hat 4.4.7-17)] on linux2
        Type "help", "copyright", "credits" or "license" for more information.
        >>> import redis
        >>>
        ```

4.  使用Python Redis客户端Redis-py客户端连接Redis实例。

    以下步骤以命令行模式进行示例（也可以将命令写入python脚本中再执行）：

    1.  执行**python**命令，进入命令行模式。

        返回如下信息说明已进入命令行模式：

        ```
        Python 2.6.6 (r266:84292, Aug 18 2016, 15:13:37) 
        [GCC 4.4.7 20120313 (Red Hat 4.4.7-17)] on linux2
        Type "help", "copyright", "credits" or "license" for more information.
        >>> import redis
        >>>
        ```

    2.  在命令行中执行以下命令，连接Redis实例。

        ```
        r = redis.StrictRedis(host='192.168.0.171', port=6379, password='******');
        ```

        其中，**192.168.0.171**为Redis实例的IP地址/域名，“6379“为Redis实例的端口。IP地址/域名和端口获取见步骤[1](#li450593110588)，请按实际情况修改后执行。**\*\*\*\*\*\***为创建Redis实例时自定义的密码，请按实际情况修改后执行。

        界面显示一行新的命令行，说明连接Redis实例成功。

        ```
        Python 2.6.6 (r266:84292, Aug 18 2016, 15:13:37) 
        [GCC 4.4.7 20120313 (Red Hat 4.4.7-17)] on linux2
        Type "help", "copyright", "credits" or "license" for more information.
        >>> import redis
        >>> r = redis.StrictRedis(host='192.168.0.171', port=6379, password='******');
        >>> 
        ```



## 连接Redis实例操作视频<a name="section1818730142011"></a>

如果需要详细了解连接Reids实例的操作，请单击以下链接观看视频。

[访问缓存实例操作视频](https://support.huaweicloud.com/dcs_video/index.html)


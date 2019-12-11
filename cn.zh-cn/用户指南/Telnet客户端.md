# Telnet客户端<a name="ZH-CN_TOPIC_0148195237"></a>

介绍使用同一VPC内弹性云服务器ECS上的Telnet客户端连接Memcached实例的方法。

## 前提条件<a name="section14501642174811"></a>

-   已成功申请Memcached实例，且状态为“运行中”。
-   已创建弹性云服务器，并已安装好客户端。创建弹性云服务器的方法，请参见《弹性云服务器用户指南》。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >1.  您创建的弹性云服务器必须与Memcached实例属于同一个VPC，并配置相同的安全组，以确保弹性云服务器与缓存实例的网络是连通的。  
    >2.  如果弹性云服务器与Memcached实例不在相同VPC中，可以通过建立VPC对等连接方式连通网络，具体请参考常见问题：[缓存实例是否支持跨VPC访问？](https://support.huaweicloud.com/dcs_faq/dcs-zh-ug-180312006.html)  
    >3.  如果弹性云服务器与Memcached实例配置了不同的安全组，可以通过设置安全组规则连通网络，具体请参考常见问题：[如何选择和配置安全组？](https://support.huaweicloud.com/dcs_faq/zh-cn_topic_0082442607.html)  


-   建议在使用本手册时删除示例代码中的所有注释信息。
-   请确保所有命令行、代码块输入格式都是UTF-8，否则会出现编译出错或者运行失败的情况。

## 操作步骤<a name="section10709163710106"></a>

1.  登录[分布式缓存服务管理控制台](https://console.huaweicloud.com/dcs)。
2.  在管理控制台左上角单击![](figures/icon-region.png)，选择区域和项目。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >此处请选择与您的应用服务相同的区域。  

3.  单击左侧菜单栏的“缓存管理”，进入缓存实例信息页面。
4.  <a name="li7304143"></a>单击需要使用的其中一个Memcached实例的名称，进入该Memcached实例的基本信息页面。查看并获取该Memcached实例的IP地址/域名和端口。
5.  连接Memcached实例。
    1.  登录已创建的弹性云服务器。
    2.  执行如下命令，确认是否已安装Telnet客户端。

        **_which telnet_**

        若界面显示Telnet客户端所在目录，表示当前云服务器已安装Telnet客户端。否则请自行安装Telnet客户端。

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >-   Linux系统中，如果没有安装Telnet客户端，可执行**yum -y install telnet**安装。  
        >-   在Windows系统中，可通过“控制面板 \> 程序 \> 打开或关闭Windows功能”，找到并打开“Telnet客户端”功能。  

    3.  执行如下命令，连接并使用Memcached实例。

        _**telnet \{ip or domain name\} \{port\}**_

        其中\{ip or domain name\} 为Memcached实例的IP地址/域名，\{port\}为Memcached实例的端口。IP地址/域名和端口获取方法请参考步骤[4](#li7304143)，请按实际情况修改后执行。

        界面提示如下表示连接缓存实例成功。

        ```
        Trying XXX.XXX.XXX.XXX...
        Connected to XXX.XXX.XXX.XXX.
        Escape character is '^]'.
        ```

        >![](public_sys-resources/icon-note.gif) **说明：**   
        >-   如果Memcached实例为**免密访问**模式，连接后可直接执行以下操作，输入命令。  
        >-   如果Memcached实例为**密码访问**模式，连接后执行以下操作，会提示“ERROR authentication required”，表示没有权限，需要先执行**auth  _用户名_@_密码_**进行认证，其中，用户名和密码，表示设置连接Memcached实例的用户名和密码。  

        输入命令，示例如下（其中红色部分内容为输入的命令，其他为命令返回内容）：

        ```
        set hello 0 0 6
        world!
        STORED
        get hello
        VALUE hello 0 6
        world!
        END
        ```




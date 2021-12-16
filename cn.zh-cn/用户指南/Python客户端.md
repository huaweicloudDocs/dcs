# Python客户端<a name="dcs-ug-190715003"></a>

介绍使用同一VPC内弹性云服务器ECS上的Python客户端连接Memcached实例的方法。

## 前提条件<a name="section16774173023520"></a>

-   已成功申请Memcached实例，且状态为“运行中”。
-   已创建弹性云服务器。创建弹性云服务器的方法，请参见《弹性云服务器用户指南》。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >您创建的弹性云服务器必须与Memcached实例属于同一个VPC，并配置相同的安全组，以确保弹性云服务器与缓存实例的网络是连通的。
    >如果弹性云服务器与Memcached实例不在相同VPC中，可以通过建立VPC对等连接方式连通网络，具体请参考常见问题：[缓存实例是否支持跨VPC访问？](https://support.huaweicloud.com/dcs_faq/dcs-faq-0427002.html)
    >如果弹性云服务器与Memcached实例配置了不同的安全组，可以通过设置安全组规则连通网络，具体请参考常见问题：[如何选择和配置安全组？](https://support.huaweicloud.com/dcs_faq/dcs-faq-0713002.html)

-   弹性云服务器已安装好Python，建议为2.7.6或更高版本。
-   已获取[<u>python-binary-memcached-x.y.z.zip</u>](https://github.com/jaysonsantos/python-binary-memcached/releases)依赖包。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >其中x.y.z为依赖包的版本号，建议获取最新版本。


## 操作步骤<a name="section233513143314"></a>

1.  登录[分布式缓存服务管理控制台](https://console.huaweicloud.com/dcs)。
2.  在管理控制台左上角单击![](figures/icon-region.png)，选择区域和项目。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >此处请选择与您的应用服务相同的区域。

3.  单击左侧菜单栏的“缓存管理”，进入缓存实例信息页面。
4.  <a name="li5282125319375"></a>单击需要使用的其中一个Memcached实例的名称，进入该Memcached实例的基本信息页面。查看并获取该Memcached实例的IP地址/域名和端口。
5.  将已获取的python-binary-memcached-x.y.z.zip依赖包上传到已创建的弹性云服务器，假设下载得到的包名为python-binary-memcached-x.y.z.zip。
6.  登录弹性云服务器。
7.  执行如下命令安装依赖包。

    **unzip -xzvf python-binary-memcached-x.y.z.zip**

    **cd python-binary-memcached-x.y.z**

    **python setup.py install**

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >如以上步骤安装报错，可使用apt或yum方式安装依赖包，如apt方式安装的具体命令如下：
    >**apt install python-pip;**
    >**pip install python-binary-memcached;**

8.  新建Python文件如dcs\_test.py，将如下Python代码复制到dcs\_test.py文件并修改代码。
    -   密码模式代码示例

        其中ip or domain name:port需要修改为[4](#li5282125319375)获取的Memcached实例IP地址/域名和端口。userName和password需要修改为Memcached实例的用户名和密码。

        ```
        import bmemcached
        client = bmemcached.Client(('ip or domain name:port'), 'userName', 'password')
        print "set('key', 'hello world!')"
        print client.set('key', 'hello world!')
        print "get('key')"
        print client.get('key')
        ```

    -   免密模式代码示例

        其中ip or domain name:port需要修改为[4](#li5282125319375)获取的Memcached实例IP地址/域名和端口。

        ```
        import bmemcached
        client = bmemcached.Client('ip or domain name:port')
        print "set('key', 'hello world!')"
        print client.set('key', 'hello world!')
        print "get('key')"
        print client.get('key')
        ```

9.  运行dcs\_test.py文件，可以看到如下结果。

    ```
    # python test.py 
    set('key', 'hello world!')
    True
    get('key')
    hello world!
    ```



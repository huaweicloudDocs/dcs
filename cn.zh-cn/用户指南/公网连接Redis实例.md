# 公网连接Redis实例<a name="ZH-CN_TOPIC_0144197309"></a>

Redis客户端可通过公网连接Redis实例。该功能便于开发人员在本地搭建开发或测试环境，提高开发效率。生产环境（正式环境）中，请通过VPC内连接方式访问Redis实例，保障访问效率。

本节介绍如何搭建一个本地环境与Redis实例间的网络通道，以Redis-cli为例演示通过公网连接Redis实例。更多的客户端的使用方法，请参考[https://redis.io/clients](https://redis.io/clients)。

## 前提条件<a name="zh-cn_topic_0102349198_section1502270695932"></a>

使用Redis-cli客户端通过公网访问Redis实例时：

-   已成功申请密码模式的Redis实例，且状态为“运行中”。
-   Redis实例已开启公网访问功能，具体可参考[开启Redis实例的公网访问](开启Redis实例的公网访问.md#ZH-CN_TOPIC_0144197373)。
-   如果访问Redis实例需要使用证书，可根据[查看缓存实例信息](查看缓存实例信息.md#ZH-CN_TOPIC_0144197334)，进入到缓存实例详情页面提前下载该证书。
-   Redis实例安全组需要配置了正确的规则（允许36379端口被外部地址访问），客户端才能正常连接Redis实例。具体请参考[如何选择和配置安全组？](https://support.huaweicloud.com/dcs_faq/zh-cn_topic_0082442607.html)。

## Stunnel客户端安装配置（Windows版）<a name="zh-cn_topic_0102349198_section1280845895932"></a>

1.  <a name="zh-cn_topic_0102349198_li74761644131012"></a>查看并获取待连接Redis实例的弹性IP地址和端口。

    具体步骤请参见[查看缓存实例信息](查看缓存实例信息.md#ZH-CN_TOPIC_0144197334)。

2.  下载Stunnel安装包。从[http://www.stunnel.org/downloads.html](http://www.stunnel.org/downloads.html)下载最新版本的Windows版Stunnel安装包（以exe结尾的安装包，例如，stunnel-5.44-win32-installer.exe）到本地Windows设备。
3.  运行Stunnel安装程序，安装Stunnel客户端。
4.  <a name="zh-cn_topic_0102349198_li11161015556"></a>配置Stunnel客户端。在任务栏单击图标![](figures/icon-editconfig.png)右键，选择“Edit Configration”，新增如下配置内容，然后保存退出。

    ```
    [redis-client]
    client = yes
    CAfile = D:\tmp\dcs\dcs-ca.cer
    accept = 8000
    connect = {弹性IP地址}:{端口}
    ```

    以下参数需要根据说明修改，其他参数不用修改：

    -   ****client****值固定填yes，表示为Stunnel客户端。
    -   **CAfile**为CA证书，可选。如果需要，请根据[查看缓存实例信息](查看缓存实例信息.md#ZH-CN_TOPIC_0144197334)，进入到Redis实例详情页面下载该证书；如果不需要，可不配置，删除此参数。
    -   **accept**为Stunnel监听端口，可以自定义。Redis客户端访问实例时填写此端口。
    -   **connect**为服务端连接地址，此处填Redis实例的IP地址与端口，即分别替换为步骤[1](#zh-cn_topic_0102349198_li74761644131012)获取的弹性IP地址和端口。

5.  在任务栏单击图标![](figures/icon-editconfig.png)右键，选择“Reload Configration”。
6.  打开命令提示符工具**cmd.exe**，执行以下命令，查看127.0.0.1:8000是否已经被监听。

    **netstat -an |find "8000"**

    假设客户端的监听端口配置为“8000”。

    返回列表行中显示有“127.0.0.1:8000”，状态为“LISTENING”，表示stunnel客户端正常运行。Redis客户端连接“127.0.0.1:8000”，stunnel会将请求转发给DCS的Redis实例。


## Stunnel客户端安装配置（Linux版）<a name="zh-cn_topic_0102349198_section66391559191819"></a>

1.  <a name="zh-cn_topic_0102349198_li1176811562811"></a>查看并获取待连接Redis实例的弹性IP地址和端口。

    具体步骤请参见[查看缓存实例信息](查看缓存实例信息.md#ZH-CN_TOPIC_0144197334)。

2.  登录本地Linux设备。
3.  安装stunnel客户端。

    这里主要介绍Stunnel客户端的几种常见安装方法。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >推荐使用apt和yum两种安装方式，常见Linux系统，一般至少支持其中一种。  
    >其他常见系统下的Stunnel客户端安装请参考：  
    >[“Mac下的Stunnel客户端安装”](https://bbs.huaweicloud.com/blogs/201166b14ac411e89fc57ca23e93a89f)。  

    1.  apt-get方式安装。apt-get管理deb格式的软件包，适用于Debian类操作系统，如Ubuntu。命令如下：

        **apt install stunnel**  或**apt-get install stunnel**

        如果命令执行后提示找不到Stunnel，可以尝试执行**apt update**，更新配置后再安装Stunnel。

    2.  yum方式安装。管理rpm格式的软件包，适用于Fedora、CentOS、Red Hat等操作系统。

        **yum install stunnel**

    3.  其他通用方式安装。Unix系统还可以直接[下载Stunnel安装包](https://www.stunnel.org/downloads.html)，编译后安装。前提是需要安装gcc编译环境，以及[openssl-devel](https://pkgs.org/download/openssl-devel)工具。安装如遇到困难，可参考[Stunnel官方网站的帮助](https://www.stunnel.org/howto.html)。

        下载并解压Stunnel后，进入解压目录，执行以下命令编译和安装：

        **./configure;**

        **make && make install;**


4.  安装成功后，编辑/etc/default/stunnel4，将参数ENABLED设置为1。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >不同的Linux系统版本，配置文件名称可能有差异，可在/etc/default/路径下查找该文件。  

    ```
    ... 
    ENABLED=1
    ...
    ```

5.  打开配置文件。

    stunnel配置文件名为：stunnel.conf。配置文件可以存储在任何路径，在Stunnel启动的时候指定改配置文件即可。

    也可以按照Stunnel默认的方式新增配置文件：

    1.  apt-get方式

        路径为/etc/stunnel/stunnel.conf，如果路径不存在或者路径下无配置文件，可新增。

    2.  yum方式

        默认路径为/usr/local/stunnel/stunnel.conf，如果路径不存在或者路径下无配置文件，可新增。

    3.  其他通用方式

        路径为/usr/local/stunnel/stunnel.conf，如果路径不存在或者路径下无配置文件，可新增。


    >![](public_sys-resources/icon-note.gif) **说明：**   
    >如果不确定配置文件应该存储在哪，可以在安装后直接输入stunnel命令，获取文件路径提示。  

6.  <a name="zh-cn_topic_0102349198_li650512191335"></a>在配置文件中新增如下内容，然后保存退出。

    ```
    debug = 4
    output = /var/log/stunnel.log
    sslVersion = all
    [redis-client]
    client = yes
    accept = 8000
    connect = {弹性IP地址}:{端口}
    CAfile = /etc/stunnel/dcs-ca.cer
    ```

    以下参数需要根据说明修改，其他参数不用修改：

    -   **client**值固定填**yes**，表示为Stunnel客户端。
    -   **CAfile**为CA证书，可选。如果需要，请根据[查看缓存实例信息](查看缓存实例信息.md#ZH-CN_TOPIC_0144197334)，进入到缓存实例详情页面下载该证书；如果不需要，此参数请删除。
    -   **accept**为Stunnel监听端口，可以自定义。Redis客户端访问缓存实例时填写此端口。
    -   **connect**为Stunnel转发地址与端口，此处填Redis缓存实例的IP地址与端口，即分别替换为步骤[1](#zh-cn_topic_0102349198_li1176811562811)获取的弹性IP地址和端口。

7.  启动stunnel服务。

    1.  使用了Stunnel默认配置文件，则直接执行命令：

        **stunnel**

    2.  自定义配置文件的路径，则执行命令：

        **stunnel /\{customdir\}/stunnel.conf**

        其中/\{customdir\}/stunnel.conf为自定义存储路径。

    3.  Ubuntu下启动命令还可以使用** /etc/init.d/stunnel4 start**。Stunnel4.x的版本，服务/进程名为stunnel4。

    启动后可执行**ps -ef|grep stunnel**确认进程是否正常运行。

8.  执行以下命令，查看127.0.0.1:8000是否已经被监听。

    其中，8000替换为[6](#zh-cn_topic_0102349198_li650512191335)中accept字段配置的Stunnel监听端口。

    **netstat -plunt |grep 8000|grep "LISTEN"**

    返回列表行中显示有“127.0.0.1:8000”，表示stunnel客户端正常运行。Redis客户端连接“127.0.0.1:8000”，stunnel会将请求转发给DCS的Redis实例。


## 连接Redis实例<a name="zh-cn_topic_0102349198_section145879354499"></a>

本节介绍使用redis命令行工具连接分布式缓存实例。

1.  Window系统上连接Redis实例参考以下步骤。
    1.  获取Redis客户端安装包到本地Windows设备，并解压安装包。

        Windows版本的Redis客户端安装包，下载请单击[这里](https://github.com/MicrosoftArchive/redis/tags)。

    2.  打开命令提示符工具**cmd.exe**，并执行以下命令，进入Redis客户端安装包的解压目录。

        以解压目录D:\\redis-64.3.0.503为例，命令如下：

        **D:**

        **cd D:\\redis-64.3.0.503**

    3.  执行以下命令连接Redis实例。

        **redis-cli -p 8000 -a <password\>**

        其中“8000”为[4](#zh-cn_topic_0102349198_li11161015556)中accept字段配置的Stunnel监听端口；**<password\>**为创建Redis实例时自定义的密码，请按实际情况修改后执行。

        连接成功后，回显信息如下：

        ```
        127.0.0.1:8000>
        ```

        输入“info”可正常返回Redis实例信息。如果不能正常返回，或者连接异常断开，可在任务栏找到Stunnel图标，并右键单击，选择“Show Log Window”，打开Stunnel客户端的日志查看原因。


2.  Linux系统上连接Redis缓存实例参考以下步骤。
    1.  获取Redis客户端源码，下载路径为http://download.redis.io/releases/redis-3.0.7.tar.gz。
    2.  将Redis客户端源码包上传到本地Linux设备。
    3.  登录本地Linux设备。
    4.  执行如下命令，解压Redis客户端源码包。

        **tar -xzf redis-3.0.7.tar.gz**

    5.  进入Redis目录并编译Redis客户端源码。

        **cd redis-3.0.7**

        **make**

    6.  执行以下命令连接Redis实例。

        **cd src**

        **./redis-cli -p 8000**

        其中“8000”为[6](#zh-cn_topic_0102349198_li650512191335)中accept字段配置的Stunnel监听端口。

    7.  输入密码，校验通过后才可进行缓存数据读写。

        **auth <password\>**

        其中，<password\>为创建Redis实例时自定义的密码，请按实际情况修改后执行。

        连接成功后，回显信息如下：

        ```
        OK 
        127.0.0.1:8000>
        ```



## 相关产品及文档<a name="zh-cn_topic_0102349198_section152613113129"></a>

<a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_table1073594361220"></a>
<table><thead align="left"><tr id="zh-cn_topic_0102349198_zh-cn_topic_0046844820_row197372430123"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p4737243111216"><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p4737243111216"></a><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p4737243111216"></a>相关产品</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p18737144301214"><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p18737144301214"></a><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p18737144301214"></a>相关文档</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0102349198_zh-cn_topic_0046844820_row17371443131210"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p13372054101419"><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p13372054101419"></a><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p13372054101419"></a><a href="https://www.huaweicloud.com/product/dcs.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Redis</a></p>
<p id="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p19548105714519"><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p19548105714519"></a><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p19548105714519"></a><a href="https://www.huaweicloud.com/product/dcsmem.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Memcached</a></p>
<p id="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p8862161219564"><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p8862161219564"></a><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p8862161219564"></a><a href="https://www.huaweicloud.com/product/ecs.html?infodocbz" target="_blank" rel="noopener noreferrer">弹性云服务器 ECS</a></p>
<p id="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p841193941416"><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p841193941416"></a><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p841193941416"></a><a href="http://www.huaweicloud.com/product/vpc.html?infodocbz" target="_blank" rel="noopener noreferrer">虚拟私有云 VPC</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p1381695711471"><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p1381695711471"></a><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p1381695711471"></a><a href="https://support.huaweicloud.com/usermanual-dcs/dcs-zh-ug-180315001.html?infodocbz" target="_blank" rel="noopener noreferrer">购买Redis实例</a></p>
<p id="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p682916370595"><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p682916370595"></a><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p682916370595"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0082114847.html?infodocbz" target="_blank" rel="noopener noreferrer">连接Redis实例</a></p>
<p id="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p16726748155912"><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p16726748155912"></a><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p16726748155912"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0061845451.html?infodocbz" target="_blank" rel="noopener noreferrer">变更缓存实例规格</a></p>
<p id="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p12250886517"><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p12250886517"></a><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p12250886517"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0079545637.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例备份恢复</a></p>
<p id="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p143616360517"><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p143616360517"></a><a name="zh-cn_topic_0102349198_zh-cn_topic_0046844820_p143616360517"></a><a href="https://support.huaweicloud.com/migration-dcs/zh-cn_topic_0078784423.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例数据迁移</a></p>
</td>
</tr>
</tbody>
</table>


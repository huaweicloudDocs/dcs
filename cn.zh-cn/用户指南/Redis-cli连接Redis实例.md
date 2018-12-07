# Redis-cli连接Redis实例<a name="ZH-CN_TOPIC_0144197337"></a>

介绍使用同一VPC内弹性云服务器ECS上的Redis-Cli连接Redis实例的方法。更多的客户端的使用方法，请参考[https://redis.io/clients](https://redis.io/clients)。

## 前提条件<a name="zh-cn_topic_0082114847_section1502270695932"></a>

-   已成功申请Redis实例，且状态为“运行中”。
-   已创建弹性云服务器，创建弹性云服务器的方法，请参见《弹性云服务器用户指南》。
-   如果弹性云服务器为Linux系统，该弹性云服务器必须已经安装gcc编译环境。

## 操作步骤<a name="zh-cn_topic_0082114847_section596432855917"></a>

1.  <a name="zh-cn_topic_0082114847_li5799181918288"></a>查看并获取待连接Redis实例的IP地址/域名和端口。

    具体步骤请参见[查看缓存实例信息](查看缓存实例信息.md#ZH-CN_TOPIC_0144197334)。

2.  使用Redis-cli客户端连接Redis实例。

    以下步骤以客户端安装在Linux系统上为例进行描述。

    1.  获取Redis客户端源码，下载路径为[http://download.redis.io/releases/redis-3.0.7.tar.gz](http://download.redis.io/releases/redis-3.0.7.tar.gz)。
    2.  将Redis客户端源码包上传到已创建的弹性云服务器。
    3.  登录弹性云服务器。
    4.  执行如下命令，解压Redis客户端源码包。

        **tar -xzf redis-3.0.7.tar.gz**

    5.  进入Redis目录并编译Redis客户端源码。

        **cd redis-3.0.7**

        **make**

    6.  执行以下命令连接Redis实例。

        **cd src**

        _**./redis-cli -h**_ _**XXX -p 6379**_

        其中“XXX“为Redis实例的IP地址/域名，“6379“为Redis实例的端口。IP地址/域名和端口获取见步骤[1](#zh-cn_topic_0082114847_li5799181918288)，请按实际情况修改后执行。

    7.  如果Redis实例设置了密码访问，则执行本步骤输入密码，校验通过后才可进行缓存数据读写。

        **auth <password\>**

        其中“<password\>“为创建Redis实例时自定义的密码，请按实际情况修改后执行。密码访问回显如下：

        ```
        OK
        redis 192.168.0.148:6379>
        ```


    >![](public_sys-resources/icon-note.gif) **说明：**   
    >Windows版本的Redis客户端安装包，下载请单击[这里](https://github.com/MicrosoftArchive/redis/tags)。下载后直接解压安装包，然后使用cmd工具进入解压目录，执行以下命令连接redis实例：  
    >**redis-cli -h** **_XXX_  -p 6379** **-a  _<password\>_**  
    >其中：  
    >-   “XXX“为Redis实例的IP地址/域名，“6379“为Redis实例的端口。IP地址/域名和端口获取见步骤[1](#zh-cn_topic_0082114847_li5799181918288)，请按实际情况修改后执行。  
    >-   “<password\>”为创建Redis实例时自定义的密码，请按实际情况修改后执行。  


## 相关产品及文档<a name="zh-cn_topic_0082114847_section152613113129"></a>

<a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_table1073594361220"></a>
<table><thead align="left"><tr id="zh-cn_topic_0082114847_zh-cn_topic_0046844820_row197372430123"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p4737243111216"><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p4737243111216"></a><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p4737243111216"></a>相关产品</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p18737144301214"><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p18737144301214"></a><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p18737144301214"></a>相关文档</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0082114847_zh-cn_topic_0046844820_row17371443131210"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p13372054101419"><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p13372054101419"></a><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p13372054101419"></a><a href="https://www.huaweicloud.com/product/dcs.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Redis</a></p>
<p id="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p19548105714519"><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p19548105714519"></a><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p19548105714519"></a><a href="https://www.huaweicloud.com/product/dcsmem.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Memcached</a></p>
<p id="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p8862161219564"><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p8862161219564"></a><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p8862161219564"></a><a href="https://www.huaweicloud.com/product/ecs.html?infodocbz" target="_blank" rel="noopener noreferrer">弹性云服务器 ECS</a></p>
<p id="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p841193941416"><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p841193941416"></a><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p841193941416"></a><a href="http://www.huaweicloud.com/product/vpc.html?infodocbz" target="_blank" rel="noopener noreferrer">虚拟私有云 VPC</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p1381695711471"><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p1381695711471"></a><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p1381695711471"></a><a href="https://support.huaweicloud.com/usermanual-dcs/dcs-zh-ug-180315001.html?infodocbz" target="_blank" rel="noopener noreferrer">购买Redis实例</a></p>
<p id="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p682916370595"><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p682916370595"></a><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p682916370595"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0082114847.html?infodocbz" target="_blank" rel="noopener noreferrer">连接Redis实例</a></p>
<p id="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p16726748155912"><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p16726748155912"></a><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p16726748155912"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0061845451.html?infodocbz" target="_blank" rel="noopener noreferrer">变更缓存实例规格</a></p>
<p id="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p12250886517"><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p12250886517"></a><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p12250886517"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0079545637.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例备份恢复</a></p>
<p id="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p143616360517"><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p143616360517"></a><a name="zh-cn_topic_0082114847_zh-cn_topic_0046844820_p143616360517"></a><a href="https://support.huaweicloud.com/migration-dcs/zh-cn_topic_0078784423.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例数据迁移</a></p>
</td>
</tr>
</tbody>
</table>


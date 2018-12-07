# Python Redis客户端连接Redis实例<a name="ZH-CN_TOPIC_0144197350"></a>

介绍使用同一VPC内弹性云服务器ECS上的Python Redis客户端Redis-py连接Redis实例的方法。更多的客户端的使用方法，请参考[https://redis.io/clients](https://redis.io/clients)。

## 前提条件<a name="zh-cn_topic_0126076985_section1502270695932"></a>

-   已成功申请Redis实例，且状态为“运行中”。
-   已创建弹性云服务器，创建弹性云服务器的方法，请参见《弹性云服务器用户指南》。
-   如果弹性云服务器为Linux系统，该弹性云服务器必须已经安装gcc编译环境。

## 操作步骤<a name="zh-cn_topic_0126076985_section886785613318"></a>

1.  <a name="zh-cn_topic_0126076985_li450593110588"></a>查看并获取待连接Redis实例的IP地址/域名和端口。

    具体步骤请参见[查看缓存实例信息](查看缓存实例信息.md#ZH-CN_TOPIC_0144197334)。

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

        其中，**192.168.0.171**为Redis实例的IP地址/域名，“6379“为Redis实例的端口。IP地址/域名和端口获取见步骤[1](#zh-cn_topic_0126076985_li450593110588)，请按实际情况修改后执行。**\*\*\*\*\*\***为创建Redis实例时自定义的密码，请按实际情况修改后执行。

        界面显示一行新的命令行，说明连接Redis实例成功。

        ```
        Python 2.6.6 (r266:84292, Aug 18 2016, 15:13:37) 
        [GCC 4.4.7 20120313 (Red Hat 4.4.7-17)] on linux2
        Type "help", "copyright", "credits" or "license" for more information.
        >>> import redis
        >>> r = redis.StrictRedis(host='192.168.0.171', port=6379, password='******');
        >>> 
        ```



## 相关产品及文档<a name="zh-cn_topic_0126076985_section152613113129"></a>

<a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_table1073594361220"></a>
<table><thead align="left"><tr id="zh-cn_topic_0126076985_zh-cn_topic_0046844820_row197372430123"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p4737243111216"><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p4737243111216"></a><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p4737243111216"></a>相关产品</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p18737144301214"><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p18737144301214"></a><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p18737144301214"></a>相关文档</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0126076985_zh-cn_topic_0046844820_row17371443131210"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p13372054101419"><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p13372054101419"></a><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p13372054101419"></a><a href="https://www.huaweicloud.com/product/dcs.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Redis</a></p>
<p id="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p19548105714519"><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p19548105714519"></a><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p19548105714519"></a><a href="https://www.huaweicloud.com/product/dcsmem.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Memcached</a></p>
<p id="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p8862161219564"><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p8862161219564"></a><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p8862161219564"></a><a href="https://www.huaweicloud.com/product/ecs.html?infodocbz" target="_blank" rel="noopener noreferrer">弹性云服务器 ECS</a></p>
<p id="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p841193941416"><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p841193941416"></a><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p841193941416"></a><a href="http://www.huaweicloud.com/product/vpc.html?infodocbz" target="_blank" rel="noopener noreferrer">虚拟私有云 VPC</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p1381695711471"><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p1381695711471"></a><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p1381695711471"></a><a href="https://support.huaweicloud.com/usermanual-dcs/dcs-zh-ug-180315001.html?infodocbz" target="_blank" rel="noopener noreferrer">购买Redis实例</a></p>
<p id="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p682916370595"><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p682916370595"></a><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p682916370595"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0082114847.html?infodocbz" target="_blank" rel="noopener noreferrer">连接Redis实例</a></p>
<p id="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p16726748155912"><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p16726748155912"></a><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p16726748155912"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0061845451.html?infodocbz" target="_blank" rel="noopener noreferrer">变更缓存实例规格</a></p>
<p id="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p12250886517"><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p12250886517"></a><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p12250886517"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0079545637.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例备份恢复</a></p>
<p id="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p143616360517"><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p143616360517"></a><a name="zh-cn_topic_0126076985_zh-cn_topic_0046844820_p143616360517"></a><a href="https://support.huaweicloud.com/migration-dcs/zh-cn_topic_0078784423.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例数据迁移</a></p>
</td>
</tr>
</tbody>
</table>


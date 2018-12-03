# phpredis连接Redis实例<a name="ZH-CN_TOPIC_0126076983"></a>

介绍使用同一VPC内弹性云服务器ECS上的phpredis连接Redis实例的方法。更多的客户端的使用方法，请参考https://redis.io/clients。

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

    **php -version**

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
        >redis.so文件的目录可能不同，需要先查找确认该文件的目录。  

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
            $redis->quit();
        ?>
        ```

        其中，**\{redis\_instance\_address\}**为Redis实例的IP地址/域名，“6379“为Redis实例的端口。IP地址/域名和端口获取见步骤[1](#li8233164074413)，请按实际情况修改后执行。\{password\}为创建Redis实例时自定义的密码，请按实际情况修改后执行。

    2.  执行 php redis.php，连接Redis实例。


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


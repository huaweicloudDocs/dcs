# predis<a name="dcs-ug-211202002"></a>

介绍使用同一VPC内弹性云服务器ECS上的predis连接Redis的方法。更多的客户端的使用方法请参考[Redis客户端](https://redis.io/clients)。

## 前提条件<a name="section21874355292"></a>

-   已成功申请Redis实例，且状态为“运行中”。
-   已创建弹性云服务器，创建弹性云服务器的方法，请参见创建弹性云服务器 。
-   如果弹性云服务器为Linux系统，该弹性云服务器必须已经安装php编译环境。

## 操作步骤<a name="section17228451112917"></a>

1.  <a name="li1655151054317"></a>查看并获取待连接Redis实例的IP地址/域名和端口。

    具体步骤请参见[查看实例信息](查看实例信息.md)。

2.  登录弹性云服务器。
3.  安装php开发包与命令行工具。执行如下命令，使用yum方式直接安装。

    **yum install php-devel php-common php-cli**

4.  安装完后可查看版本号，确认成功安装。

    **php --version**

5.  将predis包下载到/usr/share/php目录下。
    1.  通过以下命令下载predis源文件。

        **wget https://github.com/predis/predis/archive/refs/tags/v1.1.9.tar.gz**

        >![](public_sys-resources/icon-note.gif) **说明：** 
        >以上是当前最新版本。还可以去redis官网或者php官网下载其他版本的predis客户端。

    2.  解压php redis源文件包。

        **tar -zxvf predis-1.1.9.tar.gz**

6.  编辑一个文件连接redis。

    -   使用redis.php文件连接Redis单机/主备/Proxy集群示例：

        ```
        <?php
            require 'predis/autoload.php';
            Predis\Autoloader::register();
            $client = new Predis\Client([
              'scheme' => 'tcp' ,
              'host'     => '{redis_instance_address}' ,
              'port'     => {port} ,
              'password' => '' 
            ]);
            $client->set('foo', 'bar');
            $value = $client->get('foo');
            echo $value;
        ?>
        ```

    -   使用redis-cluster.php连接Redis Cluster集群代码示例：

        ```
        <?php
           require 'predis/autoload.php';
                $servers = array(
                 'tcp://{redis_instance_address}:{port}' 
                );
               $options = array('cluster' => 'redis');
               $client = new Predis\Client($servers, $options);
               $client->set('foo', 'bar');
               $value = $client->get('foo');
               echo $value;
        ?>
        ```

    其中，_\{redis\_instance\_address\}_为Redis实例真实的IP地址/域名，\{port\}为Redis实例真实的端口。IP地址/域名和端口获取见[1](#li1655151054317)，请按实际情况修改后执行。password为创建Redis实例时自定义的密码，请按实际情况修改后执行。如果免密访问，请将password行去掉。

7.  执行**php redis.php**连接Redis实例。


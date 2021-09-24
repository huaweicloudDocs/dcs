# Jedis客户端<a name="ZH-CN_TOPIC_0148195198"></a>

介绍使用同一VPC内弹性云服务器ECS上的Jedis连接Redis实例的方法。更多的客户端的使用方法请参考[Redis客户端](https://redis.io/clients)。

>![](public_sys-resources/icon-note.gif) **说明：** 
>本章节操作，仅适用于连接单机、主备、Proxy集群实例。Jedis对于Redis Cluster的支持是基于JedisCluster类，详细说明请参见[JedisCluster简介](https://javadoc.io/doc/redis.clients/jedis/2.9.0/redis/clients/jedis/JedisCluster.html)。如果是使用Jedis客户端连接Cluster集群请参考[Redis官网](https://github.com/redis/jedis/wiki)。

## 前提条件<a name="section1502270695932"></a>

-   已成功申请Redis实例，且状态为“运行中”。
-   已创建弹性云服务器，创建弹性云服务器的方法，请参见[创建弹性云服务器](https://support.huaweicloud.com/qs-ecs/ecs_02_0005.html)。
-   如果弹性云服务器为Linux系统，该弹性云服务器必须已经安装gcc编译环境。

## 操作步骤<a name="section1336235611596"></a>

1.  <a name="li695671074019"></a>查看并获取待连接Redis实例的IP地址/域名和端口。

    具体步骤请参见[查看实例信息](查看实例信息.md)。

2.  登录弹性云服务器。
3.  使用Redis Java \(Jedis\)客户端连接Redis单机/主备/Proxy集群实例。
    1.  获取Redis Java \(Jedis\)客户端源码，具体方法可参考[获取Jedis源码](https://github.com/xetorthio/jedis)。
    2.  编写如下操作代码。

        Jedis客户端访问DCS Redis服务，有以下两种方法：

        -   Jedis单连接
        -   Jedis连接池连接

        具体示例如下：

        1.  jedis单连接示例。

            ```
            // 密码模式创建连接
             String host = "192.168.0.150"; 
             int port = 6379; 
             String pwd = "passwd"; 
              
             Jedis client = new Jedis(host, port); 
             client.auth(pwd);
             client.connect(); 
            // 执行set指令
             String result = client.set("key-string", "Hello, Redis!"); 
             System.out.println( String.format("set指令执行结果:%s", result) );
             // 执行get指令
             String value = client.get("key-string"); 
             System.out.println( String.format("get指令执行结果:%s", value) );
            
            // 免密模式创建连接
             String host = "192.168.0.150"; 
             int port = 6379; 
              
             Jedis client = new Jedis(host, port); 
             client.connect(); 
            // 执行set指令
             String result = client.set("key-string", "Hello, Redis!"); 
             System.out.println( String.format("set指令执行结果:%s", result) ); 
            // 执行get指令
             String value = client.get("key-string"); 
             System.out.println( String.format("get指令执行结果:%s", value) );
            ```

            其中，**host**为Redis实例的IP地址/域名，**port**为Redis实例的端口。IP地址/域名和端口获取见步骤[1](#li695671074019)，请按实际情况修改后执行。**pwd**为创建Redis实例时自定义的密码，请按实际情况修改后执行。

        2.  jedis连接池示例。

            ```
            // 密码模式生成连接池配置信息
             String ip = "192.168.0.150"; 
             int port = 6379; 
             String pwd = "passwd"; 
             GenericObjectPoolConfig config = new GenericObjectPoolConfig(); 
             config.setTestOnBorrow(false); 
             config.setTestOnReturn(false); 
             config.setMaxTotal(100); 
             config.setMaxIdle(100); 
             config.setMaxWaitMillis(2000); 
             JedisPool pool = new JedisPool(config, ip, port, 100000, pwd);// 在应用初始化的时候生成连接池
             // 在业务操作时，从连接池获取连接
             Jedis client = pool.getResource(); 
             try { 
                 // 执行指令
                 String result = client.set("key-string", "Hello, Redis!"); 
                 System.out.println( String.format("set指令执行结果:%s", result) ); 
                 String value = client.get("key-string"); 
                 System.out.println( String.format("get指令执行结果:%s", value) ); 
             } catch (Exception e) { 
                 // TODO: handle exception
             } finally { 
                 // 业务操作完成，将连接返回给连接池
                 if (null != client) { 
                     pool.returnResource(client); 
                 } 
             } // end of try block
             // 应用关闭时，释放连接池资源
             pool.destroy();
            
            // 免密模式生成连接池配置信息
             String ip = "192.168.0.150"; 
             int port = 6379; 
             GenericObjectPoolConfig config = new GenericObjectPoolConfig(); 
             config.setTestOnBorrow(false); 
             config.setTestOnReturn(false); 
             config.setMaxTotal(100); 
             config.setMaxIdle(100); 
             config.setMaxWaitMillis(2000); 
             JedisPool pool = new JedisPool(config, ip, port, 100000);// 在应用初始化的时候生成连接池
             // 在业务操作时，从连接池获取连接
             Jedis client = pool.getResource(); 
             try { 
                 // 执行指令
                 String result = client.set("key-string", "Hello, Redis!"); 
                 System.out.println( String.format("set指令执行结果:%s", result) ); 
                 String value = client.get("key-string"); 
                 System.out.println( String.format("get指令执行结果:%s", value) ); 
             } catch (Exception e) { 
                 // TODO: handle exception
             } finally { 
                 // 业务操作完成，将连接返回给连接池
                 if (null != client) { 
                     pool.returnResource(client); 
                 } 
             } // end of try block
             // 应用关闭时，释放连接池资源
             pool.destroy();
            ```

            其中，**ip**为Redis实例的IP地址/域名，**port**为Redis实例的端口。IP地址/域名和端口获取见步骤[1](#li695671074019)，请按实际情况修改后执行。**pwd**为创建Redis实例时自定义的密码，请按实际情况修改后执行。

    3.  参考Redis Java \(Jedis\) 客户端源码中的readme文件编译代码并运行Redis Java \(Jedis\) 客户端连接Redis实例。


## 连接Redis实例操作视频<a name="section16119183431717"></a>

如果需要详细了解连接Reids实例的操作，请单击以下链接观看视频。

[访问缓存实例操作视频](https://support.huaweicloud.com/dcs_video/index.html)


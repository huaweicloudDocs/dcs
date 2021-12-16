# lettuce<a name="dcs-ug-211105002"></a>

介绍使用同一VPC内弹性云服务器ECS上的lettuce连接Redis实例的方法。更多的客户端的使用方法请参考[Redis客户端](https://redis.io/clients)。

## 前提条件<a name="section1502270695932"></a>

-   已成功申请Redis实例，且状态为“运行中”。
-   已创建弹性云服务器，创建弹性云服务器的方法，请参见[创建弹性云服务器](https://support.huaweicloud.com/qs-ecs/ecs_02_0005.html)。
-   如果弹性云服务器为Linux系统，该弹性云服务器必须已经安装java编译环境。

## 操作步骤<a name="section22138386137"></a>

1.  查看并获取待连接Redis实例的IP地址/域名和端口。

    具体步骤请参见[查看实例信息](查看实例信息.md)。

2.  登录弹性云服务器。
3.  使用Redis Java \(lettuce\)客户端连接实例。
    -   lettuce单连方式连接Redis单机、主备、proxy集群示例。

        ```
        // password是连接的密码，不需验证删除password@即可,密码中有特殊字符时需要进行转码
        RedisClient redisClient = RedisClient.create("redis://password@host:port");
        StatefulRedisConnection<String, String> connection = redisClient.connect();
        RedisCommands<String, String> syncCommands = connection.sync();
        syncCommands.set("key", "value");
        System.out.println("Connected to Redis:" + syncCommands.get("key"));
        // 连接关闭
        connection.close();
        // 客户端关闭
        redisClient.shutdown();
        ```

    -   lettuce连接池方式连接Redis单机、主备、proxy集群示例。

        ```
        // password是连接的密码，不需验证删除password@即可,密码中有特殊字符时需要进行转码
        RedisClient clusterClient = RedisClient.create("redis://password@host:port");
        GenericObjectPoolConfig<StatefulRedisConnection<String, String>> genericObjectPoolConfig = new GenericObjectPoolConfig();
        // 连接池相关参数配置
        genericObjectPoolConfig.setMaxIdle(3);
        genericObjectPoolConfig.setMinIdle(2);
        genericObjectPoolConfig.setMaxTotal(3);
        genericObjectPoolConfig.setMaxWaitMillis(-1);
        GenericObjectPool<StatefulRedisConnection<String, String>> pool = ConnectionPoolSupport
                .createGenericObjectPool(() -> clusterClient.connect(), genericObjectPoolConfig);
        // 获取连接进行操作
        try (StatefulRedisConnection<String, String> con = pool.borrowObject()) {
            RedisCommands<String, String> sync = con.sync();
        	sync.set("key", "value");
            System.out.println("Connected by pool:" + sync.get("key"));
        } catch (Exception e) {
            e.printStackTrace();
        }finally {
            // 资源关闭
            pool.close();
            clusterClient.shutdown();
        }
        ```

    -   lettuce连接cluster集群示例。

        ```
        // password是连接的密码，不需验证删除password@即可,密码中有特殊字符时需要进行转码
        RedisClusterClient redisClient = RedisClusterClient.create("redis://password@host:port");
        StatefulRedisClusterConnection<String, String> connection = redisClient.connect();
        RedisAdvancedClusterCommands<String, String> syncCommands = connection.sync();
        syncCommands.set("key", "value");
        System.out.println("Connected to RedisCluster:"+syncCommands.get("key"));
        // 连接关闭
        connection.close();
        // 客户端关闭
        redisClient.shutdown();
        ```




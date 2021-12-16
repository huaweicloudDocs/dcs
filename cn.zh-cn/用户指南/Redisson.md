# Redisson<a name="dcs-ug-211105004"></a>

介绍使用同一VPC内弹性云服务器ECS上的Redisson连接Redis实例的方法。更多的客户端的使用方法请参考[Redis客户端](https://redis.io/clients)。

## 前提条件<a name="section1502270695932"></a>

-   已成功申请Redis实例，且状态为“运行中”。
-   已创建弹性云服务器，创建弹性云服务器的方法，请参见[创建弹性云服务器](https://support.huaweicloud.com/qs-ecs/ecs_02_0005.html)。
-   如果弹性云服务器为Linux系统，该弹性云服务器必须已经安装java编译环境。

## 操作步骤<a name="section123051428162516"></a>

1.  查看并获取待连接Redis实例的IP地址/域名和端口。

    具体步骤请参见[查看实例信息](查看实例信息.md)。

2.  登录弹性云服务器。
3.  使用Redis Java \(Redisson\)客户端连接实例。
    -   Redisson单连方式连接Redis单机、主备、proxy集群示例。

        ```
        Config config = new Config();
        SingleServerConfig singleServerConfig = config.useSingleServer();
        singleServerConfig.setAddress("redis://host:port");
        // singleServerConfig.setPassword("9client!");
        RedissonClient redisson = Redisson.create(config);
        // 测试concurrentMap,put方法的时候就会同步到redis中
        ConcurrentMap<String, Object> map = redisson.getMap("FirstMap");
        map.put("wanger", "男");
        map.put("zhangsan", "nan");
        map.put("lisi", "女");
        ConcurrentMap resultMap = redisson.getMap("FirstMap");
        System.out.println("resultMap==" + resultMap.keySet());
        // 测试Set集合
        Set mySet = redisson.getSet("MySet");
        mySet.add("wanger");
        mySet.add("lisi");
        Set resultSet = redisson.getSet("MySet");
        System.out.println("resultSet===" + resultSet.size());
        // 测试Queue队列
        Queue myQueue = redisson.getQueue("FirstQueue");
        myQueue.add("wanger");
        myQueue.add("lili");
        myQueue.add("zhangsan");
        myQueue.peek();
        myQueue.poll();
        Queue resultQueue = redisson.getQueue("FirstQueue");
        System.out.println("resultQueue===" + resultQueue);
        // 关闭连接
        redisson.shutdown();
        ```

    -   Redisson连接池方式连接Redis单机、主备、proxy集群示例。

        ```
        // 1.初始化
        Config config = new Config();
        SingleServerConfig singleServerConfig = config.useSingleServer();
        singleServerConfig.setAddress("redis://host:6379");
        //设置对于master节点的连接池中连接数最大为500
        singleServerConfig.setConnectionPoolSize(500);
        // 那么这些连接将会自动被关闭，并从连接池里去掉。时间单位是毫秒。
        singleServerConfig.setIdleConnectionTimeout(10000);
        RedissonClient redisson = Redisson.create(config);
        // 测试concurrentMap,put方法的时候就会同步到redis中
        ConcurrentMap<String, Object> map = redisson.getMap("FirstMap");
        map.put("wanger", "男");
        map.put("zhangsan", "nan");
        map.put("lisi", "女");
        ConcurrentMap resultMap = redisson.getMap("FirstMap");
        System.out.println("resultMap==" + resultMap.keySet());
        // 测试Set集合
        Set mySet = redisson.getSet("MySet");
        mySet.add("wanger");
        mySet.add("lisi");
        Set resultSet = redisson.getSet("MySet");
        System.out.println("resultSet===" + resultSet.size());
        // 测试Queue队列
        Queue myQueue = redisson.getQueue("FirstQueue");
        myQueue.add("wanger");
        myQueue.add("lili");
        myQueue.add("zhangsan");
        myQueue.peek();
        myQueue.poll();
        Queue resultQueue = redisson.getQueue("FirstQueue");
        System.out.println("resultQueue===" + resultQueue);
        // 关闭连接
        redisson.shutdown();
        ```

    -   Redisson连接cluster集群示例。

        ```
        Config config = new Config();
        ClusterServersConfig clusterServersConfig = config.useClusterServers();
        clusterServersConfig.addNodeAddress("redis://host:port");
        // 设置密码
        // clusterServersConfig.setPassword("");
        RedissonClient redisson = Redisson.create(config);
        ConcurrentMap<String, Object> map = redisson.getMap("FirstMap");
        map.put("wanger", "男");
        map.put("zhangsan", "nan");
        map.put("lisi", "女");
        ConcurrentMap resultMap = redisson.getMap("FirstMap");
        System.out.println("resultMap==" + resultMap.keySet());
        // 2.测试Set集合
        Set mySet = redisson.getSet("MySet");
        mySet.add("wanger");
        mySet.add("lisi");
        Set resultSet = redisson.getSet("MySet");
        System.out.println("resultSet===" + resultSet.size());
        //3.测试Queue队列
        Queue myQueue = redisson.getQueue("FirstQueue");
        myQueue.add("wanger");
        myQueue.add("lili");
        myQueue.add("zhangsan");
        myQueue.peek();
        myQueue.poll();
        Queue resultQueue = redisson.getQueue("FirstQueue");
        System.out.println("resultQueue===" + resultQueue);
        // 关闭连接
        redisson.shutdown();
        ```




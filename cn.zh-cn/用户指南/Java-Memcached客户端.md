# Java Memcached客户端<a name="dcs-ug-190715002"></a>

介绍使用同一VPC内弹性云服务器ECS上的Java客户端连接Memcached实例的方法。

## 前提条件<a name="section188251286"></a>

-   已成功申请Memcached实例，且状态为“运行中”。
-   已创建弹性云服务器，并已安装好客户端。创建弹性云服务器的方法，请参见《弹性云服务器用户指南》。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >您创建的弹性云服务器必须与Memcached实例属于同一个VPC，并配置相同的安全组，以确保弹性云服务器与缓存实例的网络是连通的。
    >如果弹性云服务器与Memcached实例不在相同VPC中，可以通过建立VPC对等连接方式连通网络，具体请参考常见问题：[缓存实例是否支持跨VPC访问？](https://support.huaweicloud.com/dcs_faq/dcs-faq-0427002.html)
    >如果弹性云服务器与Memcached实例配置了不同的安全组，可以通过设置安全组规则连通网络，具体请参考常见问题：[如何选择和配置安全组？](https://support.huaweicloud.com/dcs_faq/dcs-faq-0713002.html)

-   您的弹性云服务器已安装好Java JDK和常用的IDE（如Eclipse）。
-   已获取spymemcached-x.y.z.jar依赖包。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >其中x.y.z为依赖包的版本号，建议获取最新版本。


## 操作步骤<a name="section199614119815"></a>

1.  登录[分布式缓存服务管理控制台](https://console.huaweicloud.com/dcs)。
2.  在管理控制台左上角单击![](figures/icon-region.png)，选择区域和项目。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >此处请选择与您的应用服务相同的区域。

3.  单击左侧菜单栏的“缓存管理”，进入缓存实例信息页面。
4.  <a name="li19539104154"></a>单击需要使用的其中一个Memcached实例的名称，进入该Memcached实例的基本信息页面。查看并获取该Memcached实例的IP地址/域名和端口。
5.  将已获取的spymemcached-x.y.z.jar依赖包上传到已创建的弹性云服务器。
6.  登录弹性云服务器。
7.  在Eclipse中创建一个Java工程，并将spymemcached-x.y.z.jar依赖包导入，工程名可自定义。
8.  新建一个ConnectMemcached1类，将如下Java代码复制到类中并修改代码。
    -   密码模式代码示例

        其中ip or domain name:port需要修改为[4](#li19539104154)获取的Memcached实例IP地址/域名和端口。userName和password需要修改为Memcached实例的用户名和密码。

        ```
        //java 连接加密的Memcached代码
        import java.io.IOException;
        import java.util.concurrent.ExecutionException;
        
        import net.spy.memcached.AddrUtil;
        import net.spy.memcached.ConnectionFactoryBuilder;
        import net.spy.memcached.ConnectionFactoryBuilder.Protocol;
        import net.spy.memcached.MemcachedClient;
        import net.spy.memcached.auth.AuthDescriptor;
        import net.spy.memcached.auth.PlainCallbackHandler;
        import net.spy.memcached.internal.OperationFuture;
        
        public class ConnectMemcached1
        {
            public static void main(String[] args)
            {
                final String connectionaddress = "ip or domain name:port"; 
                final String username = "userName";//用户名
                final String password = "password";//密码
                MemcachedClient client = null;
                try
                {
                    AuthDescriptor authDescriptor =
                        new AuthDescriptor(new String[] {"PLAIN"}, new PlainCallbackHandler(username,
                                password));
                    client = new MemcachedClient(
                            new ConnectionFactoryBuilder().setProtocol(Protocol.BINARY)
                                    .setAuthDescriptor(authDescriptor)
                                    .build(),
                            AddrUtil.getAddresses(connectionaddress));
                    String key = "memcached";//向Memcached中存一个key为"memcached"的数据
                    String value = "Hello World";//value为Hello World
                    int expireTime = 5; // 过期时间，单位s; 从写入时刻开始计时，超过expireTime s后，该数据过期失效，无法再读出；
                    doExcute(client, key, value, expireTime);//执行操作
                }
                catch (IOException e)
                {
                    e.printStackTrace();
                }
            }
        
            /**
             *向Memcached写数据方法
             */
            private static void doExcute(MemcachedClient client, String key, String value, int expireTime)
            {
                try
                {
                    OperationFuture<Boolean> future = client.set(key, expireTime, value);
                    future.get();// spymemcached set()是异步的，future.get() 等待cache.set()操作结束，也可以不等待，用户根据自己需求选择;
                    System.out.println("Set操作成功");
                    System.out.println("Get操作:" + client.get(key));
                    Thread.sleep(6000);//等待6000毫秒，即6秒，该数据将会过期失效，无法再读出
                    System.out.println("6秒后再执行Get操作:" + client.get(key));
        
                }
                catch (InterruptedException e)
                {
                    e.printStackTrace();
                }
                catch (ExecutionException e)
                {
                    e.printStackTrace();
                }
                if (client != null)
                {
                    client.shutdown();
                }
            }
        }
        ```

    -   免密模式代码示例

        其中ip or domain name:port需要修改为[4](#li19539104154)获取的Memcached实例IP地址/域名和端口。

        ```
        //java 连接免密的Memcached代码
        import java.io.IOException;
        import java.util.concurrent.ExecutionException;
        
        import net.spy.memcached.AddrUtil;
        import net.spy.memcached.BinaryConnectionFactory;
        import net.spy.memcached.MemcachedClient;
        import net.spy.memcached.internal.OperationFuture;
        
        public class ConnectMemcached
        {
            public static void main(String[] args)
            {
                final String connectionaddress = "ip or domain name:port"; 
                MemcachedClient client = null;
                try
                {
                    client = new MemcachedClient(new BinaryConnectionFactory(), AddrUtil.getAddresses(connectionaddress));
                    String key = "memcached";//向Memcached中存一个key为"memcached"的数据
                    String value = "Hello World";//value为Hello World
                    int expireTime = 5; // 过期时间，单位s; 从写入时刻开始计时，超过 expireTime s后，该数据过期失效，无法再读出；
                    doExcute(client, key, value, expireTime);//执行操作
                }
                catch (IOException e)
                {
                    e.printStackTrace();
                }
            }
        
            /**
             *向Memcached写数据方法
             */
            private static void doExcute(MemcachedClient client, String key, String value, int expireTime)
            {
                try
                {
                    OperationFuture<Boolean> future = client.set(key, expireTime, value);
                    future.get();// spymemcached set()是异步的，future.get() 等待cache.set()操作结束，也可以不等待，用户根据自己需求选择;
                    System.out.println("Set操作成功");
                    System.out.println("Get操作:" + client.get(key));
                    Thread.sleep(6000);//等待6000毫秒，即6秒，该数据将会过期失效，无法再读出
                    System.out.println("6秒后再执行Get操作:" + client.get(key));
        
                }
                catch (InterruptedException e)
                {
                    e.printStackTrace();
                }
                catch (ExecutionException e)
                {
                    e.printStackTrace();
                }
                if (client != null)
                {
                    client.shutdown();
                }
            }
        }
        ```

9.  运行main方法，在Eclipse下的Console窗口可以看到如下结果。

    ```
    Set操作成功
    Get操作:Hello World
    6秒后再执行Get操作:null
    ```



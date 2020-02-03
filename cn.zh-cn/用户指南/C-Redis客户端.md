# C\# Redis客户端<a name="ZH-CN_TOPIC_0148195355"></a>

介绍使用同一VPC内弹性云服务器ECS上的C\# Redis客户端连接Redis实例的方法。更多的客户端的使用方法，请参考[https://redis.io/clients](https://redis.io/clients)

## 前提条件<a name="section1502270695932"></a>

-   已成功申请Redis实例，且状态为“运行中”。
-   已创建弹性云服务器，创建弹性云服务器的方法，请参见《弹性云服务器用户指南》。
-   如果弹性云服务器为Linux系统，该弹性云服务器必须已经安装gcc编译环境。

## 操作步骤<a name="section994505645015"></a>

1.  <a name="li457118182512"></a>查看并获取待连接Redis实例的IP地址/域名和端口。

    具体步骤请参见[查看缓存实例信息](查看缓存实例信息.md)。

2.  登录弹性云服务器。

    弹性云服务器操作系统，这里以Window为例。

3.  在弹性云服务器安装VS 2017社区版。
4.  启动VS 2017，新建一个工程。

    工程名自定义，这里设置为“redisdemo”。

5.  使用VS的nuget管理工具安装C\# Redis客户端StackExchange.Redis。

    按照如[图1](#fig394516508313)操作，进入程序包管理器控制台，在nuget控制台输入：**Install-Package StackExchange.Redis** _-Version 1.2.6_。（版本号可以不指定）

    **图 1**  进入程序包管理器控制台<a name="fig394516508313"></a>  
    ![](figures/进入程序包管理器控制台.png "进入程序包管理器控制台")

6.  编写如下代码，并使用String的set和get测试连接。

    ```
    using System;
    using StackExchange.Redis;
    
    namespace redisdemo
    {
        class Program
        {
            // redis config
            private static ConfigurationOptions connDCS = ConfigurationOptions.Parse("10.10.38.233:6379,password=********,connectTimeout=2000");
            //the lock for singleton
            private static readonly object Locker = new object();
            //singleton
            private static ConnectionMultiplexer redisConn;
            //singleton
            public static ConnectionMultiplexer getRedisConn()
            {
                if (redisConn == null)
                {
                    lock (Locker)
                    {
                        if (redisConn == null || !redisConn.IsConnected)
                        {
                            redisConn = ConnectionMultiplexer.Connect(connDCS);
                        }
                    }
                }
                return redisConn;
            }
            static void Main(string[] args)
            {
                redisConn = getRedisConn();
                var db = redisConn.GetDatabase();
                //set get
                string strKey = "Hello";
                string strValue = "DCS for Redis!";
                Console.WriteLine( strKey + ", " + db.StringGet(strKey));
    
                Console.ReadLine();
            }
        }
    }
    ```

    其中，_10.10.38.233:6379_分别为Redis实例的IP地址/域名以及端口。IP地址/域名和端口获取见步骤[1](#li457118182512)，请按实际情况修改后执行。_\*\*\*\*\*\*\*\*_为创建Redis实例时自定义的密码，请按实际情况修改后执行。

7.  运行代码，控制台界面输出如下，表示连接成功。

    ```
    Hello, DCS for Redis!
    ```

    关于客户端的其他命令，可以参考官网：[https://stackexchange.github.io/StackExchange.Redis/](https://stackexchange.github.io/StackExchange.Redis/)。


## 连接Redis实例操作视频<a name="section107022112212"></a>

如果需要详细了解连接Reids实例的操作，请单击以下链接观看视频。

[访问缓存实例操作视频](https://support.huaweicloud.com/dcs_video/index.html)


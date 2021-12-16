# redis集群对接springboot<a name="dcs-ug-211203001"></a>

## 前提条件<a name="section1665418353414"></a>

-   已成功申请Redis实例，且状态为“运行中”。
-   已创建弹性云服务器，创建弹性云服务器的方法，请参见创建弹性云服务器。
-   如果弹性云服务器为Linux系统，该弹性云服务器必须已经安装java编译环境。

## 操作步骤<a name="section16902680423"></a>

1.  查看并获取待连接Redis实例的IP地址/域名和端口。

    具体步骤请参见[查看实例信息](查看实例信息.md)。

2.  登录弹性云服务器。
3.  首先使用maven在pom.xml添加如下依赖。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >springboot从2.0起默认使用lettuce客户端进行连接。

    ```
        <dependencies>
    		<dependency>
    			<groupId>org.springframework.boot</groupId>
    			<artifactId>spring-boot-starter-data-redis</artifactId>
    		</dependency>
    		<dependency>
    			<groupId>org.springframework.boot</groupId>
    			<artifactId>spring-boot-starter-web</artifactId>
    		</dependency>
    	</dependencies>
    ```

4.  在application.properties配置文件中加上redis配置，其中host为集群的ip/域名，port为端口。

    ```
    # redis集群配置
    spring.redis.cluster.nodes=host:port
    # Redis服务器连接密码（默认为空）
    spring.redis.password=
    
    3、编写redis操作封装类RedisDao.java
    @Repository
    public class RedisDao {
    	@Autowired
    	private StringRedisTemplate template;
    	
    	/**
    	 * 向redis中写入键值对
    	 *
    	 * @param key
    	 * @param value
    	 */
    	public void setKey(String key, String value) {
    		ValueOperations<String, String> ops = template.opsForValue();
    		ops.set(key, value, 10, TimeUnit.MINUTES);
    	}
    	/**
    	 * 从redis中根据键取值
    	 *
    	 * @param key
    	 * @return value
    	 */
    	public String getValue(String key) {
    		ValueOperations<String, String> ops = template.opsForValue();
    		return ops.get(key);
    	}
    }
    ```

5.  编写contoller类进行测试。

    ```
    @RestController
    public class HelloRedis {
    	@Autowired
    	RedisDao redisDao;
    	@RequestMapping("/getParams")
    	@ResponseBody
    	public String hello(String name, String age) {
    		System.out.println("name=" + name + " * " + "age=" + age);
    		redisDao.setKey("name", name);
    		redisDao.setKey("age", age);
    		return "name=" + redisDao.getValue("name") + " * " + "age=" + redisDao.getValue("age");
    	}
    }
    ```

6.  将项目打成jar包“test”，使用**java -jar test**运行项目。


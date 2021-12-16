# C++客户端<a name="dcs-ug-190715004"></a>

介绍使用同一VPC内弹性云服务器ECS上的C++客户端连接Memcached实例的方法。

## 前提条件<a name="section257641313363"></a>

-   已成功申请Memcached实例，且状态为“运行中”。
-   已创建弹性云服务器。创建弹性云服务器的方法，请参见《弹性云服务器用户指南》。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >您创建的弹性云服务器必须与Memcached实例属于同一个VPC，并配置相同的安全组，以确保弹性云服务器与缓存实例的网络是连通的。
    >如果弹性云服务器与Memcached实例不在相同VPC中，可以通过建立VPC对等连接方式连通网络，具体请参考常见问题：[缓存实例是否支持跨VPC访问？](https://support.huaweicloud.com/dcs_faq/dcs-faq-0427002.html)
    >如果弹性云服务器与Memcached实例配置了不同的安全组，可以通过设置安全组规则连通网络，具体请参考常见问题：[如何选择和配置安全组？](https://support.huaweicloud.com/dcs_faq/dcs-faq-0713002.html)

-   您的弹性云服务器已安装好GCC，建议为4.8.4或更高版本。
-   已获取[l](https://launchpad.net/libmemcached/+download)[ibmemcached-x.y.z.tar.gz](https://launchpad.net/libmemcached/+download)依赖包。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >其中x.y.z为依赖包的版本号，建议获取最新版本。


## 操作步骤<a name="section15431539195717"></a>

1.  登录[分布式缓存服务管理控制台](https://console.huaweicloud.com/dcs)。
2.  在管理控制台左上角单击![](figures/icon-region.png)，选择区域和项目。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >此处请选择与您的应用服务相同的区域。

3.  单击左侧菜单栏的“缓存管理”，进入缓存实例信息页面。
4.  <a name="li346073918571"></a>单击需要使用的其中一个Memcached实例的名称，进入该Memcached实例的基本信息页面。查看并获取该Memcached实例的IP地址/域名和端口。
5.  将已获取的libmemcached-x.y.z.tar.gz依赖包上传到已创建的弹性云服务器。
6.  登录弹性云服务器。
7.  安装sasl相关依赖包。

    debian类系统：**apt install libsasl2-dev cloog.ppl**

    Redhat类系统：  **yum install cyrus-sasl\***

8.  执行如下命令安装依赖包。

    _**tar -xzvf libmemcached-x.y.z.tar.gz**_

    **_cd libmemcached-x.y.z_**

    **_./configure --enable-sasl_**

    **_make_**

    **_make install_**

9.  新建build.sh文件，将如下代码复制到build.sh文件。

    ```
    g++ -o dcs_sample dcs_sample.cpp -lmemcached -std=c++0x -lpthread -lsasl2
    ```

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >编译如果报错找不到libmemcached.so.11文件，请用find命令找到此文件，并将其复制到/usr/lib目录下。

10. 新建dcs\_sample.cpp文件，将如下C++代码复制到dcs\_sample.cpp文件并修改代码。
    -   密码模式代码示例

        其中ip or domain name和port需要修改为[4](#li346073918571)获取的Memcached实例IP地址/域名和端口。userName和password需要修改为Memcached实例的用户名和密码。

        ```
        #include <iostream>
        #include <string>
        #include <libmemcached/memcached.h>
        using namespace std;
        
        #define IP  "ip or domain name"
        #define PORT  port
        #define USERNAME "userName"
        #define PASSWORD "password"
        memcached_return rusult;
        
        memcached_st * init()
        {
            memcached_st *memcached = NULL;
            memcached_server_st *cache;
            memcached = memcached_create(NULL);
            cache = memcached_server_list_append(NULL, IP, PORT, &rusult);
        
            sasl_client_init(NULL);
                 memcached_set_sasl_auth_data(memcached, USERNAME, PASSWORD); 
                 memcached_behavior_set(memcached,MEMCACHED_BEHAVIOR_BINARY_PROTOCOL,1);
                 memcached_server_push(memcached,cache);
                 memcached_server_list_free(cache);
                    return memcached;
        }
        
        int main(int argc, char *argv[])
        {
                 memcached_st *memcached=init();
            string key = "memcached";
            string value = "hello world!";
            size_t value_length = value.length();
            int expire_time = 0;
            uint32_t flag = 0;
        
            rusult = memcached_set(memcached,key.c_str(),key.length(),value.c_str(),value.length(),expire_time,flag);  
            if (rusult != MEMCACHED_SUCCESS){
              cout <<"set data failed: " << rusult << endl;
              return -1;
            }
            cout << "set succesed, key: " << key << ", value: " << value << endl;
            cout << "get key:" << key << endl;
            char* result = memcached_get(memcached,key.c_str(),key.length(),&value_length,&flag,&rusult);
            cout << "value:" << result << endl;
                        
            memcached_free(memcached);
            return 0;
        }
        ```

    -   免密模式代码示例

        其中ip or domain name和port需要修改为[4](#li346073918571)获取的Memcached实例IP地址/域名和端口。

        ```
        #include <iostream>
        #include <string>
        #include <libmemcached/memcached.h>
        using namespace std;
        
        #define IP  "ip or domain name"
        #define PORT  port
        memcached_return rusult;
        
        memcached_st * init()
        {
            memcached_st *memcached = NULL;
            memcached_server_st *cache;
            memcached = memcached_create(NULL);
            cache = memcached_server_list_append(NULL, IP, PORT, &rusult);
                 memcached_server_push(memcached,cache);
            memcached_server_list_free(cache);
                 return memcached;
        }
        
        int main(int argc, char *argv[])
        {
                 memcached_st *memcached=init();
            string key = "memcached";
            string value = "hello world!";
            size_t value_length = value.length();
            int expire_time = 0;
            uint32_t flag = 0;
        
            rusult = memcached_set(memcached,key.c_str(),key.length(),value.c_str(),value.length(),expire_time,flag);  
            if (rusult != MEMCACHED_SUCCESS){
              cout <<"set data failed: " << rusult << endl;
              return -1;
            }
            cout << "set succesed, key: " << key << " ,value: " << value << endl;
            cout << "get key:" << key << endl;
            char* result = memcached_get(memcached,key.c_str(),key.length(),&value_length,&flag,&rusult);
            cout << "value:" << result << endl;
                         
            memcached_free(memcached);
            return 0;
        }
        ```

11. 执行如下命令编译源码。

    chmod 700 build.sh

    ./build.sh

    生成dcs\_sample二进制文件。

12. 执行如下命令连接使用Memcached实例。

    ./dcs\_sample

    ```
    set succesed, key: memcached ,value: hello world!
    get key:memcached
    value:hello world!
    ```



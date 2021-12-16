# Redis连接约束<a name="dcs-ug-0312007"></a>

任何兼容Redis协议的客户端都可以访问DCS的Redis实例，您可以根据自身应用特点选用任何Redis客户端，Redis支持的客户端列表请参见[Redis客户端](https://redis.io/clients)。

>![](public_sys-resources/icon-note.gif) **说明：** 
>DCS Redis 3.0已下线，暂停售卖，建议使用Redis 4.0/5.0。

-   使用同一VPC内弹性云服务器ECS上的客户端访问Redis实例时，需要满足以下约束：
    -   安装了客户端的弹性云服务器必须与Redis实例属于同一个VPC，如果是Redis 3.0实例，需配置相同的安全组或者不同安全组时配置安全组连通规则，如果是Redis 4.0/5.0/Redis 6.0实例，需将弹性云服务器的IP地址加入实例白名单，以确保弹性云服务器与Redis实例的网络是连通的。
    -   如果弹性云服务器与Redis实例不在相同VPC中，可以通过建立VPC对等连接方式连通网络，具体请参考常见问题：[缓存实例是否支持跨VPC访问？](https://support.huaweicloud.com/dcs_faq/dcs-faq-0427002.html)

-   使用公网访问Redis 3.0实例时，需要满足以下约束：

    Redis缓存实例配置了正确的安全组规则。当SSL加密功能关闭时，Redis实例的安全组入方向规则，必须允许外部地址访问6379端口；当SSL加密功能开启时，则必须允许外部地址访问36379端口。具体配置请参考常见问题：[如何选择和配置安全组？](https://support.huaweicloud.com/dcs_faq/dcs-faq-0713002.html)

-   如果客户端服务器和Redis实例不在同一Region，需要跨Region访问Redis实例时，实例域名无法跨Region解析，无法通过域名访问。可以通过在hosts中手动配置域名与IP绑定关系或使用IP进行访问。


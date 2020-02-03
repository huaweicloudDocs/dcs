# Redis连接约束<a name="ZH-CN_TOPIC_0148195223"></a>

任何兼容Redis协议的客户端都可以访问DCS的Redis实例，您可以根据自身应用特点选用任何Redis客户端。

-   使用同一VPC内弹性云服务器ECS上的客户端访问Redis实例时，需要满足以下约束：
    -   安装了客户端的弹性云服务器必须与DCS缓存实例属于同一个VPC，并配置相同的安全组，以确保弹性云服务器与DCS缓存实例的网络是连通的。
    -   如果弹性云服务器与DCS缓存实例不在相同VPC中，可以通过建立VPC对等连接方式连通网络，具体请参考常见问题：[缓存实例是否支持跨VPC访问？](https://support.huaweicloud.com/dcs_faq/dcs-zh-ug-180312006.html)
    -   如果弹性云服务器与Redis实例配置了不同的安全组，可以通过设置安全组规则连通网络，具体请参考常见问题：[如何选择和配置安全组？](https://support.huaweicloud.com/dcs_faq/zh-cn_topic_0082442607.html)

-   使用公网访问Redis实例时，需要满足以下约束：

    Redis缓存实例配置了正确的安全组规则。当SSL加密功能关闭时，Redis实例的安全组入方向规则，必须允许外部地址访问6379端口；当SSL加密功能开启时，则必须允许外部地址访问36379端口。具体配置请参考常见问题：[如何选择和配置安全组？](https://support.huaweicloud.com/dcs_faq/zh-cn_topic_0082442607.html)



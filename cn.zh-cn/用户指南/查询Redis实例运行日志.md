# 查询Redis实例运行日志<a name="dcs-ug-1009001"></a>

您可以在控制台配置Redis实例日志采集任务，根据时间采集redis.log日志内容，采集成功后，您可以将日志下载到本地，查看实例的运行日志。

## 操作步骤<a name="section173422026132015"></a>

1.  登录[分布式缓存服务管理控制台](https://console.huaweicloud.com/dcs)。
2.  在管理控制台左上角单击![](figures/icon-region.png)，选择区域和项目。
3.  单击左侧菜单栏的“缓存管理”，进入实例信息页面。
4.  单击需要查看运行日志的DCS缓存实例名称，进入该实例的基本信息页面。
5.  单击“运行日志”页签。
6.  单击“新增日志文件”，配置日志采集信息。

    如果是主备和集群实例，支持根据分片和副本进行日志采集，您需要选择指定分片和副本。如果是单机实例，实例只有一个节点，默认采集该节点的日志。



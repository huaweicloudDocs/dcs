# 下载实例rdb和aof文件<a name="ZH-CN_TOPIC_0148195258"></a>

由于自动备份和手动备份实例有一定的限制性（自动备份的文件在系统最大保留天数为7天，手动备份会占用OBS空间），您可将实例的rdb和aof备份文件下载，本地永久保存。

当前仅支持将主备或者集群实例的备份文件下载，单机实例不支持备份恢复功能。单机实例若需要下载备份文件，可参考[导出单机实例rdb备份文件](https://support.huaweicloud.com/dcs_faq/dcs-faq-0427075.html)，使用Redis-Cli工具导出rdb文件。

以下仅针对主备和集群实例：

-   如果是Redis3.0，支持aof格式持久化，支持在控制台下载导出aof格式的备份文件，如果需要导出rdb，可以通过Redis-cli导出，使用命令：**redis-cli -h  _\{redis\_address\}_  -p 6379 \[-a  _password_\] --rdb \{output.rdb\}**。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >DCS Redis3.0已下线，暂停售卖，建议使用Redis4.0/5.0。

-   如果是Redis4.0和5.0，支持aof和rdb格式持久化，可以在控制台下载导出aof和rdb格式的备份文件。
-   如果是企业版Redis6.0，支持aof和rdb格式持久化，可以在控制台下载导出aof和rdb格式的备份文件。

## 前提条件<a name="section16471617102016"></a>

实例已做备份且没有过期。

## 操作步骤<a name="section1120817232111"></a>

1.  登录[分布式缓存服务管理控制台](https://console.huaweicloud.com/dcs)。
2.  在管理控制台左上角单击![](figures/icon-region.png)，选择区域和项目。
3.  单击左侧菜单栏的“缓存管理”，进入DCS缓存实例信息页面。

    “缓存管理”支持通过筛选来查询对应的DCS缓存实例。当前支持的筛选条件为“状态”和“名称”。

4.  在需要查看的DCS缓存实例左侧，单击实例名称，进入实例的基本信息页面。
5.  单击“备份与恢复”页签，进入备份恢复管理页面。

    页面下方显示历史备份数据列表。

6.  选择需要下载的历史备份数据，单击右侧的“下载”，弹出下载备份文件窗口。
7.  选择下载方式。

    包括以下两种下载方式：

    -   URL下载
        1.  设置URL有效期并单击“查询”按钮。
        2.  通过URL列表下载备份文件。

            >![](public_sys-resources/icon-note.gif) **说明：** 
            >如果复制下载链接，并在Linux系统中使用wget命令获取备份文件，则需要将下载链接使用**英文引号**括起来。如：
            >wget 'https://obsEndpoint.com:443/redisdemo.rdb?parm01=value01&parm02=value02'
            >原因是URL中携带符号：&，wget命令识别URL参数会出现异常，需要使用英文引号辅助识别完整URL。


    -   OBS下载

        按照页面的下载步骤描述操作即可。




# DCS API参考-API Designer

-   [使用前必读](使用前必读.md)
    -   [概述](概述.md)
    -   [调用说明](调用说明.md)
    -   [终端节点](终端节点.md)
    -   [约束与限制](约束与限制.md)
    -   [基本概念](基本概念.md)

-   [API概览](API概览.md)
-   [如何调用API](如何调用API.md)
    -   [构造请求](构造请求.md)
    -   [认证鉴权](认证鉴权.md)
    -   [返回结果](返回结果.md)

-   [应用示例](应用示例.md)
    -   [创建DCS高频场景示例](创建DCS高频场景示例.md)
    -   [示例1：创建Redis实例](示例1-创建Redis实例.md)
    -   [示例2：创建数据迁移任务](示例2-创建数据迁移任务.md)
    -   [示例3：批量删除Redis实例](示例3-批量删除Redis实例.md)

-   [API V2](API-V2.md)
    -   [生命周期管理](生命周期管理.md)
        -   [创建缓存实例](创建缓存实例.md)
        -   [查询所有实例列表](查询所有实例列表.md)
        -   [批量删除实例](批量删除实例.md)
        -   [查询指定实例](查询指定实例.md)
        -   [删除实例](删除实例.md)
        -   [修改实例信息](修改实例信息.md)
        -   [变更实例规格](变更实例规格.md)

    -   [实例管理](实例管理.md)
        -   [主备切换](主备切换.md)
        -   [修改密码](修改密码.md)
        -   [查询实例状态](查询实例状态.md)
        -   [重启实例或清空数据](重启实例或清空数据.md)
        -   [查询运行中实例的统计信息](查询运行中实例的统计信息.md)

    -   [分片与副本](分片与副本.md)
        -   [设置备节点优先级](设置备节点优先级.md)
        -   [域名摘除IP](域名摘除IP.md)
        -   [查询分片信息](查询分片信息.md)

    -   [参数管理](参数管理.md)
        -   [查询实例配置参数](查询实例配置参数.md)
        -   [修改实例配置参数](修改实例配置参数.md)

    -   [备份与恢复](备份与恢复.md)
        -   [删除备份文件](删除备份文件.md)
        -   [恢复指定实例](恢复指定实例.md)
        -   [查询实例恢复记录](查询实例恢复记录.md)
        -   [获取备份文件下载链接](获取备份文件下载链接.md)
        -   [备份指定实例](备份指定实例.md)
        -   [查询实例备份信息](查询实例备份信息.md)

    -   [数据迁移](数据迁移.md)
        -   [创建数据迁移任务](创建数据迁移任务.md)
        -   [查询迁移任务列表](查询迁移任务列表.md)
        -   [删除数据迁移任务](删除数据迁移任务.md)
        -   [查询迁移任务详情](查询迁移任务详情.md)
        -   [停止数据迁移任务](停止数据迁移任务.md)
        -   [查询在线迁移进度明细](查询在线迁移进度明细.md)

    -   [标签管理](标签管理.md)
        -   [查询租户所有标签](查询租户所有标签.md)
        -   [批量添加或删除标签](批量添加或删除标签.md)
        -   [查询单个实例标签](查询单个实例标签.md)

    -   [缓存分析](缓存分析.md)
        -   [创建大key分析任务](创建大key分析任务.md)
        -   [查询大key分析任务列表](查询大key分析任务列表.md)
        -   [查询大key分析详情](查询大key分析详情.md)
        -   [删除大key分析记录](删除大key分析记录.md)
        -   [设置大key自动分析配置](设置大key自动分析配置.md)
        -   [查询大key自动分析配置](查询大key自动分析配置.md)
        -   [创建热key分析任务](创建热key分析任务.md)
        -   [查询热key分析任务列表](查询热key分析任务列表.md)
        -   [查询热key分析详情](查询热key分析详情.md)
        -   [删除热key分析任务](删除热key分析任务.md)
        -   [设置热key自动分析配置](设置热key自动分析配置.md)
        -   [查询热key自动分析配置](查询热key自动分析配置.md)

    -   [日志管理](日志管理.md)
        -   [查询慢日志](查询慢日志.md)
        -   [查询Redis运行日志列表](查询Redis运行日志列表.md)
        -   [采集Redis运行日志](采集Redis运行日志.md)
        -   [获取日志下载链接](获取日志下载链接.md)

    -   [IP白名单管理](IP白名单管理.md)
        -   [设置IP白名单分组](设置IP白名单分组.md)
        -   [查询指定实例的IP白名单](查询指定实例的IP白名单.md)

    -   [后台任务管理](后台任务管理.md)
        -   [查询后台任务列表](查询后台任务列表.md)
        -   [删除后台任务](删除后台任务.md)

    -   [实例诊断](实例诊断.md)
        -   [创建实例诊断任务](创建实例诊断任务.md)
        -   [查询实例诊断任务列表](查询实例诊断任务列表.md)
        -   [查询指定诊断报告](查询指定诊断报告.md)

    -   [其他接口](其他接口.md)
        -   [查询产品规格](查询产品规格.md)
        -   [查询维护时间窗时间段](查询维护时间窗时间段.md)
        -   [查询租户配额](查询租户配额.md)
        -   [查询单个主维度下子维度监控对象列表](查询单个主维度下子维度监控对象列表.md)
        -   [查询主维度信息列表](查询主维度信息列表.md)
        -   [查询可用区信息](查询可用区信息.md)

-   [权限策略和授权项](权限策略和授权项.md)
-   [附录](附录.md)
    -   [状态码](状态码.md)
    -   [错误码](错误码.md)
    -   [获取项目ID](获取项目ID.md)
    -   [获取帐户名和帐号ID](获取帐户名和帐号ID.md)
    -   [缓存实例状态说明](缓存实例状态说明.md)

-   [历史API（即将下线）](历史API（即将下线）.md)
    -   [生命周期管理](生命周期管理1.md)
        -   [创建缓存实例](创建缓存实例1.md)
        -   [删除实例](删除实例1.md)
        -   [批量删除实例](批量删除实例1.md)
        -   [查询指定实例](查询指定实例1.md)
        -   [查询所有实例列表](查询所有实例列表1.md)
        -   [修改实例信息](修改实例信息1.md)
        -   [扩容缓存实例](扩容缓存实例.md)

    -   [实例管理](实例管理1.md)
        -   [重启实例或清空数据](重启实例或清空数据1.md)
        -   [查询分片信息](查询分片信息1.md)
        -   [添加副本](添加副本1.md)
        -   [查询运行中实例的统计信息](查询运行中实例的统计信息1.md)
        -   [查询实例状态](查询实例状态1.md)
        -   [修改密码](修改密码1.md)

    -   [分片与副本](分片与副本1.md)
        -   [添加副本](添加副本.md)
        -   [删除副本](删除副本.md)

    -   [参数管理](参数管理1.md)
        -   [修改实例配置参数](修改实例配置参数1.md)
        -   [查询实例配置参数](查询实例配置参数1.md)

    -   [备份和恢复](备份与恢复1.md)
        -   [备份指定实例](备份指定实例1.md)
        -   [恢复指定实例](恢复指定实例1.md)
        -   [查询实例备份信息](查询实例备份信息1.md)
        -   [查询实例恢复记录](查询实例恢复记录1.md)
        -   [删除备份文件](删除备份文件1.md)
        -   [获取备份文件下载链接](获取备份文件下载链接1.md)

    -   [标签管理](标签管理1.md)
        -   [查询租户所有标签](查询租户所有标签1.md)
        -   [批量添加或删除标签](批量添加或删除标签1.md)
        -   [查询单个实例标签](查询单个实例标签1.md)

    -   [其他接口](其他接口1.md)
        -   [查询产品规格列表](查询产品规格列表.md)
        -   [查询主维度信息列表](查询主维度信息列表1.md)
        -   [查询单个主维度下子维度监控对象列表](查询单个主维度下子维度监控对象列表1.md)
        -   [查询租户的试用权限](查询租户的试用权限.md)
        -   [查询租户配额](查询租户配额1.md)
        -   [查询维护时间窗时间段](查询维护时间窗时间段1.md)
        -   [查询可用区信息](查询可用区信息1.md)

-   [文档修订记录](文档修订记录.md)


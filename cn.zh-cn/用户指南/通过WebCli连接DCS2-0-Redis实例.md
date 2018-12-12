# 通过WebCli连接Redis 4.x实例<a name="ZH-CN_TOPIC_0144197386"></a>

DCS支持通过管理控制台的WebCli功能连接DCS2.0 Redis实例。只有DCS2.0 Redis实例支持该操作。

>![](public_sys-resources/icon-note.gif) **说明：**   
>本操作仅部分region支持，请以控制台为准。  

## 前提条件<a name="zh-cn_topic_0121496999_section46727122"></a>

只有当Redis 4.x实例处于“运行中”状态，才能执行此操作。

## 操作步骤<a name="zh-cn_topic_0121496999_section321623193712"></a>

1.  登录[分布式缓存服务管理控制台](https://console.huaweicloud.com/dcs)。
2.  在管理控制台左上角单击![](figures/icon-region.png)，选择区域和项目。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >此处请选择与租户的应用服务相同的区域。  

3.  单击左侧菜单栏的“缓存管理”，然后单击“操作”栏下的“更多 \> WebCli”，进入WebCli登录界面，如[图1](#zh-cn_topic_0121496999_fig653622219616)所示。

    **图 1**  进入WebCli登录界面<a name="zh-cn_topic_0121496999_fig653622219616"></a>  
    ![](figures/进入WebCli登录界面.jpg "进入WebCli登录界面")

4.  输入实例的密码进入WebCli，然后选择当前操作的Redis数据库，在命令输入框输入Redis命令，按Enter键执行。

## 相关产品及文档<a name="zh-cn_topic_0121496999_section152613113129"></a>

<a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_table1073594361220"></a>
<table><thead align="left"><tr id="zh-cn_topic_0121496999_zh-cn_topic_0046844820_row197372430123"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p4737243111216"><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p4737243111216"></a><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p4737243111216"></a>相关产品</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p18737144301214"><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p18737144301214"></a><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p18737144301214"></a>相关文档</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0121496999_zh-cn_topic_0046844820_row17371443131210"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p13372054101419"><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p13372054101419"></a><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p13372054101419"></a><a href="https://www.huaweicloud.com/product/dcs.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Redis</a></p>
<p id="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p19548105714519"><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p19548105714519"></a><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p19548105714519"></a><a href="https://www.huaweicloud.com/product/dcsmem.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Memcached</a></p>
<p id="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p8862161219564"><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p8862161219564"></a><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p8862161219564"></a><a href="https://www.huaweicloud.com/product/ecs.html?infodocbz" target="_blank" rel="noopener noreferrer">弹性云服务器 ECS</a></p>
<p id="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p841193941416"><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p841193941416"></a><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p841193941416"></a><a href="http://www.huaweicloud.com/product/vpc.html?infodocbz" target="_blank" rel="noopener noreferrer">虚拟私有云 VPC</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p1381695711471"><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p1381695711471"></a><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p1381695711471"></a><a href="https://support.huaweicloud.com/usermanual-dcs/dcs-zh-ug-180315001.html?infodocbz" target="_blank" rel="noopener noreferrer">购买Redis实例</a></p>
<p id="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p682916370595"><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p682916370595"></a><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p682916370595"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0082114847.html?infodocbz" target="_blank" rel="noopener noreferrer">连接Redis实例</a></p>
<p id="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p16726748155912"><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p16726748155912"></a><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p16726748155912"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0061845451.html?infodocbz" target="_blank" rel="noopener noreferrer">变更缓存实例规格</a></p>
<p id="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p12250886517"><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p12250886517"></a><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p12250886517"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0079545637.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例备份恢复</a></p>
<p id="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p143616360517"><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p143616360517"></a><a name="zh-cn_topic_0121496999_zh-cn_topic_0046844820_p143616360517"></a><a href="https://support.huaweicloud.com/migration-dcs/zh-cn_topic_0078784423.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例数据迁移</a></p>
</td>
</tr>
</tbody>
</table>


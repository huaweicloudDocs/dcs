# 查看Redis集群实例的数据存储统计信息<a name="ZH-CN_TOPIC_0144197413"></a>

用户需要查看Redis集群内各个存储节点的数据存储统计信息，当集群中各存储节点的数据存储分布不均匀时，用户可对实例进行扩容或者清理数据。

当前仅Redis3.0.7版本的DCS集群实例支持查看数据存储统计信息，其他实例类型由于只有一个存储节点，可在实例的基本信息中的已用内存查看，所以不支持。

## 操作步骤<a name="zh-cn_topic_0141903632_section15553246184012"></a>

1.  登录[分布式缓存服务管理控制台](https://console.huaweicloud.com/dcs)。
2.  在管理控制台左上角单击![](figures/icon-region.png)，选择区域和项目。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >此处请选择与租户的应用服务相同的区域。  

3.  单击左侧菜单栏的“缓存管理”，进入实例信息页面。

    “缓存管理”支持通过筛选来查询对应的缓存实例。当前支持的筛选条件为“状态”和“名称”。

4.  选择Redis集群实例，单击该实例的名称，进入该实例的基本信息页面。
5.  单击“节点管理”页签。

    界面显示集群实例中各个节点的数据量信息。

    当集群的节点数据存储容量满时，需要对实例进行扩容，具体扩容操作，请参考[变更缓存实例规格](变更缓存实例规格.md#ZH-CN_TOPIC_0144197341)。


## 相关产品及文档<a name="zh-cn_topic_0141903632_section152613113129"></a>

<a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_table1073594361220"></a>
<table><thead align="left"><tr id="zh-cn_topic_0141903632_zh-cn_topic_0046844820_row197372430123"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p4737243111216"><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p4737243111216"></a><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p4737243111216"></a>相关产品</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p18737144301214"><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p18737144301214"></a><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p18737144301214"></a>相关文档</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0141903632_zh-cn_topic_0046844820_row17371443131210"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p13372054101419"><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p13372054101419"></a><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p13372054101419"></a><a href="https://www.huaweicloud.com/product/dcs.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Redis</a></p>
<p id="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p19548105714519"><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p19548105714519"></a><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p19548105714519"></a><a href="https://www.huaweicloud.com/product/dcsmem.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Memcached</a></p>
<p id="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p8862161219564"><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p8862161219564"></a><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p8862161219564"></a><a href="https://www.huaweicloud.com/product/ecs.html?infodocbz" target="_blank" rel="noopener noreferrer">弹性云服务器 ECS</a></p>
<p id="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p841193941416"><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p841193941416"></a><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p841193941416"></a><a href="http://www.huaweicloud.com/product/vpc.html?infodocbz" target="_blank" rel="noopener noreferrer">虚拟私有云 VPC</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p1381695711471"><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p1381695711471"></a><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p1381695711471"></a><a href="https://support.huaweicloud.com/usermanual-dcs/dcs-zh-ug-180315001.html?infodocbz" target="_blank" rel="noopener noreferrer">购买Redis实例</a></p>
<p id="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p682916370595"><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p682916370595"></a><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p682916370595"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0082114847.html?infodocbz" target="_blank" rel="noopener noreferrer">连接Redis实例</a></p>
<p id="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p16726748155912"><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p16726748155912"></a><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p16726748155912"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0061845451.html?infodocbz" target="_blank" rel="noopener noreferrer">变更缓存实例规格</a></p>
<p id="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p12250886517"><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p12250886517"></a><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p12250886517"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0079545637.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例备份恢复</a></p>
<p id="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p143616360517"><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p143616360517"></a><a name="zh-cn_topic_0141903632_zh-cn_topic_0046844820_p143616360517"></a><a href="https://support.huaweicloud.com/migration-dcs/zh-cn_topic_0078784423.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例数据迁移</a></p>
</td>
</tr>
</tbody>
</table>


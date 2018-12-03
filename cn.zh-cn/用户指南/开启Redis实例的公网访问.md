# 开启Redis实例的公网访问<a name="ZH-CN_TOPIC_0101855285"></a>

用户需要通过公网地址访问Redis实例，可开启实例的公网访问功能。

>![](public_sys-resources/icon-note.gif) **说明：**   
>-   开启公网访问时，只能通过SSL方式来访问Redis实例，建议使用前先下载CA证书，并使用CA证书来验证DCS缓存实例的证书，以提高安全性。  
>-   主备或集群类型的Redis实例在因故障进行切换过程中，通过公网访问可能会失败，大约1分钟左右，请稍后再重试。  
>-   免密模式的Redis实例不支持开启公网访问功能。  
>-   开启Redis实例的公网访问后，可参考[公网连接Redis实例](公网连接Redis实例.md)连接实例。  
>-   公网访问与VPC内访问相比，可能存在网络丢包和抖动等情况，且访问时延有所增加，因此建议仅在业务开发测试阶段开启公网访问Redis实例。  

## 前提条件<a name="section34216874"></a>

已成功创建密码模式的Redis实例，且该实例未开启公网访问功能。

## 操作步骤<a name="section194222417283"></a>

1.  登录[管理控制台](https://console.huaweicloud.com/?locale=zh-cn)。
2.  在管理控制台左上角单击![](figures/zh-cn_image_0101999787.gif)图标，选择区域和项目。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >此处请选择与租户的应用服务相同的区域。  

3.  单击页面上方的“服务列表”，选择“数据库 \> 分布式缓存服务”，进入分布式缓存服务信息页面。
4.  单击左侧菜单栏的“缓存管理”。
5.  单击对应Redis实例的名称，进入该实例的基本信息页面。
6.  单击“公网访问”右侧的![](figures/zh-cn_image_0102010651.png)，打开公网访问开关。
7.  从“弹性IP地址”下拉列表中选择一个弹性IP。
8.  根据需要选择是否开启SSL加密功能。

    建议使用SSL加密Redis客户端与DCS实例之间的传输通道，确保数据传输安全。

    公网访问开启后，该参数不允许再进行修改。

9.  单击“确认”，开启公网访问功能。

    开启公网访问功能大约需要1~2分钟，请耐心等待。

    当前页面会自动跳转到“后台任务管理”页签，并显示当前任务的操作进度。任务状态为“Succeeded”，表示开启公网访问成功。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   如果“弹性IP地址”下拉列表有值，可单击“查看弹性IP”，系统跳转到虚拟私有云的弹性IP详情界面，可以查看弹性IP的详细信息。  
    >-   如果“弹性IP地址”下拉列表没有值，可单击“创建弹性IP”，系统跳转到虚拟私有云的弹性IP创建界面，可以申请一个新的弹性IP。  
    >-   选定的弹性IP地址如果已经被使用（例如，被其他DCS服务实例绑定，或被其他服务使用），会绑定失败。  


## 相关产品及文档<a name="section152613113129"></a>

<a name="zh-cn_topic_0046844820_table1073594361220"></a>
<table><thead align="left"><tr id="zh-cn_topic_0046844820_row197372430123"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0046844820_p4737243111216"><a name="zh-cn_topic_0046844820_p4737243111216"></a><a name="zh-cn_topic_0046844820_p4737243111216"></a>相关产品</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0046844820_p18737144301214"><a name="zh-cn_topic_0046844820_p18737144301214"></a><a name="zh-cn_topic_0046844820_p18737144301214"></a>相关文档</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0046844820_row17371443131210"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0046844820_p13372054101419"><a name="zh-cn_topic_0046844820_p13372054101419"></a><a name="zh-cn_topic_0046844820_p13372054101419"></a><a href="https://www.huaweicloud.com/product/dcs.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Redis</a></p>
<p id="zh-cn_topic_0046844820_p19548105714519"><a name="zh-cn_topic_0046844820_p19548105714519"></a><a name="zh-cn_topic_0046844820_p19548105714519"></a><a href="https://www.huaweicloud.com/product/dcsmem.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Memcached</a></p>
<p id="zh-cn_topic_0046844820_p8862161219564"><a name="zh-cn_topic_0046844820_p8862161219564"></a><a name="zh-cn_topic_0046844820_p8862161219564"></a><a href="https://www.huaweicloud.com/product/ecs.html?infodocbz" target="_blank" rel="noopener noreferrer">弹性云服务器 ECS</a></p>
<p id="zh-cn_topic_0046844820_p841193941416"><a name="zh-cn_topic_0046844820_p841193941416"></a><a name="zh-cn_topic_0046844820_p841193941416"></a><a href="http://www.huaweicloud.com/product/vpc.html?infodocbz" target="_blank" rel="noopener noreferrer">虚拟私有云 VPC</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0046844820_p1381695711471"><a name="zh-cn_topic_0046844820_p1381695711471"></a><a name="zh-cn_topic_0046844820_p1381695711471"></a><a href="https://support.huaweicloud.com/usermanual-dcs/dcs-zh-ug-180315001.html?infodocbz" target="_blank" rel="noopener noreferrer">购买Redis实例</a></p>
<p id="zh-cn_topic_0046844820_p682916370595"><a name="zh-cn_topic_0046844820_p682916370595"></a><a name="zh-cn_topic_0046844820_p682916370595"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0082114847.html?infodocbz" target="_blank" rel="noopener noreferrer">连接Redis实例</a></p>
<p id="zh-cn_topic_0046844820_p16726748155912"><a name="zh-cn_topic_0046844820_p16726748155912"></a><a name="zh-cn_topic_0046844820_p16726748155912"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0061845451.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例扩容</a></p>
<p id="zh-cn_topic_0046844820_p12250886517"><a name="zh-cn_topic_0046844820_p12250886517"></a><a name="zh-cn_topic_0046844820_p12250886517"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0079545637.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例备份恢复</a></p>
<p id="zh-cn_topic_0046844820_p143616360517"><a name="zh-cn_topic_0046844820_p143616360517"></a><a name="zh-cn_topic_0046844820_p143616360517"></a><a href="https://support.huaweicloud.com/migration-dcs/zh-cn_topic_0078784423.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例数据迁移</a></p>
</td>
</tr>
</tbody>
</table>


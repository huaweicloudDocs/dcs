# 开启Redis实例的公网访问<a name="dcs-zh-ug-180314001"></a>

您需要通过公网地址访问Redis实例，可开启实例的公网访问功能。

>![](public_sys-resources/icon-note.gif) **说明：**   
>-   通过公网SSL加密方式访问Redis实例时，建议使用前先下载CA证书，并使用CA证书来验证DCS缓存实例的证书，以提高安全性，可参考[公网连接Redis实例](公网连接Redis实例.md)连接实例。  
>-   通过公网直接（未开启SSL加密）访问实例时，请直接访问Redis实例的弹性公网IP与6379端口，不需下载证书，也不需要在客户端安装Stunnel工具。  
>-   推荐使用SSL加密Redis客户端与DCS实例之间的传输通道，确保数据传输安全。  
>-   主备或集群类型的Redis实例在因故障进行切换过程中，通过公网访问可能会失败，大约1分钟左右，请稍后再重试。  
>-   免密模式的Redis实例不支持开启公网访问功能。  
>-   公网访问与VPC内访问相比，可能存在网络丢包和抖动等情况，且访问时延有所增加，因此建议仅在业务开发测试阶段开启公网访问Redis实例。  

## 前提条件<a name="section34216874"></a>

已成功创建密码模式的Redis实例，且该实例未开启公网访问功能。

## 操作步骤<a name="section194222417283"></a>

1.  登录[分布式缓存服务管理控制台](https://console.huaweicloud.com/dcs)。
2.  在管理控制台左上角单击![](figures/icon-region.png)，选择区域和项目。
3.  单击左侧菜单栏的“缓存管理”。
4.  单击对应Redis实例的名称，进入该实例的基本信息页面。
5.  单击“公网访问”右侧的![](figures/icon-publicnetwork.png)，打开公网访问开关。
6.  从“弹性IP地址”下拉列表中选择一个弹性IP。
7.  （可选）根据需要选择是否开启SSL加密功能。

    建议使用SSL加密Redis客户端与DCS实例之间的传输通道，确保数据传输安全。

    公网访问开启后，该参数不允许再进行修改。

8.  单击“确认”，开启公网访问功能。

    开启公网访问功能大约需要1\~2分钟，请耐心等待。

    当前页面会自动跳转到“后台任务管理”页签，并显示当前任务的操作进度。任务状态为“Succeeded”，表示开启公网访问成功。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   如果“弹性IP地址”下拉列表有值，可单击“查看弹性IP”，系统跳转到虚拟私有云的弹性IP详情界面，可以查看弹性IP的详细信息。  
    >-   如果“弹性IP地址”下拉列表没有值，可单击“创建弹性IP”，系统跳转到虚拟私有云的弹性IP创建界面，可以申请一个新的弹性IP。  
    >-   选定的弹性IP地址如果已经被使用（例如，被其他DCS服务实例绑定，或被其他服务使用），会绑定失败。  


## 相关产品及文档<a name="section152613113129"></a>

<a name="td475c361406b4841ba0faa98fc782ed5"></a>
<table><thead align="left"><tr id="rb27d733848ce4e7a9386965803595f1b"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="a5cc8ae3032d8416f9696b6f2a50d82d4"><a name="a5cc8ae3032d8416f9696b6f2a50d82d4"></a><a name="a5cc8ae3032d8416f9696b6f2a50d82d4"></a>相关产品</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="ad3b8309045294369bdb9a006daef8f00"><a name="ad3b8309045294369bdb9a006daef8f00"></a><a name="ad3b8309045294369bdb9a006daef8f00"></a>相关文档</p>
</th>
</tr>
</thead>
<tbody><tr id="re4588baf45714b4f80c021cca1290879"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="a8c37acc50b884e0b9a71051bcb9179b4"><a name="a8c37acc50b884e0b9a71051bcb9179b4"></a><a name="a8c37acc50b884e0b9a71051bcb9179b4"></a><a href="https://www.huaweicloud.com/product/dcs.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Redis</a></p>
<p id="a11d9314698354304b9a9e9cb1270b5c9"><a name="a11d9314698354304b9a9e9cb1270b5c9"></a><a name="a11d9314698354304b9a9e9cb1270b5c9"></a><a href="https://www.huaweicloud.com/product/dcsmem.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Memcached</a></p>
<p id="abeaed75bd99c4aeeb5ef850c82a274f2"><a name="abeaed75bd99c4aeeb5ef850c82a274f2"></a><a name="abeaed75bd99c4aeeb5ef850c82a274f2"></a><a href="https://www.huaweicloud.com/product/ecs.html?infodocbz" target="_blank" rel="noopener noreferrer">弹性云服务器 ECS</a></p>
<p id="zh-cn_topic_0046844820_p841193941416"><a name="zh-cn_topic_0046844820_p841193941416"></a><a name="zh-cn_topic_0046844820_p841193941416"></a><a href="http://www.huaweicloud.com/product/vpc.html?infodocbz" target="_blank" rel="noopener noreferrer">虚拟私有云 VPC</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="a0c4ea7b976b745079231aeb676430680"><a name="a0c4ea7b976b745079231aeb676430680"></a><a name="a0c4ea7b976b745079231aeb676430680"></a><a href="https://support.huaweicloud.com/usermanual-dcs/dcs-zh-ug-180315001.html?infodocbz" target="_blank" rel="noopener noreferrer">购买Redis实例</a></p>
<p id="zh-cn_topic_0046844820_p682916370595"><a name="zh-cn_topic_0046844820_p682916370595"></a><a name="zh-cn_topic_0046844820_p682916370595"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0082114847.html?infodocbz" target="_blank" rel="noopener noreferrer">连接Redis实例</a></p>
<p id="a3d146c9e41904a09b098cc34a53b5652"><a name="a3d146c9e41904a09b098cc34a53b5652"></a><a name="a3d146c9e41904a09b098cc34a53b5652"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0061845451.html?infodocbz" target="_blank" rel="noopener noreferrer">变更缓存实例规格</a></p>
<p id="zh-cn_topic_0046844820_p12250886517"><a name="zh-cn_topic_0046844820_p12250886517"></a><a name="zh-cn_topic_0046844820_p12250886517"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0079545637.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例备份恢复</a></p>
<p id="zh-cn_topic_0046844820_p143616360517"><a name="zh-cn_topic_0046844820_p143616360517"></a><a name="zh-cn_topic_0046844820_p143616360517"></a><a href="https://support.huaweicloud.com/migration-dcs/zh-cn_topic_0078784423.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例数据迁移</a></p>
</td>
</tr>
</tbody>
</table>


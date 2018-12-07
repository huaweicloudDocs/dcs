# 开启Memcached实例的免密访问<a name="ZH-CN_TOPIC_0144197434"></a>

用户需要通过免用户名和密码访问模式连接Memcached实例，可通过开启Memcached实例的免密访问功能，清空Memcached实例的用户名和密码。

>![](public_sys-resources/icon-note.gif) **说明：**   
>-   只有处于“运行中”状态的Memcached实例支持开启免密访问。  
>-   开启免密访问需要通过已登记的手机号码获取验证码，请确保已成功登记手机号码。  
>-   Memcached文本协议不支持用户名密码认证，若需要使用文本协议连接Memcached实例，必须开启实例的免密访问。  

## 前提条件<a name="zh-cn_topic_0083516645_section34216874"></a>

已成功创建Memcached实例。

## 操作步骤<a name="zh-cn_topic_0083516645_section166215281808"></a>

1.  登录[分布式缓存服务管理控制台](https://console.huaweicloud.com/dcs)。
2.  在管理控制台左上角单击![](figures/icon-region.png)，选择区域和项目。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >此处请选择与租户的应用服务相同的区域。  

3.  单击左侧菜单栏的“缓存管理”。
4.  在需要开启免密访问的Memcached实例右侧，单击“操作”栏下的“更多 \> 免密访问”。
5.  系统弹出“免密访问设置”对话框，打开“免密访问”开关。
6.  单击“点击获取验证码”，输入验证码。单击“确定”完成免密访问设置。

    免密访问设置成功，界面提示实例免密访问成功。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >-   若用户没有登记手机号码，需要先成功登记手机号码后再进行免密访问操作。  
    >-   验证码有效期默认为10分钟，10分钟后请重新获取验证码。  


## 相关产品及文档<a name="zh-cn_topic_0083516645_section152613113129"></a>

<a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_table1073594361220"></a>
<table><thead align="left"><tr id="zh-cn_topic_0083516645_zh-cn_topic_0046844820_row197372430123"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p4737243111216"><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p4737243111216"></a><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p4737243111216"></a>相关产品</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p18737144301214"><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p18737144301214"></a><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p18737144301214"></a>相关文档</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0083516645_zh-cn_topic_0046844820_row17371443131210"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p13372054101419"><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p13372054101419"></a><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p13372054101419"></a><a href="https://www.huaweicloud.com/product/dcs.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Redis</a></p>
<p id="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p19548105714519"><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p19548105714519"></a><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p19548105714519"></a><a href="https://www.huaweicloud.com/product/dcsmem.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Memcached</a></p>
<p id="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p8862161219564"><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p8862161219564"></a><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p8862161219564"></a><a href="https://www.huaweicloud.com/product/ecs.html?infodocbz" target="_blank" rel="noopener noreferrer">弹性云服务器 ECS</a></p>
<p id="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p841193941416"><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p841193941416"></a><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p841193941416"></a><a href="http://www.huaweicloud.com/product/vpc.html?infodocbz" target="_blank" rel="noopener noreferrer">虚拟私有云 VPC</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p1381695711471"><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p1381695711471"></a><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p1381695711471"></a><a href="https://support.huaweicloud.com/usermanual-dcs/dcs-zh-ug-180315001.html?infodocbz" target="_blank" rel="noopener noreferrer">购买Redis实例</a></p>
<p id="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p682916370595"><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p682916370595"></a><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p682916370595"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0082114847.html?infodocbz" target="_blank" rel="noopener noreferrer">连接Redis实例</a></p>
<p id="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p16726748155912"><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p16726748155912"></a><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p16726748155912"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0061845451.html?infodocbz" target="_blank" rel="noopener noreferrer">变更缓存实例规格</a></p>
<p id="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p12250886517"><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p12250886517"></a><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p12250886517"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0079545637.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例备份恢复</a></p>
<p id="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p143616360517"><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p143616360517"></a><a name="zh-cn_topic_0083516645_zh-cn_topic_0046844820_p143616360517"></a><a href="https://support.huaweicloud.com/migration-dcs/zh-cn_topic_0078784423.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例数据迁移</a></p>
</td>
</tr>
</tbody>
</table>


# 购买DCS2.0 Redis实例<a name="ZH-CN_TOPIC_0102488711"></a>

DCS支持2.0版本的Redis实例，采用裸金属部署，支持用户自定义内存规格和自定义特性，您可以根据业务需要购买相应计算能力和存储空间的DCS2.0 Redis实例。

>![](public_sys-resources/icon-note.gif) **说明：**   
>本操作仅部分region支持，请以控制台为准。  

## 前提条件<a name="section62331491"></a>

DCS2.0 Redis实例运行于虚拟私有云。申请DCS2.0 Redis实例前，需保证有可用的虚拟私有云，并且已配置好安全组与子网。

创建虚拟私有云、安全组以及子网的方法，请参见[环境准备](环境准备.md)或者《虚拟私有云用户指南》。

## 操作步骤<a name="section24112512"></a>

1.  登录[管理控制台](https://console.huaweicloud.com/?locale=zh-cn)。
2.  在管理控制台左上角单击![](figures/zh-cn_image_0102488718.gif)图标，选择区域和项目。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >此处请选择与租户的应用服务相同的区域。  

3.  单击页面上方的“服务列表”，选择“数据库 \> 分布式缓存服务”，进入分布式缓存服务信息页面。
4.  单击“购买DCS2.0缓存实例”，进入购买页面。
5.  选择“计费模式”为“按需付费”。
6.  填写DCS2.0 Redis实例的参数。参数说明如[表1](#table5373863818728)所示。

    **表 1**  参数说明

    <a name="table5373863818728"></a>
    <table><thead align="left"><tr id="row5933206518728"><th class="cellrowborder" valign="top" width="17%" id="mcps1.2.3.1.1"><p id="p5858956018728"><a name="p5858956018728"></a><a name="p5858956018728"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="83%" id="mcps1.2.3.1.2"><p id="p4813390218728"><a name="p4813390218728"></a><a name="p4813390218728"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="row153681361123"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="p53681836827"><a name="p53681836827"></a><a name="p53681836827"></a>区域</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="p183684366219"><a name="p183684366219"></a><a name="p183684366219"></a>DCS服务所在区域，可在页面左上角切换区域。</p>
    </td>
    </tr>
    <tr id="row113682295213"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="p4866108918728"><a name="p4866108918728"></a><a name="p4866108918728"></a>可用区</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="p4923409718728"><a name="p4923409718728"></a><a name="p4923409718728"></a>可选择的不同可用分区。</p>
    <div class="note" id="note28642393311"><a name="note28642393311"></a><a name="note28642393311"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul8605141963712"></a><a name="ul8605141963712"></a><ul id="ul8605141963712"><li>当主备或者集群DCS2.0 Redis实例进行跨可用分区部署时，如果其中一个可用分区故障，另一个可用分区的节点不受影响。备节点会自动升级为主节点，对外提供服务，从而提供更高的容灾能力。</li><li>由于实例跨可用分区部署时网络访问效率略低于部署在同一可用分区内，因此DCS缓存实例跨可用分区部署时，主备节点之间同步效率会略有降低。</li></ul>
    </div></div>
    </td>
    </tr>
    <tr id="row5850290918728"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="p4116798118728"><a name="p4116798118728"></a><a name="p4116798118728"></a>名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="p3494740012058"><a name="p3494740012058"></a><a name="p3494740012058"></a>DCS2.0 Redis实例的名称。</p>
    <a name="ul665662631212"></a><a name="ul665662631212"></a><ul id="ul665662631212"><li>名称不能为空。</li><li>只能以英文字母开头。</li><li>长度为4到64位的字符串。</li><li>仅包含英文字母、数字、下划线（_）和中划线（-）。</li></ul>
    </td>
    </tr>
    <tr id="row3124158141414"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="p1012418171418"><a name="p1012418171418"></a><a name="p1012418171418"></a>实例配置</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="p21253811419"><a name="p21253811419"></a><a name="p21253811419"></a>DCS2.0 Redis实例的规格和特性。</p>
    <p id="p193861037151414"><a name="p193861037151414"></a><a name="p193861037151414"></a>拖动滚动条可自定义选择实例的规格，可选择的规格范围如下：</p>
    <a name="ul823161620156"></a><a name="ul823161620156"></a><ul id="ul823161620156"><li>单机支持128MB、256MB、512MB、1GB~64GB（以1G为步长增长）。</li><li>主备支持1GB~64GB，以1G为步长增长。</li><li>集群支持64GB、128GB、256GB、512GB、1024GB。</li></ul>
    <div class="note" id="note210413923715"><a name="note210413923715"></a><a name="note210413923715"></a><span class="notetitle"> 说明： </span><div class="notebody"><a name="ul14420710381"></a><a name="ul14420710381"></a><ul id="ul14420710381"><li>申请大于规格8GB的实例，需要提交工单。工单申请通过后，才能选择大于8GB的规格。</li><li>如果实例的规格大于用户的可用配额，需要先提交工单申请扩大配额。</li></ul>
    </div></div>
    </td>
    </tr>
    <tr id="row3119715618728"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="p5533269218728"><a name="p5533269218728"></a><a name="p5533269218728"></a>虚拟私有云</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="p5276310218728"><a name="p5276310218728"></a><a name="p5276310218728"></a>已创建的虚拟私有云。</p>
    <a name="ul353316111561"></a><a name="ul353316111561"></a><ul id="ul353316111561"><li>虚拟私有云可以为您的DCS缓存实例构建隔离的、用户自主配置和管理的虚拟网络环境。</li><li>单击“查看虚拟私有云”，系统跳转到虚拟私有云界面，选择相应的虚拟私有云，可以查看安全组的出方向规则和入方向规则。</li></ul>
    </td>
    </tr>
    <tr id="row4851808618728"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="p184411618728"><a name="p184411618728"></a><a name="p184411618728"></a>子网</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="p1515573018728"><a name="p1515573018728"></a><a name="p1515573018728"></a>子网名称与IP地址段。</p>
    </td>
    </tr>
    <tr id="row196181012465"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="p49541115154613"><a name="p49541115154613"></a><a name="p49541115154613"></a>安全组</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="p395471584614"><a name="p395471584614"></a><a name="p395471584614"></a>已创建的安全组。</p>
    <p id="p35999277569"><a name="p35999277569"></a><a name="p35999277569"></a>安全组是一组对弹性云服务器的访问规则的集合，为同一个VPC内具有相同安全保护需求并相互信任的弹性云服务器提供访问策略。</p>
    </td>
    </tr>
    <tr id="row6515734618728"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="p3400959418728"><a name="p3400959418728"></a><a name="p3400959418728"></a>密码</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="p204469959544"><a name="p204469959544"></a><a name="p204469959544"></a>连接DCS2.0 Redis实例的密码。包括密码及确认密码。</p>
    <div class="note" id="note14021145182415"><a name="note14021145182415"></a><a name="note14021145182415"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="p1567182319618"><a name="p1567182319618"></a><a name="p1567182319618"></a>DCS服务出于安全考虑，在密码访问模式下，连接使用DCS2.0 Redis实例时，需要先进行密码认证。请妥善保存密码，并定期更新密码。</p>
    </div></div>
    <p id="p1205499104250"><a name="p1205499104250"></a><a name="p1205499104250"></a>DCS2.0 Redis实例密码必须满足以下复杂度要求：</p>
    <a name="ul65262816102030"></a><a name="ul65262816102030"></a><ul id="ul65262816102030"><li>密码不能为空。</li><li>输入长度为6到32位的字符串。</li><li>必须包含如下四种字符中的两种组合：<a name="ul1443183119407"></a><a name="ul1443183119407"></a><ul id="ul1443183119407"><li>小写字母</li><li>大写字母</li><li>数字</li><li>特殊字符包括（`~!@#$^&amp;*()-_=+\|{}:,&lt;.&gt;/?）</li></ul>
    </li></ul>
    </td>
    </tr>
    <tr id="row175574015417"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="p185589055411"><a name="p185589055411"></a><a name="p185589055411"></a>时间窗</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="p2558130125418"><a name="p2558130125418"></a><a name="p2558130125418"></a>运维操作时间。</p>
    <p id="p538867566"><a name="p538867566"></a><a name="p538867566"></a>用户可选择22:00-02:00、02:00-06:00、06:00-10:00、10:00-14:00、14:00-18:00和18:00-22:00，在选择的时间段内，服务运维可对实例节点进行维护操作。</p>
    </td>
    </tr>
    </tbody>
    </table>

7.  填写完上述信息后，单击“立即购买”，开始创建实例。

    系统跳转到“缓存管理”页面，用户可查看并管理自己的缓存实例。

    1.  创建DCS2.0 Redis实例大约需要5到15分钟。
    2.  DCS2.0 Redis实例创建成功后，默认“状态”为“运行中”。
    3.  如果创建DCS2.0 Redis实例失败，可参考[删除缓存实例](删除缓存实例.md)，删除创建失败的实例，然后重新购买。如果重新购买仍然失败，请联系客服。


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


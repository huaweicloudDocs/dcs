# 购买IMDG实例<a name="ZH-CN_TOPIC_0144197332"></a>

购买IMDG实例支持“按需付费”。您可以根据业务需要购买相应计算能力和存储空间的IMDG实例。

>![](public_sys-resources/icon-note.gif) **说明：**   
>本操作仅部分region支持，请以控制台为准。  

## 前提条件<a name="zh-cn_topic_0102039831_section62331491"></a>

IMDG实例运行于虚拟私有云。申请IMDG实例前，需保证有可用的虚拟私有云，并且已配置好安全组与子网。

创建虚拟私有云、安全组以及子网的方法，请参见[环境准备](环境准备.md#ZH-CN_TOPIC_0144197285)或者《虚拟私有云用户指南》。

## 操作步骤<a name="zh-cn_topic_0102039831_section24112512"></a>

1.  登录[分布式缓存服务管理控制台](https://console.huaweicloud.com/dcs)。
2.  在管理控制台左上角单击![](figures/icon-region.png)，选择区域和项目。

    >![](public_sys-resources/icon-note.gif) **说明：**   
    >此处请选择与租户的应用服务相同的区域。  

3.  单击左侧菜单栏的“缓存管理”进入“缓存管理”页面。
4.  单击“购买缓存实例”，进入购买页面。
5.  选择“计费模式”，单击“按需付费”。
6.  填写IMDG实例的参数。参数说明如[表1](#zh-cn_topic_0102039831_table5373863818728)所示。

    **表 1**  参数说明

    <a name="zh-cn_topic_0102039831_table5373863818728"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0102039831_row5933206518728"><th class="cellrowborder" valign="top" width="17%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0102039831_p5858956018728"><a name="zh-cn_topic_0102039831_p5858956018728"></a><a name="zh-cn_topic_0102039831_p5858956018728"></a>参数</p>
    </th>
    <th class="cellrowborder" valign="top" width="83%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0102039831_p4813390218728"><a name="zh-cn_topic_0102039831_p4813390218728"></a><a name="zh-cn_topic_0102039831_p4813390218728"></a>说明</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0102039831_row153681361123"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0102039831_p53681836827"><a name="zh-cn_topic_0102039831_p53681836827"></a><a name="zh-cn_topic_0102039831_p53681836827"></a>区域</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0102039831_p183684366219"><a name="zh-cn_topic_0102039831_p183684366219"></a><a name="zh-cn_topic_0102039831_p183684366219"></a>DCS服务所在区域，可在页面左上角切换区域。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0102039831_row5850290918728"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0102039831_p4116798118728"><a name="zh-cn_topic_0102039831_p4116798118728"></a><a name="zh-cn_topic_0102039831_p4116798118728"></a>名称</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0102039831_p3494740012058"><a name="zh-cn_topic_0102039831_p3494740012058"></a><a name="zh-cn_topic_0102039831_p3494740012058"></a>IMDG实例的名称。</p>
    <a name="zh-cn_topic_0102039831_ul665662631212"></a><a name="zh-cn_topic_0102039831_ul665662631212"></a><ul id="zh-cn_topic_0102039831_ul665662631212"><li>名称不能为空。</li><li>只能以英文字母开头。</li><li>长度为4到64位的字符串。</li><li>仅包含英文字母、数字、下划线（_）和中划线（-）。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0102039831_row1286332818728"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0102039831_p5676413618728"><a name="zh-cn_topic_0102039831_p5676413618728"></a><a name="zh-cn_topic_0102039831_p5676413618728"></a>描述</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0102039831_p3449229518728"><a name="zh-cn_topic_0102039831_p3449229518728"></a><a name="zh-cn_topic_0102039831_p3449229518728"></a>对IMDG实例的描述信息。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0102039831_row3606388018728"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0102039831_p110575018728"><a name="zh-cn_topic_0102039831_p110575018728"></a><a name="zh-cn_topic_0102039831_p110575018728"></a>缓存类型</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0102039831_p2245694518728"><a name="zh-cn_topic_0102039831_p2245694518728"></a><a name="zh-cn_topic_0102039831_p2245694518728"></a>缓存的引擎类型，单击选择“IMDG”。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0102039831_row55532325104357"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0102039831_p1824480104357"><a name="zh-cn_topic_0102039831_p1824480104357"></a><a name="zh-cn_topic_0102039831_p1824480104357"></a>实例类型</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0102039831_p13565167104357"><a name="zh-cn_topic_0102039831_p13565167104357"></a><a name="zh-cn_topic_0102039831_p13565167104357"></a>缓存实例的类型。IMDG缓存实例支持“单机”和“集群”。</p>
    <div class="note" id="zh-cn_topic_0102039831_note1771175816202"><a name="zh-cn_topic_0102039831_note1771175816202"></a><a name="zh-cn_topic_0102039831_note1771175816202"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0102039831_p793431718365"><a name="zh-cn_topic_0102039831_p793431718365"></a><a name="zh-cn_topic_0102039831_p793431718365"></a>集群实例不支持通过VPC对等连接的方式进行跨VPC访问。</p>
    </div></div>
    <p id="zh-cn_topic_0102039831_p5105963408"><a name="zh-cn_topic_0102039831_p5105963408"></a><a name="zh-cn_topic_0102039831_p5105963408"></a>请根据实际需要选择实例类型，不同实例类型适用不同的业务场景，具体参考<a href="http://support.huaweicloud.com/productdesc-dcs/zh-cn_topic_0088428506.html">实例缓存类型说明</a>。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0102039831_row1259118918276"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0102039831_p4866108918728"><a name="zh-cn_topic_0102039831_p4866108918728"></a><a name="zh-cn_topic_0102039831_p4866108918728"></a>可用区</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0102039831_p4923409718728"><a name="zh-cn_topic_0102039831_p4923409718728"></a><a name="zh-cn_topic_0102039831_p4923409718728"></a>可选择的不同可用分区。</p>
    <div class="note" id="zh-cn_topic_0102039831_note28642393311"><a name="zh-cn_topic_0102039831_note28642393311"></a><a name="zh-cn_topic_0102039831_note28642393311"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0102039831_p824037173412"><a name="zh-cn_topic_0102039831_p824037173412"></a><a name="zh-cn_topic_0102039831_p824037173412"></a>当集群IMDG实例进行跨可用分区部署时，如果其中一个可用分区故障，另一个可用分区的节点不受影响。备节点会自动升级为主节点，对外提供服务，从而提供更高的容灾能力。</p>
    </div></div>
    </td>
    </tr>
    <tr id="zh-cn_topic_0102039831_row135215552378"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0102039831_p653155143714"><a name="zh-cn_topic_0102039831_p653155143714"></a><a name="zh-cn_topic_0102039831_p653155143714"></a>跨可用区部署</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0102039831_p125325517376"><a name="zh-cn_topic_0102039831_p125325517376"></a><a name="zh-cn_topic_0102039831_p125325517376"></a>跨可用分区部署的开关。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0102039831_row6747134473311"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0102039831_p132885014331"><a name="zh-cn_topic_0102039831_p132885014331"></a><a name="zh-cn_topic_0102039831_p132885014331"></a>备可用区</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0102039831_p3772173919354"><a name="zh-cn_topic_0102039831_p3772173919354"></a><a name="zh-cn_topic_0102039831_p3772173919354"></a>备可用分区。</p>
    <div class="note" id="zh-cn_topic_0102039831_note8573145918354"><a name="zh-cn_topic_0102039831_note8573145918354"></a><a name="zh-cn_topic_0102039831_note8573145918354"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0102039831_p184777915362"><a name="zh-cn_topic_0102039831_p184777915362"></a><a name="zh-cn_topic_0102039831_p184777915362"></a>只有当前存在多个可用分区，并且用户选择的实例类型为“集群”时，才会显示该参数。</p>
    </div></div>
    </td>
    </tr>
    <tr id="zh-cn_topic_0102039831_row5088731918728"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0102039831_p5731035618728"><a name="zh-cn_topic_0102039831_p5731035618728"></a><a name="zh-cn_topic_0102039831_p5731035618728"></a>实例规格</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0102039831_p12782887115750"><a name="zh-cn_topic_0102039831_p12782887115750"></a><a name="zh-cn_topic_0102039831_p12782887115750"></a>IMDG实例的规格。</p>
    <div class="p" id="zh-cn_topic_0102039831_p132701127173718"><a name="zh-cn_topic_0102039831_p132701127173718"></a><a name="zh-cn_topic_0102039831_p132701127173718"></a>IMDG类型的缓存实例规格如下：<a name="zh-cn_topic_0102039831_ul6752102312348"></a><a name="zh-cn_topic_0102039831_ul6752102312348"></a><ul id="zh-cn_topic_0102039831_ul6752102312348"><li>单机实例规格支持2GB、4GB和8GB。</li><li>集群实例规格支持16GB。</li></ul>
    </div>
    <p id="zh-cn_topic_0102039831_p195594514220"><a name="zh-cn_topic_0102039831_p195594514220"></a><a name="zh-cn_topic_0102039831_p195594514220"></a>用户默认配额为最多创建5个实例，总内存不超过400GB。</p>
    <p id="zh-cn_topic_0102039831_p13895221123619"><a name="zh-cn_topic_0102039831_p13895221123619"></a><a name="zh-cn_topic_0102039831_p13895221123619"></a>用户如需增加配额，单击规格下方的“申请扩大配额”，即可跳转到工单管理界面提交工单，增加配额。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0102039831_row3119715618728"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0102039831_p5533269218728"><a name="zh-cn_topic_0102039831_p5533269218728"></a><a name="zh-cn_topic_0102039831_p5533269218728"></a>虚拟私有云</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0102039831_p5276310218728"><a name="zh-cn_topic_0102039831_p5276310218728"></a><a name="zh-cn_topic_0102039831_p5276310218728"></a>已创建的虚拟私有云。</p>
    <a name="zh-cn_topic_0102039831_ul353316111561"></a><a name="zh-cn_topic_0102039831_ul353316111561"></a><ul id="zh-cn_topic_0102039831_ul353316111561"><li>虚拟私有云可以为您的DCS缓存实例构建隔离的、用户自主配置和管理的虚拟网络环境。</li><li>单击“查看虚拟私有云”，系统跳转到虚拟私有云界面，选择相应的虚拟私有云，可以查看安全组的出方向规则和入方向规则。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0102039831_row4851808618728"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0102039831_p184411618728"><a name="zh-cn_topic_0102039831_p184411618728"></a><a name="zh-cn_topic_0102039831_p184411618728"></a>子网</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0102039831_p1515573018728"><a name="zh-cn_topic_0102039831_p1515573018728"></a><a name="zh-cn_topic_0102039831_p1515573018728"></a>子网名称与IP地址段。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0102039831_row196181012465"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0102039831_p49541115154613"><a name="zh-cn_topic_0102039831_p49541115154613"></a><a name="zh-cn_topic_0102039831_p49541115154613"></a>安全组</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0102039831_p395471584614"><a name="zh-cn_topic_0102039831_p395471584614"></a><a name="zh-cn_topic_0102039831_p395471584614"></a>已创建的安全组。</p>
    <p id="zh-cn_topic_0102039831_p35999277569"><a name="zh-cn_topic_0102039831_p35999277569"></a><a name="zh-cn_topic_0102039831_p35999277569"></a>安全组是一组对弹性云服务器的访问规则的集合，为同一个VPC内具有相同安全保护需求并相互信任的弹性云服务器提供访问策略。</p>
    </td>
    </tr>
    <tr id="zh-cn_topic_0102039831_row18591615105213"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0102039831_p2860415105211"><a name="zh-cn_topic_0102039831_p2860415105211"></a><a name="zh-cn_topic_0102039831_p2860415105211"></a>用户名</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0102039831_p31871344145714"><a name="zh-cn_topic_0102039831_p31871344145714"></a><a name="zh-cn_topic_0102039831_p31871344145714"></a>连接IMDG实例的用户名。</p>
    <a name="zh-cn_topic_0102039831_ul3930103195714"></a><a name="zh-cn_topic_0102039831_ul3930103195714"></a><ul id="zh-cn_topic_0102039831_ul3930103195714"><li>名称不能为空。</li><li>只能以英文字母开头。</li><li>长度为1到64位的字符串。</li><li>仅包含英文字母、数字和中划线（-）。</li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0102039831_row6515734618728"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0102039831_p3400959418728"><a name="zh-cn_topic_0102039831_p3400959418728"></a><a name="zh-cn_topic_0102039831_p3400959418728"></a>密码</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0102039831_p204469959544"><a name="zh-cn_topic_0102039831_p204469959544"></a><a name="zh-cn_topic_0102039831_p204469959544"></a>连接IMDG实例的密码。包括密码及确认密码。</p>
    <div class="note" id="zh-cn_topic_0102039831_note14021145182415"><a name="zh-cn_topic_0102039831_note14021145182415"></a><a name="zh-cn_topic_0102039831_note14021145182415"></a><span class="notetitle"> 说明： </span><div class="notebody"><p id="zh-cn_topic_0102039831_p178451546112414"><a name="zh-cn_topic_0102039831_p178451546112414"></a><a name="zh-cn_topic_0102039831_p178451546112414"></a>DCS服务出于安全考虑，在密码访问模式下，连接IMDG实例时，需要先进行密码认证。请妥善保存密码，并定期更新密码。</p>
    </div></div>
    <p id="zh-cn_topic_0102039831_p55321553302"><a name="zh-cn_topic_0102039831_p55321553302"></a><a name="zh-cn_topic_0102039831_p55321553302"></a>IMDG实例密码必须满足以下复杂度要求：</p>
    <a name="zh-cn_topic_0102039831_ul135351531503"></a><a name="zh-cn_topic_0102039831_ul135351531503"></a><ul id="zh-cn_topic_0102039831_ul135351531503"><li>密码不能为空。</li><li>密码不能与用户名或倒序的用户名相同。</li><li>输入长度为<span id="zh-cn_topic_0102039831_ph1254618490320"><a name="zh-cn_topic_0102039831_ph1254618490320"></a><a name="zh-cn_topic_0102039831_ph1254618490320"></a>8</span>到32位的字符串。</li><li>必须包含如下四种字符中的<span id="zh-cn_topic_0102039831_ph1862505315326"><a name="zh-cn_topic_0102039831_ph1862505315326"></a><a name="zh-cn_topic_0102039831_ph1862505315326"></a>三</span>种组合：<a name="zh-cn_topic_0102039831_ul1454195314011"></a><a name="zh-cn_topic_0102039831_ul1454195314011"></a><ul id="zh-cn_topic_0102039831_ul1454195314011"><li>小写字母</li><li>大写字母</li><li>数字</li><li>特殊字符包括（`~!@#$^&amp;*()-_=+\|{}:,&lt;.&gt;/?）</li></ul>
    </li></ul>
    </td>
    </tr>
    <tr id="zh-cn_topic_0102039831_row175574015417"><td class="cellrowborder" valign="top" width="17%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0102039831_p185589055411"><a name="zh-cn_topic_0102039831_p185589055411"></a><a name="zh-cn_topic_0102039831_p185589055411"></a>时间窗</p>
    </td>
    <td class="cellrowborder" valign="top" width="83%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0102039831_p2558130125418"><a name="zh-cn_topic_0102039831_p2558130125418"></a><a name="zh-cn_topic_0102039831_p2558130125418"></a>运维操作时间。</p>
    <p id="zh-cn_topic_0102039831_p538867566"><a name="zh-cn_topic_0102039831_p538867566"></a><a name="zh-cn_topic_0102039831_p538867566"></a>用户可选择22:00-02:00、02:00-06:00、06:00-10:00、10:00-14:00、14:00-18:00和18:00-22:00，在选择的时间段内，服务运维可对实例节点进行维护操作。</p>
    </td>
    </tr>
    </tbody>
    </table>

7.  填写完上述信息后，单击“立即购买”，进入确认页面。
8.  确认实例信息无误后，提交请求，开始创建实例。
9.  缓存实例创建成功后，用户可以在“缓存管理”页面，查看并管理自己的缓存实例。
    1.  创建缓存实例大约需要5到15分钟，如果创建集群实例，则需要大约30分钟。
    2.  缓存实例创建成功后，默认“状态”为“运行中”。
    3.  如果创建缓存实例失败，可参考[删除缓存实例](删除缓存实例.md#ZH-CN_TOPIC_0144197343)，删除创建失败的缓存实例，然后重新购买。如果重新申请仍然失败，请联系客服。


## 相关产品及文档<a name="zh-cn_topic_0102039831_section6598122311256"></a>

<a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_table1073594361220"></a>
<table><thead align="left"><tr id="zh-cn_topic_0102039831_zh-cn_topic_0046844820_row197372430123"><th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.1"><p id="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p4737243111216"><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p4737243111216"></a><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p4737243111216"></a>相关产品</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.1.3.1.2"><p id="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p18737144301214"><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p18737144301214"></a><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p18737144301214"></a>相关文档</p>
</th>
</tr>
</thead>
<tbody><tr id="zh-cn_topic_0102039831_zh-cn_topic_0046844820_row17371443131210"><td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.1 "><p id="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p13372054101419"><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p13372054101419"></a><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p13372054101419"></a><a href="https://www.huaweicloud.com/product/dcs.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Redis</a></p>
<p id="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p19548105714519"><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p19548105714519"></a><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p19548105714519"></a><a href="https://www.huaweicloud.com/product/dcsmem.html?infodocbz" target="_blank" rel="noopener noreferrer">分布式缓存 Memcached</a></p>
<p id="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p8862161219564"><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p8862161219564"></a><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p8862161219564"></a><a href="https://www.huaweicloud.com/product/ecs.html?infodocbz" target="_blank" rel="noopener noreferrer">弹性云服务器 ECS</a></p>
<p id="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p841193941416"><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p841193941416"></a><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p841193941416"></a><a href="http://www.huaweicloud.com/product/vpc.html?infodocbz" target="_blank" rel="noopener noreferrer">虚拟私有云 VPC</a></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.1.3.1.2 "><p id="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p1381695711471"><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p1381695711471"></a><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p1381695711471"></a><a href="https://support.huaweicloud.com/usermanual-dcs/dcs-zh-ug-180315001.html?infodocbz" target="_blank" rel="noopener noreferrer">购买Redis实例</a></p>
<p id="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p682916370595"><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p682916370595"></a><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p682916370595"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0082114847.html?infodocbz" target="_blank" rel="noopener noreferrer">连接Redis实例</a></p>
<p id="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p16726748155912"><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p16726748155912"></a><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p16726748155912"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0061845451.html?infodocbz" target="_blank" rel="noopener noreferrer">变更缓存实例规格</a></p>
<p id="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p12250886517"><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p12250886517"></a><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p12250886517"></a><a href="https://support.huaweicloud.com/usermanual-dcs/zh-cn_topic_0079545637.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例备份恢复</a></p>
<p id="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p143616360517"><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p143616360517"></a><a name="zh-cn_topic_0102039831_zh-cn_topic_0046844820_p143616360517"></a><a href="https://support.huaweicloud.com/migration-dcs/zh-cn_topic_0078784423.html?infodocbz" target="_blank" rel="noopener noreferrer">缓存实例数据迁移</a></p>
</td>
</tr>
</tbody>
</table>


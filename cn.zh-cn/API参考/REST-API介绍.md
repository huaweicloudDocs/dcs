# REST API介绍<a name="ZH-CN_TOPIC_0107752340"></a>

API符合RESTful API的设计理论。

REST从资源的角度来观察整个网络，提供创建、查询、更新、删掉等方法访问服务的资源。

REST API请求/响应对可以分为如下部分：

-   请求URI
-   请求方法
-   请求消息头
-   请求消息体
-   响应消息头
-   响应消息体

## 请求URI<a name="section1849899574"></a>

请求URI由如下部分组成。

**\{URI-scheme\} :// \{**Endpoint**\} / \{resource-path\} ? \{query-string\}**

尽管请求URI包含在请求消息头中，但大多数语言或框架都要求您从请求消息中单独传递它，所以在此单独描述。

**表 1**  URI中的参数说明

<a name="t1797260c744a4e1a85d354f259cae55a"></a>
<table><thead align="left"><tr id="r6dceed05bcc649d2b032accbb2980a31"><th class="cellrowborder" valign="top" width="24.529999999999998%" id="mcps1.2.3.1.1"><p id="a3446b6b785cb432bae9f45aef9177041"><a name="a3446b6b785cb432bae9f45aef9177041"></a><a name="a3446b6b785cb432bae9f45aef9177041"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="75.47%" id="mcps1.2.3.1.2"><p id="abe71244a12ac45308e99d4bbf975a9f8"><a name="abe71244a12ac45308e99d4bbf975a9f8"></a><a name="abe71244a12ac45308e99d4bbf975a9f8"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row106982018513"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="p136991001517"><a name="p136991001517"></a><a name="p136991001517"></a>URI-scheme</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="p56992017520"><a name="p56992017520"></a><a name="p56992017520"></a>表示用于传输请求的协议。</p>
</td>
</tr>
<tr id="rb217758afff146a1b40b0dcbb28a4ae1"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0035614179_p480227019422"><a name="zh-cn_topic_0035614179_p480227019422"></a><a name="zh-cn_topic_0035614179_p480227019422"></a>Endpoint</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="p1780595345416"><a name="p1780595345416"></a><a name="p1780595345416"></a>指定承载REST服务端点的服务器域名或IP，从<a href="http://developer.huaweicloud.com/endpoint.html" target="_blank" rel="noopener noreferrer">地区和终端节点</a>中获取。</p>
</td>
</tr>
<tr id="refeed61892004ea682639be281a1a707"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="p1797614317513"><a name="p1797614317513"></a><a name="p1797614317513"></a>resource-path</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="a90409cbb8b1c49c4ad4d3cfee16f475e"><a name="a90409cbb8b1c49c4ad4d3cfee16f475e"></a><a name="a90409cbb8b1c49c4ad4d3cfee16f475e"></a>资源路径，也即API访问路径。从具体接口的URI模块获取，例如“v3/auth/tokens”。</p>
</td>
</tr>
<tr id="row19939365518"><td class="cellrowborder" valign="top" width="24.529999999999998%" headers="mcps1.2.3.1.1 "><p id="p393966455"><a name="p393966455"></a><a name="p393966455"></a>Query string</p>
</td>
<td class="cellrowborder" valign="top" width="75.47%" headers="mcps1.2.3.1.2 "><p id="p159401867517"><a name="p159401867517"></a><a name="p159401867517"></a>可选参数，例如API版本或资源选择标准。</p>
</td>
</tr>
</tbody>
</table>

## 请求方法<a name="section580035055419"></a>

HTTP方法（也称为操作或动词），它告诉服务你正在请求什么类型的操作。 

**表 2**  HTTP方法

<a name="table26515221161"></a>
<table><thead align="left"><tr id="row10728192251616"><th class="cellrowborder" valign="top" width="18%" id="mcps1.2.3.1.1"><p id="p157281422201616"><a name="p157281422201616"></a><a name="p157281422201616"></a>方法</p>
</th>
<th class="cellrowborder" valign="top" width="82%" id="mcps1.2.3.1.2"><p id="p672872219161"><a name="p672872219161"></a><a name="p672872219161"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1394642154919"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p13848247114919"><a name="p13848247114919"></a><a name="p13848247114919"></a>GET</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p2850147164917"><a name="p2850147164917"></a><a name="p2850147164917"></a>请求服务器返回指定资源。</p>
</td>
</tr>
<tr id="row5728322121617"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p97281922111616"><a name="p97281922111616"></a><a name="p97281922111616"></a>PUT</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p1572882241617"><a name="p1572882241617"></a><a name="p1572882241617"></a>请求服务器更新指定资源。</p>
</td>
</tr>
<tr id="row172872211168"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p472820225166"><a name="p472820225166"></a><a name="p472820225166"></a>POST</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p272812212161"><a name="p272812212161"></a><a name="p272812212161"></a>请求服务器新增资源或执行特殊操作。</p>
</td>
</tr>
<tr id="row8728132231620"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p16729422151616"><a name="p16729422151616"></a><a name="p16729422151616"></a>DELETE</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p10729122261616"><a name="p10729122261616"></a><a name="p10729122261616"></a>请求服务器删除指定资源，如删除对象等。</p>
</td>
</tr>
<tr id="row2157183019175"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p15159030201715"><a name="p15159030201715"></a><a name="p15159030201715"></a>HEAD</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p42261787492"><a name="p42261787492"></a><a name="p42261787492"></a>请求服务器资源头部。</p>
</td>
</tr>
<tr id="row16729182210163"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.3.1.1 "><p id="p1772932218162"><a name="p1772932218162"></a><a name="p1772932218162"></a>PATCH</p>
</td>
<td class="cellrowborder" valign="top" width="82%" headers="mcps1.2.3.1.2 "><p id="p13729192251620"><a name="p13729192251620"></a><a name="p13729192251620"></a>请求服务器更新资源的部分内容。</p>
<p id="p0729142221616"><a name="p0729142221616"></a><a name="p0729142221616"></a>当资源不存在的时候，PATCH可能会去创建一个新的资源。</p>
</td>
</tr>
</tbody>
</table>

## 请求消息头<a name="section1454211155819"></a>

可选的附加请求头字段，如指定的URI和HTTP方法所要求的字段。详细的公共请求消息头字段请参见[表3](#t24b12299374a4f4ba9fbf5880aec2658)，其中请求认证信息根据认证方式请参见[Token认证](Token认证.md)或[AK/SK认证](AK-SK认证.md)。 

**表 3**  公共请求消息头

<a name="t24b12299374a4f4ba9fbf5880aec2658"></a>
<table><thead align="left"><tr id="r4c9188c98a9542db96d6d1aa49483890"><th class="cellrowborder" valign="top" width="18%" id="mcps1.2.5.1.1"><p id="a0e8fe10f8be440a59cea60dfcef9d616"><a name="a0e8fe10f8be440a59cea60dfcef9d616"></a><a name="a0e8fe10f8be440a59cea60dfcef9d616"></a>名称</p>
</th>
<th class="cellrowborder" valign="top" width="23%" id="mcps1.2.5.1.2"><p id="a0c5134defa3643d4a487a98564df4386"><a name="a0c5134defa3643d4a487a98564df4386"></a><a name="a0c5134defa3643d4a487a98564df4386"></a>描述</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.3"><p id="a5e198cd1f1c84cd4a906d9afd43ee792"><a name="a5e198cd1f1c84cd4a906d9afd43ee792"></a><a name="a5e198cd1f1c84cd4a906d9afd43ee792"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="34%" id="mcps1.2.5.1.4"><p id="ac34a236127304521999242538b072c58"><a name="ac34a236127304521999242538b072c58"></a><a name="ac34a236127304521999242538b072c58"></a>示例</p>
</th>
</tr>
</thead>
<tbody><tr id="row10629133710114"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.5.1.1 "><p id="p46301737411"><a name="p46301737411"></a><a name="p46301737411"></a>Content-Type</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.5.1.2 "><p id="p363011371216"><a name="p363011371216"></a><a name="p363011371216"></a>消息体的类型（格式）</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p1263043712111"><a name="p1263043712111"></a><a name="p1263043712111"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="34%" headers="mcps1.2.5.1.4 "><p id="p13630183715110"><a name="p13630183715110"></a><a name="p13630183715110"></a>application/json</p>
</td>
</tr>
<tr id="r48b466a7608e4d6eb042a35f56cbdfb8"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.5.1.1 "><p id="zh-cn_topic_0035614236_p792363911913"><a name="zh-cn_topic_0035614236_p792363911913"></a><a name="zh-cn_topic_0035614236_p792363911913"></a>X-Auth-Token</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.5.1.2 "><p id="p3237430121524"><a name="p3237430121524"></a><a name="p3237430121524"></a>Token认证信息，通</p>
<p id="p2293325721524"><a name="p2293325721524"></a><a name="p2293325721524"></a>过<a href="Token认证.md">Token认证</a>获取。</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="a1f6108d2189d4cd09376eebef87bb335"><a name="a1f6108d2189d4cd09376eebef87bb335"></a><a name="a1f6108d2189d4cd09376eebef87bb335"></a>当使用Token方式认证时，必须填充该字段。</p>
</td>
<td class="cellrowborder" valign="top" width="34%" headers="mcps1.2.5.1.4 "><p id="a993f118dde7d4c2f9164d578e9bc8c13"><a name="a993f118dde7d4c2f9164d578e9bc8c13"></a><a name="a993f118dde7d4c2f9164d578e9bc8c13"></a>-</p>
</td>
</tr>
<tr id="r0a259195cce44cee955af0a771a20d71"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.5.1.1 "><p id="a4259b0099d3e432f88928e25c01d1127"><a name="a4259b0099d3e432f88928e25c01d1127"></a><a name="a4259b0099d3e432f88928e25c01d1127"></a>X-Sdk-Date</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.5.1.2 "><p id="abe5e383ccc8543c2aa4563830f67957a"><a name="abe5e383ccc8543c2aa4563830f67957a"></a><a name="abe5e383ccc8543c2aa4563830f67957a"></a>请求发送的时间。</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p1309136221732"><a name="p1309136221732"></a><a name="p1309136221732"></a>当使用AK/SK认证时，必须填该字段。</p>
</td>
<td class="cellrowborder" valign="top" width="34%" headers="mcps1.2.5.1.4 "><p id="a0f19b458af404df982f0dbb457a13925"><a name="a0f19b458af404df982f0dbb457a13925"></a><a name="a0f19b458af404df982f0dbb457a13925"></a>20151222T034042Z</p>
</td>
</tr>
<tr id="rc97d5ad8e26a47d9aadce68591dbbe62"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.5.1.1 "><p id="a7238e21480a841c7a1cbbbb21bdfc864"><a name="a7238e21480a841c7a1cbbbb21bdfc864"></a><a name="a7238e21480a841c7a1cbbbb21bdfc864"></a>Authorization</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.5.1.2 "><p id="p952592421823"><a name="p952592421823"></a><a name="p952592421823"></a>签名认证信息，该值来源于请求签名结果。</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p865747321840"><a name="p865747321840"></a><a name="p865747321840"></a>当使用AK/SK认证时，必须填该字段。</p>
</td>
<td class="cellrowborder" valign="top" width="34%" headers="mcps1.2.5.1.4 "><p id="p608112012194"><a name="p608112012194"></a><a name="p608112012194"></a>SDK-HMACSHA256</p>
<p id="p104299002194"><a name="p104299002194"></a><a name="p104299002194"></a>Credential=ZIRRKMTWPTQFQI1WKNKB/20151222/cnnorth-1/ec2/sdk_request,SignedHeaders=con</p>
<p id="p202219192194"><a name="p202219192194"></a><a name="p202219192194"></a>nection;contenttype;host;x-sdk-date,Signature=7972cc9145876d174b386218</p>
<p id="p17922872194"><a name="p17922872194"></a><a name="p17922872194"></a>8a0f61819431fa71c8a8a060809ea8b898</p>
<p id="p109575352194"><a name="p109575352194"></a><a name="p109575352194"></a>e3eaa9</p>
<p id="p315089562194"><a name="p315089562194"></a><a name="p315089562194"></a>Host:dcs.cn-north-1.myhuaweicloud.com</p>
<p id="p20886442194"><a name="p20886442194"></a><a name="p20886442194"></a></p>
</td>
</tr>
<tr id="row1781273623910"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.5.1.1 "><p id="p11533145922512"><a name="p11533145922512"></a><a name="p11533145922512"></a>X-Project-ID</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.5.1.2 "><p id="p45331059142519"><a name="p45331059142519"></a><a name="p45331059142519"></a>子项目ID</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p853313594251"><a name="p853313594251"></a><a name="p853313594251"></a>在多项目场景中，必须填写该字段。</p>
</td>
<td class="cellrowborder" valign="top" width="34%" headers="mcps1.2.5.1.4 "><p id="p45336598251"><a name="p45336598251"></a><a name="p45336598251"></a>-</p>
</td>
</tr>
<tr id="row59331337113918"><td class="cellrowborder" valign="top" width="18%" headers="mcps1.2.5.1.1 "><p id="p16533115911258"><a name="p16533115911258"></a><a name="p16533115911258"></a>X-Domain-ID</p>
</td>
<td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.5.1.2 "><p id="p18533459182516"><a name="p18533459182516"></a><a name="p18533459182516"></a>账号ID</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p14821740144110"><a name="p14821740144110"></a><a name="p14821740144110"></a>否，在调用全局服务接口时必须填写该字段。</p>
</td>
<td class="cellrowborder" valign="top" width="34%" headers="mcps1.2.5.1.4 "><p id="p9534205942518"><a name="p9534205942518"></a><a name="p9534205942518"></a>-</p>
</td>
</tr>
</tbody>
</table>

## 请求消息体（可选）<a name="section14612192315587"></a>

请求消息体通常以结构化格式（如JSON或XML）发出，与请求消息头中Content-type对应，传递除请求消息头之外的内容。

## 响应消息头<a name="section7804143005810"></a>

响应消息头包含如下两部分。

-   一个HTTP状态代码：从2xx成功代码到4xx或5xx错误代码，或者，可以返回服务定义的状态码，如API文档中所示。
-   附加响应头字段，支持请求的响应所需，如Content-Type响应消息头。详细的公共响应消息头字段请参见[表4](#tb5107e70c1d545de8b97ed913f602b83)。

    **表 4**  响应消息头

    <a name="tb5107e70c1d545de8b97ed913f602b83"></a>
    <table><thead align="left"><tr id="rf674063bc81649e8b9789a311a3bcf6e"><th class="cellrowborder" valign="top" width="23%" id="mcps1.2.4.1.1"><p id="a4db082cf93e748d7b44040c488d0d38c"><a name="a4db082cf93e748d7b44040c488d0d38c"></a><a name="a4db082cf93e748d7b44040c488d0d38c"></a>名称</p>
    </th>
    <th class="cellrowborder" valign="top" width="44%" id="mcps1.2.4.1.2"><p id="aa3e3c39e04e2407ea5bcda8fc61f112d"><a name="aa3e3c39e04e2407ea5bcda8fc61f112d"></a><a name="aa3e3c39e04e2407ea5bcda8fc61f112d"></a>描述</p>
    </th>
    <th class="cellrowborder" valign="top" width="33%" id="mcps1.2.4.1.3"><p id="a53b16f94658d4903834e1c161d7759af"><a name="a53b16f94658d4903834e1c161d7759af"></a><a name="a53b16f94658d4903834e1c161d7759af"></a>示例</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="r471495aa79dc4a88a7110f2db9a835e3"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.1 "><p id="acebd9ce341d144b38d8674ad67443074"><a name="acebd9ce341d144b38d8674ad67443074"></a><a name="acebd9ce341d144b38d8674ad67443074"></a>Date</p>
    </td>
    <td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.2 "><p id="a14609642298f4650890b08516c7db143"><a name="a14609642298f4650890b08516c7db143"></a><a name="a14609642298f4650890b08516c7db143"></a>HTTP协议标准报头。表示消息发送的时间，时间的描述格式由rfc822定义。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.3 "><p id="ab1d152d4a35a4fbb86ed423b4b6d9bad"><a name="ab1d152d4a35a4fbb86ed423b4b6d9bad"></a><a name="ab1d152d4a35a4fbb86ed423b4b6d9bad"></a>Mon, 12 Nov 2007 15:55:01 GMT</p>
    </td>
    </tr>
    <tr id="r0588e315fb784df790128bb6aecf61c9"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.1 "><p id="zh-cn_topic_0035614305_p306646695935"><a name="zh-cn_topic_0035614305_p306646695935"></a><a name="zh-cn_topic_0035614305_p306646695935"></a>Server</p>
    </td>
    <td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.2 "><p id="a572e7868aa564539a661a36c8134adc4"><a name="a572e7868aa564539a661a36c8134adc4"></a><a name="a572e7868aa564539a661a36c8134adc4"></a>HTTP协议标准报头。包含了服务器用来处理请求的软件信息。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.3 "><p id="afb122eb44b7446dd9a410167ac7c06ff"><a name="afb122eb44b7446dd9a410167ac7c06ff"></a><a name="afb122eb44b7446dd9a410167ac7c06ff"></a>Apache</p>
    </td>
    </tr>
    <tr id="raa835d5c2e194ed19dc56366f0aedbe9"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.1 "><p id="a4bc2f8a7407b40329d7549814743dba4"><a name="a4bc2f8a7407b40329d7549814743dba4"></a><a name="a4bc2f8a7407b40329d7549814743dba4"></a>Content-Length</p>
    </td>
    <td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.2 "><p id="a5db1494308504d32b0ed7464c14f3c91"><a name="a5db1494308504d32b0ed7464c14f3c91"></a><a name="a5db1494308504d32b0ed7464c14f3c91"></a>HTTP协议标准报头。用于指明实体正文的长度，以字节方式存储的十进制数字来表示。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.3 "><p id="a016917505ad54f32bf5ae9e73c561ad2"><a name="a016917505ad54f32bf5ae9e73c561ad2"></a><a name="a016917505ad54f32bf5ae9e73c561ad2"></a>xxx</p>
    </td>
    </tr>
    <tr id="rb4087468a73c487a84c136020cc4ef89"><td class="cellrowborder" valign="top" width="23%" headers="mcps1.2.4.1.1 "><p id="ad6ed459cd4494fe1a0cbfe7988567c6f"><a name="ad6ed459cd4494fe1a0cbfe7988567c6f"></a><a name="ad6ed459cd4494fe1a0cbfe7988567c6f"></a>Content-Type</p>
    </td>
    <td class="cellrowborder" valign="top" width="44%" headers="mcps1.2.4.1.2 "><p id="ab38ec730e7b243d89e12ba173377ba37"><a name="ab38ec730e7b243d89e12ba173377ba37"></a><a name="ab38ec730e7b243d89e12ba173377ba37"></a>HTTP协议标准报头。用于指明发送给接收者的实体正文的媒体类型。</p>
    </td>
    <td class="cellrowborder" valign="top" width="33%" headers="mcps1.2.4.1.3 "><p id="zh-cn_topic_0035614305_p940161295935"><a name="zh-cn_topic_0035614305_p940161295935"></a><a name="zh-cn_topic_0035614305_p940161295935"></a>application/json</p>
    </td>
    </tr>
    </tbody>
    </table>


## 响应消息体（可选）<a name="section034615592583"></a>

响应消息体通常以结构化格式（如JSON或XML）返回，与响应消息头中Content-type对应，传递除响应消息头之外的内容。

## 发起请求<a name="section140743661613"></a>

共有三种方式可以基于已构建好的请求消息发起请求，分别为：

-   cURL

    cURL是一个命令行工具，用来执行各种URL操作和信息传输。cURL充当的是HTTP客户端，可以发送HTTP请求给服务端，并接收响应消息。cURL适用于接口调试。关于cURL详细信息请参见[https://curl.haxx.se/](https://curl.haxx.se/)。

-   编码

    通过编码调用接口，组装请求消息，并发送处理请求消息。

-   REST客户端

    Mozilla、Google都为REST提供了图形化的浏览器插件，发送处理请求消息。如果浏览器是Firefox，请参见[Firefox REST Client](https://addons.mozilla.org/en-US/firefox/addon/restclient/)。如果浏览器是Chrome，请参见[Postman Interceptor](https://chrome.google.com/webstore/detail/postman-interceptor/aicmkgpgakddgnaphhhpliifpcfhicfo/)。



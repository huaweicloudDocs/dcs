# API概览<a name="ZH-CN_TOPIC_0166889586"></a>

**表 1**  分布式缓存服务接口列表

<a name="table1577981717153"></a>
<table><thead align="left"><tr id="row16810121712155"><th class="cellrowborder" valign="top" width="35%" id="mcps1.2.3.1.1"><p id="p13834717131516"><a name="p13834717131516"></a><a name="p13834717131516"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="65%" id="mcps1.2.3.1.2"><p id="p3883151714159"><a name="p3883151714159"></a><a name="p3883151714159"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row12121816153"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p158557202817"><a name="p158557202817"></a><a name="p158557202817"></a><a href="缓存实例管理类接口.md">缓存实例管理类接口</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p218111811518"><a name="p218111811518"></a><a name="p218111811518"></a>分布式缓存实例的管理类接口，包括实例的创建、查询和删除，实例信息的修改以及实例扩容。</p>
</td>
</tr>
<tr id="row112051871512"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p162647151476"><a name="p162647151476"></a><a name="p162647151476"></a><a href="缓存实例维护类接口.md">缓存实例维护类接口</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p1836118151518"><a name="p1836118151518"></a><a name="p1836118151518"></a>分布式缓存实例的日常维护类接口，包括查询实例的统计信息、查询或修改实例配置参数、修改密码、备份恢复等接口。</p>
</td>
</tr>
<tr id="row1980621151411"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p53431927124713"><a name="p53431927124713"></a><a name="p53431927124713"></a><a href="租户管理类接口.md">租户管理类接口</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p178077117141"><a name="p178077117141"></a><a name="p178077117141"></a>租户用于管理分布式缓存服务的相关接口，包括查询实例列表以及租户配额接口。</p>
</td>
</tr>
<tr id="row17941818161515"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p1051015555473"><a name="p1051015555473"></a><a name="p1051015555473"></a><a href="其他接口.md">其他接口</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p129272016201817"><a name="p129272016201817"></a><a name="p129272016201817"></a>用于查询系统信息类的接口，包括查询可用区信息、产品规格列表以及维护时间窗接口。</p>
</td>
</tr>
</tbody>
</table>

## 缓存实例管理类接口<a name="section10335165821712"></a>

**表 2**  缓存实例管理类接口

<a name="table88711342351"></a>
<table><thead align="left"><tr id="row88716427513"><th class="cellrowborder" valign="top" width="35%" id="mcps1.2.3.1.1"><p id="p1871442156"><a name="p1871442156"></a><a name="p1871442156"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="65%" id="mcps1.2.3.1.2"><p id="p12871194215516"><a name="p12871194215516"></a><a name="p12871194215516"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row08723421515"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p178724421156"><a name="p178724421156"></a><a name="p178724421156"></a><a href="创建缓存实例.md">创建缓存实例</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p49892401260"><a name="p49892401260"></a><a name="p49892401260"></a>创建缓存实例，该接口创建的缓存实例支持按需计费和包周期两种方式。</p>
</td>
</tr>
<tr id="row1187211423510"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p168729428512"><a name="p168729428512"></a><a name="p168729428512"></a><a href="查询指定实例.md">查询指定实例</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p188721642859"><a name="p188721642859"></a><a name="p188721642859"></a>查询指定缓存实例的详细信息。</p>
</td>
</tr>
<tr id="row7724185465312"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p11138195613535"><a name="p11138195613535"></a><a name="p11138195613535"></a><a href="查询所有实例列表.md">查询所有实例列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p5138115614536"><a name="p5138115614536"></a><a name="p5138115614536"></a>查询所有缓存实例的列表信息。</p>
</td>
</tr>
<tr id="row2087254219512"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p1387211421756"><a name="p1387211421756"></a><a name="p1387211421756"></a><a href="修改实例信息.md">修改实例信息</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p78721842259"><a name="p78721842259"></a><a name="p78721842259"></a>修改缓存实例的信息。可修改信息包括实例名称、描述、备份策略、维护时间窗开始和结束时间以及安全组。</p>
</td>
</tr>
<tr id="row1387219421653"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p1687215421514"><a name="p1687215421514"></a><a name="p1687215421514"></a><a href="删除实例.md">删除实例</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p1987310424515"><a name="p1987310424515"></a><a name="p1987310424515"></a>删除指定的缓存实例，释放该实例的所有资源。</p>
</td>
</tr>
<tr id="row20873042758"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p88731942453"><a name="p88731942453"></a><a name="p88731942453"></a><a href="批量删除实例.md">批量删除实例</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p19873442156"><a name="p19873442156"></a><a name="p19873442156"></a>批量删除多个缓存实例。此接口还可以用于清理失败任务。</p>
</td>
</tr>
<tr id="row6873942558"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p487317428518"><a name="p487317428518"></a><a name="p487317428518"></a><a href="扩容缓存实例.md">扩容缓存实例</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p48734421454"><a name="p48734421454"></a><a name="p48734421454"></a>扩容缓存实例。</p>
</td>
</tr>
</tbody>
</table>

## 缓存实例维护类接口<a name="section34131638122111"></a>

**表 3**  缓存实例维护类接口

<a name="table114596508218"></a>
<table><thead align="left"><tr id="row11464185019219"><th class="cellrowborder" valign="top" width="35%" id="mcps1.2.3.1.1"><p id="p2465145052110"><a name="p2465145052110"></a><a name="p2465145052110"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="65%" id="mcps1.2.3.1.2"><p id="p1646613504210"><a name="p1646613504210"></a><a name="p1646613504210"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1646895012217"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p114774323112"><a name="p114774323112"></a><a name="p114774323112"></a><a href="查询运行中实例的统计信息.md">查询运行中实例的统计信息</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p1969934615328"><a name="p1969934615328"></a><a name="p1969934615328"></a>查询租户所有缓存实例的统计信息。</p>
</td>
</tr>
<tr id="row10476175012216"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p112684323112"><a name="p112684323112"></a><a name="p112684323112"></a><a href="查询实例配置参数.md">查询实例配置参数</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p11675104603212"><a name="p11675104603212"></a><a name="p11675104603212"></a>查询缓存实例的配置参数信息。</p>
</td>
</tr>
<tr id="row13801122653110"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p1380218263317"><a name="p1380218263317"></a><a name="p1380218263317"></a><a href="查询实例状态.md">查询实例状态</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p680210264310"><a name="p680210264310"></a><a name="p680210264310"></a>查询缓存实例数量的统计信息。</p>
</td>
</tr>
<tr id="row1380222693118"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p980252612316"><a name="p980252612316"></a><a name="p980252612316"></a><a href="修改实例配置参数.md">修改实例配置参数</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p1680292613316"><a name="p1680292613316"></a><a name="p1680292613316"></a>修改缓存实例的配置参数。</p>
</td>
</tr>
<tr id="row193636318311"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p143631731193115"><a name="p143631731193115"></a><a name="p143631731193115"></a><a href="重启实例或清空数据.md">重启实例或清空数据</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p163631931173118"><a name="p163631931173118"></a><a name="p163631931173118"></a>重启缓存实例，或者清空缓存实例数据。</p>
</td>
</tr>
<tr id="row836318314313"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p1036333193112"><a name="p1036333193112"></a><a name="p1036333193112"></a><a href="修改密码.md">修改密码</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p1536323193110"><a name="p1536323193110"></a><a name="p1536323193110"></a>修改缓存实例的密码。</p>
</td>
</tr>
<tr id="row5498529121813"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p1942751141813"><a name="p1942751141813"></a><a name="p1942751141813"></a><a href="备份指定实例.md">备份指定实例</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p18421051201815"><a name="p18421051201815"></a><a name="p18421051201815"></a>备份指定的缓存实例。</p>
</td>
</tr>
<tr id="row1749902951820"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p174225119183"><a name="p174225119183"></a><a name="p174225119183"></a><a href="恢复指定实例.md">恢复指定实例</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p242115111819"><a name="p242115111819"></a><a name="p242115111819"></a>恢复指定的缓存实例。</p>
</td>
</tr>
<tr id="row1849992901813"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p124235111815"><a name="p124235111815"></a><a name="p124235111815"></a><a href="查询实例备份信息.md">查询实例备份信息</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p74316518186"><a name="p74316518186"></a><a name="p74316518186"></a>查询指定缓存实例的备份信息列表。</p>
</td>
</tr>
<tr id="row5500162913181"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p14431651111814"><a name="p14431651111814"></a><a name="p14431651111814"></a><a href="查询实例恢复记录.md">查询实例恢复记录</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p19435513185"><a name="p19435513185"></a><a name="p19435513185"></a>查询指定缓存实例的恢复记录列表。</p>
</td>
</tr>
<tr id="row18261144118187"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p943195112189"><a name="p943195112189"></a><a name="p943195112189"></a><a href="删除备份文件.md">删除备份文件</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p144375114188"><a name="p144375114188"></a><a name="p144375114188"></a>删除缓存实例已备份的文件。</p>
</td>
</tr>
</tbody>
</table>

## 缓存实例标签管理类接口<a name="section106521227195316"></a>

**表 4**  实例标签管理类接口

<a name="table1059255310538"></a>
<table><thead align="left"><tr id="row05931353205316"><th class="cellrowborder" valign="top" width="35%" id="mcps1.2.3.1.1"><p id="p12593653165313"><a name="p12593653165313"></a><a name="p12593653165313"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="65%" id="mcps1.2.3.1.2"><p id="p85931853165314"><a name="p85931853165314"></a><a name="p85931853165314"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1159305345316"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p92034610548"><a name="p92034610548"></a><a name="p92034610548"></a><a href="为指定实例批量添加或删除标签.md">为指定实例批量添加或删除标签</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p1620246105416"><a name="p1620246105416"></a><a name="p1620246105416"></a>为指定实例批量添加标签，或批量删除标签。</p>
</td>
</tr>
<tr id="row20593195316530"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p1320115613546"><a name="p1320115613546"></a><a name="p1320115613546"></a><a href="通过实例ID查询标签.md">通过实例ID查询标签</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p172001169541"><a name="p172001169541"></a><a name="p172001169541"></a>通过实例ID查询该实例所有标签。</p>
</td>
</tr>
<tr id="row10593175335313"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p161992655417"><a name="p161992655417"></a><a name="p161992655417"></a><a href="查询租户所有标签.md">查询租户所有标签</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p719856195415"><a name="p719856195415"></a><a name="p719856195415"></a>查询租户在指定Project中实例类型的所有资源标签集合。</p>
</td>
</tr>
</tbody>
</table>

## 租户管理类接口<a name="section7253124819418"></a>

**表 5**  租户管理类接口

<a name="table68652515413"></a>
<table><thead align="left"><tr id="row14868105112412"><th class="cellrowborder" valign="top" width="36%" id="mcps1.2.3.1.1"><p id="p1586915512417"><a name="p1586915512417"></a><a name="p1586915512417"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="64%" id="mcps1.2.3.1.2"><p id="p168716514418"><a name="p168716514418"></a><a name="p168716514418"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row687617514415"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p487865104114"><a name="p487865104114"></a><a name="p487865104114"></a><a href="查询租户配额.md">查询租户配额</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p1088113519411"><a name="p1088113519411"></a><a name="p1088113519411"></a>查询租户配额。</p>
</td>
</tr>
<tr id="row1195585124411"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p4955105115440"><a name="p4955105115440"></a><a name="p4955105115440"></a><a href="查询租户的试用权限.md">查询租户的试用权限</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p18956451174417"><a name="p18956451174417"></a><a name="p18956451174417"></a>查询租户的试用权限。</p>
</td>
</tr>
</tbody>
</table>

## 其他接口<a name="section7519141734312"></a>

**表 6**  其他接口

<a name="table1052113174438"></a>
<table><thead align="left"><tr id="row6527417164312"><th class="cellrowborder" valign="top" width="36%" id="mcps1.2.3.1.1"><p id="p125281317124313"><a name="p125281317124313"></a><a name="p125281317124313"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="64%" id="mcps1.2.3.1.2"><p id="p5530817104317"><a name="p5530817104317"></a><a name="p5530817104317"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1953120175439"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p88268910440"><a name="p88268910440"></a><a name="p88268910440"></a><a href="查询可用区信息.md">查询可用区信息</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p1653741724315"><a name="p1653741724315"></a><a name="p1653741724315"></a>查询可用区信息。</p>
</td>
</tr>
<tr id="row1053812170438"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p5824179104411"><a name="p5824179104411"></a><a name="p5824179104411"></a><a href="查询产品规格列表.md">查询产品规格列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p4543141734312"><a name="p4543141734312"></a><a name="p4543141734312"></a>查询产品规格列表信息。</p>
</td>
</tr>
<tr id="row1123103120433"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p181241331134312"><a name="p181241331134312"></a><a name="p181241331134312"></a><a href="查询维护时间窗时间段.md">查询维护时间窗时间段</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p912413124315"><a name="p912413124315"></a><a name="p912413124315"></a>查询实例的维护时间窗时间段。</p>
</td>
</tr>
<tr id="row625283212717"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p3253163213278"><a name="p3253163213278"></a><a name="p3253163213278"></a><a href="查询主维度信息列表.md">查询主维度信息列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p12538322274"><a name="p12538322274"></a><a name="p12538322274"></a>查询主维度对象列表，主维度ID当前支持dcs_instance_id和dcs_memcached_instance_id。</p>
</td>
</tr>
<tr id="row4253432162712"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p16253183292719"><a name="p16253183292719"></a><a name="p16253183292719"></a><a href="查询单个主维度下子维度监控对象列表.md">查询单个主维度下子维度监控对象列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p1522304218228"><a name="p1522304218228"></a><a name="p1522304218228"></a>查询主维度下子维度监控对象列表，当前支持子维度的主维度ID的有dcs_instance_id。</p>
</td>
</tr>
</tbody>
</table>


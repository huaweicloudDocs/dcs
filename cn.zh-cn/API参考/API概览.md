# API概览<a name="dcs-zh-api-180423002"></a>

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
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p49892401260"><a name="p49892401260"></a><a name="p49892401260"></a>创建缓存实例，该接口创建的缓存实例支持按需计费和包周期两种方式</p>
</td>
</tr>
<tr id="row1187211423510"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p168729428512"><a name="p168729428512"></a><a name="p168729428512"></a><a href="查询指定实例.md">查询指定实例</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p188721642859"><a name="p188721642859"></a><a name="p188721642859"></a>查询指定缓存实例的详细信息。</p>
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
<tbody><tr id="row1646895012217"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p114774323112"><a name="p114774323112"></a><a name="p114774323112"></a><a href="查询所有实例的统计信息.md">查询所有实例的统计信息</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p1969934615328"><a name="p1969934615328"></a><a name="p1969934615328"></a>查询租户所有缓存实例的统计信息。</p>
</td>
</tr>
<tr id="row10476175012216"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p112684323112"><a name="p112684323112"></a><a name="p112684323112"></a><a href="查询实例配置参数.md">查询实例配置参数</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p11675104603212"><a name="p11675104603212"></a><a name="p11675104603212"></a>查询缓存实例的配置参数信息。</p>
</td>
</tr>
<tr id="row13801122653110"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p1380218263317"><a name="p1380218263317"></a><a name="p1380218263317"></a><a href="查询实例数量统计信息.md">查询实例数量统计信息</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p680210264310"><a name="p680210264310"></a><a name="p680210264310"></a>查询缓存实例数量的统计信息。</p>
</td>
</tr>
<tr id="row1380222693118"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p980252612316"><a name="p980252612316"></a><a name="p980252612316"></a><a href="修改实例配置参数.md">修改实例配置参数</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p1680292613316"><a name="p1680292613316"></a><a name="p1680292613316"></a>修改缓存实例的配置参数。</p>
</td>
</tr>
<tr id="row193636318311"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p143631731193115"><a name="p143631731193115"></a><a name="p143631731193115"></a><a href="启动-停止-重启实例或清空数据.md">启动/停止/重启实例或清空数据</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p163631931173118"><a name="p163631931173118"></a><a name="p163631931173118"></a>启动、停止、重启缓存实例，或者清空缓存实例数据。</p>
</td>
</tr>
<tr id="row836318314313"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p1036333193112"><a name="p1036333193112"></a><a name="p1036333193112"></a><a href="修改密码.md">修改密码</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p1536323193110"><a name="p1536323193110"></a><a name="p1536323193110"></a>修改缓存实例的密码。</p>
</td>
</tr>
<tr id="row960573543114"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p13605193512312"><a name="p13605193512312"></a><a name="p13605193512312"></a><a href="备份指定实例.md">实例备份恢复管理</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p7605835183119"><a name="p7605835183119"></a><a name="p7605835183119"></a>缓存实例的备份恢复管理接口，具体接口列表请参考<a href="#table8610133523717">表4</a>。</p>
</td>
</tr>
</tbody>
</table>

**表 4**  实例备份恢复管理接口

<a name="table8610133523717"></a>
<table><thead align="left"><tr id="row96221435153710"><th class="cellrowborder" valign="top" width="35%" id="mcps1.2.3.1.1"><p id="p662512352377"><a name="p662512352377"></a><a name="p662512352377"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="65%" id="mcps1.2.3.1.2"><p id="p1763373563714"><a name="p1763373563714"></a><a name="p1763373563714"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row10636835133711"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p1698016663811"><a name="p1698016663811"></a><a name="p1698016663811"></a><a href="备份指定实例.md">备份指定实例</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p064883511371"><a name="p064883511371"></a><a name="p064883511371"></a>备份指定的缓存实例。</p>
</td>
</tr>
<tr id="row14650123523717"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p1899219619386"><a name="p1899219619386"></a><a name="p1899219619386"></a><a href="恢复指定实例.md">恢复指定实例</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p136617358377"><a name="p136617358377"></a><a name="p136617358377"></a>恢复指定的缓存实例。</p>
</td>
</tr>
<tr id="row566317356373"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p183673380"><a name="p183673380"></a><a name="p183673380"></a><a href="查询实例备份信息.md">查询实例备份信息</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p16742353370"><a name="p16742353370"></a><a name="p16742353370"></a>查询指定缓存实例的备份信息列表。</p>
</td>
</tr>
<tr id="row86751356370"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p1811579381"><a name="p1811579381"></a><a name="p1811579381"></a><a href="查询实例恢复记录.md">查询实例恢复记录</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p196887354376"><a name="p196887354376"></a><a name="p196887354376"></a>查询指定缓存实例的恢复记录列表。</p>
</td>
</tr>
<tr id="row3689193563712"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p1319778387"><a name="p1319778387"></a><a name="p1319778387"></a><a href="删除备份文件.md">删除备份文件</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p1703173593713"><a name="p1703173593713"></a><a name="p1703173593713"></a>删除缓存实例已备份的文件。</p>
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
<tbody><tr id="row1987212519413"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p19637156194412"><a name="p19637156194412"></a><a name="p19637156194412"></a><a href="查询所有实例列表.md">查询所有实例列表</a></p>
</td>
<td class="cellrowborder" valign="top" width="64%" headers="mcps1.2.3.1.2 "><p id="p4876551104112"><a name="p4876551104112"></a><a name="p4876551104112"></a>查询所有缓存实例的列表信息。</p>
</td>
</tr>
<tr id="row687617514415"><td class="cellrowborder" valign="top" width="36%" headers="mcps1.2.3.1.1 "><p id="p487865104114"><a name="p487865104114"></a><a name="p487865104114"></a><a href="查询租户配额.md">查询租户配额</a></p>
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
</tbody>
</table>


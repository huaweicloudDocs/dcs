# API概览<a name="dcs-api-0312002"></a>

**表 1**  分布式缓存服务接口列表

<a name="table1577981717153"></a>
<table><thead align="left"><tr id="row16810121712155"><th class="cellrowborder" valign="top" width="35%" id="mcps1.2.3.1.1"><p id="p13834717131516"><a name="p13834717131516"></a><a name="p13834717131516"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="65%" id="mcps1.2.3.1.2"><p id="p3883151714159"><a name="p3883151714159"></a><a name="p3883151714159"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row12121816153"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p158557202817"><a name="p158557202817"></a><a name="p158557202817"></a><a href="生命周期管理.md">生命周期管理</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p218111811518"><a name="p218111811518"></a><a name="p218111811518"></a>包括实例的创建、查询和删除，实例信息的修改以及实例扩容。</p>
</td>
</tr>
<tr id="row112051871512"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p162647151476"><a name="p162647151476"></a><a name="p162647151476"></a><a href="实例管理.md">实例管理</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p1836118151518"><a name="p1836118151518"></a><a name="p1836118151518"></a>包括重启实例、查询实例状态、修改密码、查询实例的统计信息等接口。</p>
</td>
</tr>
<tr id="row6788145215357"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p1978825218353"><a name="p1978825218353"></a><a name="p1978825218353"></a><a href="分片与副本.md">分片与副本</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p7788135212359"><a name="p7788135212359"></a><a name="p7788135212359"></a>包括添加副本、设置备节点切换为主节点的优先级、查询分片信息等接口。</p>
</td>
</tr>
<tr id="row9131898550"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p113209115510"><a name="p113209115510"></a><a name="p113209115510"></a><a href="参数管理.md">参数管理</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p113219965515"><a name="p113219965515"></a><a name="p113219965515"></a>包括查询和修改实例配置参数接口。</p>
</td>
</tr>
<tr id="row2013919341557"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p4359178105619"><a name="p4359178105619"></a><a name="p4359178105619"></a><a href="备份与恢复.md">备份与恢复</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p113594816567"><a name="p113594816567"></a><a name="p113594816567"></a>包括备份实例、恢复实例、查看备份信息和恢复记录等接口</p>
</td>
</tr>
<tr id="row1435911810569"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p1714010348552"><a name="p1714010348552"></a><a name="p1714010348552"></a><a href="数据迁移.md">数据迁移</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p18140133485512"><a name="p18140133485512"></a><a name="p18140133485512"></a>包括创建实例迁移任务接口。</p>
</td>
</tr>
<tr id="row1767960133518"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p198491448175415"><a name="p198491448175415"></a><a name="p198491448175415"></a><a href="标签管理.md">标签管理</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p7850448125419"><a name="p7850448125419"></a><a name="p7850448125419"></a>用户管理实例标签的接口，包括为实例添加标签、删除标签、查询标签以及查询租户所有标签。</p>
</td>
</tr>
<tr id="row19848548175416"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p63148274355"><a name="p63148274355"></a><a name="p63148274355"></a><a href="缓存分析.md">缓存分析</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p16937644757"><a name="p16937644757"></a><a name="p16937644757"></a>包括设置大Key和热Key分析任务、查询大Key和热Key等接口。</p>
</td>
</tr>
<tr id="row17941818161515"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p1051015555473"><a name="p1051015555473"></a><a name="p1051015555473"></a><a href="日志管理.md">日志管理</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p456713363511"><a name="p456713363511"></a><a name="p456713363511"></a>包括查询慢日志的接口。</p>
</td>
</tr>
<tr id="row10464938449"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p3464738245"><a name="p3464738245"></a><a name="p3464738245"></a><a href="IP白名单管理.md">IP白名单管理</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p031392733513"><a name="p031392733513"></a><a name="p031392733513"></a>包括为指定实例设置IP白名单分组、查询实例的IP白名单的接口。</p>
</td>
</tr>
<tr id="row204659383410"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p1446513387411"><a name="p1446513387411"></a><a name="p1446513387411"></a><a href="后台任务管理.md">后台任务管理</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p9465173813413"><a name="p9465173813413"></a><a name="p9465173813413"></a>包括查询后台任务列表、删除后台任务的接口。</p>
</td>
</tr>
<tr id="row154652038749"><td class="cellrowborder" valign="top" width="35%" headers="mcps1.2.3.1.1 "><p id="p64651938147"><a name="p64651938147"></a><a name="p64651938147"></a><a href="实例诊断.md">实例诊断</a></p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.3.1.2 "><p id="p129272016201817"><a name="p129272016201817"></a><a name="p129272016201817"></a>包括查询可用区信息、产品规格列表以及维护时间窗等接口。</p>
</td>
</tr>
</tbody>
</table>


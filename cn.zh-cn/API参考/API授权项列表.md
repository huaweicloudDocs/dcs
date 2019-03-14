# API授权项列表<a name="ZH-CN_TOPIC_0160424827"></a>

DCS管理控制操作相关的企业项目细粒度权限授权项，明细如下表所示。用户调用如下API时，需要获取对应的权限。权限获取请参考[统一身份认证服务（IAM）](https://support.huaweicloud.com/productdesc-iam/iam_01_0024.html)的帮助指导。

**表 1**  API授权项明细

<a name="table11274340112310"></a>
<table><thead align="left"><tr id="row172741640142312"><th class="cellrowborder" valign="top" width="15.690000000000001%" id="mcps1.2.5.1.1"><p id="p1570042013242"><a name="p1570042013242"></a><a name="p1570042013242"></a>模块</p>
</th>
<th class="cellrowborder" valign="top" width="38.190000000000005%" id="mcps1.2.5.1.2"><p id="p22751540142314"><a name="p22751540142314"></a><a name="p22751540142314"></a>API</p>
</th>
<th class="cellrowborder" valign="top" width="19.35%" id="mcps1.2.5.1.3"><p id="p1327544010234"><a name="p1327544010234"></a><a name="p1327544010234"></a>API功能</p>
</th>
<th class="cellrowborder" valign="top" width="26.77%" id="mcps1.2.5.1.4"><p id="p102751040102320"><a name="p102751040102320"></a><a name="p102751040102320"></a>授权项</p>
</th>
</tr>
</thead>
<tbody><tr id="row132751840142315"><td class="cellrowborder" rowspan="5" valign="top" width="15.690000000000001%" headers="mcps1.2.5.1.1 "><p id="p7275154032314"><a name="p7275154032314"></a><a name="p7275154032314"></a>缓存实例管理</p>
</td>
<td class="cellrowborder" valign="top" width="38.190000000000005%" headers="mcps1.2.5.1.2 "><p id="p1327511407237"><a name="p1327511407237"></a><a name="p1327511407237"></a>POST /v1.0/{project_id}/instances</p>
</td>
<td class="cellrowborder" valign="top" width="19.35%" headers="mcps1.2.5.1.3 "><p id="p1027517409233"><a name="p1027517409233"></a><a name="p1027517409233"></a>创建缓存实例</p>
</td>
<td class="cellrowborder" valign="top" width="26.77%" headers="mcps1.2.5.1.4 "><p id="p62755403237"><a name="p62755403237"></a><a name="p62755403237"></a>dcs:instance:create</p>
</td>
</tr>
<tr id="row1127517408235"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p1127594032316"><a name="p1127594032316"></a><a name="p1127594032316"></a>GET /v1.0/{project_id}/instances/{instance_id}</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p8275340112319"><a name="p8275340112319"></a><a name="p8275340112319"></a>查询指定实例</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p3275840172318"><a name="p3275840172318"></a><a name="p3275840172318"></a>dcs:instance:get</p>
</td>
</tr>
<tr id="row13275124052313"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p427584092310"><a name="p427584092310"></a><a name="p427584092310"></a>PUT /v1.0/{project_id}/instances/{instance_id}</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p827513402234"><a name="p827513402234"></a><a name="p827513402234"></a>修改实例信息</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p4275840152320"><a name="p4275840152320"></a><a name="p4275840152320"></a>dcs:instance:modify</p>
</td>
</tr>
<tr id="row18275154014237"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p1927554014232"><a name="p1927554014232"></a><a name="p1927554014232"></a>DELETE /v1.0/{project_id}/instances/{instance_id}</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p4275144014234"><a name="p4275144014234"></a><a name="p4275144014234"></a>删除实例</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p18275340142310"><a name="p18275340142310"></a><a name="p18275340142310"></a>dcs:instance:delete</p>
</td>
</tr>
<tr id="row1027510402232"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p32752402233"><a name="p32752402233"></a><a name="p32752402233"></a>POST /v1.0/{project_id}/instances/{instance_id}/extend</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p12757406235"><a name="p12757406235"></a><a name="p12757406235"></a>扩容实例</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p5275134062317"><a name="p5275134062317"></a><a name="p5275134062317"></a>dcs:instance:scale</p>
</td>
</tr>
<tr id="row72756407239"><td class="cellrowborder" rowspan="5" valign="top" width="15.690000000000001%" headers="mcps1.2.5.1.1 "><p id="p3275440112312"><a name="p3275440112312"></a><a name="p3275440112312"></a>实例维护</p>
</td>
<td class="cellrowborder" valign="top" width="38.190000000000005%" headers="mcps1.2.5.1.2 "><p id="p518010446237"><a name="p518010446237"></a><a name="p518010446237"></a>GET /v1.0/{project_id}/instances</p>
</td>
<td class="cellrowborder" valign="top" width="19.35%" headers="mcps1.2.5.1.3 "><p id="p627564012316"><a name="p627564012316"></a><a name="p627564012316"></a>查询实例列表</p>
</td>
<td class="cellrowborder" valign="top" width="26.77%" headers="mcps1.2.5.1.4 "><p id="p6275204011236"><a name="p6275204011236"></a><a name="p6275204011236"></a>dcs:instance:list</p>
</td>
</tr>
<tr id="row627584042310"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p4275740122320"><a name="p4275740122320"></a><a name="p4275740122320"></a>GET /v1.0/{project_id}/instances/{instance_id}/configs</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p1627514010235"><a name="p1627514010235"></a><a name="p1627514010235"></a>查询实例配置信息</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p10275124092317"><a name="p10275124092317"></a><a name="p10275124092317"></a>dcs:instance:getConfiguration</p>
</td>
</tr>
<tr id="row155430432232"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p1954494332316"><a name="p1954494332316"></a><a name="p1954494332316"></a>PUT /v1.0/{project_id}/instances/{instance_id}/configs</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p17544174322316"><a name="p17544174322316"></a><a name="p17544174322316"></a>修改实例配置信息</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p3544174319238"><a name="p3544174319238"></a><a name="p3544174319238"></a>dcs:instance:modifyConfigureation</p>
</td>
</tr>
<tr id="row108626437233"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p18862743192315"><a name="p18862743192315"></a><a name="p18862743192315"></a>PUT /v1.0/{project_id}/instances/status</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p161874793613"><a name="p161874793613"></a><a name="p161874793613"></a>启动/停止/重启实例或清空数据</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p1786224312310"><a name="p1786224312310"></a><a name="p1786224312310"></a>dcs:instance:modifyStatus</p>
</td>
</tr>
<tr id="row1016184432319"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p01654482310"><a name="p01654482310"></a><a name="p01654482310"></a>PUT /v1.0/{project_id}/instances/{instance_id}/password</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p1116104422312"><a name="p1116104422312"></a><a name="p1116104422312"></a>修改实例密码</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p11618447232"><a name="p11618447232"></a><a name="p11618447232"></a>dcs:instance:modifyAuthInfo</p>
</td>
</tr>
<tr id="row0325144112317"><td class="cellrowborder" rowspan="5" valign="top" width="15.690000000000001%" headers="mcps1.2.5.1.1 "><p id="p878685415412"><a name="p878685415412"></a><a name="p878685415412"></a>备份恢复管理</p>
</td>
<td class="cellrowborder" valign="top" width="38.190000000000005%" headers="mcps1.2.5.1.2 "><p id="p1432684411231"><a name="p1432684411231"></a><a name="p1432684411231"></a>POST /v1.0/{project_id}/instances/{instance_id}/backups</p>
</td>
<td class="cellrowborder" valign="top" width="19.35%" headers="mcps1.2.5.1.3 "><p id="p3326124418230"><a name="p3326124418230"></a><a name="p3326124418230"></a>备份实例数据</p>
</td>
<td class="cellrowborder" valign="top" width="26.77%" headers="mcps1.2.5.1.4 "><p id="p0326124402311"><a name="p0326124402311"></a><a name="p0326124402311"></a>dcs:instance:backupData</p>
</td>
</tr>
<tr id="row114777445232"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p194777441230"><a name="p194777441230"></a><a name="p194777441230"></a>POST /v1.0/{project_id}/instances/{instance_id}/restores</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p1847724418236"><a name="p1847724418236"></a><a name="p1847724418236"></a>恢复实例数据</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p2477344182312"><a name="p2477344182312"></a><a name="p2477344182312"></a>dcs:instance:restoreData</p>
</td>
</tr>
<tr id="row6632044102314"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p1263224412239"><a name="p1263224412239"></a><a name="p1263224412239"></a>GET /v1.0/{project_id}/instances/{instance_id}/backups</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p1063204492311"><a name="p1063204492311"></a><a name="p1063204492311"></a>查询备份任务</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p16632344182311"><a name="p16632344182311"></a><a name="p16632344182311"></a>dcs:instance:getDataBackupLog</p>
</td>
</tr>
<tr id="row278814441234"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p14788174415235"><a name="p14788174415235"></a><a name="p14788174415235"></a>GET /v1.0/{project_id}/instances/{instance_id}/restores</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p6788154415238"><a name="p6788154415238"></a><a name="p6788154415238"></a>查询恢复任务</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p9788114422312"><a name="p9788114422312"></a><a name="p9788114422312"></a>dcs:instance:getDataRestoreLog</p>
</td>
</tr>
<tr id="row119293445235"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p7929184412313"><a name="p7929184412313"></a><a name="p7929184412313"></a>DELETE /v1.0/{project_id}/instances/{instance_id}/backups/{backup_id}</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p16929204442315"><a name="p16929204442315"></a><a name="p16929204442315"></a>删除备份文件</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p2929744182310"><a name="p2929744182310"></a><a name="p2929744182310"></a>dcs:instance:deleteDataBackupFile</p>
</td>
</tr>
<tr id="row6819452233"><td class="cellrowborder" rowspan="2" valign="top" width="15.690000000000001%" headers="mcps1.2.5.1.1 "><p id="p1428618132421"><a name="p1428618132421"></a><a name="p1428618132421"></a>其他</p>
</td>
<td class="cellrowborder" valign="top" width="38.190000000000005%" headers="mcps1.2.5.1.2 "><p id="p20811945142314"><a name="p20811945142314"></a><a name="p20811945142314"></a>GET /v1.0/{project_id}/instances/{instance_id}/tasks</p>
</td>
<td class="cellrowborder" valign="top" width="19.35%" headers="mcps1.2.5.1.3 "><p id="p5815451231"><a name="p5815451231"></a><a name="p5815451231"></a>查询后台任务</p>
</td>
<td class="cellrowborder" valign="top" width="26.77%" headers="mcps1.2.5.1.4 "><p id="p17812451239"><a name="p17812451239"></a><a name="p17812451239"></a>dcs:instance:getBackgroundTask</p>
</td>
</tr>
<tr id="row1922424512238"><td class="cellrowborder" valign="top" headers="mcps1.2.5.1.1 "><p id="p2022434532313"><a name="p2022434532313"></a><a name="p2022434532313"></a>DELETE /v1.0/{project_id}/instances/{instance_id}/tasks/{task_id}</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.2 "><p id="p172241445132310"><a name="p172241445132310"></a><a name="p172241445132310"></a>删除实例后台任务</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.5.1.3 "><p id="p1422424512310"><a name="p1422424512310"></a><a name="p1422424512310"></a>dcs:instance:deleteBackgroundTask</p>
</td>
</tr>
</tbody>
</table>


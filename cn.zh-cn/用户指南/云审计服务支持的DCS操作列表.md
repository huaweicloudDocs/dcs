# 云审计服务支持的DCS操作列表<a name="ZH-CN_TOPIC_0148195296"></a>

DCS通过云审计服务（Cloud Trace Service，简称CTS）为您提供云服务资源的操作记录，记录内容包括您从公有云管理控制台或者开放API发起的的云服务资源操作请求以及每次请求的结果，供您查询、审计和回溯使用。

本节主要介绍云审计服务支持的DCS操作列表。

**表 1**  云审计服务支持的DCS操作列表

<a name="table159151912144710"></a>
<table><thead align="left"><tr id="row1191521216471"><th class="cellrowborder" valign="top" width="18.64186418641864%" id="mcps1.2.4.1.1"><p id="p12915191254720"><a name="p12915191254720"></a><a name="p12915191254720"></a>操作类型</p>
</th>
<th class="cellrowborder" valign="top" width="20.49204920492049%" id="mcps1.2.4.1.2"><p id="p1591591234710"><a name="p1591591234710"></a><a name="p1591591234710"></a>资源类型</p>
</th>
<th class="cellrowborder" valign="top" width="60.866086608660865%" id="mcps1.2.4.1.3"><p id="p0915812194718"><a name="p0915812194718"></a><a name="p0915812194718"></a>事件名称</p>
</th>
</tr>
</thead>
<tbody><tr id="row209181612164717"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p1791881204719"><a name="p1791881204719"></a><a name="p1791881204719"></a>创建实例</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p11918151212473"><a name="p11918151212473"></a><a name="p11918151212473"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p5918412194717"><a name="p5918412194717"></a><a name="p5918412194717"></a>createDCSInstance</p>
</td>
</tr>
<tr id="row89181912184717"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p3918141284720"><a name="p3918141284720"></a><a name="p3918141284720"></a>提交创建实例请求</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p91521937155811"><a name="p91521937155811"></a><a name="p91521937155811"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p991813122479"><a name="p991813122479"></a><a name="p991813122479"></a>submitCreateDCSInstanceRequest</p>
</td>
</tr>
<tr id="row191819121478"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p15918151214717"><a name="p15918151214717"></a><a name="p15918151214717"></a>批量删除实例</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p021910374589"><a name="p021910374589"></a><a name="p021910374589"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p29180126475"><a name="p29180126475"></a><a name="p29180126475"></a>batchDeleteDCSInstance</p>
</td>
</tr>
<tr id="row12918141216477"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p1691841215479"><a name="p1691841215479"></a><a name="p1691841215479"></a>删除实例</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p15243103735812"><a name="p15243103735812"></a><a name="p15243103735812"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p179181124476"><a name="p179181124476"></a><a name="p179181124476"></a>deleteDCSInstance</p>
</td>
</tr>
<tr id="row3918412124718"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p1191810122472"><a name="p1191810122472"></a><a name="p1191810122472"></a>修改实例信息</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p17273637175814"><a name="p17273637175814"></a><a name="p17273637175814"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p191918126471"><a name="p191918126471"></a><a name="p191918126471"></a>modifyDCSInstanceInfo</p>
</td>
</tr>
<tr id="row11919912184716"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p1591911210475"><a name="p1591911210475"></a><a name="p1591911210475"></a>修改实例配置</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p1030513377584"><a name="p1030513377584"></a><a name="p1030513377584"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p20919412104718"><a name="p20919412104718"></a><a name="p20919412104718"></a>modifyDCSInstanceConfig</p>
</td>
</tr>
<tr id="row291931294718"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p2919101212479"><a name="p2919101212479"></a><a name="p2919101212479"></a>修改实例密码</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p103271437155818"><a name="p103271437155818"></a><a name="p103271437155818"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p4919912114717"><a name="p4919912114717"></a><a name="p4919912114717"></a>modifyDCSInstancePassword</p>
</td>
</tr>
<tr id="row11919212154718"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p169191112164712"><a name="p169191112164712"></a><a name="p169191112164712"></a>停止实例</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p734713719585"><a name="p734713719585"></a><a name="p734713719585"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p11920112194714"><a name="p11920112194714"></a><a name="p11920112194714"></a>stopDCSInstance</p>
</td>
</tr>
<tr id="row492014125478"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p1792011122473"><a name="p1792011122473"></a><a name="p1792011122473"></a>提交停止实例请求</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p1437173775817"><a name="p1437173775817"></a><a name="p1437173775817"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p1692012129478"><a name="p1692012129478"></a><a name="p1692012129478"></a>submitStopDCSInstanceRequest</p>
</td>
</tr>
<tr id="row18920151218473"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p1992019128479"><a name="p1992019128479"></a><a name="p1992019128479"></a>重启实例</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p6394163710587"><a name="p6394163710587"></a><a name="p6394163710587"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p9920212154712"><a name="p9920212154712"></a><a name="p9920212154712"></a>restartDCSInstance</p>
</td>
</tr>
<tr id="row592081274716"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p2092071213472"><a name="p2092071213472"></a><a name="p2092071213472"></a>提交重启实例请求</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p18419163795814"><a name="p18419163795814"></a><a name="p18419163795814"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p1092071234720"><a name="p1092071234720"></a><a name="p1092071234720"></a>submitRestartDCSInstanceRequest</p>
</td>
</tr>
<tr id="row3921181213471"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p20921181204714"><a name="p20921181204714"></a><a name="p20921181204714"></a>启动实例</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p2442103713585"><a name="p2442103713585"></a><a name="p2442103713585"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p1992116123476"><a name="p1992116123476"></a><a name="p1992116123476"></a>startDCSInstance</p>
</td>
</tr>
<tr id="row19922201212477"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p39221612114716"><a name="p39221612114716"></a><a name="p39221612114716"></a>提交启动实例请求</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p84693377585"><a name="p84693377585"></a><a name="p84693377585"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p0922111210473"><a name="p0922111210473"></a><a name="p0922111210473"></a>submitStartDCSInstanceRequest</p>
</td>
</tr>
<tr id="row169221712184716"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p1592212122477"><a name="p1592212122477"></a><a name="p1592212122477"></a>清空实例</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p16497143712582"><a name="p16497143712582"></a><a name="p16497143712582"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p39221912124715"><a name="p39221912124715"></a><a name="p39221912124715"></a>flushDCSInstance</p>
</td>
</tr>
<tr id="row4922171274712"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p39221012134712"><a name="p39221012134712"></a><a name="p39221012134712"></a>批量停止实例</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p17525183716580"><a name="p17525183716580"></a><a name="p17525183716580"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p092361254711"><a name="p092361254711"></a><a name="p092361254711"></a>batchStopDCSInstance</p>
</td>
</tr>
<tr id="row59232012164718"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p292371294716"><a name="p292371294716"></a><a name="p292371294716"></a>提交批量停止实例请求</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p105481337135815"><a name="p105481337135815"></a><a name="p105481337135815"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p4923141274717"><a name="p4923141274717"></a><a name="p4923141274717"></a>submitBatchStopDCSInstanceRequest</p>
</td>
</tr>
<tr id="row18923912194712"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p4923181220475"><a name="p4923181220475"></a><a name="p4923181220475"></a>批量重启实例</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p6572937175814"><a name="p6572937175814"></a><a name="p6572937175814"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p39258120476"><a name="p39258120476"></a><a name="p39258120476"></a>batchRestartDCSInstance</p>
</td>
</tr>
<tr id="row15925201211473"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p692531244717"><a name="p692531244717"></a><a name="p692531244717"></a>提交批量重启实例请求</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p4280743155810"><a name="p4280743155810"></a><a name="p4280743155810"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p692681214476"><a name="p692681214476"></a><a name="p692681214476"></a>submitBatchRestartDCSInstanceRequest</p>
</td>
</tr>
<tr id="row09261512114713"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p1992651224716"><a name="p1992651224716"></a><a name="p1992651224716"></a>批量启动实例</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p203021043165816"><a name="p203021043165816"></a><a name="p203021043165816"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p1292681294710"><a name="p1292681294710"></a><a name="p1292681294710"></a>batchStartDCSInstance</p>
</td>
</tr>
<tr id="row49267129476"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p2926812124715"><a name="p2926812124715"></a><a name="p2926812124715"></a>提交批量启动实例请求</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p183251643125819"><a name="p183251643125819"></a><a name="p183251643125819"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p5926312134715"><a name="p5926312134715"></a><a name="p5926312134715"></a>submitBatchStartDCSInstanceRequest</p>
</td>
</tr>
<tr id="row1892614127475"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p392651214710"><a name="p392651214710"></a><a name="p392651214710"></a>恢复实例数据</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p1935304314582"><a name="p1935304314582"></a><a name="p1935304314582"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p12927101234714"><a name="p12927101234714"></a><a name="p12927101234714"></a>restoreDCSInstance</p>
</td>
</tr>
<tr id="row11927812174710"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p15927121224715"><a name="p15927121224715"></a><a name="p15927121224715"></a>提交恢复实例数据请求</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p237619431581"><a name="p237619431581"></a><a name="p237619431581"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p992741220474"><a name="p992741220474"></a><a name="p992741220474"></a>submitRestoreDCSInstanceRequest</p>
</td>
</tr>
<tr id="row8927111254717"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p19927111224710"><a name="p19927111224710"></a><a name="p19927111224710"></a>备份实例数据</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p173981643165816"><a name="p173981643165816"></a><a name="p173981643165816"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p9927171214711"><a name="p9927171214711"></a><a name="p9927171214711"></a>backupDCSInstance</p>
</td>
</tr>
<tr id="row69271212144717"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p49284127474"><a name="p49284127474"></a><a name="p49284127474"></a>提交备份实例数据请求</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p64221143205820"><a name="p64221143205820"></a><a name="p64221143205820"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p1792881234712"><a name="p1792881234712"></a><a name="p1792881234712"></a>submitBackupDCSInstanceRequest</p>
</td>
</tr>
<tr id="row1792861294711"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p1392851214711"><a name="p1392851214711"></a><a name="p1392851214711"></a>删除实例备份文件</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p04465434586"><a name="p04465434586"></a><a name="p04465434586"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p392851294711"><a name="p392851294711"></a><a name="p392851294711"></a>deleteInstanceBackupFile</p>
</td>
</tr>
<tr id="row692881212479"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p0929512194716"><a name="p0929512194716"></a><a name="p0929512194716"></a>删除后台任务记录</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p15470643145811"><a name="p15470643145811"></a><a name="p15470643145811"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p692911128471"><a name="p692911128471"></a><a name="p692911128471"></a>deleteDCSInstanceJobRecord</p>
</td>
</tr>
<tr id="row19929151254711"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p492912127476"><a name="p492912127476"></a><a name="p492912127476"></a>实例规格变更</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p1349394395815"><a name="p1349394395815"></a><a name="p1349394395815"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p6929101213474"><a name="p6929101213474"></a><a name="p6929101213474"></a>modifySpecification</p>
</td>
</tr>
<tr id="row169291512174711"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p99298129470"><a name="p99298129470"></a><a name="p99298129470"></a>提交实例规格变更请求</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p751524311581"><a name="p751524311581"></a><a name="p751524311581"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p692913122475"><a name="p692913122475"></a><a name="p692913122475"></a>submitModifySpecificationRequest</p>
</td>
</tr>
<tr id="row59298123477"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p492941224712"><a name="p492941224712"></a><a name="p492941224712"></a>创建实例订单</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p165403439582"><a name="p165403439582"></a><a name="p165403439582"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p79304125477"><a name="p79304125477"></a><a name="p79304125477"></a>createInstanceOrder</p>
</td>
</tr>
<tr id="row119301912164720"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p8930171215476"><a name="p8930171215476"></a><a name="p8930171215476"></a>创建实例规格变更订单</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p956624318584"><a name="p956624318584"></a><a name="p956624318584"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p69309123472"><a name="p69309123472"></a><a name="p69309123472"></a>createSpecificationChangeOrder</p>
</td>
</tr>
<tr id="row293017128472"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p139301412184716"><a name="p139301412184716"></a><a name="p139301412184716"></a>更新企业项目ID</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p12585243185815"><a name="p12585243185815"></a><a name="p12585243185815"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p493051210472"><a name="p493051210472"></a><a name="p493051210472"></a>updateEnterpriseProjectId</p>
</td>
</tr>
<tr id="row6930212154710"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p39301512184712"><a name="p39301512184712"></a><a name="p39301512184712"></a>主备切换</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p6604143165810"><a name="p6604143165810"></a><a name="p6604143165810"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p2930212194718"><a name="p2930212194718"></a><a name="p2930212194718"></a>masterStandbySwitchover</p>
</td>
</tr>
<tr id="row893021220476"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p199304126476"><a name="p199304126476"></a><a name="p199304126476"></a>关闭公网访问</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p1347110471588"><a name="p1347110471588"></a><a name="p1347110471588"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p1931131294712"><a name="p1931131294712"></a><a name="p1931131294712"></a>disablePublicNetworkAccess</p>
</td>
</tr>
<tr id="row193131254713"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p1931181212476"><a name="p1931181212476"></a><a name="p1931181212476"></a>开启公网访问</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p1649315477581"><a name="p1649315477581"></a><a name="p1649315477581"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p19311212104718"><a name="p19311212104718"></a><a name="p19311212104718"></a>enablePublicNetworkAccess</p>
</td>
</tr>
<tr id="row09311812204715"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p18931101284715"><a name="p18931101284715"></a><a name="p18931101284715"></a>重置实例密码</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p1951634785812"><a name="p1951634785812"></a><a name="p1951634785812"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p15931212114714"><a name="p15931212114714"></a><a name="p15931212114714"></a>resetDCSInstancePassword</p>
</td>
</tr>
<tr id="row1893115123477"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p4931121218479"><a name="p4931121218479"></a><a name="p4931121218479"></a>提交清空实例请求</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p18539347175819"><a name="p18539347175819"></a><a name="p18539347175819"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p493117120473"><a name="p493117120473"></a><a name="p493117120473"></a>submitFlushDCSInstanceRequest</p>
</td>
</tr>
<tr id="row17931812124714"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p129311212124719"><a name="p129311212124719"></a><a name="p129311212124719"></a>WebCli登录</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p19561747165810"><a name="p19561747165810"></a><a name="p19561747165810"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p49320122473"><a name="p49320122473"></a><a name="p49320122473"></a>webCliLogin</p>
</td>
</tr>
<tr id="row1393218122470"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p0932101214475"><a name="p0932101214475"></a><a name="p0932101214475"></a>webCli命令执行</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p7588184745818"><a name="p7588184745818"></a><a name="p7588184745818"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p1932612114718"><a name="p1932612114718"></a><a name="p1932612114718"></a>webCliCommand</p>
</td>
</tr>
<tr id="row1293291294713"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p18932161244715"><a name="p18932161244715"></a><a name="p18932161244715"></a>webCli登出</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p14609124710589"><a name="p14609124710589"></a><a name="p14609124710589"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p693221254712"><a name="p693221254712"></a><a name="p693221254712"></a>webCliLogout</p>
</td>
</tr>
<tr id="row59321712174717"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p993321217475"><a name="p993321217475"></a><a name="p993321217475"></a>离线迁移</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p1563018474585"><a name="p1563018474585"></a><a name="p1563018474585"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p3933151284715"><a name="p3933151284715"></a><a name="p3933151284715"></a>offlineMigrate</p>
</td>
</tr>
<tr id="row12933111244720"><td class="cellrowborder" valign="top" width="18.64186418641864%" headers="mcps1.2.4.1.1 "><p id="p8933012124720"><a name="p8933012124720"></a><a name="p8933012124720"></a>计费模式变更</p>
</td>
<td class="cellrowborder" valign="top" width="20.49204920492049%" headers="mcps1.2.4.1.2 "><p id="p4655174745815"><a name="p4655174745815"></a><a name="p4655174745815"></a>分布式缓存服务</p>
</td>
<td class="cellrowborder" valign="top" width="60.866086608660865%" headers="mcps1.2.4.1.3 "><p id="p11933412194711"><a name="p11933412194711"></a><a name="p11933412194711"></a>billingModeChange</p>
</td>
</tr>
</tbody>
</table>


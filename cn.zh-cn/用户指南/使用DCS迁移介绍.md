# 使用DCS迁移介绍<a name="ZH-CN_TOPIC_0179456696"></a>

华为云Redis支持备份文件导入和在线迁移两种迁移方式：

-   备份文件导入方式：您需要先将源Redis的数据备份并下载，然后将备份数据文件上传到华为云与DCS Redis实例同一租户下相同Region下的OBS桶中，DCS从OBS桶中读取备份数据，并将数据迁移到华为云Redis中。

    **支持从其他云厂商Redis服务、自建Redis迁移到华为云Redis**。

-   在线迁移：在满足源Redis和目标Redis的网络相通、源Redis未禁用SYNC和PSYNC命令这两个前提下，使用在线迁移的方式，将源Redis中的数据全量迁移或增量迁移到目标Redis中。

当前使用DCS控制台支持的迁移能力，如[表1](#zh-cn_topic_0176540003_table1732614449178)所示，您可以根据业务实际情况，选择迁移方式。

**表 1**  DCS支持的迁移能力

<a name="zh-cn_topic_0176540003_table1732614449178"></a>
<table><tbody><tr id="zh-cn_topic_0176540003_row7327944161716"><td class="cellrowborder" rowspan="2" valign="top"><p id="zh-cn_topic_0176540003_p20327194412170"><a name="zh-cn_topic_0176540003_p20327194412170"></a><a name="zh-cn_topic_0176540003_p20327194412170"></a>迁移类型</p>
</td>
<td class="cellrowborder" rowspan="2" valign="top"><p id="zh-cn_topic_0176540003_p179166209193"><a name="zh-cn_topic_0176540003_p179166209193"></a><a name="zh-cn_topic_0176540003_p179166209193"></a>源端</p>
</td>
<td class="cellrowborder" colspan="3" valign="top"><p id="zh-cn_topic_0176540003_p18279163818267"><a name="zh-cn_topic_0176540003_p18279163818267"></a><a name="zh-cn_topic_0176540003_p18279163818267"></a>目标端：华为云DCS服务</p>
</td>
</tr>
<tr id="zh-cn_topic_0176540003_row16168192410286"><td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p516811241288"><a name="zh-cn_topic_0176540003_p516811241288"></a><a name="zh-cn_topic_0176540003_p516811241288"></a>单机/主备</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p716811248286"><a name="zh-cn_topic_0176540003_p716811248286"></a><a name="zh-cn_topic_0176540003_p716811248286"></a>Proxy集群</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p1116832415287"><a name="zh-cn_topic_0176540003_p1116832415287"></a><a name="zh-cn_topic_0176540003_p1116832415287"></a>Cluster集群</p>
</td>
</tr>
<tr id="zh-cn_topic_0176540003_row6327244151714"><td class="cellrowborder" rowspan="2" valign="top" width="12.879999999999999%"><p id="zh-cn_topic_0176540003_p23271044201715"><a name="zh-cn_topic_0176540003_p23271044201715"></a><a name="zh-cn_topic_0176540003_p23271044201715"></a>备份文件导入</p>
<p id="zh-cn_topic_0176540003_p032713448173"><a name="zh-cn_topic_0176540003_p032713448173"></a><a name="zh-cn_topic_0176540003_p032713448173"></a></p>
</td>
<td class="cellrowborder" valign="top" width="19.78%"><p id="zh-cn_topic_0176540003_p232713446171"><a name="zh-cn_topic_0176540003_p232713446171"></a><a name="zh-cn_topic_0176540003_p232713446171"></a>OBS桶：AOF文件</p>
</td>
<td class="cellrowborder" valign="top" width="21.32%"><p id="zh-cn_topic_0176540003_p19327544201716"><a name="zh-cn_topic_0176540003_p19327544201716"></a><a name="zh-cn_topic_0176540003_p19327544201716"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.310000000000002%"><p id="zh-cn_topic_0176540003_p7197181473715"><a name="zh-cn_topic_0176540003_p7197181473715"></a><a name="zh-cn_topic_0176540003_p7197181473715"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.709999999999997%"><p id="zh-cn_topic_0176540003_p230620162612"><a name="zh-cn_topic_0176540003_p230620162612"></a><a name="zh-cn_topic_0176540003_p230620162612"></a>×</p>
</td>
</tr>
<tr id="zh-cn_topic_0176540003_row18327124419177"><td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p13887145514323"><a name="zh-cn_topic_0176540003_p13887145514323"></a><a name="zh-cn_topic_0176540003_p13887145514323"></a>OBS桶：RDB文件</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p83271044171712"><a name="zh-cn_topic_0176540003_p83271044171712"></a><a name="zh-cn_topic_0176540003_p83271044171712"></a>√</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p219819148377"><a name="zh-cn_topic_0176540003_p219819148377"></a><a name="zh-cn_topic_0176540003_p219819148377"></a>√</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p1975522123817"><a name="zh-cn_topic_0176540003_p1975522123817"></a><a name="zh-cn_topic_0176540003_p1975522123817"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0176540003_row332704421710"><td class="cellrowborder" rowspan="9" valign="top" width="12.879999999999999%"><p id="zh-cn_topic_0176540003_p532724414178"><a name="zh-cn_topic_0176540003_p532724414178"></a><a name="zh-cn_topic_0176540003_p532724414178"></a>在线迁移</p>
<p id="zh-cn_topic_0176540003_p5328644171716"><a name="zh-cn_topic_0176540003_p5328644171716"></a><a name="zh-cn_topic_0176540003_p5328644171716"></a></p>
<p id="zh-cn_topic_0176540003_p393017571331"><a name="zh-cn_topic_0176540003_p393017571331"></a><a name="zh-cn_topic_0176540003_p393017571331"></a></p>
<p id="zh-cn_topic_0176540003_p29306572334"><a name="zh-cn_topic_0176540003_p29306572334"></a><a name="zh-cn_topic_0176540003_p29306572334"></a></p>
<p id="zh-cn_topic_0176540003_p1181817434346"><a name="zh-cn_topic_0176540003_p1181817434346"></a><a name="zh-cn_topic_0176540003_p1181817434346"></a></p>
<p id="zh-cn_topic_0176540003_p1181834303416"><a name="zh-cn_topic_0176540003_p1181834303416"></a><a name="zh-cn_topic_0176540003_p1181834303416"></a></p>
<p id="zh-cn_topic_0176540003_p1281918433341"><a name="zh-cn_topic_0176540003_p1281918433341"></a><a name="zh-cn_topic_0176540003_p1281918433341"></a></p>
<p id="zh-cn_topic_0176540003_p27365256350"><a name="zh-cn_topic_0176540003_p27365256350"></a><a name="zh-cn_topic_0176540003_p27365256350"></a></p>
<p id="zh-cn_topic_0176540003_p28197432340"><a name="zh-cn_topic_0176540003_p28197432340"></a><a name="zh-cn_topic_0176540003_p28197432340"></a></p>
</td>
<td class="cellrowborder" valign="top" width="19.78%"><p id="zh-cn_topic_0176540003_p23281144181716"><a name="zh-cn_topic_0176540003_p23281144181716"></a><a name="zh-cn_topic_0176540003_p23281144181716"></a>华为云Redis：单机/主备</p>
</td>
<td class="cellrowborder" valign="top" width="21.32%"><p id="zh-cn_topic_0176540003_p99458238378"><a name="zh-cn_topic_0176540003_p99458238378"></a><a name="zh-cn_topic_0176540003_p99458238378"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.310000000000002%"><p id="zh-cn_topic_0176540003_p139911924183713"><a name="zh-cn_topic_0176540003_p139911924183713"></a><a name="zh-cn_topic_0176540003_p139911924183713"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.709999999999997%"><p id="zh-cn_topic_0176540003_p746562618370"><a name="zh-cn_topic_0176540003_p746562618370"></a><a name="zh-cn_topic_0176540003_p746562618370"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0176540003_row11328174451719"><td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p932894491715"><a name="zh-cn_topic_0176540003_p932894491715"></a><a name="zh-cn_topic_0176540003_p932894491715"></a>华为云Redis：Proxy集群</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p12328204421716"><a name="zh-cn_topic_0176540003_p12328204421716"></a><a name="zh-cn_topic_0176540003_p12328204421716"></a>×</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p183288446177"><a name="zh-cn_topic_0176540003_p183288446177"></a><a name="zh-cn_topic_0176540003_p183288446177"></a>×</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p231192062619"><a name="zh-cn_topic_0176540003_p231192062619"></a><a name="zh-cn_topic_0176540003_p231192062619"></a>×</p>
</td>
</tr>
<tr id="zh-cn_topic_0176540003_row793015576338"><td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p1293085783318"><a name="zh-cn_topic_0176540003_p1293085783318"></a><a name="zh-cn_topic_0176540003_p1293085783318"></a>华为云Redis：Cluster集群</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p1278073214373"><a name="zh-cn_topic_0176540003_p1278073214373"></a><a name="zh-cn_topic_0176540003_p1278073214373"></a>√</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p5180133493711"><a name="zh-cn_topic_0176540003_p5180133493711"></a><a name="zh-cn_topic_0176540003_p5180133493711"></a>√</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p202517354378"><a name="zh-cn_topic_0176540003_p202517354378"></a><a name="zh-cn_topic_0176540003_p202517354378"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0176540003_row1930165710331"><td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p16469124943418"><a name="zh-cn_topic_0176540003_p16469124943418"></a><a name="zh-cn_topic_0176540003_p16469124943418"></a>自建Redis：单机/主备</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p424921414382"><a name="zh-cn_topic_0176540003_p424921414382"></a><a name="zh-cn_topic_0176540003_p424921414382"></a>√</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p13249111443810"><a name="zh-cn_topic_0176540003_p13249111443810"></a><a name="zh-cn_topic_0176540003_p13249111443810"></a>√</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p1024910144382"><a name="zh-cn_topic_0176540003_p1024910144382"></a><a name="zh-cn_topic_0176540003_p1024910144382"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0176540003_row1881874393419"><td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p14469184916347"><a name="zh-cn_topic_0176540003_p14469184916347"></a><a name="zh-cn_topic_0176540003_p14469184916347"></a>自建Redis：Proxy集群</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p522114156385"><a name="zh-cn_topic_0176540003_p522114156385"></a><a name="zh-cn_topic_0176540003_p522114156385"></a>√</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p142212152382"><a name="zh-cn_topic_0176540003_p142212152382"></a><a name="zh-cn_topic_0176540003_p142212152382"></a>√</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p1522171513818"><a name="zh-cn_topic_0176540003_p1522171513818"></a><a name="zh-cn_topic_0176540003_p1522171513818"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0176540003_row1818124343420"><td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p2470949113414"><a name="zh-cn_topic_0176540003_p2470949113414"></a><a name="zh-cn_topic_0176540003_p2470949113414"></a>自建Redis：Cluster集群</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p106618164389"><a name="zh-cn_topic_0176540003_p106618164389"></a><a name="zh-cn_topic_0176540003_p106618164389"></a>√</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p2661416163818"><a name="zh-cn_topic_0176540003_p2661416163818"></a><a name="zh-cn_topic_0176540003_p2661416163818"></a>√</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p2066141614383"><a name="zh-cn_topic_0176540003_p2066141614383"></a><a name="zh-cn_topic_0176540003_p2066141614383"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0176540003_row2819184314341"><td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p124721133193520"><a name="zh-cn_topic_0176540003_p124721133193520"></a><a name="zh-cn_topic_0176540003_p124721133193520"></a>其他云Redis服务：单机/主备</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p17714328381"><a name="zh-cn_topic_0176540003_p17714328381"></a><a name="zh-cn_topic_0176540003_p17714328381"></a>×</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p137141326387"><a name="zh-cn_topic_0176540003_p137141326387"></a><a name="zh-cn_topic_0176540003_p137141326387"></a>×</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p127141129388"><a name="zh-cn_topic_0176540003_p127141129388"></a><a name="zh-cn_topic_0176540003_p127141129388"></a>×</p>
</td>
</tr>
<tr id="zh-cn_topic_0176540003_row1373512573516"><td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p1147223314359"><a name="zh-cn_topic_0176540003_p1147223314359"></a><a name="zh-cn_topic_0176540003_p1147223314359"></a>其他云Redis服务：Proxy集群</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p108671643383"><a name="zh-cn_topic_0176540003_p108671643383"></a><a name="zh-cn_topic_0176540003_p108671643383"></a>×</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p11867144133810"><a name="zh-cn_topic_0176540003_p11867144133810"></a><a name="zh-cn_topic_0176540003_p11867144133810"></a>×</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p19867164163810"><a name="zh-cn_topic_0176540003_p19867164163810"></a><a name="zh-cn_topic_0176540003_p19867164163810"></a>×</p>
</td>
</tr>
<tr id="zh-cn_topic_0176540003_row68191343153418"><td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p1547253363515"><a name="zh-cn_topic_0176540003_p1547253363515"></a><a name="zh-cn_topic_0176540003_p1547253363515"></a>其他云Redis服务：Cluster集群</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p11328713813"><a name="zh-cn_topic_0176540003_p11328713813"></a><a name="zh-cn_topic_0176540003_p11328713813"></a>×</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p143217743815"><a name="zh-cn_topic_0176540003_p143217743815"></a><a name="zh-cn_topic_0176540003_p143217743815"></a>×</p>
</td>
<td class="cellrowborder" valign="top"><p id="zh-cn_topic_0176540003_p7328743811"><a name="zh-cn_topic_0176540003_p7328743811"></a><a name="zh-cn_topic_0176540003_p7328743811"></a>×</p>
</td>
</tr>
</tbody>
</table>

>![](public_sys-resources/icon-note.gif) **说明：**   
>-   **华为云Redis**，指的是华为云分布式缓存服务的Redis。  
>-   **自建Redis**，指的是在华为云、其他云厂商、本地数据中心自行搭建Redis。  
>-   **其他云Redis服务**，指的是其他云厂商的Redis服务。  
>-   √表示支持，×表示不支持。  


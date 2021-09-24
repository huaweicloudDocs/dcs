# 使用DCS迁移介绍<a name="ZH-CN_TOPIC_0179456696"></a>

DCS控制台界面支持在线迁移和离线迁移（备份文件导入）两种方式，其中，在线迁移支持增量数据迁移。

-   离线迁移，适用于源Redis和目标Redis网络不连通、源Redis不支持SYNC/PSYNC命令的场景。需要将数据备份文件导入到OBS，DCS从OBS桶中读取数据，将数据迁移到华为云Redis中。
-   在线迁移，涉及到SYNC/PSYNC命令，适用于源Redis放通了SYNC/PSYNC命令的场景。支持将源Redis中的数据全量迁移或增量迁移到目标Redis中。

    进行在线迁移时，迁移执行机会向源端地址发送PSYNC命令，其原理可参考[Replication介绍](https://redis.io/topics/replication)，该命令会引起源端执行fork系统调用，对时延产生影响，其影响范围可参考[Redis官网](https://redis.io/topics/latency#latency-generated-by-fork)。


>![](public_sys-resources/icon-note.gif) **说明：** 
>当前数据迁移功能为公测免费，开始收费时间会另行通知。

更多迁移工具和方案介绍，请参考[迁移方案概览](https://support.huaweicloud.com/migration-dcs/dcs-migration-090626002.html)。

**表 1**  DCS支持的迁移能力

<a name="zh-cn_topic_0179456696_zh-cn_topic_0176540003_table1732614449178"></a>
<table><tbody><tr id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_row7327944161716"><th class="firstcol" rowspan="2" valign="top" id="mcps1.2.6.1.1"><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p20327194412170"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p20327194412170"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p20327194412170"></a>迁移类型</p>
</th>
<td class="cellrowborder" rowspan="2" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p179166209193"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p179166209193"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p179166209193"></a>源端</p>
</td>
<td class="cellrowborder" colspan="3" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p18279163818267"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p18279163818267"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p18279163818267"></a>目标端：DCS服务</p>
</td>
</tr>
<tr id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_row16168192410286"><td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p516811241288"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p516811241288"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p516811241288"></a>单机/主备</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p716811248286"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p716811248286"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p716811248286"></a>Proxy集群</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.1.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1116832415287"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1116832415287"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1116832415287"></a>Cluster集群</p>
</td>
</tr>
<tr id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_row6327244151714"><th class="firstcol" rowspan="2" valign="top" width="12.879999999999999%" id="mcps1.2.6.3.1"><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p23271044201715"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p23271044201715"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p23271044201715"></a>备份文件导入</p>
</th>
<td class="cellrowborder" valign="top" width="19.78%" headers="mcps1.2.6.3.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p232713446171"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p232713446171"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p232713446171"></a>OBS桶：AOF文件</p>
</td>
<td class="cellrowborder" valign="top" width="21.32%" headers="mcps1.2.6.3.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p19327544201716"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p19327544201716"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p19327544201716"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.310000000000002%" headers="mcps1.2.6.3.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p7197181473715"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p7197181473715"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p7197181473715"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.709999999999997%" headers="mcps1.2.6.3.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p230620162612"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p230620162612"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p230620162612"></a>×</p>
</td>
</tr>
<tr id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_row18327124419177"><td class="cellrowborder" valign="top" headers="mcps1.2.6.3.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p13887145514323"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p13887145514323"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p13887145514323"></a>OBS桶：RDB文件</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.3.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p83271044171712"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p83271044171712"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p83271044171712"></a>√</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.3.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p219819148377"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p219819148377"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p219819148377"></a>√</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.3.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1975522123817"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1975522123817"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1975522123817"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_row332704421710"><th class="firstcol" rowspan="9" valign="top" width="12.879999999999999%" id="mcps1.2.6.5.1"><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p532724414178"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p532724414178"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p532724414178"></a>在线迁移</p>
</th>
<td class="cellrowborder" valign="top" width="19.78%" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p23281144181716"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p23281144181716"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p23281144181716"></a>DCS Redis：单机/主备</p>
</td>
<td class="cellrowborder" valign="top" width="21.32%" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p99458238378"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p99458238378"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p99458238378"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="21.310000000000002%" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p139911924183713"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p139911924183713"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p139911924183713"></a>√</p>
</td>
<td class="cellrowborder" valign="top" width="24.709999999999997%" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p746562618370"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p746562618370"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p746562618370"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_row11328174451719"><td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p932894491715"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p932894491715"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p932894491715"></a>DCS Redis：Proxy集群</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p12328204421716"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p12328204421716"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p12328204421716"></a>√</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_p1582116511787"><a name="zh-cn_topic_0102134091_p1582116511787"></a><a name="zh-cn_topic_0102134091_p1582116511787"></a>√</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p231192062619"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p231192062619"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p231192062619"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_row793015576338"><td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1293085783318"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1293085783318"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1293085783318"></a>DCS Redis：Cluster集群</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1278073214373"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1278073214373"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1278073214373"></a>√</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p5180133493711"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p5180133493711"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p5180133493711"></a>√</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p202517354378"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p202517354378"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p202517354378"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_row1930165710331"><td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p16469124943418"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p16469124943418"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p16469124943418"></a>自建Redis：单机/主备</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p424921414382"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p424921414382"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p424921414382"></a>√</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p13249111443810"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p13249111443810"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p13249111443810"></a>√</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1024910144382"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1024910144382"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1024910144382"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_row1881874393419"><td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p14469184916347"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p14469184916347"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p14469184916347"></a>自建Redis：Proxy集群</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p522114156385"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p522114156385"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p522114156385"></a>√</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p142212152382"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p142212152382"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p142212152382"></a>√</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1522171513818"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1522171513818"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1522171513818"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_row1818124343420"><td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p2470949113414"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p2470949113414"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p2470949113414"></a>自建Redis：Cluster集群</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p106618164389"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p106618164389"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p106618164389"></a>√</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p2661416163818"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p2661416163818"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p2661416163818"></a>√</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p2066141614383"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p2066141614383"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p2066141614383"></a>√</p>
</td>
</tr>
<tr id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_row2819184314341"><td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p124721133193520"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p124721133193520"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p124721133193520"></a>其他云Redis服务：单机/主备</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p17714328381"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p17714328381"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p17714328381"></a>×</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p137141326387"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p137141326387"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p137141326387"></a>×</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p127141129388"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p127141129388"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p127141129388"></a>×</p>
</td>
</tr>
<tr id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_row1373512573516"><td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1147223314359"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1147223314359"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1147223314359"></a>其他云Redis服务：Proxy集群</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p108671643383"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p108671643383"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p108671643383"></a>×</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p11867144133810"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p11867144133810"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p11867144133810"></a>×</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p19867164163810"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p19867164163810"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p19867164163810"></a>×</p>
</td>
</tr>
<tr id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_row68191343153418"><td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1547253363515"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1547253363515"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p1547253363515"></a>其他云Redis服务：Cluster集群</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p11328713813"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p11328713813"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p11328713813"></a>×</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p143217743815"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p143217743815"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p143217743815"></a>×</p>
</td>
<td class="cellrowborder" valign="top" headers="mcps1.2.6.5.1 "><p id="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p7328743811"><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p7328743811"></a><a name="zh-cn_topic_0102134091_zh-cn_topic_0179456696_zh-cn_topic_0176540003_p7328743811"></a>×</p>
</td>
</tr>
</tbody>
</table>

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   **DCS Redis**，指的是分布式缓存服务的Redis。
>-   **自建Redis**，指的是在云上、其他云厂商、本地数据中心自行搭建Redis。
>-   **其他云Redis服务**，指的是其他云厂商的Redis服务。
>-   √表示支持，×表示不支持。


# 实例交换IP<a name="ZH-CN_TOPIC_0000001148100324"></a>

## 场景描述<a name="section19329103914358"></a>

实例规格变更目前只支持同类型实例间的扩容和缩容，不支持跨实例类型的变更。因此我们可以通过“数据迁移+交换IP”方式实现跨实例类型的规格变更。同时，还可通过该方式更改实例可用区及CPU架构。

-   通过在线迁移方式将数据迁移之后，交换两个实例的IP。
-   交换IP后支持回滚功能。

>![](public_sys-resources/icon-note.gif) **说明：** 
>-   目前支持实例交换IP功能的Region有：北京四、上海一，若其他Region也需使用此功能，请您在控制台提交工单，技术人员会在后台为您进行开通。
>-   只有Redis4.0及Redis5.0支持实例交换IP。
>-   只有源实例和目标实例都为云服务Redis实例才支持实例交换IP。

## 前提条件<a name="zh-cn_topic_0177563520_section393611177"></a>

-   获取源实例及目标实例信息，可参考[步骤2：准备目标Redis实例](在线迁移方式.md#zh-cn_topic_0177563541_section1128152020384)准备目标实例。
-   参考[步骤:3：检查网络](在线迁移方式.md#zh-cn_topic_0177563541_section84284075116)确保源实例和目标实例网络互通。
-   进行实例交换IP满足的条件为：
    -   进行实例IP交换依赖的是数据迁移功能，所以，源实例及目标实例必须支持数据迁移功能，详见[表1](使用DCS迁移介绍.md#zh-cn_topic_0179456696_zh-cn_topic_0176540003_table1732614449178)。
    -   源实例和目标实例都为云服务Redis实例。
    -   交换IP支持的能力如下[表1](#table09121148162513)。

        **表 1**  交换ip能力

        <a name="table09121148162513"></a>
        <table><thead align="left"><tr id="row139110486254"><th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.1"><p id="p9911948112516"><a name="p9911948112516"></a><a name="p9911948112516"></a>源端</p>
        </th>
        <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.2"><p id="p491116486258"><a name="p491116486258"></a><a name="p491116486258"></a>目标端</p>
        </th>
        <th class="cellrowborder" valign="top" width="33.33333333333333%" id="mcps1.2.4.1.3"><p id="p791114818256"><a name="p791114818256"></a><a name="p791114818256"></a>备注</p>
        </th>
        </tr>
        </thead>
        <tbody><tr id="row691214486252"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p16912194815257"><a name="p16912194815257"></a><a name="p16912194815257"></a>单机/主备/读写分离</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p12912148132518"><a name="p12912148132518"></a><a name="p12912148132518"></a>单机/主备/读写分离/proxy集群</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p12912348132519"><a name="p12912348132519"></a><a name="p12912348132519"></a>-</p>
        </td>
        </tr>
        <tr id="row1491212483255"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p4912948102512"><a name="p4912948102512"></a><a name="p4912948102512"></a>Proxy集群</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p0912184810254"><a name="p0912184810254"></a><a name="p0912184810254"></a>单机/主备/读写分离/proxy集群</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p189121648182516"><a name="p189121648182516"></a><a name="p189121648182516"></a>-</p>
        </td>
        </tr>
        <tr id="row3912124812255"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p1091213484258"><a name="p1091213484258"></a><a name="p1091213484258"></a>Cluster集群</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p4912154822518"><a name="p4912154822518"></a><a name="p4912154822518"></a>Cluster集群（分片数增加）</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p391254820253"><a name="p391254820253"></a><a name="p391254820253"></a>源端实例选择全部ip进行交换</p>
        <div class="notice" id="note1991284818252"><a name="note1991284818252"></a><a name="note1991284818252"></a><span class="noticetitle"> 须知： </span><div class="noticebody"><p id="p2912204822518"><a name="p2912204822518"></a><a name="p2912204822518"></a>源端及目标端必须是相同子网。</p>
        </div></div>
        </td>
        </tr>
        <tr id="row69121848112517"><td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.1 "><p id="p89121948172517"><a name="p89121948172517"></a><a name="p89121948172517"></a>Cluster集群</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.2 "><p id="p89121848122519"><a name="p89121848122519"></a><a name="p89121848122519"></a>Cluster集群（分片数减少）</p>
        </td>
        <td class="cellrowborder" valign="top" width="33.33333333333333%" headers="mcps1.2.4.1.3 "><p id="p891254813258"><a name="p891254813258"></a><a name="p891254813258"></a>源端实例选择部分ip进行交换</p>
        <div class="notice" id="note1912948162512"><a name="note1912948162512"></a><a name="note1912948162512"></a><span class="noticetitle"> 须知： </span><div class="noticebody"><p id="p891211489251"><a name="p891211489251"></a><a name="p891211489251"></a>源端及目标端必须是相同子网。</p>
        </div></div>
        </td>
        </tr>
        </tbody>
        </table>



## 交换IP须知<a name="section02191539882"></a>

1.  交换IP过程中，会自动停止在线迁移任务。
2.  交换实例IP地址时，会有一分钟内只读和秒级的闪断。
3.  请确保您的客户端应用具备重连机制和处理异常的能力，否则在交换IP后有可能需要重启客户端应用。
4.  源实例和目标实例不在同一子网时，交换IP地址后，会更新实例的子网信息。
5.  如果源端是主备实例，交换IP时不会交换备节点IP，请确保应用中没有直接引用备节点IP。
6.  如果应用中有直接引用域名，请选择交换域名，否则域名会挂在源实例中。
7.  请确保目标Redis和源Redis密码一致，否则交换IP后，客户端会出现密码验证错误。
8.  当Cluster集群分片数减少时，只能选择源端实例的部分IP进行交换，请确保应用中没有直接引用未进行交换的IP。

## 交换IP操作步骤<a name="section525820381326"></a>

1.  登录[分布式缓存服务管理控制台](https://console.huaweicloud.com/dcs)。
2.  在管理控制台左上角单击![](figures/icon-region.png)，选择区域和项目。
3.  单击左侧菜单栏的“数据迁移”。
4.  参考[步骤4：创建在线迁移任务](在线迁移方式.md#zh-cn_topic_0177563541_section157769524519)创建迁移任务。
5.  参考[步骤5：配置在线迁移任务](在线迁移方式.md#zh-cn_topic_0177563541_section14919536272)配置迁移任务，此处迁移方式只能选择“全量迁移+增量迁移”。
6.  在“在线迁移”页面，当迁移任务状态显示为“增量迁移中”时，单击操作列的“更多 \> 交换IP”打开交换IP弹框。
7.  在交换IP弹框中，在交换域名区域，选择是否交换域名。

    >![](public_sys-resources/icon-note.gif) **说明：** 
    >-   如果使用域名，则必须要选择交换域名，否则客户端应用需要修改使用的域名。
    >-   如果没有使用域名，则直接更新两个实例的DNS。

8.  单击“确定”，交换IP任务提交成功，当迁移任务的状态显示为“IP交换成功”，表示交换IP任务完成。

## 回滚IP操作步骤<a name="section14894173013269"></a>

若您想将实例IP切换成原始的IP，请执行以下操作。

1.  登录[分布式缓存服务管理控制台](https://console.huaweicloud.com/dcs)。
2.  在管理控制台左上角单击![](figures/icon-region.png)，选择区域和项目。
3.  单击左侧菜单栏的“数据迁移”。
4.  在“在线迁移”页面，迁移任务状态为“IP交换成功”，单击操作列的“更多 \> 回滚IP”。
5.  在确认框中，单击“确定”，IP回滚任务提交成功。但任务状态显示为“IP回滚成功”表示回滚任务完成。


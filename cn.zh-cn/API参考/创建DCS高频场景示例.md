# 创建DCS高频场景示例<a name="dcs-api-211104001"></a>

本节介绍了使用API购买DCS实例过程中的一些常见问题及处理方法。

**表 1**  购买DCS实例常见问题及处理方法

<a name="table10726475020"></a>
<table><thead align="left"><tr id="row197218471016"><th class="cellrowborder" valign="top" width="49.43%" id="mcps1.2.3.1.1"><p id="p157316471806"><a name="p157316471806"></a><a name="p157316471806"></a>常见问题</p>
</th>
<th class="cellrowborder" valign="top" width="50.57000000000001%" id="mcps1.2.3.1.2"><p id="p1773947505"><a name="p1773947505"></a><a name="p1773947505"></a>处理方法</p>
</th>
</tr>
</thead>
<tbody><tr id="row18731847003"><td class="cellrowborder" valign="top" width="49.43%" headers="mcps1.2.3.1.1 "><p id="p14734479015"><a name="p14734479015"></a><a name="p14734479015"></a><a href="#section4977542173219">购买包周期实例</a></p>
</td>
<td class="cellrowborder" valign="top" width="50.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p187315471002"><a name="p187315471002"></a><a name="p187315471002"></a>为您介绍购买包周期实例时参数设置。</p>
</td>
</tr>
<tr id="row195651336155316"><td class="cellrowborder" valign="top" width="49.43%" headers="mcps1.2.3.1.1 "><p id="p105652036195319"><a name="p105652036195319"></a><a name="p105652036195319"></a><a href="#section15996103755518">删除包周期实例</a></p>
</td>
<td class="cellrowborder" valign="top" width="50.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p195657367532"><a name="p195657367532"></a><a name="p195657367532"></a>包周期资源需要通过退订的方式才可以被删除。</p>
</td>
</tr>
<tr id="row973047404"><td class="cellrowborder" valign="top" width="49.43%" headers="mcps1.2.3.1.1 "><p id="p10735478011"><a name="p10735478011"></a><a name="p10735478011"></a><a href="#section1625019213483">使用API购买实例时设置副本数</a></p>
</td>
<td class="cellrowborder" valign="top" width="50.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p77316471206"><a name="p77316471206"></a><a name="p77316471206"></a>使用API购买的实例，副本数的值取决于在购买时输入的spec_code参数，为调用<a href="查询产品规格.md">查询产品规格</a>响应示例中replica_count的值。</p>
</td>
</tr>
<tr id="row69721332144"><td class="cellrowborder" valign="top" width="49.43%" headers="mcps1.2.3.1.1 "><p id="p99732333144"><a name="p99732333144"></a><a name="p99732333144"></a><a href="#section1435114494417">获取子网ID</a></p>
</td>
<td class="cellrowborder" valign="top" width="50.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p14973183313143"><a name="p14973183313143"></a><a name="p14973183313143"></a>通过查询子网ID接口，获取正确的ID供购买实例时配置。</p>
</td>
</tr>
<tr id="row57310479013"><td class="cellrowborder" valign="top" width="49.43%" headers="mcps1.2.3.1.1 "><p id="p1073124714015"><a name="p1073124714015"></a><a name="p1073124714015"></a><a href="#section1015082315582">购买实例时可用区资源不足</a></p>
</td>
<td class="cellrowborder" valign="top" width="50.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p87394718018"><a name="p87394718018"></a><a name="p87394718018"></a>可用区资源不足会导致创建实例失败，可通过调用<a href="查询产品规格.md">查询产品规格</a>响应示例中flavors_available_zones.az_codes的值来确保在购买实例时选择充足资源的可用区。</p>
</td>
</tr>
<tr id="row147311471802"><td class="cellrowborder" valign="top" width="49.43%" headers="mcps1.2.3.1.1 "><p id="p11738473013"><a name="p11738473013"></a><a name="p11738473013"></a><a href="#section10138171616811">查看资源的可用配额</a></p>
</td>
<td class="cellrowborder" valign="top" width="50.57000000000001%" headers="mcps1.2.3.1.2 "><p id="p197310471806"><a name="p197310471806"></a><a name="p197310471806"></a>通过调用<a href="查询租户配额.md">查询租户配额</a>接口，通过quota值可确定可以创建的实例最大数和总内存的配额限制。</p>
</td>
</tr>
</tbody>
</table>

## 购买包周期实例<a name="section4977542173219"></a>

您可使用[创建缓存实例](创建缓存实例.md)接口购买包周期实例，其与购买按需实例的区别在于，购买实例的body体中，将bss\_param.charging\_mode字段配置为“prePaid”，

bss\_param的详细介绍请参考[表3](创建缓存实例.md#request_BssParam)。

如下请求体所示，在cn-north-4区域购买一个包周期DCS实例，时长为一个月，且下单后不自动续订，不自动付费。

```
{
 "name": "test",
 "engine": "Redis",
 "engine_version": "5.0",
 "capacity": 2,
 "spec_code": "redis.ha.xu1.large.r2.2",
 "az_codes": [
  "cn-north-4a"
 ],
 "vpc_id": "c29eade3-05d3-41a3-84e4-2cc1f3057502",
 "subnet_id": "b573d369-2b49-4595-8727-2408244a7675",
 "no_password_access": true,
 "bss_param": {
  "charging_mode": "prePaid",
  "is_auto_pay": "false",
  "period_type": "month",
  "period_num": 2
 },
 "instance_backup_policy": {
  "backup_type": "auto",
  "save_days": 2,
  "periodical_backup_plan": {
   "backup_at": [
    2
   ],
   "period_type": "weekly",
   "begin_at": "00:00-01:00"
  }
 },
 "tags": [
  {
   "key": "test",
   "value": "123"
  }
 ]
}
```

购买任务提交成功后，会返回以下order\_id，即订单ID。

```
{
 "instance_id": "23be3a34-8cc1-4eab-9ad2-b085eadee9c4",
 "order_id": "CS2111091732PY0DE",
 "instances": [
  {
   "instance_id": "23be3a34-8cc1-4eab-9ad2-b085eadee9c4",
   "instance_name": "test"
  }
 ]
}
```

上面请求体中bss\_param.is\_auto\_pay取值为false或不填该字段则需要手动去支付，手动支付可以填写优惠券和折扣券等信息。手动支付需要调用[支付包年/包月产品订单](https://support.huaweicloud.com/api-oce/api_order_00016.html)支付，示例如下。

```
POST https://bss.myhuaweicloud.com/v2/orders/customer-orders/pay
{
  "order_id": "CS2111091732PY0DE"
}
```

## 删除包周期实例<a name="section15996103755518"></a>

包周期的DCS实例无法直接删除，需要调用[退订包年/包月资源](https://support.huaweicloud.com/api-oce/api_order_00019.html)接口进行退订。

```
POST https://bss.myhuaweicloud.com/v2/orders/subscriptions/resources/unsubscribe
{
   "resource_ids": [
   "44b393c8-e4e4-4dcb-bad3-54858dcc72c7"
 ],
   "unsubscribe_type": 1
}
```

其中resource\_ids表示资源ID，对退订DCS来说，就是购买包周期DCS时返回的instance\_id。

## 使用API购买实例时设置副本数<a name="section1625019213483"></a>

使用API购买实例后，副本数的值取决于在购买时输入的spec\_code参数。副本数即为[查询产品规格](查询产品规格.md)接口响应示例的replica\_count值。

请求示例：

```
GET https://{dcs_endpoint}/v2/flavors?cache_mode={cache_mode}&engine={engine}&engine_version={engine_version}&cpu_type={cpu_type}&capacity={capacity}
```

响应示例：

```
{
 "flavors": [
  {
   "dec": false,
   "spec_code": "redis.ha.xu1.large.r4.2",
   "cloud_service_type_code": "hws.service.type.dcs",
   "cloud_resource_type_code": "hws.resource.type.dcs3",
   "cache_mode": "ha",
   "engine": "redis",
   "engine_version": "4.0;5.0",
   "product_type": "generic",
   "cpu_type": "x86_64",
   "storage_type": "DRAM",
   "capacity": [
    "2"
   ],
   "billing_mode": [
    "Hourly",
    "Monthly",
    "Yearly"
   ],
   "tenant_ip_count": 4,
   "pricing_type": "normal",
   "is_dec": false,
   "attrs": [
    {
     "capacity": "2",
     "name": "max_memory",
     "value": "2"
    },
    {
     "capacity": "2",
     "name": "max_connections",
     "value": "50000"
    },
    {
     "capacity": "2",
     "name": "sharding_num",
     "value": "1"
    },
    {
     "capacity": "2",
     "name": "proxy_num",
     "value": "0"
    },
    {
     "capacity": "2",
     "name": "db_number",
     "value": "256"
    },
    {
     "capacity": "2",
     "name": "max_clients",
     "value": "10000"
    },
    {
     "capacity": "2",
     "name": "max_bandwidth",
     "value": "128"
    }
   ],
   "flavors_available_zones": [
    {
     "capacity": "2",
     "unit": "GB",
     "available_zones": [
      "a0865121f83b41cbafce65930a22a6e8",
      "15dcd3f789cb4fc088dbdece9c5eb547",
      "2dcb154ac2724a6d92e9bcc859657c1e",
      "effdcbc7d4d64a02aa1fa26b42f56533"
     ],
     "az_codes": [
      "cn-north-4b",
      "cn-north-4g",
      "cn-north-4c",
      "cn-north-4a"
     ]
    }
   ],
   "replica_count": 4,
   "inquery_spec_code": null
  }
 ]
}
```

>![](public_sys-resources/icon-note.gif) **说明：** 
>在购买实例时，输入的spec\_code参数须与capacity参数一一对应。

## 获取子网ID<a name="section1435114494417"></a>

在购买实例时配置正确的子网ID，才能够成功连接实例。可通过GET /v1/\{project\_id\}/subnets?\{vpc\_id\}获取准确子网ID，其中vpc\_id可通过GET /v1/\{project\_id\}/vpcs接口获取。

获取vpc\_id的请求示例：

```
GET https://{vpc_endpoint}/v1/7d80ae32f57b499eb8781f9a9f57c538/vpcs
```

\{vpc\_endpoint\}信息，请从[地区和终端节点](https://developer.huaweicloud.com/endpoint)获取。

获取vpc\_id的响应示例：

```
{
	"vpcs": [{
		"id": "743bf021-2c2d-4511-aeac-85bd48c06af7",
		"name": "vpc-d2d4",
		"description": "",
		"cidr": "192.168.0.0/16",
		"status": "OK",
		"routes": [],
		"enterprise_project_id": "0"
	}]
}
```

获取子网ID的请求示例：

```
GET https://{vpc_endpoint}/v1/7d80ae32f57b499eb8781f9a9f57c538/subnets?vpc_id=743bf021-2c2d-4511-aeac-85bd48c06af7
```

获取子网ID的响应示例：

```
{
	"subnets": [{
		"id": "b0d6e0ac-fcce-4e11-a4a6-707e851ae1c3",
		"name": "subnet-d2e4",
		"description": "",
		"cidr": "192.168.0.0/24",
		"dnsList": ["100.125.1.250",
		"100.125.129.250"],
		"status": "ACTIVE",
		"vpc_id": "743bf021-2c2d-4511-aeac-85bd48c06af7",
		"ipv6_enable": false,
		"gateway_ip": "192.168.0.1",
		"dhcp_enable": true,
		"primary_dns": "100.125.1.250",
		"secondary_dns": "100.125.129.250",
		"availability_zone": "cn-southwest-2a",
		"neutron_network_id": "b0d6e0ac-fcce-4e11-a4a6-707e851ae1c3",
		"neutron_subnet_id": "3d4ccce0-cadc-4af4-8c21-14d2857ffe5e",
		"extra_dhcp_opts": []
	}]
}
```

## 购买实例时可用区资源不足<a name="section1015082315582"></a>

在购买实例时，如需要查询某一规格在某可用区是否资源充足，可通过调用[查询产品规格](查询产品规格.md)查看规格所在可用区的详细信息，通过flavors\_available\_zones的值判断该规格可选的可用区。

如在北京四、规格为redis.ha.xu1.large.r2.2的资源充足可用区的信息，请求示例：

```
https://dcs.cn-north-4.myhuaweicloud.com/v2/05041fffa40025702f6dc009cc6f8f33/flavors?spec_code=redis.ha.xu1.large.r2.2
```

响应示例：

```
{
 "flavors": [
  {
   "dec": false,
   "spec_code": "redis.ha.xu1.large.r2.2",
   "cloud_service_type_code": "hws.service.type.dcs",
   "cloud_resource_type_code": "hws.resource.type.dcs3",
   "cache_mode": "ha",
   "engine": "redis",
   "engine_version": "4.0;5.0",
   "product_type": "generic",
   "cpu_type": "x86_64",
   "storage_type": "DRAM",
   "capacity": [
    "2"
   ],
   "billing_mode": [
    "Hourly",
    "Monthly",
    "Yearly"
   ],
   "tenant_ip_count": 2,
   "pricing_type": "normal",
   "is_dec": false,
   "attrs": [
    {
     "capacity": "2",
     "name": "max_memory",
     "value": "2"
    },
    {
     "capacity": "2",
     "name": "max_connections",
     "value": "50000"
    },
    {
     "capacity": "2",
     "name": "sharding_num",
     "value": "1"
    },
    {
     "capacity": "2",
     "name": "proxy_num",
     "value": "0"
    },
    {
     "capacity": "2",
     "name": "db_number",
     "value": "256"
    },
    {
     "capacity": "2",
     "name": "max_clients",
     "value": "10000"
    },
    {
     "capacity": "2",
     "name": "max_bandwidth",
     "value": "128"
    }
   ],
   "flavors_available_zones": [
    {
     "capacity": "2",
     "unit": "GB",
     "available_zones": [
      "a0865121f83b41cbafce65930a22a6e8",
      "15dcd3f789cb4fc088dbdece9c5eb547",
      "2dcb154ac2724a6d92e9bcc859657c1e",
      "effdcbc7d4d64a02aa1fa26b42f56533"
     ],
     "az_codes": [
      "cn-north-4b",
      "cn-north-4g",
      "cn-north-4c",
      "cn-north-4a"
     ]
    }
   ],
   "replica_count": 2,
   "inquery_spec_code": null
  }
 ]
}
```

其中flavors\_available\_zones罗列出了该规格资源充足的可用区。

## 查看资源的可用配额<a name="section10138171616811"></a>

如需查询当前帐号号的资源配额信息，包括已使用的配额，可以通过调用[查询租户配额](查询租户配额.md)接口。

请求示例：

```
GET https://dcs.cn-north-4.myhuaweicloud.com/v2/05041fffa40025702f6dc009cc6f8f33/quota
```

响应示例：

```
{
 "quotas": {
  "resources": [
   {
    "quota": 160,
    "used": 1,
    "type": "instance",
    "min": 0,
    "max": 2147483647,
    "unit": null
   },
   {
    "quota": 64000,
    "used": 0,
    "type": "ram",
    "min": 0,
    "max": 1048576,
    "unit": "GB"
   }
  ]
 }
}
```

-   当type为instance时，max表示可申请实例配额的最大值，min表示可申请实例配额的最小值。
-   当type为ram时，max表示可申请内存配额的最大值，min表示可申请内存配额的最小值。
-   quota为可以创建的实例最大数和总内存的配额限制。
-   used为已创建的实例个数和已使用的内存配额。


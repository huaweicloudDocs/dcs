# 示例1：创建Redis实例<a name="dcs-api-0514011"></a>

## 场景描述<a name="section2234145810131"></a>

本章节指导用户通过API创建Redis实例。API的调用方法请参见[如何调用API](如何调用API.md)。

本文以创建一个实例规格为2G、缓存版本为Redis5.0、实例类型为单机、CPU架构为ARM、免密访问方式的缓存实例。

## 涉及接口<a name="section6243173314149"></a>

创建Redis实例时，需要进行查询产品规格、查询VPC、子网等操作，涉及的API如下：

-   [查询VPC ID](#section67361836263)：确定待创建DCS实例的VPC ID。
-   [查询子网ID](#section1891455519611)：确定待创建DCS实例的子网ID。
-   [查询产品规格](#section1047010717713)：确定待创建DCS实例的产品规格。
-   [创建实例](#section5713171772)：创建指定规格的DCS实例。
-   [查询创建结果](#section941224874)：确认创建DCS实例是否成功。

## 步骤1：确定待创建实例的VPC<a name="section67361836263"></a>

1.  查询VPC列表。
    -   接口相关信息

        URI格式：GET /v1/\{project\_id\}/vpcs

    -   请求示例

        GET https://\{vpc\_endpoint\}/v1/7d80ae32f57b499eb8781f9a9f57c538/vpcs

        \{vpc\_endpoint\}信息，请从[地区和终端节点](https://developer.huaweicloud.com/endpoint)获取。

    -   响应示例

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

2.  根据需要，记录VPC ID。

## 步骤2：确定待创建实例的子网<a name="section1891455519611"></a>

1.  查询子网列表。
    -   接口相关信息

        URI格式：GET /v1/\{project\_id\}/subnets?\{vpc\_id\}

    -   请求示例

        GET https://\{vpc\_endpoint\}/v1/7d80ae32f57b499eb8781f9a9f57c538/subnets?vpc\_id=743bf021-2c2d-4511-aeac-85bd48c06af7

        \{vpc\_endpoint\}信息，请从[地区和终端节点](https://developer.huaweicloud.com/endpoint)获取。

    -   响应示例

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

2.  根据需要，记录子网ID。

## 步骤3：确定待创建实例的产品规格<a name="section1047010717713"></a>

1.  查询产品规格。
    -   接口相关信息

        URI格式：GET /v2/\{project\_id\}/flavors?spec\_code=\{spec\_code\}&cache\_mode=\{cache\_mode\}&engine=\{engine\}&engine\_version=\{engine\_version\}&cpu\_type=\{cpu\_type\}&capacity=\{capacity\}

    -   请求示例

        GET https://\{dcs\_endpoint\}/v2/666486c2d9b948c1bbea57e714d744fa/flavors?cache\_mode=single&engine=Redis&engine\_version=5.0&cpu\_type=aarch64&capacity=2

        \{dcs\_endpoint\}信息请从[地区和终端节点](https://developer.huaweicloud.com/endpoint)获取。

    -   响应示例

        ```
        [{
        	"dec": false,
        	"spec_code": "redis.single.au1.large.2",
        	"cloud_service_type_code": "hws.service.type.dcs",
        	"cloud_resource_type_code": "hws.resource.type.dcs3",
        	"cache_mode": "single",
        	"engine": "redis",
        	"engine_version": "4.0;5.0",
        	"product_type": "generic",
        	"cpu_type": "aarch64",
        	"storage_type": "DRAM",
        	"capacity": ["2"],
        	"billing_mode": ["Hourly",
        	"RI",
        	"Monthly",
        	"Yearly"],
        	"tenant_ip_count": 1,
        	"pricing_type": "normal",
        	"is_dec": false,
        	"attrs": [{
        		"capacity": "2",
        		"name": "max_memory",
        		"value": "2"
        	},
        	{
        		"capacity": "2",
        		"name": "max_connections",
        		"value": "10000"
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
        	}],
        	"flavors_available_zones": [{
        		"capacity": "2",
        		"unit": "GB",
        		"available_zones": ["a0865121f83b41cbafce65930a22a6e8",
        		"effdcbc7d4d64a02aa1fa26b42f56533"],
        		"az_codes": ["cn-north-4b",
        		"cn-north-4a"]
        	}]
        }]
        ```

2.  根据需要选择产品类型，并记录产品规格编码和有资源的可用区编码。

## 步骤4：创建实例<a name="section5713171772"></a>

-   接口相关信息

    URI格式：POST /v2/\{project\_id\}/instances

-   请求示例

    POST  https://\{dcs\_endpoint\}/v2/666486c2d9b948c1bbea57e714d744fa/instances

    \{dcs\_endpoint\}信息请从[地区和终端节点](https://developer.huaweicloud.com/endpoint)获取。

    Body：

    ```
    {
    	"az_codes": ["cn-north-4a"],
    	"capacity": 2,
    	"engine": "Redis",
    	"engine_version": "5.0",
    	"name": "dcs-api-test",
    	"no_password_access": true,
    	"security_group_id": "1982d3a8-67a0-4fc9-a850-bc42a26ba2c0",
    	"spec_code": "redis.single.au1.large.2",
    	"subnet_id": "b0d6e0ac-fcce-4e11-a4a6-707e851ae1c3",
    	"vpc_id": "743bf021-2c2d-4511-aeac-85bd48c06af7"
    }
    ```

-   响应示例

    ```
    {
    	"instances": [{
    		"instance_id": "21bc7b53-2494-4f10-bb0b-c0b913d9e329",
    		"instance_name": "dcs-api-test"
    	}]
    }
    ```


## 步骤5：查询创建结果<a name="section941224874"></a>

-   接口相关信息

    URI格式：GET /v2/\{project\_id\}/instances/\{instance\_id\}

-   请求示例

    GEThttps://\{dcs\_endpoint\}/v2/666486c2d9b948c1bbea57e714d744fa/instances/21bc7b53-2494-4f10-bb0b-c0b913d9e329

    \{dcs\_endpoint\}信息请从[地区和终端节点](https://developer.huaweicloud.com/endpoint)获取。

-   响应示例

    ```
    {
    	"free": null,
    	"max_memory": 2048,
    	"used_memory": 1,
    	"instance_id": "21bc7b53-2494-4f10-bb0b-c0b913d9e329",
    	"name": "dcs-api-test",
    	"resource_spec_code": "redis.single.au1.large.2",
    	"engine": "Redis",
    	"engine_version": "5.0",
    	"internal_version": null,
    	"charging_mode": 0,
    	"capacity": 2,
    	"capacity_minor": null,
    	"vpc_id": "743bf021-2c2d-4511-aeac-85bd48c06af7",
    	"vpc_name": "vpc-d2d4",
    	"ip": "192.168.0.100",
    	"domain_name": "redis-88a7bbb-dcs-api-test.dcs.huaweicloud.com",
    	"readonly_domain_name": null,
    	"port": 6379,
    	"status": "RUNNING",
    	"freeze_scene": null,
    	"created_at": "2020-06-05T03:30:36.273Z",
    	"update_at": "2020-06-05T03:30:47.231Z",
    	"error_code": null,
    	"user_id": "d53977d1adfb49c5b025ba7d33a13fd7",
    	"user_name": "paas_dcs_a00421997_02",
    	"maintain_begin": "02:00:00",
    	"maintain_end": "06:00:00",
    	"no_password_access": "true",
    	"access_user": null,
    	"enable_publicip": false,
    	"publicip_id": null,
    	"publicip_address": null,
    	"enable_ssl": false,
    	"service_upgrade": false,
    	"service_task_id": "",
    	"enterprise_project_id": "0",
    	"security_group_id": null,
    	"tags": [],
    	"product_type": "generic",
    	"cpu_type": "aarch64",
    	"storage_type": "DRAM",
    	"launched_at": "2020-06-05T03:30:47.238Z",
    	"is_free": null,
    	"libos": false,
    	"cache_mode": "single",
    	"available_zones": ["d539378ec1314c85b76fefa3f7071458"],
    	"subnet_id": "a4112635-3ec0-471c-95c3-5cf49b9533af",
    	"backend_addrs": null,
    	"crr_role": null,
    	"cloud_service_type_code": "hws.service.type.dcs",
    	"cloud_resource_type_code": "hws.resource.type.dcs3",
    	"support_slow_log_flag": null,
    	"ipv6": null,
    	"enable_ipv6": false,
    	"description": "",
    	"product_id": "redis.single.au1.large.2-h",
    	"security_group_name": null,
    	"subnet_name": "dcs-beta",
    	"order_id": null,
    	"subnet_cidr": "192.168.0.0/24",
    	"task": null,
    	"instance_backup_policy": null,
    	"enterprise_project_name": null
    }
    ```

    实例状态为RUNNING时，即创建成功。



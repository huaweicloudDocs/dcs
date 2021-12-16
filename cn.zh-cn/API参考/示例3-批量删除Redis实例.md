# 示例3：批量删除Redis实例<a name="dcs-api-0618001"></a>

## 场景描述<a name="section2234145810131"></a>

本章节指导用户通过API批量删除Redis实例。API的调用方法请参见[如何调用API](如何调用API.md)。

## 涉及接口<a name="section6243173314149"></a>

批量删除Redis实例时，需要进行查询待删除实例的ID，涉及的API如下：

-   [查询实例ID](#section1659412211258)：查询待删除Redis实例的ID。
-   [批量删除实例](#section059682113517)：批量删除Redis实例。

## 步骤1：查询待删除实例的ID<a name="section1659412211258"></a>

1.  查询实例ID。
    -   接口相关信息

        URI格式：GET /v2/\{project\_id\}/instances

    -   请求示例

        GET https://\{dcs\_endpoint\}/v2/7d80ae32f57b499eb8781f9a9f57c538/instances

        \{dcs\_endpoint\}信息，请从[地区和终端节点](https://developer.huaweicloud.com/endpoint)获取。

    -   响应示例

        ```
        {
        	"instances": [{
        		"free": null,
        		"max_memory": 1024,
        		"used_memory": 2,
        		"instance_id": "aabe73af-1db8-4401-b39c-c56996023989",
        		"name": "dcs-8b1c-000",
        		"resource_spec_code": "redis.ha.xu1.large.r2.1",
        		"engine": "Redis",
        		"engine_version": "5.0",
        		"internal_version": null,
        		"charging_mode": 0,
        		"capacity": 1,
        		"capacity_minor": null,
        		"vpc_id": "cec3dca1-3700-4305-8eb0-5669c01f05b6",
        		"vpc_name": null,
        		"ip": "192.168.0.12",
        		"domainName": "redis-aabe73a-dcs-8b1c-000.dcs.huaweicloud.com",
        		"domain_name": "redis-aabe73a-dcs-8b1c-000.dcs.huaweicloud.com",
        		"readonlyDomainName": null,
        		"readonly_domain_name": null,
        		"port": 6379,
        		"status": "RUNNING",
        		"freeze_scene": null,
        		"created_at": "2020-06-18T03:11:30.615Z",
        		"update_at": "2020-06-18T03:11:58.936Z",
        		"error_code": null,
        		"user_id": "05040c67cc00256f1f28c009a1c2a0f7",
        		"user_name": "dcstest",
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
        		"tags": null,
        		"product_type": "generic",
        		"cpu_type": "x86_64",
        		"storage_type": "DRAM",
        		"task_status": null,
        		"launched_at": "2020-06-18T03:11:58.945Z",
        		"is_free": null,
        		"libos": false,
        		"cache_mode": "ha",
        		"available_zones": ["dfeb4826256b47aa828e72d7522e108c",
        		"043c7e39ecb347a08dc8fcb6c35a274e"],
        		"subnet_id": "e6eb5ff4-da2a-4323-bddc-c7b179f9aa1e",
        		"backend_addrs": null,
        		"crr_role": null,
        		"cloud_service_type_code": "hws.service.type.dcs",
        		"cloud_resource_type_code": "hws.resource.type.dcs3",
        		"support_slow_log_flag": null,
        		"ipv6": null,
        		"enable_ipv6": false,
        		"description": ""
        	},
        	{
        		"free": null,
        		"max_memory": 1024,
        		"used_memory": 2,
        		"instance_id": "9d78d0f4-a110-4bcd-8ca3-5aec414163c1",
        		"name": "dcs-8b1c-001",
        		"resource_spec_code": "redis.ha.xu1.large.r2.1",
        		"engine": "Redis",
        		"engine_version": "5.0",
        		"internal_version": null,
        		"charging_mode": 0,
        		"capacity": 1,
        		"capacity_minor": null,
        		"vpc_id": "cec3dca1-3700-4305-8eb0-5669c01f05b6",
        		"vpc_name": null,
        		"ip": "192.168.0.33",
        		"domainName": "redis-9d78d0f-dcs-8b1c-001.dcs.huaweicloud.com",
        		"domain_name": "redis-9d78d0f-dcs-8b1c-001.dcs.huaweicloud.com",
        		"readonlyDomainName": null,
        		"readonly_domain_name": null,
        		"port": 6379,
        		"status": "RUNNING",
        		"freeze_scene": null,
        		"created_at": "2020-06-18T03:11:30.618Z",
        		"update_at": "2020-06-18T03:11:58.937Z",
        		"error_code": null,
        		"user_id": "05040c67cc00256f1f28c009a1c2a0f7",
        		"user_name": "dcstest",
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
        		"tags": null,
        		"product_type": "generic",
        		"cpu_type": "x86_64",
        		"storage_type": "DRAM",
        		"task_status": null,
        		"launched_at": "2020-06-18T03:11:58.943Z",
        		"is_free": null,
        		"libos": false,
        		"cache_mode": "ha",
        		"available_zones": ["dfeb4826256b47aa828e72d7522e108c",
        		"043c7e39ecb347a08dc8fcb6c35a274e"],
        		"subnet_id": "e6eb5ff4-da2a-4323-bddc-c7b179f9aa1e",
        		"backend_addrs": null,
        		"crr_role": null,
        		"cloud_service_type_code": "hws.service.type.dcs",
        		"cloud_resource_type_code": "hws.resource.type.dcs3",
        		"support_slow_log_flag": null,
        		"ipv6": null,
        		"enable_ipv6": false,
        		"description": ""
        	}],
        	"instance_num": 2
        }
        
        ```

2.  根据需要，记录要删除实例的instance\_id。

## 步骤2：批量删除实例<a name="section059682113517"></a>

-   接口相关信息

    URI格式：DELETE /v2/\{project\_id\}/instances

-   请求示例

    DELETE https://\{dcs\_endpoint\}/v2/\{project\_id\}/instances

    \{dcs\_endpoint\}信息，请从[地区和终端节点](https://developer.huaweicloud.com/endpoint)获取。

    Body：

    ```
    {
     "instances": [
      "aabe73af-1db8-4401-b39c-c56996023989",
      "9d78d0f4-a110-4bcd-8ca3-5aec414163c1"
     ]
    }
    ```

-   响应示例

    ```
    {
     "results": [
      {
       "result": "success",
       "instance": "aabe73af-1db8-4401-b39c-c56996023989"
      },
      {
       "result": "success",
       "instance": "9d78d0f4-a110-4bcd-8ca3-5aec414163c1"
      }
     ]
    }
    ```



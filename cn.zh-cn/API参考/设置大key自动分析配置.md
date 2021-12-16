# 设置大key自动分析配置<a name="UpdateBigkeyAutoscanConfig"></a>

## 功能介绍

设置大key自动分析配置。

## 调试

您可以在[API Explorer](https://apiexplorer.developer.huaweicloud.com/apiexplorer/doc?product=DCS&api=UpdateBigkeyAutoscanConfig)中调试该接口，并获取该接口关联的CLI示例：  [hcloud DCS UpdateBigkeyAutoscanConfig](https://apiexplorer.developer.huaweicloud.com/apiexplorer/cli?product=DCS&api=UpdateBigkeyAutoscanConfig)。

## URI

PUT /v2/\{project\_id\}/instances/\{instance\_id\}/bigkey/autoscan

**表 1**  路径参数

<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>项目ID。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>instance_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>是</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>实例ID。</p>
</td>
</tr>
</tbody>
</table>

## 请求参数

**表 2**  请求Body参数

<a name="request_AutoscanConfigRequest"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.3"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="40%" id="mcps1.2.5.1.4"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>enable_auto_scan</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>是否开启缓存分析定时任务</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p>schedule_at</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p>否</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.3 "><p>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="40%" headers="mcps1.2.5.1.4 "><p>每日缓存分析时间，时间格式为21:00，时间为UTC时间</p>
</td>
</tr>
</tbody>
</table>

## 响应参数

**状态码： 200**

**表 3**  响应Body参数

<a name="response_AutoScanConfigResponse"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>instance_id</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>所属实例ID</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>enable_auto_scan</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>是否开启缓存分析定时任务</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>schedule_at</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>Array of strings</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>每日分析时间，时间格式为21:00，时间为UTC时间</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>updated_at</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>配置更新时间，时间格式为2020-06-15T02:21:18.669Z</p>
</td>
</tr>
</tbody>
</table>

**状态码： 400**

**表 4**  响应Body参数

<a name="response_ErrorResponse"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>error_msg</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>错误信息</p>
<p>最大长度：<strong>1024</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>error_code</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>错误码</p>
<p>最大长度：<strong>9</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>error_ext_msg</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>扩展错误信息(暂未使用，赋值为null)</p>
<p>最大长度：<strong>1024</strong></p>
</td>
</tr>
</tbody>
</table>

**状态码： 401**

**表 5**  响应Body参数

<a name="response_ErrorResponse_1"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>error_msg</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>错误信息</p>
<p>最大长度：<strong>1024</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>error_code</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>错误码</p>
<p>最大长度：<strong>9</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>error_ext_msg</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>扩展错误信息(暂未使用，赋值为null)</p>
<p>最大长度：<strong>1024</strong></p>
</td>
</tr>
</tbody>
</table>

**状态码： 403**

**表 6**  响应Body参数

<a name="response_ErrorResponse_2"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>error_msg</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>错误信息</p>
<p>最大长度：<strong>1024</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>error_code</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>错误码</p>
<p>最大长度：<strong>9</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>error_ext_msg</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>扩展错误信息(暂未使用，赋值为null)</p>
<p>最大长度：<strong>1024</strong></p>
</td>
</tr>
</tbody>
</table>

**状态码： 404**

**表 7**  响应Body参数

<a name="response_ErrorResponse_3"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>error_msg</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>错误信息</p>
<p>最大长度：<strong>1024</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>error_code</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>错误码</p>
<p>最大长度：<strong>9</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>error_ext_msg</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>扩展错误信息(暂未使用，赋值为null)</p>
<p>最大长度：<strong>1024</strong></p>
</td>
</tr>
</tbody>
</table>

**状态码： 500**

**表 8**  响应Body参数

<a name="response_ErrorResponse_4"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.2"><p>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="60%" id="mcps1.2.4.1.3"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>error_msg</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>错误信息</p>
<p>最大长度：<strong>1024</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>error_code</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>错误码</p>
<p>最大长度：<strong>9</strong></p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p>error_ext_msg</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.2 "><p>String</p>
</td>
<td class="cellrowborder" valign="top" width="60%" headers="mcps1.2.4.1.3 "><p>扩展错误信息(暂未使用，赋值为null)</p>
<p>最大长度：<strong>1024</strong></p>
</td>
</tr>
</tbody>
</table>

## 请求示例

```
PUT https://dcs.cn-south-1.myhuaweicloud.com/v2/a4d31cb6-3d72-4fdc-8ec9-6e3a41e47f71/instances/5560df16-cebf-4473-95c4-d1b573c16e79/bigkey/autoscan
```

## 响应示例

**状态码： 200**

设置大key分析配置成功。

```
{
  "instance_id" : "5f9057b5-c330-4ee2-8138-7e69896eeec3",
  "enable_auto_scan" : true,
  "schedule_at" : [ "21:00" ],
  "updated_at" : "2020-06-17T02:42:40.793Z"
}
```

**状态码： 400**

非法请求。

```
{
  "error_code" : "DCS.4919",
  "error_msg" : "Does not support bigkey analyze."
}
```

## 状态码

<a name="status_code"></a>
<table><thead align="left"><tr><th class="cellrowborder" valign="top" width="15%" id="mcps1.1.3.1.1"><p>状态码 </p>
</th>
<th class="cellrowborder" valign="top" width="85%" id="mcps1.1.3.1.2"><p>描述</p>
</th>
</tr>
</thead>
<tbody><tr><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p>200</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p>设置大key分析配置成功。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p>400</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p>非法请求。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p>401</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p>认证信息非法。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p>403</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p>请求被拒绝访问。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p>404</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p>所请求的资源不存在。</p>
</td>
</tr>
<tr><td class="cellrowborder" valign="top" width="15%" headers="mcps1.1.3.1.1 "><p>500</p>
</td>
<td class="cellrowborder" valign="top" width="85%" headers="mcps1.1.3.1.2 "><p>内部服务错误。</p>
</td>
</tr>
</tbody>
</table>

## 错误码

请参见[错误码](错误码.md)。


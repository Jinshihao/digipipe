## Digipipe
----

### 数据推送
>接口地址

```js
http://...
```

>数据格式

```js
JSON
```
>请求方式

```js
POST
```

>请求头

| 名称 | 类型 |说明|
|-----|------|----|
|Content-Type|application/json|数据格式|
|apikey|xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx|api key|

>请求参数

|名称 |类型 |必填 |说明 |
|---- |-----|------|----|
|data |Array`<Item>` |true |推送数据Item集合 |
|timestamp |Number |true |时间戳 |
|sign |String |true |请求签名 |

**签名算法：1、请求参数字典序  2、签名字符串：key=value&key1=value (value为Object/Array使用JSON.stringify格式化) 3、md5(api_secret+签名字符串+api_secret)*

**Item结构**

|名称 |类型 |必填 |说明 |
|---- |-----|------|----|
|no |String |true |设备号 |
|product |String |true |投放产品 |
|type |String |true |产品类型 |
|show |Boolean |true |是否曝光 |
|click |Boolean |true |是否点击 |  

>响应数据

| 名称 | 类型 |说明|
|----- |------|----|
| code | int|状态码
|msg | string|状态描述|

>JSON返回示例

```js
// 成功
{
  "code": 0,
  "msg": "success"
}

// 失败
{
  "code": -1,
  "msg": "..."
}
```

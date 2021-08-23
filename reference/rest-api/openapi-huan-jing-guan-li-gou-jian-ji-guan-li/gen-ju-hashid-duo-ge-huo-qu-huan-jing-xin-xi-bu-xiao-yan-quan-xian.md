# 根据hashId\(多个\)获取环境信息\(不校验权限\)

### 请求方法/请求路径

#### POST  /apigw-app/v3/environment/projects/{projectId}/envs/listRawByEnvHashIds

### 资源描述

#### 根据hashId\(多个\)获取环境信息\(不校验权限\)

### 输入参数说明

#### Query参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| app\_secret | string | 应用态必须 | 安全秘钥\(app secret\)，可以通过 蓝鲸开发者中心 -&gt; 应用基本设置 -&gt; 基本信息 -&gt; 鉴权信息 获取 |  |
| app\_code | string | 应用态必须 | 应用ID\(app id\)，可以通过 蓝鲸开发者中心 -&gt; 应用基本设置 -&gt; 基本信息 -&gt; 鉴权信息 获取 |  |

#### Header参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| X-DEVOPS-APP-CODE | string | 是 | appCode | bkci |
| X-DEVOPS-UID | string | 是 | 用户ID | admin |

#### Body参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| body | array | 是 | 环境 hashId\(s\) |  |

#### Path参数

| 参数名称 | 参数类型 | 必须 | 参数说明 | 默认值 |
| :--- | :--- | :--- | :--- | :--- |
| apigwType | string | 是 | apigw Type |  |
| projectId | string | 是 | 项目ID |  |

#### 响应

| HTTP代码 | 说明 | 参数类型 |
| :--- | :--- | :--- |
| 200 | successful operation | 数据返回包装模型List环境信息\(权限\) |

#### 请求样例

```javascript
curl -X POST '[请替换为API地址栏请求地址]?app_secret={app_secret}&amp;app_code={app_code}'
```

#### HEADER样例

```javascript
accept: application/json
Content-Type: application/json
X-DEVOPS-APP-CODE: {X-DEVOPS-APP-CODE}
X-DEVOPS-UID: {X-DEVOPS-UID}
```

### 返回样例-200

```javascript
{
  "data" : [ {
    "updatedTime" : 0,
    "canEdit" : true,
    "envVars" : [ {
      "name" : "String",
      "secure" : true,
      "value" : "String"
    } ],
    "updatedUser" : "String",
    "canUse" : true,
    "envType" : "String",
    "name" : "String",
    "createdTime" : 0,
    "nodeCount" : 0,
    "canDelete" : true,
    "envHashId" : "String",
    "createdUser" : "String",
    "desc" : "String"
  } ],
  "message" : "String",
  "status" : 0
}
```

## 数据返回包装模型List环境信息\(权限\)

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| data | List&lt;环境信息\(权限\)&gt; | 否 | 数据 |
| message | string | 否 | 错误信息 |
| status | integer | 是 | 状态码 |

## 环境信息\(权限\)

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| updatedTime | integer | 是 | 更新时间 |
| canEdit | boolean | 否 | 是否可以编辑 |
| envVars | List&lt;环境变量&gt; | 是 | 环境变量 |
| updatedUser | string | 是 | 更新人 |
| canUse | boolean | 否 | 是否可以使用 |
| envType | string | 是 | 环境类型（开发环境{DEV} |
| name | string | 是 | 环境名称 |
| createdTime | integer | 是 | 创建时间 |
| nodeCount | integer | 否 | 节点数量 |
| canDelete | boolean | 否 | 是否可以删除 |
| envHashId | string | 是 | 环境 HashId |
| createdUser | string | 是 | 创建人 |
| desc | string | 是 | 环境描述 |

## 环境变量

| 参数名称 | 参数类型 | 必须 | 参数说明 |
| :--- | :--- | :--- | :--- |
| name | string | 是 | 变量名 |
| secure | boolean | 是 | 是否安全变量 |
| value | string | 是 | 变量值 |

# 原生协议

> 原生插件和原生交互，通过统一的协议通信，格式为：

```java
FBNativeXXXX functionName(params)
```

XXXX服务名称，functionName具体的方法名称，params固定字符串，由各自服务提供格式

## 日志

*   描述

    日志打印到宿主
*   服务名

    ```java
    FNNativeLog
    ```
*   方法集合

    | 方法名  | 备注     |
    | ---- | ------ |
    | logD | 打印d级日志 |
    | logV | 打印v级日志 |
    | logW | 打印w级日志 |
    | logE | 打印e级日志 |
    | logI | 打印i级日志 |
*   入参

    | 参数名   | 备注      |
    | ----- | ------- |
    | param | 需要打印到内容 |
*   出参

    无

## 统计

*   描述

    统计埋到宿主
*   服务名

    ```java
    FNNativeEvent
    ```
*   方法集合

    | 方法名       | 备注   |
    | --------- | ---- |
    | sendEvent | 统计埋点 |
*   入参

    | 参数名   | 备注          |
    | ----- | ----------- |
    | param | 需要埋点的json内容 |

    > param说明

    | 字段名        | 类型     | 默认值 | 必选 | 备注          |
    | ---------- | ------ | --- | -- | ----------- |
    | moduleName | String | -   | 是  | 模块名，比如微服务ID |
    | eventId    | String | -   | 是  | 埋点key       |
    | map        | Map    | -   | 是  | 错误栈日志内容     |
*   出参

    无

## 用户信息

*   描述

    宿主中的用户信息
*   服务名

    ```java
    FNNativeUserInfo
    ```
*   方法集合

    | 方法名         | 备注     |
    | ----------- | ------ |
    | getUserInfo | 获取用户信息 |
*   入参

    | 参数名   | 备注          |
    | ----- | ----------- |
    | param | 需要埋点的json内容 |

    > param说明

    | Json的key         | 类型     | 备注                      |
    | ---------------- | ------ | ----------------------- |
    | id               | String | 用户编号                    |
    | userName         | String | 工号                      |
    | fullName         | String | 客户名                     |
    | mobile           | String | 手机号                     |
    | netCode          | String | 网点代码(多网点的情况下，小哥登录选择的网点) |
    | areaCode         | String | 大区代码                    |
    | belongDeptCode   | String | 归属网点                    |
    | serviceDeptCode  | String | 服务网点                    |
    | positionProperty | String | 员工属性                    |
*   出参

    无

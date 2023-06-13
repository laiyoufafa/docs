# @ohos.resourceschedule.deviceStandby（设备待机模块）
当设备长时间未被使用或通过按键，可以使设备进入待机模式。待机模式不影响应用使用，还可以延长电池续航时间。通过本模块接口，可查询设备是否为待机模式，以及使应用灵活申请开启或关闭待机模式。

>  **说明：**
> - 本模块首批接口从API version 10开始支持。后续版本的新增接口，采用上角标单独标记接口的起始版本。

## 导入模块
```js
import deviceStandby from '@ohos.resourceschedule.deviceStandby';
```
## deviceStandby.isDeviceInStandby
isDeviceInStandby(callback: AsyncCallback&lt;boolean&gt;): void;

当前设备是否进入待机低功耗续航模式，使用Callback异步回调。

**系统能力:** SystemCapability.ResourceSchedule.DeviceStandby

**参数**：

| 参数名      | 类型                   | 必填   | 说明                             |
| -------- | -------------------- | ---- | ------------------------------ |
| callback | AsyncCallback&lt;boolean&gt; | 是    | 延迟即将超时的回调函数，一般在超时前6秒通过此回调通知应用。 |

**错误码**：

以下错误码的详细介绍请参见[后台任务错误码](../errorcodes/errorcode-backgroundTaskMgr.md)。

| 错误码ID  | 错误信息             |
| ---- | --------------------- |
| 9800001 | Memory operation failed. |
| 9800002 | Parcel operation failed. |
| 9800003 | IPC failed. |
| 9800004 | System service operation failed. |
| 18700001 | Caller information verification failed when applying for efficiency resources. |

## deviceStandby.isDeviceInStandby
isDeviceInStandby(): Promise&lt;boolean&gt;

当前设备是否进入待机低功耗续航模式，使用Promise异步回调。

**系统能力:** SystemCapability.ResourceSchedule.DeviceStandby

**返回值**：

| 类型                    | 说明                                       |
| --------------------- | ---------------------------------------- |
| Promise&lt;boolean&gt; | 指定的Promise回调方法。返回是否进入待机低功耗续航模式。|

**错误码**：

以下错误码的详细介绍请参见[后台任务错误码](../errorcodes/errorcode-backgroundTaskMgr.md)。

| 错误码ID  | 错误信息             |
| ---- | --------------------- |
| 9800001 | Memory operation failed. |
| 9800002 | Parcel operation failed. |
| 9800003 | IPC failed. |
| 9800004 | System service operation failed. |
| 18700001 | Caller information verification failed when applying for efficiency resources. |

## deviceStandby.getExemptedApps
getExemptedApps(resourceTypes: number, callback: AsyncCallback<Array&lt;ExemptedAppInfo&gt;>): void;

获取进入待机模式的应用名单，使用Callback异步回调。

**系统能力:** SystemCapability.ResourceSchedule.DeviceStandby

**系统API:** 此接口为系统接口。

**参数**：

| 参数名      | 类型                   | 必填   | 说明                             |
| -------- | -------------------- | ---- | ------------------------------ |
| [ResourceType](#resourcetype)|number | 是    | 资源类型 |
| callback | AsyncCallback<Array&lt;[ExemptedAppInfo](#exemptedappinfo)&gt;> | 是    |豁免应用信息 |

**错误码**：

以下错误码的详细介绍请参见[后台任务错误码](../errorcodes/errorcode-backgroundTaskMgr.md)。

| 错误码ID  | 错误信息             |
| ---- | --------------------- |
| 9800001 | Memory operation failed. |
| 9800002 | Parcel operation failed. |
| 9800003 | IPC failed. |
| 9800004 | System service operation failed. |
| 18700001 | Caller information verification failed when applying for efficiency resources. |

## deviceStandby.getExemptedApps
getExemptedApps(resourceTypes: number): Promise<Array&lt;ExemptedAppInfo&gt;>;

获取进入待机模式的应用名单，使用Promise异步回调。

**系统能力:** SystemCapability.ResourceSchedule.DeviceStandby

**系统API:** 此接口为系统接口。

**参数**：

| 参数名      | 类型                   | 必填   | 说明                             |
| -------- | -------------------- | ---- | ------------------------------ |
| [ResourceType](#resourcetype)|number | 是    |资源类型|

**返回值**：

| 类型                    | 说明                                       |
| --------------------- | ---------------------------------------- |
| Promise<Array&lt;[ExemptedAppInfo](#exemptedappinfo)&gt;> | 豁免应用信息 |

**错误码**：

以下错误码的详细介绍请参见[后台任务错误码](../errorcodes/errorcode-backgroundTaskMgr.md)。

| 错误码ID  | 错误信息             |
| ---- | --------------------- |
| 201 | Permission denied. |
| 202 | Not System App. |
| 401 | Parameter error. |
| 9800001 | Memory operation failed. |
| 9800002 | Parcel operation failed. |
| 9800003 | IPC failed. |
| 9800004 | System service operation failed. |
| 18700001 | Caller information verification failed when applying for efficiency resources. |

## deviceStandby.requestExemptionResource
requestExemptionResource(request: ResourceRequest): void;

订阅申请豁免，为应用申请临时不进入待机管控能力。

**系统能力:** SystemCapability.ResourceSchedule.DeviceStandby.Exemption

**系统API:** 此接口为系统接口。

**参数**：

| 参数名      | 类型                   | 必填   | 说明                             |
| -------- | -------------------- | ---- | ------------------------------ |
| request |[ResourceRequest](#resourcerequest)| 是    | 资源请求 |

**错误码**：

以下错误码的详细介绍请参见[后台任务错误码](../errorcodes/errorcode-backgroundTaskMgr.md)。

| 错误码ID  | 错误信息             |
| ---- | --------------------- |
| 9800001 | Memory operation failed. |
| 9800002 | Parcel operation failed. |
| 9800003 | IPC failed. |
| 9800004 | System service operation failed. |
| 18700001 | Caller information verification failed when applying for efficiency resources. |

## deviceStandby.releaseExemptionResource
releaseExemptionResource(request: ResourceRequest): void;

去除订阅申请豁免，去除应用暂时不进入待机管控的能力。

**系统能力:** SystemCapability.ResourceSchedule.DeviceStandby.Exemption

**系统API:** 此接口为系统接口。

**参数**：

| 参数名      | 类型                   | 必填   | 说明                             |
| -------- | -------------------- | ---- | ------------------------------ |
| request |[ResourceRequest](#resourcerequest)| 是    | 资源请求 |

**错误码**：

以下错误码的详细介绍请参见[后台任务错误码](../errorcodes/errorcode-backgroundTaskMgr.md)。

| 错误码ID  | 错误信息             |
| ---- | --------------------- |
| 9800001 | Memory operation failed. |
| 9800002 | Parcel operation failed. |
| 9800003 | IPC failed. |
| 9800004 | System service operation failed. |
| 18700001 | Caller information verification failed when applying for efficiency resources. |

## ResourceType
非待机应用资源枚举。
<br>

|名称   |值   |说明|
| ------------ | ------------ |--------------|
|NETWORK    |1   |网络访问资源|
|RUNNING_LOCK    |2   |cpu-runninglock资源|
|TIMER     |4   | timer任务资源|
|WORK_SCHEDULER     |8   | work任务资源|
|AUTO_SYNC      |16   | 自动同步的资源 |
|PUSH     |32   | pushkit资源|
|FREEZE       |64   | 冻结应用资源|

## ExemptedAppInfo 
豁免应用信息，不进入待机管控的应用信息。
<br>

|名称  |类型   |说明   |
| ------------ | ------------ | ------------ |
|resourceTypes   | number  |应用的资源类型   |
|name   |string   |  应用名  |
|duration   | number  | 豁免时长 |

## ResourceRequest
待机资源请求体。
<br>

|名称   |类型   |说明   |
| ------------ | ------------ | ------------ |
|resourceTypes   | number  |应用的资源类型   |
|uid   | number  |应用uid   |
|name   |string   | 应用名称  |
|duration   | number  | 豁免时长 |
|reason   |string   |  申请原因  |
# 窗口

窗口提供管理窗口的一些基础能力，包括对窗口的创建、销毁，以及对窗口的属性设置等各项功能。

> **说明：**
> 
> 本模块首批接口从API version 6开始支持。后续版本的新增接口，采用上角标单独标记接口的起始版本。

## 导入模块

```js
import window from '@ohos.window';
```

## WindowType<sup>7+</sup>

窗口类型。

**系统能力：** 以下各项对应的系统能力均为SystemCapability.WindowManager.WindowManager.Core。

| 名称              | 默认值 | 说明               |
| ----------------- | ------ | ------------------ |
| TYPE_APP          | 0      | 表示应用子窗口。   |
| TYPE_SYSTEM_ALERT | 1      | 表示系统告警窗口。 |

## AvoidAreaType<sup>7+</sup>

窗口内容需要规避区域的类型。

**系统能力：** 以下各项对应的系统能力均为SystemCapability.WindowManager.WindowManager.Core。

| 名称        | 默认值 | 说明               |
| ----------- | ------ | ------------------ |
| TYPE_SYSTEM | 0      | 表示系统默认区域。 |
| TYPE_CUTOUT | 1      | 表示刘海屏区域。   |

## WindowMode<sup>7+</sup>

窗口模式。

此接口为系统接口，三方应用不支持调用。

**系统能力：** 以下各项对应的系统能力均为SystemCapability.WindowManager.WindowManager.Core。

| 名称       | 默认值 | 说明                          |
| ---------- | ------ | ----------------------------- |
| UNDEFINED  | 1      | 表示APP未定义窗口模式。       |
| FULLSCREEN | 2      | 表示APP全屏模式。             |
| PRIMARY    | 3      | 表示APP分屏多窗口主要模式。   |
| SECONDARY  | 4      | 表示APP分屏多窗口次要模式。   |
| FLOATING   | 5      | 表示APP自由悬浮形式窗口模式。 |

## SystemBarProperties

状态栏导航栏的属性。

**系统能力：** 以下各项对应的系统能力均为SystemCapability.WindowManager.WindowManager.Core。

| 名称                                   | 参数类型 | 可读 | 可写 | 说明                                                         |
| -------------------------------------- | -------- | ---- | ---- | ------------------------------------------------------------ |
| statusBarColor                         | string   | 是   | 是   | 状态栏背景颜色，为16进制RGB或ARGB颜色，例如"\#00FF00"或"\#FF00FF00"。 |
| isStatusBarLightIcon<sup>7+</sup>      | boolean  | 否   | 是   | 状态栏图标是否为高亮状态。                                   |
| statusBarContentColor<sup>8+</sup>     | string   | 否   | 是   | 状态栏文字颜色。                                             |
| navigationBarColor                     | string   | 是   | 是   | 导航栏背景颜色，为16进制RGB或ARGB颜色，例如"\#00FF00"或"\#FF00FF00"。 |
| isNavigationBarLightIcon<sup>7+</sup>  | boolean  | 否   | 否   | 导航栏图标是否为高亮状态。                                   |
| navigationBarContentColor<sup>8+</sup> | string   | 否   | 是   | 导航栏文字颜色。                                             |

## SystemBarRegionTint<sup>8+</sup>

单个导航栏或状态栏回调信息。

此接口为系统接口，三方应用不支持调用。

**系统能力：** 以下各项对应的系统能力均为SystemCapability.WindowManager.WindowManager.Core。

| 名称            | 参数类型                  | 可读 | 可写 | 说明                                                         |
| --------------- | ------------------------- | ---- | ---- | ------------------------------------------------------------ |
| type            | [WindowType](#windowtype) | 是   | 是   | 当前属性改变的系统栏类型，仅支持类型为导航栏、状态栏的系统栏。 |
| isEnable        | boolean                   | 是   | 是   | 当前系统栏是否显示。                                         |
| region          | [Rect](#rect)             | 是   | 是   | 当前系统栏的位置及大小。                                     |
| backgroundColor | string                    | 是   | 是   | 系统栏背景颜色，为16进制RGB或ARGB颜色，例如"\#00FF00"或"\#FF00FF00"。 |
| contentColor    | string                    | 是   | 是   | 系统栏文字颜色。                                             |

## SystemBarTintState<sup>8+</sup>

当前系统栏回调信息集合。

此接口为系统接口，三方应用不支持调用。

**系统能力：** 以下各项对应的系统能力均为SystemCapability.WindowManager.WindowManager.Core。

| 名称       | 参数类型                                            | 可读 | 可写 | 说明                       |
| ---------- | --------------------------------------------------- | ---- | ---- | -------------------------- |
| displayId  | number                                              | 是   | 否   | 当前物理屏幕id。           |
| regionTint | Array<[SystemBarRegionTint](#systembarregiontint8)> | 是   | 是   | 当前改变所有的系统栏信息。 |

## Rect<sup>7+</sup>

窗口矩形区域。

**系统能力：** 以下各项对应的系统能力均为SystemCapability.WindowManager.WindowManager.Core。

| 名称   | 参数类型 | 可读 | 可写 | 说明               |
| ------ | -------- | ---- | ---- | ------------------ |
| left   | number   | 是   | 是   | 矩形区域的左边界。 |
| top    | number   | 是   | 是   | 矩形区域的上边界。 |
| width  | number   | 是   | 是   | 矩形区域的宽度。   |
| height | number   | 是   | 是   | 矩形区域的高度。   |

## AvoidArea<sup>7+</sup>

窗口内容规避区域。

**系统能力：** 以下各项对应的系统能力均为SystemCapability.WindowManager.WindowManager.Core。

| 名称       | 参数类型      | 可读 | 可写 | 说明               |
| ---------- | ------------- | ---- | ---- | ------------------ |
| leftRect   | [Rect](#rect) | 是   | 是   | 屏幕左侧的矩形区。 |
| topRect    | [Rect](#rect) | 是   | 是   | 屏幕顶部的矩形区。 |
| rightRect  | [Rect](#rect) | 是   | 是   | 屏幕右侧的矩形区。 |
| bottomRect | [Rect](#rect) | 是   | 是   | 屏幕底部的矩形区。 |

## Size<sup>7+</sup>

窗口大小。

**系统能力：** 以下各项对应的系统能力均为SystemCapability.WindowManager.WindowManager.Core。

| 名称   | 参数类型 | 可读 | 可写 | 说明       |
| ------ | -------- | ---- | ---- | ---------- |
| width  | number   | 是   | 是   | 窗口宽度。 |
| height | number   | 是   | 是   | 窗口高度。 |

## WindowProperties

窗口属性。

**系统能力：** 以下各项对应的系统能力均为SystemCapability.WindowManager.WindowManager.Core。

| 名称                            | 参数类型                  | 可读 | 可写 | 说明                                         |
| ------------------------------- | ------------------------- | ---- | ---- | -------------------------------------------- |
| windowRect<sup>7+</sup>         | [Rect](#rect)             | 是   | 是   | 窗口尺寸。                                   |
| type<sup>7+</sup>               | [WindowType](#windowtype) | 是   | 是   | 窗口类型。                                   |
| isFullScreen                    | boolean                   | 是   | 是   | 是否全屏，默认为false。                      |
| isLayoutFullScreen<sup>7+</sup> | boolean                   | 是   | 是   | 窗口是否为沉浸式，默认为false。              |
| focusable<sup>7+</sup>          | boolean                   | 是   | 否   | 窗口是否可聚焦，默认为true。                 |
| touchable<sup>7+</sup>          | boolean                   | 是   | 否   | 窗口是否可触摸，默认为true。                 |
| brightness                      | number                    | 是   | 是   | 屏幕亮度， 取值范围为0~1，1表示最大亮度值。  |
| isKeepScreenOn                  | boolean                   | 是   | 是   | 屏幕是否常亮，默认为false。                  |
| isPrivacyMode<sup>7+</sup>      | boolean                   | 是   | 是   | 隐私模式，默认为false。                      |
| isRoundCorner<sup>7+</sup>      | boolean                   | 是   | 是   | 窗口是否为圆角。默认为false。                |
| isTransparent<sup>7+</sup>      | boolean                   | 是   | 是   | 窗口是否透明。默认为false。                  |

## ColorSpace<sup>8+</sup>

色域模式。

**系统能力：** 以下各项对应的系统能力均为SystemCapability.WindowManager.WindowManager.Core。

| 名称       | 默认值 | 说明           |
| ---------- | ------ | -------------- |
| DEFAULT    | 0      | 默认色域模式。 |
| WIDE_GAMUT | 1      | 广色域模式。   |

## window.create<sup>7+</sup>

create(id: string, type: WindowType, callback: AsyncCallback&lt;Window&gt;): void

创建子窗口，使用callback异步回调。

从API version 8开始，此接口废弃，推荐使用[window.create<sup>8+</sup>](#windowcreate8)接口。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                                   | 必填 | 说明                       |
| -------- | -------------------------------------- | ---- | -------------------------- |
| id       | string                                 | 是   | 窗口id。                   |
| type     | [WindowType](#windowtype)              | 是   | 窗口类型。                 |
| callback | AsyncCallback&lt;[Window](#window)&gt; | 是   | 回调返回创建的子窗口对象。 |

**示例：** 

  ```js
   var windowClass = null;
   window.create("first", window.WindowType.TYPE_APP, (err, data) => {
      if (err.code) {
          console.error('Failed to create the subWindow. Cause: ' + JSON.stringify(err));
          return;
      }
      windowClass = data;
      console.info('SubWindow created. Data: ' + JSON.stringify(data))
      windowClass.resetSize(500, 1000);
  });
  ```

## window.create<sup>7+</sup>

create(id: string, type: WindowType): Promise&lt;Window&gt;

创建子窗口，使用Promise异步回调。

从API version 8开始，此接口废弃，推荐使用[window.create<sup>8+</sup>](#windowcreate8)接口。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名 | 类型                      | 必填 | 说明       |
| ------ | ------------------------- | ---- | ---------- |
| id     | string                    | 是   | 窗口id。   |
| type   | [WindowType](#windowtype) | 是   | 窗口类型。 |

**返回值：** 

| 类型                             | 说明                                              |
| -------------------------------- | ------------------------------------------------- |
| Promise&lt;[Window](#window)&gt; | 以Promise形式返回结果，返回当前创建的子窗口对象。 |

**示例：** 

  ```js
   var windowClass = null;
   let promise = window.create("first", window.WindowType.TYPE_APP);
   promise.then((data)=> {
   	windowClass = data;
      console.info('SubWindow created. Data: ' + JSON.stringify(data))
   }).catch((err)=>{
      console.error('Failed to create the subWindow. Cause: ' + JSON.stringify(err));
   });
  ```

## window.create<sup>8+</sup>

create(ctx: Context, id: string, type: WindowType, callback: AsyncCallback&lt;Window&gt;): void

创建子窗口，使用callback异步回调，其中Context详见[Context](js-apis-Context.md)。

从API version 9开始，当Context为[ServiceExtensionContext](js-apis-service-extension-context.md)时，创建系统窗口，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                                   | 必填 | 说明                                                         |
| -------- | -------------------------------------- | ---- | ------------------------------------------------------------ |
| ctx      | Context                                | 是   | 当前应用上下文信息。<br>API version 8的Context定义见[Context](js-apis-Context.md)。<br>API version 9的Context定义见[Context](js-apis-service-extension-context.md)。 |
| id       | string                                 | 是   | 窗口id。                                                     |
| type     | [WindowType](#windowtype)              | 是   | 窗口类型。                                                   |
| callback | AsyncCallback&lt;[Window](#window)&gt; | 是   | 回调返回当前窗口对象。                                       |

**示例：** 

  ```js
   var windowClass = null;
   window.create(this.context, "alertWindow", window.WindowType.TYPE_SYSTEM_ALERT, (err, data) => {
      if (err.code) {
          console.error('Failed to create the Window. Cause: ' + JSON.stringify(err));
          return;
      }
      windowClass = data;
      console.info('Window created. Data: ' + JSON.stringify(data))
      windowClass.resetSize(500, 1000);
  });
  ```

## window.create<sup>8+</sup>

create(ctx: Context, id: string, type: WindowType): Promise&lt;Window&gt;

创建子窗口，使用Promise异步回调，其中Context详见[Context](js-apis-Context.md)。

从API version 9开始，当Context为[ServiceExtensionContext](js-apis-service-extension-context.md)时，创建系统窗口，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名 | 类型                      | 必填 | 说明                                                         |
| ------ | ------------------------- | ---- | ------------------------------------------------------------ |
| ctx    | Context                   | 是   | 当前应用上下文信息。<br/>API version 8的Context定义见[Context](js-apis-Context.md)。<br/>API version 9的Context定义见[Context](js-apis-service-extension-context.md)。 |
| id     | string                    | 是   | 窗口id。                                                     |
| type   | [WindowType](#windowtype) | 是   | 窗口类型。                                                   |

**返回值：** 

| 类型                             | 说明                                            |
| -------------------------------- | ----------------------------------------------- |
| Promise&lt;[Window](#window)&gt; | 以Promise形式返回结果，返回当前创建的窗口对象。 |

**示例：** 

  ```js
   var windowClass = null;
   let promise = window.create(this.context, "alertWindow", window.WindowType.TYPE_SYSTEM_ALERT);
   promise.then((data)=> {
   	windowClass = data;
      console.info('Window created. Data: ' + JSON.stringify(data))
   }).catch((err)=>{
      console.error('Failed to create the Window. Cause: ' + JSON.stringify(err));
   });
  ```

## window.find<sup>7+</sup>

find(id: string, callback: AsyncCallback&lt;Window&gt;): void

查找id所对应的窗口，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                                   | 必填 | 说明                         |
| -------- | -------------------------------------- | ---- | ---------------------------- |
| id       | string                                 | 是   | 窗口id。                     |
| callback | AsyncCallback&lt;[Window](#window)&gt; | 是   | 回调返回当前查找的窗口对象。 |

**示例：** 

  ```js
   var windowClass = null;
   window.find("alertWindow", (err, data) => {
     if (err.code) {
         console.error('Failed to find the Window. Cause: ' + JSON.stringify(err));
         return;
     }
     windowClass = data;
     console.info('window found. Data: ' + JSON.stringify(data))
  });
  ```

## window.find<sup>7+</sup>

find(id: string): Promise&lt;Window&gt;

查找id所对应的窗口，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名 | 类型   | 必填 | 说明     |
| ------ | ------ | ---- | -------- |
| id     | string | 是   | 窗口id。 |

**返回值：** 

| 类型                             | 说明                                            |
| -------------------------------- | ----------------------------------------------- |
| Promise&lt;[Window](#window)&gt; | 以Promise形式返回结果，返回当前查找的窗口对象。 |

**示例：** 

  ```js
   var windowClass = null;
   let promise = window.find("alertWindow");
   promise.then((data)=> {
   	windowClass = data;
      console.info('window found. Data: ' + JSON.stringify(data))
   }).catch((err)=>{
      console.error('Failed to find the Window. Cause: ' + JSON.stringify(err));
   });
  ```

## window.getTopWindow

getTopWindow(callback: AsyncCallback&lt;Window&gt;): void

获取当前应用内最后显示的窗口，使用callback异步回调。

从API version 8开始，此接口废弃，推荐使用[window.getTopWindow<sup>8+</sup>](#windowgettopwindow8)接口。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                                   | 必填 | 说明                                   |
| -------- | -------------------------------------- | ---- | -------------------------------------- |
| callback | AsyncCallback&lt;[Window](#window)&gt; | 是   | 回调返回当前应用内最后显示的窗口对象。 |

**示例：** 

  ```js
  var windowClass = null;
  window.getTopWindow((err, data) => {
      if (err.code) {
          console.error('Failed to obtain the top window. Cause: ' + JSON.stringify(err));
          return;
      }
      windowClass = data;
      console.info('Succeeded in obtaining the top window. Data: ' + JSON.stringify(data));
  });
  ```

## window.getTopWindow

getTopWindow(): Promise&lt;Window&gt;

获取当前应用内最后显示的窗口，使用Promise异步回调。

从API version 8开始，此接口废弃，推荐使用[window.getTopWindow<sup>8+</sup>](#windowgettopwindow8)接口。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**返回值：** 

| 类型                             | 说明                                                      |
| -------------------------------- | --------------------------------------------------------- |
| Promise&lt;[Window](#window)&gt; | 以Promise形式返回结果，返回当前应用内最后显示的窗口对象。 |

**示例：** 

  ```js
   var windowClass = null;
   let promise = window.getTopWindow();
   promise.then((data)=> {
   	windowClass = data;
      console.info('Succeeded in obtaining the top window. Data: ' + JSON.stringify(data))
   }).catch((err)=>{
      console.error('Failed to obtain the top window. Cause: ' + JSON.stringify(err));
   })
  ```

## window.getTopWindow<sup>8+</sup>

getTopWindow(ctx: Context, callback: AsyncCallback&lt;Window&gt;): void

获取当前应用内最后显示的窗口，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                                   | 必填 | 说明                                                         |
| -------- | -------------------------------------- | ---- | ------------------------------------------------------------ |
| ctx      | Context                                | 是   | 当前应用上下文信息。<br>API version 8的Context定义见[Context](js-apis-Context.md)。<br>API version 9的Context定义见[Context](js-apis-ability-context.md)。 |
| callback | AsyncCallback&lt;[Window](#window)&gt; | 是   | 回调返回当前应用内最后显示的窗口对象。                       |

**示例：** 

  ```js
  var windowClass = null;
  window.getTopWindow(this.context, (err, data) => {
      if (err.code) {
          console.error('Failed to obtain the top window. Cause: ' + JSON.stringify(err));
          return;
      }
      windowClass = data;
      console.info('Succeeded in obtaining the top window. Data: ' + JSON.stringify(data));
  });
  ```

## window.getTopWindow<sup>8+</sup>

getTopWindow(ctx: Context): Promise&lt;Window&gt;

获取当前应用内最后显示的窗口，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名 | 类型    | 必填 | 说明                                                         |
| ------ | ------- | ---- | ------------------------------------------------------------ |
| ctx    | Context | 是   | 当前应用上下文信息。<br/>API version 8的Context定义见[Context](js-apis-Context.md)。<br/>API version 9的Context定义见[Context](js-apis-ability-context.md)。 |

**返回值：** 

| 类型                             | 说明                                                      |
| -------------------------------- | --------------------------------------------------------- |
| Promise&lt;[Window](#window)&gt; | 以Promise形式返回结果，返回当前应用内最后显示的窗口对象。 |

**示例：** 

  ```js
   var windowClass = null;
   let promise = window.getTopWindow(this.context);
   promise.then((data)=> {
   	windowClass = data;
      console.info('Succeeded in obtaining the top window. Data: ' + JSON.stringify(data))
   }).catch((err)=>{
      console.error('Failed to obtain the top window. Cause: ' + JSON.stringify(err));
   })
  ```

## on('systemBarTintChange')<sup>8+</sup>

on(type: 'systemBarTintChange', callback: Callback&lt;SystemBarTintState&gt;): void

注册状态栏、导航栏的监听函数。

此接口为系统接口，三方应用不支持调用。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                                                      | 必填 | 说明                                                         |
| -------- | --------------------------------------------------------- | ---- | ------------------------------------------------------------ |
| type     | string                                                    | 是   | 监听事件，固定为'systemBarTintChange'，即导航栏、状态栏属性变化事件。 |
| callback | Callback&lt;[SystemBarTintState](#systembartintstate)&gt; | 是   | 回调返回监听到的信息。                                       |

**示例：** 

  ```js
  var type = 'systemBarTintChange';
  windowClass.on(type, (data) => {
      console.info('Succeeded in enabling the listener for systemBarTint changes. Data: ' + JSON.stringify(data));
  });
  ```

## off('systemBarTintChange')<sup>8+</sup>

off(type: 'systemBarTintChange', callback?: Callback&lt;SystemBarTintState &gt;): void

关闭监听。

此接口为系统接口，三方应用不支持调用。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                                                      | 必填 | 说明                                                         |
| -------- | --------------------------------------------------------- | ---- | ------------------------------------------------------------ |
| type     | string                                                    | 是   | 监听事件，固定为'systemBarTintChange'，即导航栏、状态栏属性变化事件。 |
| callback | Callback&lt;[SystemBarTintState](#systembartintstate)&gt; | 否   | 回调返回监听到的信息。                                       |

**示例：** 

  ```js
  var type = 'systemBarTintChange';
  windowClass.off(type);
  ```

## Window

下列API示例中都需先使用[getTopWindow()](#windowgettopwindow)、[create()](#windowcreate7)、[find()](#windowfind7)中的任一方法获取到Window实例，再通过此实例调用对应方法。

### hide<sup>7+</sup>

hide (callback: AsyncCallback&lt;void&gt;): void

隐藏当前窗口，使用callback异步回调。

此接口为系统接口，三方应用不支持调用。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                      | 必填 | 说明       |
| -------- | ------------------------- | ---- | ---------- |
| callback | AsyncCallback&lt;void&gt; | 是   | 回调函数。 |

**示例：** 

  ```js
  windowClass.hide((err, data) => {
      if (err.code) {
          console.error('Failed to hide the window. Cause: ' + JSON.stringify(err));
          return;
      }
      console.info('window hidden. data: ' + JSON.stringify(data))
  })
  ```

### hide<sup>7+</sup>

hide(): Promise&lt;void&gt;

隐藏当前窗口，使用Promise异步回调。

此接口为系统接口，三方应用不支持调用。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
   let promise = windowClass.hide();
   promise.then((data)=> {
      console.info('window hidden. Data: ' + JSON.stringify(data))
   }).catch((err)=>{
      console.error('Failed to hide the window. Cause: ' + JSON.stringify(err));
   })
  ```

### show<sup>7+</sup>

show(callback: AsyncCallback&lt;void&gt;): void

显示当前窗口，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                      | 必填 | 说明       |
| -------- | ------------------------- | ---- | ---------- |
| callback | AsyncCallback&lt;void&gt; | 是   | 回调函数。 |

**示例：** 

  ```js
  windowClass.show((err, data) => {
      if (err.code) {
          console.error('Failed to show the window. Cause: ' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in showing the window. Data: ' + JSON.stringify(data))
  })
  ```

### show<sup>7+</sup>

show(): Promise&lt;void&gt;

显示当前窗口，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
   let promise = windowClass.show();
   promise.then((data)=> {
      console.info('Succeeded in showing the window. Data: ' + JSON.stringify(data))
   }).catch((err)=>{
      console.error('Failed to show the window. Cause: ' + JSON.stringify(err));
   })
  ```

### destroy<sup>7+</sup>

destroy(callback: AsyncCallback&lt;void&gt;): void

销毁当前窗口，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                      | 必填 | 说明       |
| -------- | ------------------------- | ---- | ---------- |
| callback | AsyncCallback&lt;void&gt; | 是   | 回调函数。 |

**示例：** 

  ```js
  windowClass.destroy((err, data) => {
      if (err.code) {
          console.error('Failed to destroy the window. Cause:' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in destroying the window. Data: ' + JSON.stringify(data))
  })
  ```

### destroy<sup>7+</sup>

destroy(): Promise&lt;void&gt;

销毁当前窗口，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
   let promise = windowClass.destroy();
   promise.then((data)=> {
      console.info('Succeeded in destroying the window. Data: ' + JSON.stringify(data))
   }).catch((err)=>{
      console.error('Failed to destroy the window. Cause: ' + JSON.stringify(err));
   })
  ```

### moveTo<sup>7+</sup>

moveTo(x: number, y: number, callback: AsyncCallback&lt;void&gt;): void

移动窗口位置，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                      | 必填 | 说明                                    |
| -------- | ------------------------- | ---- | --------------------------------------- |
| x        | number                    | 是   | 窗口在x轴方向移动的值，值为正表示右移。 |
| y        | number                    | 是   | 窗口在y轴方向移动的值，值为正表示下移。 |
| callback | AsyncCallback&lt;void&gt; | 是   | 回调函数。                              |

**示例：** 

  ```js
  windowClass.moveTo(300, 300, (err, data)=>{
      if (err.code) {
          console.error('Failed to move the window. Cause:' + JSON.stringify(err));
          return;
      }
      console.info('Window moved. Data: ' + JSON.stringify(data))
  
  });
  ```

### moveTo<sup>7+</sup>

moveTo(x: number, y: number): Promise&lt;void&gt;

移动窗口位置，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名 | 类型   | 必填 | 说明                                    |
| ------ | ------ | ---- | --------------------------------------- |
| x      | number | 是   | 窗口在x轴方向移动的值，值为正表示右移。 |
| y      | number | 是   | 窗口在y轴方向移动的值，值为正表示下移。 |

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
   let promise = windowClass.moveTo(300, 300);
   promise.then((data)=> {
      console.info('Window moved. Data: ' + JSON.stringify(data))
   }).catch((err)=>{
      console.error('Failed to move the window. Cause: ' + JSON.stringify(err));
   })
  ```

### resetSize<sup>7+</sup>

resetSize(width: number, height: number, callback: AsyncCallback&lt;void&gt;): void

改变当前窗口大小，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                      | 必填 | 说明             |
| -------- | ------------------------- | ---- | ---------------- |
| width    | number                    | 是   | 目标窗口的宽度。 |
| height   | number                    | 是   | 目标窗口的高度。 |
| callback | AsyncCallback&lt;void&gt; | 是   | 回调函数。       |

**示例：** 

  ```js
  windowClass.resetSize(500, 1000, (err, data) => {
      if (err.code) {
          console.error('Failed to change the window size. Cause:' + JSON.stringify(err));
          return;
      }
      console.info('Window size changed. Data: ' + JSON.stringify(data))
  });
  ```

### resetSize<sup>7+</sup>

resetSize(width: number, height: number): Promise&lt;void&gt;

改变当前窗口大小，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名 | 类型   | 必填 | 说明             |
| ------ | ------ | ---- | ---------------- |
| width  | number | 是   | 目标窗口的宽度。 |
| height | number | 是   | 目标窗口的高度。 |

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
   let promise = windowClass.resetSize(500, 1000);
   promise.then((data)=> {
      console.info('Window size changed. Data: ' + JSON.stringify(data))
   }).catch((err)=>{
      console.error('Failed to change the window size. Cause: ' + JSON.stringify(err));
   });
  ```

### setWindowType<sup>7+</sup>

setWindowType(type: WindowType, callback: AsyncCallback&lt;void&gt;): void

设置窗口类型，使用callback异步回调。

此接口为系统接口，三方应用不支持调用。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                      | 必填 | 说明       |
| -------- | ------------------------- | ---- | ---------- |
| type     | [WindowType](#windowtype) | 是   | 窗口类型。 |
| callback | AsyncCallback&lt;void&gt; | 是   | 回调函数。 |

**示例：** 

  ```js
  var type = window.TYPE_APP;
  windowClass.setWindowType(type, (err, data) => {
    if (err.code) {
        console.error('Failed to set the window type. Cause: ' + JSON.stringify(err));
        return;
    }
    console.info('Succeeded in setting the window type. Data: ' + JSON.stringify(data))
  });
  ```

### setWindowType<sup>7+</sup>

setWindowType(type: WindowType): Promise&lt;void&gt;

设置窗口类型，使用Promise异步回调。

此接口为系统接口，三方应用不支持调用。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名 | 类型                      | 必填 | 说明       |
| ------ | ------------------------- | ---- | ---------- |
| type   | [WindowType](#windowtype) | 是   | 窗口类型。 |

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
   var type = window.TYPE_APP;
   let promise = windowClass.setWindowType(type);
   promise.then((data)=> {
      console.info('Succeeded in setting the window type. Data: ' + JSON.stringify(data))
   }).catch((err)=>{
      console.error('Failed to set the window type. Cause: ' + JSON.stringify(err));
   });
  ```

### getProperties

getProperties(callback: AsyncCallback&lt;WindowProperties&gt;): void

获取当前窗口的属性，使用callback异步回调，返回WindowProperties。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                                                       | 必填 | 说明               |
| -------- | ---------------------------------------------------------- | ---- | ------------------ |
| callback | AsyncCallback&lt;[WindowProperties](#windowproperties)&gt; | 是   | 回调返回窗口属性。 |

**示例：** 

  ```js
  windowClass.getProperties((err, data) => {
      if (err.code) {
          console.error('Failed to obtain the window properties. Cause: ' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in obtaining the window properties. Data: ' + JSON.stringify(data));
  });
  ```

### getProperties

getProperties(): Promise&lt;WindowProperties&gt;

获取当前窗口的属性，使用Promise异步回调，返回WindowProperties。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**返回值：** 

| 类型                                                 | 说明                                  |
| ---------------------------------------------------- | ------------------------------------- |
| Promise&lt;[WindowProperties](#windowproperties)&gt; | 以Promise形式返回结果，返回窗口属性。 |

**示例：** 

  ```js
   let promise = windowClass.getProperties();
   promise.then((data)=> {
      console.info('Succeeded in obtaining the window properties. Data: ' + JSON.stringify(data))
   }).catch((err)=>{
      console.error('Failed to obtain the window properties. Cause: ' + JSON.stringify(err));
   });
  ```

### getAvoidArea<sup>7+</sup>

getAvoidArea(type: AvoidAreaType, callback: AsyncCallback&lt;AvoidArea&gt;): void

获取窗口内容规避的区域，如系统的系统栏区域、凹凸区域。使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                                         | 必填 | 说明                                                         |
| -------- | -------------------------------------------- | ---- | ------------------------------------------------------------ |
| type     | [AvoidAreaType](#avoidareatype)              | 是   | 表示规避区类型。type为TYPE_SYSTEM，表示系统默认区域。type为TYPE_CUTOUT，表示刘海屏区域。 |
| callback | AsyncCallback&lt;[AvoidArea](#avoidarea)&gt; | 是   | 回调返回窗口内容规避区域。                                   |

**示例：** 

  ```js
  var type = window.AvoidAreaType.TYPE_SYSTEM;
  windowClass.getAvoidArea(type, (err, data) => {
      if (err.code) {
          console.error('Failed to obtain the area. Cause:' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in obtaining the area. Data:' + JSON.stringify(data));
  });
  ```

### getAvoidArea<sup>7+</sup>

getAvoidArea(type: AvoidAreaType): Promise&lt;AvoidArea&gt;

获取窗口内容规避的区域，如系统的系统栏区域、凹凸区域。使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名 | 类型                            | 必填 | 说明                                                         |
| ------ | ------------------------------- | ---- | ------------------------------------------------------------ |
| type   | [AvoidAreaType](#avoidareatype) | 是   | 表示规避区类型。type为TYPE_SYSTEM，表示系统默认区域。type为TYPE_CUTOUT，表示刘海屏区域。 |

**返回值：** 

| 类型                                   | 说明                                          |
| -------------------------------------- | --------------------------------------------- |
| Promise&lt;[AvoidArea](#avoidarea)&gt; | 以Promise形式返回结果，返回窗口内容规避区域。 |

**示例：** 

  ```js
   let promise = windowClass.getAvoidArea();
   promise.then((data)=> {
      console.info('Succeeded in obtaining the area. Data:' + JSON.stringify(data))
   }).catch((err)=>{
      console.error('Failed to obtain the area. Cause:' + JSON.stringify(err));
   });
  ```

### setFullScreen

setFullScreen(isFullScreen: boolean, callback: AsyncCallback&lt;void&gt;): void

设置是否为全屏状态，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名       | 类型                      | 必填 | 说明                                           |
| ------------ | ------------------------- | ---- | ---------------------------------------------- |
| isFullScreen | boolean                   | 是   | 是否设为全屏状态，且全屏状态隐藏状态栏导航栏。 |
| callback     | AsyncCallback&lt;void&gt; | 是   | 回调函数。                                     |

**示例：** 

  ```js
  var isFullScreen = true;
  windowClass.setFullScreen(isFullScreen, (err, data) => {
      if (err.code) {
          console.error('Failed to enable the full-screen mode. Cause: ' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in enabling the full-screen mode. Data: ' + JSON.stringify(data))
  });
  ```

### setFullScreen

setFullScreen(isFullScreen: boolean): Promise&lt;void&gt;

设置是否为全屏状态，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名       | 类型    | 必填 | 说明                                           |
| ------------ | ------- | ---- | ---------------------------------------------- |
| isFullScreen | boolean | 是   | 是否设为全屏状态，且全屏状态隐藏状态栏导航栏。 |

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
  var isFullScreen = true;
  let promise = windowClass.setFullScreen(isFullScreen);
  promise.then((data)=> {
      console.info('Succeeded in enabling the full-screen mode. Data: ' + JSON.stringify(data))
  }).catch((err)=>{
      console.error('Failed to enable the full-screen mode. Cause: ' + JSON.stringify(err));
  });
  ```

### setLayoutFullScreen<sup>7+</sup>

setLayoutFullScreen(isLayoutFullScreen: boolean, callback: AsyncCallback&lt;void&gt;): void

设置窗口的布局是否为全屏显示状态，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名             | 类型                      | 必填 | 说明                                                         |
| ------------------ | ------------------------- | ---- | ------------------------------------------------------------ |
| isLayoutFullScreen | boolean                   | 是   | 窗口的布局是否为全屏显示状态，且全屏状态下状态栏、导航栏仍然显示。 |
| callback           | AsyncCallback&lt;void&gt; | 是   | 回调函数。                                                   |

**示例：** 

  ```js
  var isLayoutFullScreen= true;
  windowClass.setLayoutFullScreen(isLayoutFullScreen, (err, data) => {
      if (err.code) {
          console.error('Failed to set the window layout to full-screen mode. Cause:' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in setting the window layout to full-screen mode. Data: ' + JSON.stringify(data))
  });
  ```

### setLayoutFullScreen<sup>7+</sup>

setLayoutFullScreen(isLayoutFullScreen: boolean): Promise&lt;void&gt;

设置窗口的布局是否为全屏显示状态，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名             | 类型    | 必填 | 说明                                                         |
| ------------------ | ------- | ---- | ------------------------------------------------------------ |
| isLayoutFullScreen | boolean | 是   | 窗口的布局是否为全屏显示状态，且全屏状态下状态栏、导航栏仍然显示。 |

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
  var isLayoutFullScreen = true;
  let promise = windowClass.setLayoutFullScreen(isLayoutFullScreen);
  promise.then((data)=> {
      console.info('Succeeded in setting the window layout to full-screen mode. Data: ' + JSON.stringify(data))
  }).catch((err)=>{
      console.error('Failed to set the window layout to full-screen mode. Cause:' + JSON.stringify(err));
  });
  ```

### setSystemBarEnable<sup>7+</sup>

setSystemBarEnable(names: Array<'status' | 'navigation'>, callback: AsyncCallback&lt;void&gt;): void

设置导航栏、状态栏的可见模式，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                      | 必填 | 说明                                                         |
| -------- | ------------------------- | ---- | ------------------------------------------------------------ |
| names    | Array                     | 是   | 设置状态栏和导航栏是否显示。例如，需全部显示，该参数设置为["status",&nbsp;"navigation"], 不设置，则默认不显示。 |
| callback | AsyncCallback&lt;void&gt; | 是   | 回调函数。                                                   |

**示例：** 

  ```js
  var names = ["status", "navigation"];
  windowClass.setSystemBarEnable(names, (err, data) => {
      if (err.code) {
          console.error('Failed to set the system bar to be visible. Cause:' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in setting the system bar to be visible. Data: ' + JSON.stringify(data))
  });
  ```

### setSystemBarEnable<sup>7+</sup>

setSystemBarEnable(names: Array<'status' | 'navigation'>): Promise&lt;void&gt;

设置导航栏、状态栏的可见模式，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名 | 类型  | 必填 | 说明                                                         |
| ------ | ----- | ---- | ------------------------------------------------------------ |
| names  | Array | 是   | 设置状态栏和导航栏是否显示。例如，需全部显示，该参数设置为["status",&nbsp;"navigation"], 不设置，则默认不显示。 |

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
  var names = ["status", "navigation"];
  let promise = windowClass.setSystemBarEnable(names);
  promise.then((data)=> {
      console.info('Succeeded in setting the system bar to be visible. Data: ' + JSON.stringify(data))
  }).catch((err)=>{
      console.error('Failed to set the system bar to be visible. Cause:' + JSON.stringify(err));
  });
  ```

### setSystemBarProperties

setSystemBarProperties(systemBarProperties: SystemBarProperties, callback: AsyncCallback&lt;void&gt;): void

设置窗口内导航栏、状态栏的属性，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名              | 类型                                        | 必填 | 说明                 |
| ------------------- | ------------------------------------------- | ---- | -------------------- |
| SystemBarProperties | [SystemBarProperties](#systembarproperties) | 是   | 导航栏状态栏的属性。 |
| callback            | AsyncCallback&lt;void&gt;                   | 是   | 回调函数。           |

**示例：** 

  ```js
  var SystemBarProperties={
      statusBarColor: '#ff00ff',
      navigationBarColor: '#00ff00',
      //以下两个属性从API Version7开始支持
      isStatusBarLightIcon: true,
      isNavigationBarLightIcon:false,
      //以下两个属性从API Version8开始支持
      statusBarContentColor:'#ffffff',
      navigationBarContentColor:'#00ffff'
  };
  windowClass.setSystemBarProperties(SystemBarProperties, (err, data) => {
      if (err.code) {
          console.error('Failed to set the system bar properties. Cause: ' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in setting the system bar properties. Data: ' + JSON.stringify(data))
  });
  ```

### setSystemBarProperties

setSystemBarProperties(systemBarProperties: SystemBarProperties): Promise&lt;void&gt;

设置窗口内导航栏、状态栏的属性，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名              | 类型                                        | 必填 | 说明                 |
| ------------------- | ------------------------------------------- | ---- | -------------------- |
| SystemBarProperties | [SystemBarProperties](#systembarproperties) | 是   | 导航栏状态栏的属性。 |

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
  var SystemBarProperties={
      statusBarColor: '#ff00ff',
      navigationBarColor: '#00ff00',
      //以下两个属性从API Version7开始支持
      isStatusBarLightIcon: true,
      isNavigationBarLightIcon:false,
      //以下两个属性从API Version8开始支持
      statusBarContentColor:'#ffffff',
      navigationBarContentColor:'#00ffff'
  };
  let promise = windowClass.setSystemBarProperties(SystemBarProperties);
  promise.then((data)=> {
      console.info('Succeeded in setting the system bar properties. Data: ' + JSON.stringify(data))
  }).catch((err)=>{
      console.error('Failed to set the system bar properties. Cause: ' + JSON.stringify(err));
  });
  ```

### loadContent<sup>7+</sup>

loadContent(path: string, callback: AsyncCallback&lt;void&gt;): void

当前窗口加载具体页面内容，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                      | 必填 | 说明                 |
| -------- | ------------------------- | ---- | -------------------- |
| path     | string                    | 是   | 设置加载页面的路径。 |
| callback | AsyncCallback&lt;void&gt; | 是   | 回调函数。           |

**示例：** 

  ```js
  windowClass.loadContent("pages/page2/page2", (err, data) => {
     if (err.code) {
           console.error('Failed to load the content. Cause:' + JSON.stringify(err));
           return;
     }
    console.info('Succeeded in loading the content. Data: ' + JSON.stringify(data))
  });
  ```

### loadContent<sup>7+</sup>

loadContent(path: string): Promise&lt;void&gt;

当前窗口加载具体页面内容，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名 | 类型   | 必填 | 说明                 |
| ------ | ------ | ---- | -------------------- |
| path   | string | 是   | 设置加载页面的路径。 |

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
  let promise = windowClass.loadContent("pages/page2/page2");
  promise.then((data)=> {
      console.info('Succeeded in loading the content. Data: ' + JSON.stringify(data))
  }).catch((err)=>{
      console.error('Failed to load the content. Cause: ' + JSON.stringify(err));
  });
  ```

### isShowing<sup>7+</sup>

isShowing(callback: AsyncCallback&lt;boolean&gt;): void

判断当前窗口是否已显示，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                         | 必填 | 说明                             |
| -------- | ---------------------------- | ---- | -------------------------------- |
| callback | AsyncCallback&lt;boolean&gt; | 是   | 回调函数返回是否显示子窗口结果。 |

**示例：** 

  ```js
  windowClass.isShowing((err, data) => {
      if (err.code) {
          console.error('Failed to check whether the window is showing. Cause:' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in checking whether the window is showing. Data: ' + JSON.stringify(data))
  });
  ```

### isShowing<sup>7+</sup>

isShowing(): Promise&lt;boolean&gt;

判断当前窗口是否已显示，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**返回值：** 

| 类型                   | 说明                                                  |
| ---------------------- | ----------------------------------------------------- |
| Promise&lt;boolean&gt; | 以Promise形式返回结果，返回当前窗口是否已显示的结果。 |

**示例：** 

  ```js
  let promise = windowClass.isShowing();
  promise.then((data)=> {
      console.info('Succeeded in checking whether the window is showing. Data: ' + JSON.stringify(data))
  }).catch((err)=>{
      console.error('Failed to check whether the window is showing. Cause: ' + JSON.stringify(err));
  });
  ```

### on('windowSizeChange')<sup>7+</sup>

on(type:  'windowSizeChange', callback: Callback&lt;Size&gt;): void

开启监听。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                          | 必填 | 说明                                                     |
| -------- | ----------------------------- | ---- | -------------------------------------------------------- |
| type     | string                        | 是   | 监听事件，固定为'windowSizeChange'，即窗口尺寸变化事件。 |
| callback | Callback&lt;[Size](#size)&gt; | 是   | 回调返回监听到的信息。                                   |

**示例：** 

  ```js
  var type = 'windowSizeChange';
  windowClass.on(type, (data) => {
      console.info('Succeeded in enabling the listener for window size changes. Data: ' + JSON.stringify(data));
  });
  ```

### off('windowSizeChange')<sup>7+</sup>

off(type: 'windowSizeChange', callback?: Callback&lt;Size &gt;): void

关闭监听。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                          | 必填 | 说明                                                     |
| -------- | ----------------------------- | ---- | -------------------------------------------------------- |
| type     | string                        | 是   | 监听事件，固定为'windowSizeChange'，即窗口尺寸变化事件。 |
| callback | Callback&lt;[Size](#size)&gt; | 否   | 回调返回监听到的信息。                                   |

**示例：** 

  ```js
  var type = 'windowSizeChange';
  windowClass.off(type);
  ```

### on('systemAvoidAreaChange')<sup>7+</sup>

on(type: 'systemAvoidAreaChange', callback: Callback&lt;AvoidArea&gt;): void

开启监听。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                                    | 必填 | 说明                                                         |
| -------- | --------------------------------------- | ---- | ------------------------------------------------------------ |
| type     | string                                  | 是   | 监听事件，固定为'systemAvoidAreaChange'，即系统窗口规避区变化事件。 |
| callback | Callback&lt;[AvoidArea](#avoidarea)&gt; | 是   | 回调返回监听到的信息。                                       |

**示例：** 

  ```js
  var type = 'systemAvoidAreaChange';
  windowClass.on(type, (data) => {
      console.info('Succeeded in enabling the listener for system avoid area changes. Data: ' + JSON.stringify(data));
  });
  ```

### off('systemAvoidAreaChange')<sup>7+</sup>

off(type: 'systemAvoidAreaChange', callback?: Callback&lt;AvoidArea&gt;): void

关闭监听。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                                    | 必填 | 说明                                                         |
| -------- | --------------------------------------- | ---- | ------------------------------------------------------------ |
| type     | string                                  | 是   | 监听事件，固定为'systemAvoidAreaChange'，即系统窗口规避区变化事件。 |
| callback | Callback&lt;[AvoidArea](#avoidarea)&gt; | 否   | 回调返回监听到的信息。                                       |

**示例：** 

  ```js
  var type = 'systemAvoidAreaChange';
  windowClass.off(type);
  ```

### on('keyboardHeightChange')<sup>7+</sup>

on(type: 'keyboardHeightChange', callback: Callback&lt;number&gt;): void

开启键盘高度变化的监听。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型               | 必填 | 说明                                                         |
| -------- | ------------------ | ---- | ------------------------------------------------------------ |
| type     | string             | 是   | 监听事件，固定为'keyboardHeightChange'，即键盘高度变化事件。 |
| callback | Callbacknumber&gt; | 是   | 回调返回监听到的信息。                                       |

**示例：** 

  ```js
  var type = 'keyboardHeightChange';
  windowClass.on(type, (data) => {
      console.info('Succeeded in enabling the listener for keyboard height changes. Data: ' + JSON.stringify(data));
  });
  ```

### off('keyboardHeightChange')<sup>7+</sup>

off(type: 'keyboardHeightChange', callback?: Callback&lt;number&gt;): void

关闭键盘高度变化的监听。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                   | 必填 | 说明                                                         |
| -------- | ---------------------- | ---- | ------------------------------------------------------------ |
| type     | string                 | 是   | 监听事件，固定为'keyboardHeightChange'，即键盘高度变化事件。 |
| callback | Callback&lt;number&gt; | 否   | 回调返回监听到的信息。                                       |

**示例：** 

  ```js
  var type = 'keyboardHeightChange';
  windowClass.off(type);
  ```

### isSupportWideGamut<sup>8+</sup>

isSupportWideGamut(callback: AsyncCallback&lt;boolean&gt;): void

判断当前窗口是否支持广色域模式，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                         | 必填 | 说明                             |
| -------- | ---------------------------- | ---- | -------------------------------- |
| callback | AsyncCallback&lt;boolean&gt; | 是   | 回调函数返回是否支持广色域模式。 |

**示例：** 

  ```js
  windowClass.isSupportWideGamut((err, data) => {
      if (err.code) {
          console.error('Failed to check whether the window support WideGamut. Cause:' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in checking whether the window support WideGamut Data: ' + JSON.stringify(data))
  })
  ```

### isSupportWideGamut<sup>8+</sup>

isSupportWideGamut(): Promise&lt;boolean&gt;

判断当前窗口是否支持广色域模式，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**返回值：** 

| 类型                   | 说明                                                         |
| ---------------------- | ------------------------------------------------------------ |
| Promise&lt;boolean&gt; | 以Promise形式返回结果，返回当前窗口是否支持广色域模式的结果。 |

**示例：** 

  ```js
  let promise = windowClass.isSupportWideGamut();
  promise.then((data)=> {
      console.info('Succeeded in checking whether the window support WideGamut. Data: ' + JSON.stringify(data))
  }).catch((err)=>{
      console.error('Failed to check whether the window support WideGamut. Cause: ' + JSON.stringify(err));
  });
  ```

### setColorSpace<sup>8+</sup>

setColorSpace(colorSpace:ColorSpace, callback: AsyncCallback&lt;void&gt;): void

设置当前窗口为广色域模式或默认色域模式，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名     | 类型                      | 必填 | 说明         |
| ---------- | ------------------------- | ---- | ------------ |
| colorSpace | [ColorSpace](#colorspace) | 是   | 设置色域模式 |
| callback   | AsyncCallback&lt;void&gt; | 是   | 回调函数。   |

**示例：** 

  ```js
  windowClass.setColorSpace(window.ColorSpace.WIDE_GAMUT, (err, data) => {
      if (err.code) {
          console.error('Failed to set window colorspace. Cause:' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in setting window colorspace. Data: ' + JSON.stringify(data))
  })
  ```

### setColorSpace<sup>8+</sup>

setColorSpace(colorSpace:ColorSpace): Promise&lt;void&gt;

设置当前窗口为广色域模式或默认色域模式，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名     | 类型                      | 必填 | 说明         |
| ---------- | ------------------------- | ---- | ------------ |
| colorSpace | [ColorSpace](#colorspace) | 是   | 设置色域模式 |

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
  let promise = windowClass.isSupportWideGamut(window.ColorSpace.WIDE_GAMUT);
  promise.then((data)=> {
      console.info('Succeeded in setting window colorspace. Data: ' + JSON.stringify(data))
  }).catch((err)=>{
      console.error('Failed to set window colorspacet. Cause: ' + JSON.stringify(err));
  });
  ```

### getColorSpace<sup>8+</sup>

getColorSpace(callback: AsyncCallback&lt;ColorSpace&gt;): void

获取当前窗口色域模式，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                                           | 必填 | 说明                       |
| -------- | ---------------------------------------------- | ---- | -------------------------- |
| callback | AsyncCallback&lt;[ColorSpace](#colorspace)&gt; | 是   | 回调函数返回当前色域模式。 |

**示例：** 

  ```js
  windowClass.getColorSpace((err, data) => {
      if (err.code) {
          console.error('Failed to get window color space. Cause:' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in getting window color space. Cause:' + JSON.stringify(data))
  })
  ```

### getColorSpace<sup>8+</sup>

getColorSpace(): Promise&lt;ColorSpace&gt;

获取当前窗口色域模式，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**返回值：** 

| 类型                                     | 说明                                      |
| ---------------------------------------- | ----------------------------------------- |
| Promise&lt;[ColorSpace](#colorspace)&gt; | 以Promise形式返回结果，返回当前色域模式。 |

**示例：** 

  ```js
  let promise = windowClass.getColorSpace();
  promise.then((data)=> {
      console.info('Succeeded in getting window color space. Cause:' + JSON.stringify(data))
  }).catch((err)=>{
      console.error('Failed to set window colorspacet. Cause: ' + JSON.stringify(err));
  });
  ```

### setBackgroundColor

setBackgroundColor(color: string, callback: AsyncCallback&lt;void&gt;): void

设置窗口的背景色，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                      | 必填 | 说明                                                         |
| -------- | ------------------------- | ---- | ------------------------------------------------------------ |
| color    | string                    | 是   | 需要设置的背景色，为16进制颜色，例如"#00FF00"或"#FF00FF00"。 |
| callback | AsyncCallback&lt;void&gt; | 是   | 回调函数。                                                   |

**示例：** 

  ```js
  var color = '#00ff33';
  windowClass.setBackgroundColor(color, (err, data) => {
      if (err.code) {
          console.error('Failed to set the background color. Cause: ' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in setting the background color. Data: ' + JSON.stringify(data));
  });
  ```

### setBackgroundColor

setBackgroundColor(color: string): Promise&lt;void&gt;

设置窗口的背景色，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名 | 类型   | 必填 | 说明                                                         |
| ------ | ------ | ---- | ------------------------------------------------------------ |
| color  | string | 是   | 需要设置的背景色，为16进制颜色，例如"#00FF00"或"#FF00FF00"。 |

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
  var color = '#00ff33';
  let promise = windowClass.setBackgroundColor(color);
  promise.then((data)=> {
      console.info('Succeeded in setting the background color. Data: ' + JSON.stringify(data))
  }).catch((err)=>{
      console.error('Failed to set the background color. Cause: ' + JSON.stringify(err));
  });
  ```

### setBrightness

setBrightness(brightness: number, callback: AsyncCallback&lt;void&gt;): void

设置屏幕亮度值，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名     | 类型                      | 必填 | 说明                                 |
| ---------- | ------------------------- | ---- | ------------------------------------ |
| brightness | number                    | 是   | 屏幕亮度值，值为0-1之间。1表示最亮。 |
| callback   | AsyncCallback&lt;void&gt; | 是   | 回调函数。                           |

**示例：** 

  ```js
  var brightness = 1;
  windowClass.setBrightness(brightness, (err, data) => {
      if (err.code) {
          console.error('Failed to set the brightness. Cause: ' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in setting the brightness. Data: ' + JSON.stringify(data));
  });
  ```

### setBrightness

setBrightness(brightness: number): Promise&lt;void&gt;

设置屏幕亮度值，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名     | 类型   | 必填 | 说明                                 |
| ---------- | ------ | ---- | ------------------------------------ |
| brightness | number | 是   | 屏幕亮度值，值为0-1之间。1表示最亮。 |

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
  var brightness = 1;
  let promise = windowClass.setBrightness(brightness);
  promise.then((data)=> {
      console.info('Succeeded in setting the brightness. Data: ' + JSON.stringify(data))
  }).catch((err)=>{
      console.error('Failed to set the brightness. Cause: ' + JSON.stringify(err));
  });
  ```

### setFocusable<sup>7+</sup>

setFocusable(isFocusable: boolean, callback: AsyncCallback&lt;void&gt;): void

设置点击时是否支持切换焦点窗口，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名      | 类型                      | 必填 | 说明                         |
| ----------- | ------------------------- | ---- | ---------------------------- |
| isFocusable | boolean                   | 是   | 点击时是否支持切换焦点窗口。 |
| callback    | AsyncCallback&lt;void&gt; | 是   | 回调函数。                   |

**示例：** 

  ```js
  var isFocusable= true;
  windowClass.setFocusable(isFocusable, (err, data) => {
      if (err.code) {
          console.error('Failed to set the window to be focusable. Cause:' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in setting the window to be focusable. Data: ' + JSON.stringify(data));
  });
  ```

### setFocusable<sup>7+</sup>

setFocusable(isFocusable: boolean): Promise&lt;void&gt;

设置点击时是否支持切换焦点窗口，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名      | 类型    | 必填 | 说明                         |
| ----------- | ------- | ---- | ---------------------------- |
| isFocusable | boolean | 是   | 点击时是否支持切换焦点窗口。 |

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
  var isFocusable= true;
  let promise = windowClass.setFocusable(isFocusable);
  promise.then((data)=> {
      console.info('Succeeded in setting the window to be focusable. Data: ' + JSON.stringify(data))
  }).catch((err)=>{
      console.error('Failed to set the window to be focusable. Cause: ' + JSON.stringify(err));
  });
  ```

### setKeepScreenOn

setKeepScreenOn(isKeepScreenOn: boolean, callback: AsyncCallback&lt;void&gt;): void

设置屏幕是否为常亮状态，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名         | 类型                      | 必填 | 说明                     |
| -------------- | ------------------------- | ---- | ------------------------ |
| isKeepScreenOn | boolean                   | 是   | 是否设置为屏幕常亮状态。 |
| callback       | AsyncCallback&lt;void&gt; | 是   | 回调函数。               |

**示例：** 

  ```js
  var isKeepScreenOn = true;
  windowClass.setKeepScreenOn(isKeepScreenOn, (err, data) => {
      if (err.code) {
          console.error('Failed to set the screen to be always on. Cause: ' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in setting the screen to be always on. Data: ' + JSON.stringify(data));
  });
  ```

### setKeepScreenOn

setKeepScreenOn(isKeepScreenOn: boolean): Promise&lt;void&gt;

设置屏幕是否为常亮状态，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名         | 类型    | 必填 | 说明                     |
| -------------- | ------- | ---- | ------------------------ |
| isKeepScreenOn | boolean | 是   | 是否设置为屏幕常亮状态。 |

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
  var isKeepScreenOn= true;
  let promise = windowClass.setKeepScreenOn(isKeepScreenOn);
  promise.then((data)=> {
      console.info('Succeeded in setting the screen to be always on. Data: ' + JSON.stringify(data))
  }).catch((err)=>{
      console.error('Failed to set the screen to be always on. Cause: ' + JSON.stringify(err));
  });
  ```

### setPrivacyMode<sup>7+</sup>

setPrivacyMode(isPrivacyMode: boolean, callback: AsyncCallback&lt;void&gt;): void

设置窗口是否为隐私模式，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名        | 类型                      | 必填 | 说明                 |
| ------------- | ------------------------- | ---- | -------------------- |
| isPrivacyMode | boolean                   | 是   | 窗口是否为隐私模式。 |
| callback      | AsyncCallback&lt;void&gt; | 是   | 回调函数。           |

**示例：** 

  ```js
  var isPrivacyMode = true;
  windowClass.setPrivacyMode(isPrivacyMode, (err, data) => {
      if (err.code) {
          console.error('Failed to set the window to privacy mode. Cause:' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in setting the window to privacy mode. Data:' + JSON.stringify(data));
  
  });
  ```

### setPrivacyMode<sup>7+</sup>

setPrivacyMode(isPrivacyMode: boolean): Promise&lt;void&gt;

设置窗口是否为隐私模式，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名        | 类型    | 必填 | 说明                 |
| ------------- | ------- | ---- | -------------------- |
| isPrivacyMode | boolean | 是   | 窗口是否为隐私模式。 |

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
  var isPrivacyMode = true;
  let promise = windowClass.setPrivacyMode(isPrivacyMode);
  promise.then((data)=> {
      console.info('Succeeded in setting the window to privacy mode. Data: ' + JSON.stringify(data))
  }).catch((err)=>{
      console.error('Failed to set the window to privacy mode. Cause: ' + JSON.stringify(err));
  });
  ```

### setTouchable<sup>7+</sup>

setTouchable(isTouchable: boolean, callback: AsyncCallback&lt;void&gt;): void

设置窗口是否为可触状态，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名      | 类型                      | 必填 | 说明                 |
| ----------- | ------------------------- | ---- | -------------------- |
| isTouchable | boolean                   | 是   | 窗口是否为可触状态。 |
| callback    | AsyncCallback&lt;void&gt; | 是   | 回调函数。           |

**示例：** 

  ```js
  var isTouchable = true;
  windowClass.setTouchable(isTouchable, (err, data) => {
      if (err.code) {
          console.error('Failed to set the window to be touchable. Cause:' + JSON.stringify(err));
          return;
      }
      console.info('Succeeded in setting the window to be touchable. Data:' + JSON.stringify(data));
  
  });
  ```

### setTouchable<sup>7+</sup>

setTouchable(isTouchable: boolean): Promise&lt;void&gt;

设置窗口是否为可触状态，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名      | 类型    | 必填 | 说明                 |
| ----------- | ------- | ---- | -------------------- |
| isTouchable | boolean | 是   | 窗口是否为可触状态。 |

**返回值：** 

| 类型                | 说明                                            |
| ------------------- | ----------------------------------------------- |
| Promise&lt;void&gt; | 以Promise形式返回结果，返回当前函数执行的结果。 |

**示例：** 

  ```js
  var isTouchable = true;
  let promise = windowClass.setTouchable(isTouchable);
  promise.then((data)=> {
      console.info('Succeeded in setting the window to be touchable. Data: ' + JSON.stringify(data))
  }).catch((err)=>{
      console.error('Failed to set the window to be touchable. Cause: ' + JSON.stringify(err));
  });
  ```

## WindowStageEventType<sup>9+</sup>

WindowStage生命周期。

**系统能力：** 以下各项对应的系统能力均为SystemCapability.WindowManager.WindowManager.Core

| 名称       | 默认值 | 说明     |
| ---------- | ------ | -------- |
| FOREGROUND | 1      | 切到前台 |
| ACTIVE     | 2      | 获焦状态 |
| INACTIVE   | 3      | 失焦状态 |
| BACKGROUND | 4      | 切到后台 |

## WindowStage<sup>9+</sup>

下列API示例中都需在[onWindowStageCreate()](js-apis-application-ability.md#abilityonwindowstagecreate)函数中使用WindowStage的实例调用对应方法。

### getMainWindow<sup>9+</sup>

getMainWindow(): Promise&lt;Window&gt;

获取该WindowStage实例下的主窗口，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**返回值：** 

| 类型                             | 说明                                                       |
| -------------------------------- | ---------------------------------------------------------- |
| Promise&lt;[Window](#window)&gt; | 以Promise形式返回结果，返回当前WindowStage下的主窗口对象。 |

**示例：** 

  ```ts
  class myAbility extends Ability {
      onWindowStageCreate(windowStage) {
          console.log('onWindowStageCreate');
          var windowClass = null;
          let promise = windowStage.getMainWindow();
          promise.then((data)=> {
          windowClass = data;
              console.info('Succeeded in obtaining the main window. Data: ' + JSON.stringify(data))
          }).catch((err)=>{
              console.error('Failed to obtain the main window. Cause: ' + JSON.stringify(err));
          });
      }
  }
  ```

### getMainWindow<sup>9+</sup>

getMainWindow(callback: AsyncCallback&lt;Window&gt;): void

获取该WindowStage实例下的主窗口，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                                   | 必填 | 说明                                    |
| -------- | -------------------------------------- | ---- | --------------------------------------- |
| callback | AsyncCallback&lt;[Window](#window)&gt; | 是   | 回调返回当前WindowStage下的主窗口对象。 |

**示例：** 

  ```ts
  class myAbility extends Ability {
      onWindowStageCreate(windowStage) {
          console.log('onWindowStageCreate');
          var windowClass = null;
          windowStage.getMainWindow((err, data) => {
              if (err.code) {
                  console.error('Failed to obtain the main window. Cause: ' + JSON.stringify(err));
                  return;
              }
              windowClass = data;
              console.info('Succeeded in obtaining the main window. Data: ' + JSON.stringify(data));
          });
      }
  }
  ```

### createSubWindow<sup>9+</sup>

createSubWindow(name: string): Promise&lt;Window&gt;

创建该WindowStage实例下的子窗口，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名 | 类型   | 必填 | 说明           |
| ------ | ------ | ---- | -------------- |
| name   | String | 是   | 子窗口的名字。 |

**返回值：** 

| 类型                             | 说明                                              |
| -------------------------------- | ------------------------------------------------- |
| Promise&lt;[Window](#window)&gt; | 以Promise形式返回结果，返回当前创建的子窗口对象。 |

**示例：** 

  ```ts
  class myAbility extends Ability {
      onWindowStageCreate(windowStage) {
          console.log('onWindowStageCreate');
          var windowClass = null;
          let promise = windowStage.createSubWindow("mySubWindow");
          promise.then((data)=> {
              windowClass = data;
              console.info('Succeeded in create sub window. Data: ' + JSON.stringify(data))
          }).catch((err)=>{
              console.error('Failed to create sub window. Cause: ' + JSON.stringify(err));
          })
      }
  }
  ```

### createSubWindow<sup>9+</sup>

createSubWindow(name: string, callback: AsyncCallback&lt;Window&gt;): void

创建该WindowStage实例下的子窗口，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                                   | 必填 | 说明                           |
| -------- | -------------------------------------- | ---- | ------------------------------ |
| name     | String                                 | 是   | 子窗口的名字。                 |
| callback | AsyncCallback&lt;[Window](#window)&gt; | 是   | 回调返回当前创建的子窗口对象。 |

**示例：** 

  ```ts
  class myAbility extends Ability {
      onWindowStageCreate(windowStage) {
          console.log('onWindowStageCreate');
          var windowClass = null;
          windowStage.createSubWindow("mySubWindow", (err, data) => {
              if (err.code) {
                  console.error('Failed to create sub window. Cause: ' + JSON.stringify(err));
                  return;
              }
              windowClass = data;
              console.info('Succeeded in create sub window. Data: ' + JSON.stringify(data));
              windowClass.resetSize(500, 1000);
          });
      }
  }
  ```

### getSubWindow<sup>9+</sup>

getSubWindow(): Promise&lt;Array&lt;Window&gt;&gt;

获取该WindowStage实例下的所有子窗口，使用Promise异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**返回值：** 

| 类型                                          | 说明                                                         |
| --------------------------------------------- | ------------------------------------------------------------ |
| Promise&lt;Array&lt;[Window](#window)&gt;&gt; | 以Promise形式返回结果，返回当前WindowStage下的所有子窗口对象。 |

**示例：** 

  ```ts
  class myAbility extends Ability {
      onWindowStageCreate(windowStage) {
          console.log('onWindowStageCreate');
          var windowClass = null;
          let promise = windowStage.getSubWindow();
          promise.then((data)=> {
              windowClass = data;
              console.info('Succeeded in obtaining the sub window. Data: ' + JSON.stringify(data))
          }).catch((err)=>{
              console.error('Failed to obtain the sub window. Cause: ' + JSON.stringify(err));
          })
      }
  }
  ```

### getSubWindow<sup>9+</sup>

getSubWindow(callback: AsyncCallback&lt;Array&lt;Window&gt;&gt;): void

获取该WindowStage实例下的所有子窗口，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                                                | 必填 | 说明                                        |
| -------- | --------------------------------------------------- | ---- | ------------------------------------------- |
| callback | AsyncCallback&lt;Array&lt;[Window](#window)&gt;&gt; | 是   | 回调返回当前WindowStage下的所有子窗口对象。 |

**示例：** 

  ```ts
  class myAbility extends Ability {
      onWindowStageCreate(windowStage) {
          console.log('onWindowStageCreate');
          var windowClass = null;
          windowStage.getSubWindow((err, data) => {
              if (err.code) {
                  console.error('Failed to obtain the sub window. Cause: ' + JSON.stringify(err));
                  return;
              }
              windowClass = data;
              console.info('Succeeded in obtaining the sub window. Data: ' + JSON.stringify(data));
          });
      }
  }
  ```

### loadContent<sup>9+</sup>

loadContent(path: string, callback: AsyncCallback&lt;void&gt;): void

为当前WindowStage的主窗口加载具体页面内容，使用callback异步回调。

**系统能力：** SystemCapability.WindowManager.WindowManager.Coretype为'windowSizeChange'

**参数：** 

| 参数名   | 类型                      | 必填 | 说明                 |
| -------- | ------------------------- | ---- | -------------------- |
| path     | string                    | 是   | 设置加载页面的路径。 |
| callback | AsyncCallback&lt;void&gt; | 是   | 回调函数。           |

**示例：** 

  ```ts
  class myAbility extends Ability {
      onWindowStageCreate(windowStage) {
          console.log('onWindowStageCreate');
          windowStage.loadContent("pages/page2", (err, data) => {
              if (err.code) {
                  console.error('Failed to load the content. Cause:' + JSON.stringify(err));
                  return;
              }
              console.info('Succeeded in loading the content. Data: ' + JSON.stringify(data))
          });
      }
  }
  ```

### on('windowStageEvent')<sup>9+</sup>

on(eventType: 'windowStageEvent', callback: Callback&lt;WindowStageEventType&gt;): void

开启WindowStage生命周期变化的监听。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                                                         | 必填 | 说明                                                         |
| -------- | ------------------------------------------------------------ | ---- | ------------------------------------------------------------ |
| type     | string                                                       | 是   | 监听事件，固定为'windowStageEvent'，即WindowStage生命周期变化事件。 |
| callback | Callback&lt;[WindowStageEventType](#windowstageeventtype9)&gt; | 是   | 回调返回监听到的信息。                                       |

**示例：** 

  ```ts
  class myAbility extends Ability {
      onWindowStageCreate(windowStage) {
          console.log('onWindowStageCreate');
          var type = 'windowStageEvent';
          windowStage.on(type, (data) => {
              console.info('Succeeded in enabling the listener for window stage event changes. Data: ' + JSON.stringify(data));
          });
      }
  }
  ```

### off('windowStageEvent')<sup>9+</sup>

off(eventType: 'windowStageEvent', callback?: Callback&lt;WindowStageEventType&gt;): void

关闭WindowStage生命周期变化的监听。

**系统能力：** SystemCapability.WindowManager.WindowManager.Core

**参数：** 

| 参数名   | 类型                                                         | 必填 | 说明                                                         |
| -------- | ------------------------------------------------------------ | ---- | ------------------------------------------------------------ |
| type     | string                                                       | 是   | 监听事件，固定为'windowStageEvent'，即WindowStage生命周期变化事件。 |
| callback | Callback&lt;[WindowStageEventType](#windowstageeventtype9)&gt; | 否   | 回调返回监听到的信息。                                       |

**示例：** 

  ```ts
  class myAbility extends Ability {
      onWindowStageCreate(windowStage) {
          console.log('onWindowStageCreate');
          var type = 'windowStageEvent';
          windowStage.off(type);
      }
  }
  ```
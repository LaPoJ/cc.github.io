## Message

### **<font color=#FF0000>用前必读</font>**

> 目前该组件适用于静态页的开发，**注意：** **没有导出模板，请勿使用`import`或者`require`导入**
使用时应当使用`script:src`的方式引入 `js` 文件

- **<font color=red>[查看API](#api)</font>**
- **[所有参数见文章底部API参数配置](#params)**


### 展示信息

> 页面展示信息使用方法，查看[API](#api)

```javascript
// 最简单的使用方法
$Message('$Message展示信息') // msg 类型为字符串

// 提示信息为json格式对象
$Message({
  message: "$Message展示信息" // 页面提示为 msg
})

$Message.info({
    message: "$Message展示信息"
})

// 选择挂载的dom节点
$Message({
  el: '#test', // 选择挂载的 dom 的 ID 为 test 默认挂载节点为 body
  // el: '.app', // 选择挂载的 dom 类名为 app
  message： '挂载的app',
})

// 可选展示时间
$Message({
  message: '$Message展示信息',
  duration: 2500, //展示时间 默认时间2500，单位(ms)
})

$Message({
    message: "持续展示提示信息"，
    duration: 0, // duration 为 0 时，将持续展示提示信息
})
```

### 成功、失败、警告 提示信息

> **注意**：  `success`、`error`、`warning`、`info`  使用方式一样

```javascript
// 最简单用法
$Message.success('成功')

$Message.success({
  message: '成功'
})
```

### <div id="clear">关闭提示</div>
```javascript
// 关闭提示
$Message.clear()
```

**<div id="api"><font color=#FF0000>API</font></div>**

| 方法名        | 说明                 |        参数            |  返回值   |
| :------------ | :------------------- | :-----------------:    | :-------: |
| `$Message`    | 展示提示             | `options` \| `message` | `$Message`实例 |
| `$Message.info` | 展示 `信息` 提示   | `options` \| `message` | `$Message`实例 |
| `$Message.success` | 展示 `成功` 提示         | `options` \| `message` | `$Message`实例 |
| `$Message.error`   | 展示 `失败` \| `错误` 提示  | `options` \| `message` | `$Message`实例 |
| `$Message.warning`   | 展示 `警告` 提示  | `options` \| `message` | `$Message`实例 |
| `$Message.clear`   | 关闭提示              |       `null`          |  `void`   |

**<div id="params"><font color=#FF0000>API Options</font></div>**

| 参数     | 说明                                                         |   类型    | 默认值  |
| :------- | :----------------------------------------------------------- | :-------: | :-----: |
| `el`       | `$Message` 挂载的 `dom` 节点，默认挂载节点为`body`，可指定挂载节点。`可选` | `string`  |  `app`  |
| `type`     | 提示类型，默认为`text`，可选类型为`success`、`error`、`loading`，`可选` | `string`  | `text`  |
| `message`  | 需要提示的内容，`必选`              | `string`  | `null`  |
| `duration` | `$Message`显示时间，可自选提示时间；当`duration`为`0`时展示内容将一直存在，销毁则需要使用`$Message.clear()` 销毁；(单位: ms)，`可选` | `number`  | `2500`  |

**使用须知**

> 目前页面只会存在一个 `$Message` 提示, 请注意合理使用
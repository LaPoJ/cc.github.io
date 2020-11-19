## Toast

### **<font color=#FF0000>用前必读</font>**

> 目前该组件适用于静态页的开发，**注意：** **没有导出模板，请勿使用`import`或者`require`导入**
使用时应当使用`script:src`的方式引入js文件

- **<font color=red>[查看API](#api)</font>**
- **[所有参数见文章底部API参数配置](#params)**


### 展示信息

> 页面展示信息使用方法，查看[API](#api)

```javascript
// 最简单的使用方法
Toast('Toast展示信息') // msg 类型为字符串

// 提示信息为json格式对象
Toast({
  message: "Toast展示信息" // 页面提示为 msg
})

// 选择挂载的dom节点
Toast({
  el: 'test', // 选择挂载的dom的ID为test 默认ID为app
  message： '挂载的app',
})

// 可选展示时间
Toast({
  message: 'Toast展示信息',
  duration: 3000, //展示时间 默认时间2000，单位(ms)
})
```

### 加载提示

```javascript
// 直接使用
Toast.loading('加载中') // loading提示不建议这样使用

Toast.loading({
  duration: 0, // 持续展示loading提示
  message: '加载中',
})

Toast({
  type: 'loading',

})
```
> `loading` 应和[`Toast.clear`](#clear)搭配使用

### 成功、失败提示
```javascript
// 最简单用法
Toast.success('成功')

Toast.success({
  message: '成功'
})
```

> `success`和`error`使用方式一样

### <div id="clear">关闭提示</div>
```javascript
// 关闭提示
Toast.clear()
```

**<div id="api"><font color=#FF0000>API</font></div>**

| 方法名        | 说明                   |        参数           |  返回值   |
| :------------ | :------------------- | :-----------------:  | :-------: |
| `Toast`        | 展示提示              | `option` \| `message` | `Toast`实例 |
| `Toast.loading` | 展示`加载`提示         | `option` \| `message` | `Toast`实例 |
| `Toast.success` | 展示`成功`提示         | `option` \| `message` | `Toast`实例 |
| `Toast.error`   | 展示`失败`\|`错误`提示  | `option` \| `message` | `Toast`实例 |
| `Toast.clear`   | 关闭提示              |       `null`          |  `void`   |

**<div id="params"><font color=#FF0000>API Options</font></div>**

| 参数     | 说明                                                         |   类型    | 默认值  |
| :------- | :----------------------------------------------------------- | :-------: | :-----: |
| `el`       | `toast`挂载的`dom`节点，默认挂载节点为`app`，若无`app`节点需要指定挂载节点，`可选` | `string`  |  `app`  |
| `type`     | 提示类型，默认为`text`，可选类型为`success`、`error`、`loading`，`可选` | `string`  | `text`  |
| `mask`     | 背景蒙层，适用于`loading`提示给页面提供模糊蒙层，`可选` | `boolean` | `false` |
| `message`  | 需要提示的内容，`必选`              | `string`  | `null`  |
| `duration` | `toast`显示时间，可自选提示时间；当`duration`为`0`时展示内容将一直存在，销毁则需要使用`Toast.clear()` 销毁；(单位: ms)，`可选` | `number`  | `2000`  |
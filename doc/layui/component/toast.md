## 基本介绍

Notify 组件常用于 消息通知 场景 (新增)

## 使用方式

#### 开发环境

```html
<link rel="stylesheet" href="component/pear/css/pear.css">
 或
<link rel="stylesheet" href="component/pear/css/pear-module/notify.css">
 并
<script src="component/layui/layui.js"></script>
 并
<script src="component/pear/pear.js"></script>
```

#### 简单使用

```javascript
layui.use(['toast', 'jquery', 'layer', 'code'], function() {
    var toast = layui.toast;
                         
    toast.success({title:"成功消息",message:"消息描述"})

    toast.error({title:"危险消息",message:"消息描述"})

    toast.warning({title:"警告消息",message:"消息描述"})

    toast.info({title:"通知消息",message:"消息描述"})
})

```

#### 消息移除

```javascript
layui.use(['toast', 'jquery', 'layer', 'code'], function() {
    var toast = layui.toast;
                         
    toast.destroy();
})
```

toast.destroy 清除全部消息
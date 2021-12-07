## 核心函数

简介: admin.js 除渲染基本框架的能力外，还提供了大量的 api 全局函数，它可以帮助你更高的构建应用程序


1. 侧边状态切换
```
parent.layui.admin.collaspeSide()
```

2. 刷新当前页面
```
parent.layui.admin.refreshThis()
```

3. 刷新指定页面
```
parent.layui.admin.refresh(14)
```

4. 新增选项卡
```
parent.layui.admin.addTab(14,"百度一下","http://www.bing.com")
```

5. 关闭指定选项卡
```
parent.layui.admin.closeTab(14)
```

6. 关闭当前选项卡
```
parent.layui.admin.closeCurrentTab()
```

7. 关闭所有选项卡
```
parent.layui.admin.closeAllTab()
```

8. 关闭其他选项卡
```
parent.layui.admin.closeOtherTab()
```

9. 切换 IFrame 地址
```
parent.layui.admin.changeIframe(14,"百度一下","http://www.bing.com")
```

10. 兼容跳转, 支持 Iframe 与 MuiltTab 模式
```
parent.layui.admin.jump(14,"百度一下","http://www.bing.com")
```

11. 全屏状态切换
```
parent.layui.admin.fullScreen()
```


备注: 调用时，使用 parent 的目的，使用场景为子页面，如果在 index.html 中使用，切记去掉 parent
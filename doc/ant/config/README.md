## 配置文件

Pear.config.json 框架配置文件，通过配置文件的修改，渲染出适合你的界面布局

admin.reander() 函数在初始化时会读取 pear.config.json 配置文件构建框架

> 默认读取 index.html 同级目录下的 `pear.config.json` 。

那么我们如何去自定义配置文件的读取路径

举例，我们在 index.html 同级目录下创建 config 目录，然后将配置文件存放到该目录中

此时你只需要在 index.html ，admin.render() 之前去设置全局配置即可，代码如下

```javascript

admin.setConfigPath("config/pear.config.json");

admin.render();
```

setConfigPath(..) 用于重新定义配置文件的存放位置


接下来，我们来看配置文件的配置信息都有哪些


## 基础配置

```json
"logo": {
	"title": "Pear Admin",
	"image": "admin/images/logo.png"
	.....
}
```

- title : 网站名称
- image : 网站图标


## 侧边菜单

```json
"menu": {
	"data": "admin/data/menu.json",
	"accordion": true,
	"control": false,
	"select": "0",
	"async": true
	.....
}
```

- data : 菜单数据
- accordion : 是否开启菜单手风琴
- control : 菜单模式
- select : 默认选中菜单项 (ID)
- async: 渲染模式

## 多选项卡

```json
"tab": {
	"muiltTab": true,
	"keepState": true,
	"tabMax": 30,
	"index": {
		"id": "0",
		"href": "view/console/console1.html",
		"title": "首页"
	}
	.....
}
```

- muiltTab : 是否开启多标签页
- keepState : 选项卡切换时，是否刷新页面
- tabMax : 最大打开标签页数量
- index: 主页初始化数据

## 主题配置

```json
"theme": {
	"defaultColor": "2",
	"defaultMenu": "dark-theme",
	"allowCustom": true
	.....
}
```

- defaultColor : 默认主题
- defaultMenu : 菜单默认颜色 (dark-theme / light-theme)
- allowCustom : 是否允许用户自行切换主题

```json
"colors": [
	{
		"id": "1",
		"color": "#FF5722"
	},
	{
		"id": "2",
		"color": "#5FB878"
	},
	{
		"id": "3",
		"color": "#1E9FFF"
	}, {
		"id": "4",
		"color": "#FFB800"
	}, {
		"id": "5",
		"color": "darkgray"
	}
	.....
]
```

- id : 主题编号
- color: 主题颜色

## 其他配置

```json
"other": {
	"keepLoad": 1200,
	.....
	.....
	.....
}
```
- keepLoad : 主页加载时长

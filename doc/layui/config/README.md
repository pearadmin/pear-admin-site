## 配置文件  :id=config

Pear.config.json 框架配置文件，通过配置文件的修改，渲染出适合你的界面布局


#### 基础配置

```json
"logo": {
	"title": "Pear Admin",
	"image": "admin/images/logo.png"
}
```

- title : 网站名称
- image : 网站图标


#### 菜单配置

```json
"menu": {
	"data": "admin/data/menu.json",
	"accordion": true,
	"control": false,
	"select": "0"
}
```

- data : 菜单数据
- accordion : 是否开启菜单手风琴
- control : 菜单模式
- select : 默认选中菜单项 (ID)

#### 选项卡配置

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
}
```

- muiltTab : 是否开启多标签页
- keepState : 选项卡切换时，是否刷新页面
- tabMax : 最大打开标签页数量
- index: 主页初始化数据

#### 主题配置

```json
"theme": {
	"defaultColor": "2",
	"defaultMenu": "dark-theme",
	"allowCustom": true
}
```

- defaultColor : 默认主题
- defaultMenu : 菜单默认颜色 (dark-theme / light-theme)
- allowCustom : 是否允许用户自行切换主题

#### 颜色配置

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
]
```

- id : 主题编号
- color: 主题颜色

#### 更多选项

```json
"other": {
		"keepLoad": 1200
	}
```
- keepLoad : 主页加载时长

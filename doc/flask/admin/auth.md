### 权限管理 :id=authorize

使用装饰器 @authorize时需要注意，该装饰器需要写在	@app.route	之后

```python
@authorize(power: str, log: bool)
```

第一个参数为权限 code

第二个参数为是否生成日志

```python
# 例如
@authorize("admin:power:remove", log=True)
```

在前端中，例如增加，删除按钮，对于没有编辑权限的用户不显示的话，可以使用

 `{% **if** authorize("admin:user:edit") %}`

 `{% endif %}`

例如

```python
	{% if authorize("admin:user:edit") %}
        <button class="pear-btn pear-btn-primary pear-btn-sm" lay-event="edit">
    	<i class="pear-icon pear-icon-edit"></i>
        </button>
    {% endif %}
    {% if authorize("admin:user:remove") %}
        <button class="pear-btn pear-btn-danger pear-btn-sm" lay-event="remove">
        <i class="pear-icon pear-icon-ashbin"></i>
        </button>
    {% endif %}
```


## model序列化 :id=Schema

- sqlalchemy查询的model对象转dict

  
```
 model_to_dicts(Schema, model)
```

Schema 是  序列化类,我把他放在了models文件里，觉得没有必要见一个文件夹叫Schema，也方便看着模型写序列化类

```python
# 例如
class DeptSchema(ma.Schema):  # 序列化类
    deptId = fields.Integer(attribute="id")
    parentId = fields.Integer(attribute="parent_id")
    deptName = fields.Str(attribute="dept_name")
    leader = fields.Str()
    phone = fields.Str()
    email = fields.Str()
    address = fields.Str()
    status = fields.Str()
    sort = fields.Str()
```

>这一部分有问题的话请看marshmallow文档

model写的是查询后的对象

```python
dept = Dept.query.order_by(Dept.sort).all()
```

进行序列化

```python
res = model_to_dicts(Schema=DeptSchema, model=dept)
```

## 查询多字段构造器

```python
from applications.common.helper import ModelFilter
mf = ModelFilter()

field_name: 模型字段名称，models里的字段名称,sqlalchemy的field字段
    class User(db.Model, UserMixin):
    	username = db.Column(db.String(20), comment='用户名')
    就是username
value: 值，前端传过来的
    request.args.get('UserName', type=str)

# 准确查询字段
mf.exact(field_name, value)

# 不等于查询字段
mf.neq(field_name, value):

# 大于查询字段
mf.greater(field_name, value):

# 小于查询字段
mf.less(field_name, value):
# 模糊查询字段(%+xxx+%)
mf.vague(field_name, value: str):

# 左模糊 (% + xxx)
 mf.left_vague(field_name, value: str):
      
# 右模糊查询字段(xxx+ %)
mf.right_vague(field_name, value: str):
        
# 包含查询字段
mf.contains(field_name, value: str):

#范围查询字段
mf.between(field_name, value1, value2)


# 查询
你的Model.query.filter(mf.get_filter(model=User)).all()

    

    
    # 例如

	# 获取请求参数
real_name = xss_escape(request.args.get('realName', type=str))
username = xss_escape(request.args.get('username', type=str))
dept_id = request.args.get('deptId', type=int)
    # 查询参数构造
mf = ModelFilter()
    if real_name:
        mf.contains(field_name="realname", value=real_name)
    if username:
        mf.contains(field_name="username", value=username)
    if dept_id:
        mf.exact(field_name="dept_id", value=dept_id)
    # orm查询
    # 使用分页获取data需要.items
    user = User.query.filter(mf.get_filter(model=User)).layui_paginate()

```

## xss过滤

```python
from applications/common/utils/validate import xss_escape
real_name = xss_escape(request.args.get('realName', type=str))
```



## 邮件发送

```python
#在.flaskenv中配置邮箱

from applications/common/utils/mail import send_main
send_mail(subject='title', recipients=['123@qq.com'], content='body')
```



## 返回格式

```
from applications/common/utils/http import success_api,fail_api,table_api

# 这是源代码
def success_api(msg: str = "成功"):
    """ 成功响应 默认值”成功“ """
    return jsonify(success=True, msg=msg)


def fail_api(msg: str = "失败"):
    """ 失败响应 默认值“失败” """
    return jsonify(success=False, msg=msg)


def table_api(msg: str = "", count=0, data=None, limit=10):
    """ 动态表格渲染响应 """
        res = {
            'msg': msg,
            'code': 0,
            'data': data,
            'count': count,
            'limit': limit

        }
        return jsonify(res)
```
### 环境要求 :id=install
- Python >= 3.6
- Mysql >= 5.7.0

###  安装配置
```shell
git clone https://gitee.com/pear-admin/pear-admin-flask.git

# 进 入 项 目 主 目 录

# 创 建 虚 拟 环 境 在 当 前 目 录 的 venv 文 件 夹
python -m venv venv

# 激 活 虚 拟环 境
venv\Scripts\activate

# 安 装
pip install -r requirement.txt

# 配 置 数 据 库
applications\config\database.py

# 初始化数据库
python dev/initDb.py

```



### 设置

```.flaskenv
.flaskenv文件
# flask配置
FLASK_APP=app.py
FLASK_ENV=development
FLASK_DEBUG=1
FLASK_RUN_HOST = 127.0.0.1	#如果远程开发或者内网访问,改成 0.0.0.0
FLASK_RUN_PORT = 5000

# pear admin flask配置
SYSTEM_NAME = Pear Admin	#系统的名称，前端展示

# MySql配置信息
MYSQL_HOST=127.0.0.1
# MYSQL_HOST=dbserver		#docker-compose的link地址
MYSQL_PORT=3306
MYSQL_DATABASE=PearAdminFlask
MYSQL_USERNAME=root
MYSQL_PASSWORD=root

# Redis 配置
REDIS_HOST=127.0.0.1
REDIS_PORT=6379

# 密钥配置(记得改)
SECRET_KEY='pear-admin-flask'	#很重要，部署一定要改

# 邮箱配置
MAIL_SERVER='smtp.qq.com'
MAIL_USERNAME='123@qq.com'
MAIL_PASSWORD='XXXXX' # 生成的授权码
```



- 如果局域网访问，将FLASK_RUN_HOST设置为 0.0.0.0

  
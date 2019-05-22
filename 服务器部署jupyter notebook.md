## 先安装jupyter notebook
```
pip install ipython
pip install jupyter
```

## 创建一个目录（jupyter notebook工作目录）
```
mkdir jupyter_notebook
```

## 生成配置文件
```
jupyter-notebook --generate-config
```

## 生成密码
```
from notebook.auth import passwd
passwd()
会生成一个sha1加密的密码  这个后面要用  保存一下
```

## 修改配置文件
```
vim /root/.jupyter/jupyter_notebook_config.py
在jupyter_notebook_config.py中最下面添加一下配置
c.NotebookApp.ip='*' # *代表所有机器都可访问，或者输入服务ip
c.NotebookApp.password = u'sha1:......' # 把引号中的内容替换为刚刚生成的sha1开头的密码
c.NotebookApp.notebook_dir = u'/root/jupyter_notebook' # 第一步创建的工作目录
c.NotebookApp.open_browser = False
c.NotebookApp.port = 8888
c.NotebookApp.allow_root = True
:wq 保存退出
```

## 修改密码并启动服务
```
由于上面生成的密码太长，所以修改一个简单的密码
jupyter notebook password
输入2次新密码
为了使密码生效，防止jupyter notebook不允许以root方式启动，我们需要在首次访问需要加入参数 
nohup jupyter-notebook --allow-root --config=/root/.jupyter/jupyter_notebook_config.py &
第二次启动就不用--config这个参数了
nohup jupyter-notebook --allow-root &启动即可
```
## 打开浏览器输入ip:8888就可以看到jupyter notebook的页面了
输入密码就可以使用jupyter notebook了



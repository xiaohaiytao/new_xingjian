Swiper
======

项目初始化

```shell
# 一、在github上创建项目：
#   1. 选择.gitignore: python
#   2. license: MIT / Apache 2.0 / GPL3
#   3. 勾选创建 readme.md / 是一个非常好的文档

# 二
git clone https://github.com/yuzebin/new0917.git # 克隆代码下来
cd new0917

# 三
python -m venv .venv                # 创建 Python 虚拟环境
source .venv/bin/activate           # 激活虚拟环境
# .venv/Scripts/activate.bat        # Windows 下的激活命令

# 四、安装软件包
pip install django==1.11.18 gunicorn gevent redis==2.10.6 celery ipython requests
pip freeze > requirment.txt         # 冻结环境，未来还原环境时使用
# pip install -r requirment.txt     # 还原环境方法

# 五
django-admin startproject swiper ./ # 新建一个 Django 项目
# 将代码加入主干
git add .
git commit -m 'first commit'
git push                            # 推送到远端

# 六、创建一个新的工作分支
git branch user                     
git checkout user                   # 切换到新分支
django-admin startapp user          # 启动一个新的 Django 应用，此时django会创建一个user子目录
vi ./swiper/settings.py             # 把 user 加入 INSTALLED_APPS
# 把新的代码加入到新的工作分支中
git add .
git commit -m "user first commit"
git push --set-upstream origin user # 把本地新建分支推送到远端

# git使用的方法：
# 每天早上，至少要 pull 一次
# 每天中间，可以频密的 add 和 commit
# 一小阶段工作，就做一次 push
# 如果与别人协作一个模块，要相对比较频密的 push
# 有了 push 及时通知别人 pull

# 禁忌：
# 千万不要留着冲突不解决
```

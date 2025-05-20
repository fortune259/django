首先查看docker-compose版本
在这里我所使用的版本为v2.27.1
docker-compose --version


如果版本较低，将docker-compose更新到最新版
rm /usr/local/bin/docker-compose
curl  -L  "https://github.com/docker/compose/releases/download/v2.27.1/docker-compose-$(uname
-s)-$(uname -m)" -o /usr/local/bin/docker-compose
chmod  +x  /usr/local/bin/docker-compose	给新下载的dockers compose文件加上一个可执行的权限
docker-compose  --version	这个命令用来确认新版本是否成功安装

首先创建一个目录django


将文件通过MobaXterm移动到django目录中然后进入项目目录


然后将文件解压


然后进入项目目录




在项目目录创建Dockerfile文件


vim Dockerfile	在 Linux 系统中使用vim文本编辑器创建或编辑Dockerfile文件的命令 FROM python:3.11-slim	指定基础镜像，这里选择了官方的python:3.11-slim镜像

WORKDIR /app

设置工作目录


# 安装系统依赖
RUN apt-get update && apt-get install -y --no-install-recommends \ 更新 Debian 系统的软件包索引，安装指定的软件包，不安装推荐的软件包
gcc \	列出的软件包

python3-dev \
default-libmysqlclient-dev \ pkg-config \
libssl-dev \ libmariadb-dev \ netcat-openbsd \
&& rm -rf /var/lib/apt/lists/*  # 清理缓存必须在同一RUN中
# 安装Python依赖
COPY requirements.txt . 将宿主机当前目录下的requirements.txt文件复制到容器的工作目录 RUN pip intall --upgrade pip && \	将pip升级到最新版本，然后根据requirements.txt文件中内容安装项目所需的Python包
pip install -r requirements.txt


# 复制项目代码
COPY . .
EXPOSE 8000	声明容器运行时会监听 8000 端口
CMD ["sh", "-c", "sleep 60s && python manage.py migrate && python manage.py runserver 0. 0.0.0:8000"]	使用sh（Bourne Shell）来执行后面的命令字符串。让容器启动后等待 60 秒。在数据库中创建相应的表结构。启动 Django 开发服务器通过容器的 IP 地址和 8000 端口来访问 Django 应用
#

创建yml文件（需要注意compose的版本）
docker-compose.yml




执行命令（预计11分钟）

docker compose up -d	根据docker-compose.yml文件的配置，启动 “my_mysql” 和 “mydjango” 两个容器



进入mysql容器



mysql 权限root远程登录

用户 root






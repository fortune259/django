
se --version
如果版本较低，将docker-compose更新到最新版
rm /usr/local/bin/docker-compose  删除当前安装在?/usr/local/bin?目录下的 Docker Compose
curl  -L  "https://github.com/docker/compose/releases/download/v2.27.1/docker-compose-$(uname
-s)-$(uname -m)" -o /usr/local/bin/docker-compose       从 GitHub 的 Docker Compose 发布页面下载指定
版本（v2.27.1）的 Docker Compose 二进制文件,$(uname -s)?和?$(uname -m)?分别用于获取当前系统的操作系>统名称和硬件架构用来保证下载dockers compose是适配>当前系统的文件
chmod  +x  /usr/local/bin/docker-compose        给
新下载的dockers compose文件加上一个可执行的权限
docker-compose  --version       这个命令用来确认新
版本是否成功安装
mkdir django
将文件通过MobaXterm移动到django目录中然后进入项目>目录
cd django
然后将文件解压
unzip web_site.zip
然后进入项目目录
cd  web_site
mkdir mysql     创建一个名为mysql的文件夹
cd mysql        切换至改文件夹路径下
cp /root/django/d_site_backup.sql . ql文件复制到mysql文件夹下

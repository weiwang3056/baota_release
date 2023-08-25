# 宝塔Linux历史版本存档
由于宝塔官方的历史版本下载链接失效，故收集了一波历史版本以供使用

# 版本说明
* 7.4.2版本有pma漏洞
* 7.4.5之后的版本（不包括7.4.5）需要强制绑定手机号
* 7.2.0之前的版本不推荐使用，因为代码改动过大，降级后无法正常使用

# 使用方法
### 安装宝塔
先使用宝塔官方的安装脚本安装最新版宝塔
* Centos安装命令：

yum install -y wget && wget -O install.sh http://download.bt.cn/install/install_6.0.sh && sh install.sh
curl -sSO http://download.bt.cn/install/install_6.0.sh && bash install_panel.sh 
* Ubuntu/Deepin安装命令：

wget -O install.sh http://download.bt.cn/install/install-ubuntu_6.0.sh && sudo bash install.sh 
* Debian安装命令：

wget -O install.sh http://download.bt.cn/install/install-ubuntu_6.0.sh && bash install.sh 
* Fedora安装命令:

wget -O install.sh http://download.bt.cn/install/install_6.0.sh && bash install.sh

### 降级
然后解压对应的降级包，运行panel文件夹中的update.sh脚本即可

# 注意事项

* 宝塔降级后会出现密码不正确的情况，修改密码即可（bt 5）
* 降级成功后建议将宝塔修改为离线模式，进入宝塔面板，选择面板设置 -> 离线模式即可

# 宝塔降级常见问题

* Q：降级后显示宝塔无法启动，但无任何报错

  S：需要将markupsafe==2.0.1添加到panel目录下的requirements.txt文件中并执行/www/server/panel/pyenv/bin/pip3 install -r requirements.txt安装python库后重启面板即可

* Q：降级后登录宝塔面板时提示密码错误

  S：需要在终端修改宝塔密码

* Q：降级后登录宝塔面板时无法显示验证码图片或无法下载文件

  S：需要将/www/server/panel/BTPanel/\_\_init\_\_.py文件中的send_file函数中的cache_timeout参数名改为max_age
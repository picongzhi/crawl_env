# crawl_env  
1. 安装好后更新系统
sudo apt update
sudo apt upgrade

2. 安装虚拟机增强功能  
https://websiteforstudents.com/installing-virtualbox-guest-additions-on-ubuntu-18-04-beta/  
sudo apt install linux-headers-$(uname -r) build-essential dkms  
sudo reboot  
Devices => Insert Guest Additions CD image => Run  
sudo reboot  
添加复制粘贴功能  

3. 配置终端  
sudo apt install vim zsh wget curl git  
vim /etc/shells 添加zsh的绝对路径  
切换shell chsh -s /usr/bin/zsh  
安装oh-my-zsh sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"  
安装powerline字体 sudo apt-get install fonts-powerline  
切换主题 vim ~/.zshrc theme = "agnoster"  
修改提示符 vim ~/.oh-my-zsh/themes/agonster 最下面注释context (# context)  

4. 终端代理  
安装shadowsocks-qt5  
sudo add-apt-repository ppa:hzwhuang/ss-qt5  
vim /etc/apt/sources.list.d/hzwhuang-ubuntu-ss-qt5-cosmic.list 将cosmic改成artful（两个地方都要改）  
sudo apt-get update  
sudo apt-get install shadowsocks-qt5  
添加代理服务器配置  
打开shadowsocks-qt5，添加一个连接  
终端代理  
安装polipo sudo apt-get install polipo  
修改配置文件 sudo vim /etc/polipo/config  
添加  
socksParentProxy = "localhost:1080"  
socksProxyType = socks5  
logLevel=4  
终端使用代理  
vim ~/.zshrc
alias proxy="export http_proxy=http://localhost:8123;export https_proxy=http://localhost:8123"  
alias unproxy="unset http_proxy;unset https_proxy"  
添加别名  
使用代理执行proxy  
取消执行unproxy  
验证curl cip.cc  

4. 安装pyenv  
安装依赖  
sudo apt-get install -y make build-essential libssl1.0-dev zlib1g-dev libbz2-dev \
libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev \
xz-utils tk-dev libffi-dev liblzma-dev libedit-dev  
git clone https://github.com/pyenv/pyenv.git ~/.pyenv  
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.zshrc

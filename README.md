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

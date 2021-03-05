# ubuntu

## 常见命令

```sh
apt search <package>
apt show <package>

# 查看
apt list
apt list | grep <package>
apt list --installed
# 可升级的
apt list --upgradeable

# 安装
apt install

# 删除安装时缓存的安装包 /var/cache/apt/archives/和/var/cache/apt/archives/partial/
apt clean
# 删除过期版本
apt autoclean

# 删除(卸载)已经安装的软件包(保留相关文件)
apt remove
# 同时删除配置文件
apt pugre
# 删除未使用的
apt autoremove

# 更新索引
apt update

# 升级所有
apt upgrade
# 删了再升
apt full-upgrade
# 升级特定
apt upgrade <package>
```

## 配置镜像

<https://mirrors.tuna.tsinghua.edu.cn/help/ubuntu/>

## 背景设置

```sh
# clear current image setting
gsettings set org.gnome.desktop.background picture-uri ""

# set primary color
gsettings set org.gnome.desktop.background primary-color '#000000'

gsettings set org.gnome.desktop.background secondary-color '#000000'

# 'solid' for one color, 'horizontal' or 'vertical' for gradient
gsettings set org.gnome.desktop.background color-shading-type 'solid'
```

## 快捷键

```text
Super + M: 通知栏
Alt+F2: 运行控制台
Ctrl+Alt+箭头: 切换工作区
Ctrl+Alt+Del: 注销
```

## 软件安装

### qv2ray

<https://github.com/Qv2ray/debian>

```sh
sudo apt install gnupg ca-certificates curl

curl -sSL https://qv2ray.net/debian/pubkey.gpg | sudo apt-key add -

echo "deb [arch=amd64] https://qv2ray.net/debian/ stable main" | sudo tee /etc/apt/sources.list.d/qv2ray.list

sudo apt update

sudo apt install qv2ray

# mirror
sudo apt install gnupg ca-certificates curl

curl -sSL https://raw.fastgit.org/Qv2ray/debian/master/pubkey.gpg | sudo apt-key add -

echo "deb [arch=amd64] https://raw.fastgit.org/Qv2ray/debian/master/ stable main" | sudo tee /etc/apt/sources.list.d/qv2ray-fastgit.list

sudo apt update

sudo apt install qv2ray
```

### proxychains

<https://github.com/rofl0r/proxychains-ng>

```sh
sudo apt install proxychains4

# sudo vim /etc/proxychains.conf
# socks5 127.0.0.1 1080

# sudo vim ~/.zshrc
# alias pc=proxychains
```

### rime 输入法

<https://github.com/rime/home/wiki/RimeWithIBus>
<https://github.com/rime/home/wiki/CustomizationGuide#rime-%E5%AE%9A%E8%A3%BD%E6%8C%87%E5%8D%97>

<https://github.com/Iorest/rime-setting>
<https://einverne.github.io/post/2014/11/rime.html>

#### 安装

```sh
sudo apt install ibus-rime
```

#### 配置

```sh
cd ~/.config/ibus/rime
```

```yaml
# default.custom.yaml
patch:
  menu:
    page_size: 9
  ascii_composer:
    switch_key:
      Shift_L: commit_code
```

```yaml
# ibus_rime.yaml
style:
  horizontal: true # 横向布局
```

```yaml
# luna_pinyin.custom.yaml
patch:
  switches:
    - name: ascii_mode
      reset: 1
      states: [中文, 西文]
    - name: full_shape
      states: [半角, 全角]
    - name: simplification
      reset: 1
      states: [漢字, 汉字]
  translator:
    dictionary: luna_pinyin.sougou # 词库
```

### chrome

```sh
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb

sudo apt install ./google-chrome-stable_current_amd64.deb
```

### redshift

<https://github.com/jonls/redshift>
<https://github.com/jonls/redshift/blob/master/redshift.conf.sample>

```sh
sudo apt install redshift
vim ~/.config/redshift/redshift.conf
```

### 开发工具

```sh
sudo apt install openjdk-11-jdk openjdk-11-source
sudo apt install maven
sudo apt install git
sudo apt install tmux
sudo apt install dos2unix
```

### 字体

<https://github.com/tonsky/FiraCode/wiki/Linux-instructions#installing-with-a-package-manager>

```sh
sudo add-apt-repository universe
sudo apt install fonts-firacode
```

### telegram

```sh
sudo add-apt-repository ppa:atareao/telegram

sudo apt install telegram-desktop
```

### depin

```sh
# wechat 修复
sudo apt install libjpeg62:i386
```

### imwheel

```sh
sudo apt install imwheel

vim ~/.imwheelrc
```

```text
# 用来指定在哪些应用中生效
".*"
# 滚动行数
None,      Up,   Button4, 5
None,      Down, Button5, 5
# 鼠标支持
Control_L, Up,   Control_L|Button4
Control_L, Down, Control_L|Button5
Shift_L,   Up,   Shift_L|Button4
Shift_L,   Down, Shift_L|Button5
```

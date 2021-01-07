# RunAsRoot
以root运行软件, 文件管理器等 (Ubuntu/deepin)

Run app as root in linux (Ubuntu/deepin)

ubuntu已经够头疼了，deepin更想吐，感觉是个不能装花的花瓶，桌面用用就卡死了，想提点建议，论坛注册了，发帖子网易验证码输了几十次全错，网易人才

# 方法/Instruction：
新建文本，另存为 gksudo.sh到 桌面，即/home/(你的用户名)/Desktop/，内容如下:
copy below and save as gksudo.sh at Desktop:

```shell
#!/bin/bash

wget http://mirrors.kernel.org/ubuntu/pool/main/libg/libgtop2/libgtop-2.0-10_2.32.0-1_amd64.deb
sudo apt install ./libgtop-2.0-10_2.32.0-1_amd64.deb

wget https://mirrors.edge.kernel.org/ubuntu/pool/universe/libg/libgksu/libgksu2-0_2.0.13~pre1-6ubuntu8_amd64.deb
sudo apt install ./libgksu2-0_2.0.13~pre1-6ubuntu8_amd64.deb

wget http://mirrors.kernel.org/ubuntu/pool/universe/g/gksu/gksu_2.0.2-9ubuntu1_amd64.deb
sudo apt install ./gksu_2.0.2-9ubuntu1_amd64.deb

sudo apt-get install shc
```

打开终端工具，输入 / open terminal, type in:

```shell
sh /home/(你的用户名/yourAccountNameHere)/Desktop/gksudo.sh
```
提示按y了就按Y ,等待完成/ PRESS Y WHEN ASK Y/N and wait

然后输入：/ then type in
```shell
shc -f gksudo.sh
```

# 选择要以root执行的程序 / choose app
例如 文件管理器(dde-file-manager)，新建文本，输入 
eg dde-file-manager(ubuntu is nautilus)，copy codes and save as runasroot.sh

```shell
#!/bin/bash
gksudo dde-file-manager
```
到终端输入如下/ open terminal
```shell
shc -f runasroot.sh
```
会生成 rootfm.sh.x，
Will generate **rootfm.sh.x

双击，弹出框输入密码，就是root模式的文件管理器了，其他的可以删了
Open it and type in you password, voila, root!

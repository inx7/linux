# linux homework 01
## Compiling kernel:
```
sudo wget https://cdn.kernel.org/pub/linux/kernel/v3.x/linux-3.18.124.tar.xz
tar xf linux-3.18.124.tar.xz
sudo tar xf linux-3.18.124.tar.xz
ll
sudo rm -r linux-3.18.124.tar.xz
cd linux-3.18.124
less .config
sudo cp /boot/config-3.10.0-514.el7.x86_64 .config
sudo make olddefconfig
sudo make -j 4 
sudo make modules_install
sudo make install
```
## Updating GRUB configuration
```
sudo awk -F\' '$1=="menuentry " {print i++ " : " $2}' /etc/grub2.cfg
0 : CentOS Linux (3.18.124) 7 (Core)
1 : CentOS Linux (3.10.0-514.el7.x86_64) 7 (Core)
2 : CentOS Linux (0-rescue-bd50eb09709a4224bcb4a66da8546219) 7 (Core)
sudo grub2-set-default 0
sudo grub2-mkconfig -o /boot/grub2/grub.cfg
```

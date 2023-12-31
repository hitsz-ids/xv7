# 安装过程
## 1、准备基础环境
准备1台安装有ubuntu 20.04的机器，可以安装在物理机上，也可以安装在虚拟机中。

[X86版ubuntu在这里下载](https://ubuntu.com/download/desktop)

[ARM版ubuntu在这里下载](https://ubuntu.com/download/server/arm)
ARM版ubuntu需要安装桌面
```shell
sudo apt-get install ubuntu-desktop
```

以下步骤在ubuntu 20.04中操作

## 2、下载操作系统xv7代码
```shell
git clone https://github.com/hitsz-ids/xv7.git
```

## 3、安装rust
```shell
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs > rust.sh
sh rust.sh
```
提示
```
Current installation options:


   default host triple: aarch64-unknown-linux-gnu
     default toolchain: stable (default)
               profile: default
  modify PATH variable: yes

1) Proceed with installation (default)
2) Customize installation
3) Cancel installation
>
```
选择1即可

导入环境变量
```shell
source "$HOME/.cargo/env"
```

## 4、安装gcc
安装gcc
```shell
sudo apt-get install gcc
```

## 5、安装qemu
安装qemu-system-x86，操作系统编译完成后将使用qemu启动
```shell
sudo apt-get install qemu-system-x86
```

## 6、安装cargo-make
xv7采用cargo-make作为编译命令
```shell
cargo install cargo-make
```

## 7、安装cargo-xbuild
```shell
cargo install cargo-xbuild
```

## 8、安装nightly版本的rustc
安装并切换nightly版本
```shell
rustup install nightly-2021-04-25
rustup default nightly-2021-04-25
rustup override set nightly-2021-04-25
rustup component add rust-src
```

## 9、编译
```shell
cargo make qemu
```
此时应能正常启动xv7系统

有问题请联系：<jie.lin.fj@gmail.com>

# xv7操作系统原始链接
https://github.com/imtsuki/xv7

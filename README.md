# Padavan
基于hanwckf,chongshengB以及padavanonly的源码整合而来，支持kvr
编译方法同其他Padavan源码，主要特点如下：

1.采用padavanonly源码的5.0.4.0无线驱动，支持kvr
2.添加了chongshengB源码的所有插件
3.其他部分等同于hanwckf的源码，有少量优化来自immortalwrt的padavan源码
4.添加了MSG1500的7615版本config
5.新增了对XTLS和XRAY的支持

# 编译
* 集成/取消新增插件请修改此文件: trunk/build_firmware_modify

```
# Debian/Ubuntu
sudo apt update
sudo apt install unzip libtool-bin curl cmake gperf gawk flex bison nano xxd fakeroot \
cpio git python-docutils gettext automake autopoint texinfo build-essential help2man \
pkg-config zlib1g-dev libgmp3-dev libmpc-dev libmpfr-dev libncurses5-dev libltdl-dev wget
```
* 克隆代码仓库

```
git clone --depth=1 https://github.com/sudoec/Padavan.git Padavan
```
* 准备工具链

```
cd Padavan/toolchain-mipsel
sh dl_toolchain.sh
./clean_toolchain
./build_toolchain
```
* 清理代码树开始编译

```
cd Padavan/trunk
./clear_tree
fakeroot ./build_firmware_modify K2P  #K2P就是对应型号路由器的配置文件名
# 脚本第一个参数为路由型号，在trunk/configs/templates/中
# 编译好的固件在trunk/images里
```

# 配置
固件默认WIFI名称PDCN及PDCN_5G
WIFI密码: 1234567890
管理地址: 192.168.123.1
管理账号密码: admin

源码地址供参考:
https://github.com/hanwckf/rt-n56u
https://github.com/chongshengB/rt-n56u
https://github.com/padavanonly/rt-n56u
https://github.com/immortalwrt/padavan
https://github.com/xumng123/rt-n56u
https://github.com/vb1980/Padavan-KVR

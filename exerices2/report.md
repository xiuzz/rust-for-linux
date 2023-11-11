在linux/sample/rust/ 下编写rust_helloworld.rs
![Alt text](image-4.png)

在同级的makefile里面加上
obj-$(CONFIG_SAMPLE_RUST_HELLOWORLD)    += rust_helloworld.o
![Alt text](image-1.png)

同时在kconfig里面添加HelloWorld的配置信息
![Alt text](image-2.png)

在练习1基础上，添加 rust_helloworld 模块配置

make ARCH=arm64 LLVM=1 O=build menuconfig

勾选module
![Alt text](image-3.png)

进入build 进行make
![Alt text](image-5.png)

可以看到编译后生成了helloworld.ko
![Alt text](image-6.png)

配置一下练习1的脚本，将ko文件放入busybox里面
![Alt text](image-7.png)

手动insmod一下 /lib/rust_helloworld.ko
![Alt text](image-8.png)
![Alt text](image-9.png)
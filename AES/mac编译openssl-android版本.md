---
typora-copy-images-to: ./屏幕快照 2021-12-16 下午10.31.00.png
---

# 1.3 mac编译openssl-android版本



## 1.从官网下载OpenSSL

下载地址是https://www.openssl.org/source/

点击如下的openssl-1.1.1m.tar.gz的链接
![](/AES/image.png/屏幕快照 2021-12-16 下午10.54.05.png)


## 2.在mac上使用NDK编译OpenSSL

1.从android 官网上下载mac版本的NDK;

2.设置编译器

```
export ANDROID_NDK_HOME=/Users/leifeng/fenglei/tools/ndk/r20b
export PATH=$ANDROID_NDK_HOME/toolchains/llvm/prebuilt/darwin-x86_64/bin:$ANDROID_NDK_HOME/toolchains/arm-linux-androideabi-4.9/prebuilt/darwin-x86_64/bin:$PATH
```

注意：/Users/leifeng/fenglei/tools/ndk/r20b 是我自己的路径，这里需要设置你自己的NDK路径

3.执行下面的编译命令

```
./Configure android-arm64 -D__ANDROID_API__=28 -fPIC no-shared
```

如果配置成功，会有类似下面图片显示，而且上面的-D__ANDROID_API__=28是可以修改的，需要自行是查询NDK

对应的API;no-shared的意思是不编译动态库

![](/AES/image.png/屏幕快照 2021-12-16 下午10.46.11.png)

4.执行make命令就好了

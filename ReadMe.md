## 飞腾新四核KYEE接口测试步骤

#### 1. 运行环境

　　适用于飞腾新四核机器，需适配从专用的内核镜像引导启动，且需烧录对应的optee镜像到固件。



#### 2. 测试步骤

​	A）启动飞腾机器，并以root用户登陆系统；

​	B）拷贝测试用例的可执行文件和TA文件到相应目录；

```shell
cp  binary/* /data/bin
cp 	ta/* /data/optee_armtz
```
​	C)  加载TEE应用支持；					

```SHELL
/data/env_v1.sh	
```

​	D)  运行测试程序。

```shel
/data/bin/KYEE_auth_management
/data/bin/KYEE_sm2_encrypt
/data/bin/KYEE_sm3_summary
/data/bin/KYEE_sm4_encrypt
```




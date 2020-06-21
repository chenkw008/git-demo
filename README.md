## 飞腾新四核KYEE接口测试说明

#### 1. 用例说明

	针对KYEE接口测试，共编写了6个测试用例（每个测试用例中包含对若干个同类型接口函数的测试），分别为KYEE_auth_management、KYEE_secure_storage、KYEE_sm2_encrypt、KYEE_sm3_summary、KYEE_sm4_encrypt、KYEE_data_clear。其测试用例的optee源码文件存放在KTYY_TEST_src目录，已编译好的可直接用于测试的可执行文件存放在KYEE_TEST_bin目录。

	测试用例具体测试哪些接口、测试用例的调用顺序以及接口间的调用关系，请查看**<u>《KYEE测试用例说明文档_V1.0》</u>**。

​	接口函数的详细介绍，请查看**<u>《KYEE接口说明文档_v1.6》</u>**。



#### 2.  文件说明

	KYEE_TEST_bin						//存放二进制和TA文件（可直接用于测试）

​			| binary				//编译好的可执行文件

​			| ta					//可执行文件对应的TA文件

​			| ReadMe.md				//执行步骤详细说明



	KTYY_TEST_src						//存放测试用例的optee源码 

​			| KYEE_auth_management			//认证管理用例

​			| KYEE_secure_storage		   	//安全存储用例

​			| KYEE_sm2_encrypt			//SM2加密服务用例

​			| KYEE_sm3_summary		   	//SM3摘要算法用例

​			| KYEE_sm4_encrypt			//SM4加密用例

​			| KYEE_data_clear			//数据销毁用例



	KYEE_TEST_img						//存放镜像文件	

​			| Image-suchangzheng		  	//内核镜像，Linux需替换成从该镜像启动

​			| fip-all				//optee镜像，需烧录至飞腾optee固件



#### 3. 运行环境

	适用于飞腾新四核机器，需适配从专用的内核镜像引导启动，且需烧录对应的optee镜像到固件。



#### 4. 测试步骤

​	A）启动飞腾机器，并以root用户登陆系统；

​	

​	B）拷贝测试用例的可执行文件和TA文件到相应目录；

```shell
cp  KYEE_TEST_bin/binary/* /data/bin
cp 	KYEE_TEST_bin/ta/* /data/optee_armtz
```

​	

​	C)  加载TEE应用支持；

```shell
/data/env_v1.sh	
```



​	D)  运行测试程序。

```shel
/data/bin/KYEE_auth_management
/data/bin/KYEE_secure_storage
/data/bin/KYEE_sm2_encrypt
/data/bin/KYEE_sm3_summary
/data/bin/KYEE_sm4_encrypt
/data/bin/KYEE_data_clear
```




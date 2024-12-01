写这篇学习笔记时，参考视频为：【MySQL数据库基础教程_数据库_小白零基础带你掌握SQL数据库_包括（下载、安装和卸载）_小白必看】 [https://www.bilibili.com/video/BV1y2mKYQEeg/?share_source=copy_web&vd_source=26a21a8ac3f19fd0d663fb58dee41081](https://www.bilibili.com/video/BV1y2mKYQEeg/?share_source=copy_web&vd_source=26a21a8ac3f19fd0d663fb58dee41081)

参考资料为：《MySQL5.7从入门到精通（视频教学版)（第二版)》![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732439739987-2505f73b-5f12-4efd-9a11-ec436d011f6f.jpeg)

# <font style="color:rgb(51, 51, 51);">一、SQL 概述</font>
## <font style="color:rgb(51, 51, 51);">1.基本概念</font>
**<font style="color:rgb(51, 51, 51);">SQL</font>**<font style="color:rgb(51, 51, 51);"> (Structured Query Language:结构化查询语言) 是用于管理关系数据库管理系统（RDBMS）。</font>

<font style="color:rgb(51, 51, 51);">SQL 通过一系列的语句和命令来执行数据定义、数据查询、数据操作和数据控制等功能,包括数据插入、查询、更新和删除，数据库模式创建和修改，以及数据访问控制。</font>

## <font style="color:rgb(51, 51, 51);">2.SQL 分类</font>
<font style="color:rgb(51, 51, 51);">DDL（Data Definition Language）：数据定义语言，用来定义数据库对象：库、表、列等；</font>

<font style="color:rgb(51, 51, 51);">DML（Data Manipulation Language）：数据操作语言，用来定义数据库记录（数据）；</font>

<font style="color:rgb(51, 51, 51);">DCL（Data Control Language）：数据控制语言，用来定义访问权限和安全级别；</font>

<font style="color:rgb(51, 51, 51);">DQL（Data Query Language）：数据查询语言，用来查询记录（数据）</font>

## <font style="color:rgb(79, 79, 79);">3.语法要求</font>
<font style="color:rgba(0, 0, 0, 0.75);">SQL 语句可以单行或多行书写，以分号结尾；</font>

<font style="color:rgba(0, 0, 0, 0.75);">可以用空格和缩进来来增强语句的可读性；</font>

<font style="color:rgba(0, 0, 0, 0.75);">关键字不区别大小写；</font>

## <font style="color:rgba(0, 0, 0, 0.75);">4.数据类型</font>
<font style="color:rgba(0, 0, 0, 0.75);">MySQL 与 Java、C 一样，也有数据类型MySQL 中数据类型主要应用在列上。</font>

<font style="color:rgba(0, 0, 0, 0.75);">常用类型：</font>

<font style="color:rgba(0, 0, 0, 0.75);">int：整型</font>

<font style="color:rgba(0, 0, 0, 0.75);">double：浮点型，例如 double(5,2)表示最多 5 位，其中必须有 2 位小数，即最大值为 999.99；</font>

<font style="color:rgba(0, 0, 0, 0.75);">decimal：泛型型，在表单线方面使用该类型，因为不会出现精度缺失问题；</font>

<font style="color:rgba(0, 0, 0, 0.75);">char：固定长度字符串类型；(当输入的字符不够长度时会补空格)</font>

<font style="color:rgba(0, 0, 0, 0.75);">varchar：固定长度字符串类型；</font>

<font style="color:rgba(0, 0, 0, 0.75);">text：字符串类型；</font>

<font style="color:rgba(0, 0, 0, 0.75);">blob：字节类型；</font>

<font style="color:rgba(0, 0, 0, 0.75);">date：日期类型，格式为：yyyy-MM-dd；</font>

<font style="color:rgba(0, 0, 0, 0.75);">time：时间类型，格式为：hh:mm:ss</font>

<font style="color:rgba(0, 0, 0, 0.75);">timestamp：时间戳类型；</font>



参考资料：[https://blog.csdn.net/PILIpilipala/article/details/113798383](https://blog.csdn.net/PILIpilipala/article/details/113798383)

# 二、MySQL概述
## 1.MySQL是什么
MySQL是一个小型关系数据库管理系统，它虽然规模小、功能有限，但是它体积小、速度快、成本低，且提供的功能对于稍微复杂的应用来说已经够用了，这些特性使得它成为世界上最受欢迎的开放源代码数据库。

## 2.MySQL的安装与配置
### MySQL的安装
在[https://dev.mysql.com/downloads/windows/installer/](https://dev.mysql.com/downloads/windows/installer/)下载5.7.44版本，这时候会弹出登录界面，按照页面提示注册好就可以下载了。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732009691202-90de94dc-fd68-4b86-ad14-39c716853d9d.png)

<font style="color:rgb(51, 51, 51);">下载好后进行安装，这几步忘截图了，就放参考书上的图片了，提醒一下中间设置的密码一定不能忘</font>

![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732010902781-29583f3f-65fd-4040-82e1-ae6b081310b2.jpeg)![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732010932242-a0156a80-42ae-4c70-95eb-9f39f89bae4b.jpeg)![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732010952294-8bd0c13a-7745-4e5f-963a-8034b27dca77.jpeg)![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732010977524-946a9ab4-097e-4399-8312-15ba362bfb6b.jpeg)![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732010989782-acafd647-9f85-4432-9dfa-d7f7cb885114.jpeg)![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732011552665-8bd60b45-d4ba-40fd-aea1-ee57d406f7bb.jpeg)![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732011571498-fb749614-98fe-4ddd-95c8-4e6d4919a3fa.jpeg)

这下算是已经安装好了，接下来还要启动服务器

打开搜索栏搜索services.msc，并打开

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732079017710-9b46f6c6-d5f8-476f-89ad-a72c245d9487.png)

启用MySQL服务

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732079087554-313e3106-4ed3-493a-86c3-4b3e78d2337f.png)

### 登录MySQL服务
在搜索栏输入MySQL 5.7 Command Line Client并打开![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732079554834-658b15a4-96e3-4096-b06e-8f6abbc64214.png)

输入密码就登录了MySQL数据库

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732079627844-288eeea7-0e1a-4253-84fa-da87b2234989.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732079690397-2074376f-5de8-4932-ba79-80e62eb1be80.png)

### 配置path变量
在桌面上右键此电脑点击属性，打开系统窗口，单击高级系统设置链接，打开系统属性对话框单机环境变量

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732079970005-df92ec75-1ac6-4dcb-8f0c-1317072d77bf.png)

之后选择path点击编辑把MySQL Server 5.7\bin的路径复制上去

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732080030847-47f8dc82-13f2-4947-b24d-6ae8139657f7.png)![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732080043800-e3e77b34-3bc1-48eb-b66f-d4c96ab8579e.png)

点击确定这样就完成了path的配置，之后就可以直接输入MySQL指令来登录数据库了

# 三、数据库的基本操作
## 1.创建数据库
在MySQL自带的客户端工具登录后显示![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732206876871-e797b743-d322-410f-b884-2484a5d583ef.png)

接下来查看已有数据库，输入语句来查看：

_**<font style="color:#601BDE;">show databases;</font>**_

注意databases是有复数的，且末尾分号不要忘。

可以看到数据库中有4个数据库，其中mysql是必须的，用于用户访问权限

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732206781434-bb1193eb-9630-44d6-8037-b3d3cdac2600.png)

创建数据库的输入语句格式为：

_**<font style="color:#601BDE;">create database</font>**__**  数据库名 ;**___

比如说现在要创建一个名为fischl0527的数据库，需要输入：“create database fischl0527;”，注意database不加-s，后面需要有分号表示语句结束。![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732208444297-38834837-8a9f-4676-afa2-bffe5cc5d6d5.png)

## 2.查看数据库
如果我们想要查看某一个数据库，使用以下语句：

_**<font style="color:#601BDE;">show create database </font>**__**数据库名;**_ 

如果我们想要查看某一个数据库的定义，可以使用：

_**<font style="color:#601BDE;">show create database </font>**__** 数据库名**__**<font style="color:#601BDE;">\G;</font>**_

<font style="color:#000000;">比如说现在要查看一个名为text的数据库,需要输入：“show create database text;”</font>

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732262439785-bc68f251-30fe-4455-8c8d-db42ece88fdf.png)

比如说现在要查看一个名为egg的数据库的定义，需要输入：“show create database egg\G;”![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732208375912-be9fff65-b938-40f7-9bd8-f2ae85350d9d.png)

## 3.删除数据库
如果我们想要删除一个数据库，输入语句格式如下：

_**<font style="color:#601BDE;">drop database </font>**__** 数据库名**_**<font style="color:#601BDE;"> ;</font>**

比如说现在要删除一个名为fischl0527的数据库，需要输入：“drop database fischl0527;”

此时我们再查看所有数据库就已经没有了“fischl0527"这个数据库了。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732207720256-3e784a36-a140-4807-9edd-6835ecbb7094.png)

如果再次查看fischl数据库时，执行结果会报错

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732208118432-6e150c27-c385-449a-af1d-e85d7e12488e.png)

并且要注意删除数据库时MySQL不会给出任何确认信息，删除数据库后所有数据表、数据不可恢复，因此删除数据库时一定要小心谨慎。

# 四、数据表的基本操作
## 1.数据类型
### <font style="color:rgb(51, 51, 51);">(1) 数值类型：</font>
数值类型的长度m是指显示长度，并不表示存储长度，只有字段指定zerofill时有用

例如：int（3)，如果实际值是2，如果列指定了zerofill，那查询结果是002，左边的0用来填充

在浮点类型中，（m,d)，m为总位数，d为小数位。

| <font style="color:rgb(255, 255, 255);">类型</font> | <font style="color:rgb(255, 255, 255);">大小</font> | <font style="color:rgb(255, 255, 255);">范围（有符号）</font> | <font style="color:rgb(255, 255, 255);">范围（无符号）</font> | <font style="color:rgb(255, 255, 255);">用途</font> |
| --- | --- | --- | --- | --- |
| <font style="color:rgb(51, 51, 51);">tinyint(m)</font> | <font style="color:rgb(51, 51, 51);">1 Bytes</font> | <font style="color:rgb(51, 51, 51);">(-128，127)</font> | <font style="color:rgb(51, 51, 51);">(0，255)</font> | <font style="color:rgb(51, 51, 51);">小整数值</font> |
| <font style="color:rgb(51, 51, 51);">smallint(m)</font> | <font style="color:rgb(51, 51, 51);">2 Bytes</font> | <font style="color:rgb(51, 51, 51);">(-32 768，32 767)</font> | <font style="color:rgb(51, 51, 51);">(0，65 535)</font> | <font style="color:rgb(51, 51, 51);">大整数值</font> |
| <font style="color:rgb(51, 51, 51);">mediumint(m)</font> | <font style="color:rgb(51, 51, 51);">3 Bytes</font> | <font style="color:rgb(51, 51, 51);">(-8 388 608，8 388 607)</font> | <font style="color:rgb(51, 51, 51);">(0，16 777 215)</font> | <font style="color:rgb(51, 51, 51);">大整数值</font> |
| <font style="color:rgb(51, 51, 51);">int(m)或integer(m)</font> | <font style="color:rgb(51, 51, 51);">4 Bytes</font> | <font style="color:rgb(51, 51, 51);">(-2 147 483 648，2 147 483 647)</font> | <font style="color:rgb(51, 51, 51);">(0，4 294 967 295)</font> | <font style="color:rgb(51, 51, 51);">大整数值</font> |
| <font style="color:rgb(51, 51, 51);">bigint(m)</font> | <font style="color:rgb(51, 51, 51);">8 Bytes</font> | <font style="color:rgb(51, 51, 51);">(-9,223,372,036,854,775,808，9 223 372 036 854 775 807)</font> | <font style="color:rgb(51, 51, 51);">(0，18 446 744 073 709 551 615)</font> | <font style="color:rgb(51, 51, 51);">极大整数值</font> |
| <font style="color:rgb(51, 51, 51);">float(m，d)</font> | <font style="color:rgb(51, 51, 51);">4 Bytes</font> | <font style="color:rgb(51, 51, 51);">(-3.402 823 466 E+38，-1.175 494 351 E-38)，0，(1.175 494 351 E-38，3.402 823 466 351 E+38)</font> | <font style="color:rgb(51, 51, 51);">0，(1.175 494 351 E-38，3.402 823 466 E+38)</font> | <font style="color:rgb(51, 51, 51);">单精度   </font><font style="color:rgb(51, 51, 51);">浮点数值</font> |
| <font style="color:rgb(51, 51, 51);">double(m,d)</font> | <font style="color:rgb(51, 51, 51);">8 Bytes</font> | <font style="color:rgb(51, 51, 51);">(-1.797 693 134 862 315 7 E+308，-2.225 073 858 507 201 4 E-308)，0，(2.225 073 858 507 201 4 E-308，1.797 693 134 862 315 7 E+308)</font> | <font style="color:rgb(51, 51, 51);">0，(2.225 073 858 507 201 4 E-308，1.797 693 134 862 315 7 E+308)</font> | <font style="color:rgb(51, 51, 51);">双精度   </font><font style="color:rgb(51, 51, 51);">浮点数值</font> |
| <font style="color:rgb(51, 51, 51);">decimal(m,d)</font> | <font style="color:rgb(51, 51, 51);">对decimal(M,D) ，如果M>D，为M+2否则为D+2</font> | <font style="color:rgb(51, 51, 51);">依赖于M和D的值</font> | <font style="color:rgb(51, 51, 51);">依赖于M和D的值</font> | <font style="color:rgb(51, 51, 51);">小数值</font> |


### <font style="color:rgb(51, 51, 51);">(2) 日期和时间类型：</font>
datatime不支持跨时区，它没有时区处理timestamp是有时间戳的，支持时区处理。

| <font style="color:rgb(255, 255, 255);">类型</font> | <font style="color:rgb(255, 255, 255);">大小   </font><font style="color:rgb(255, 255, 255);">( bytes)</font> | <font style="color:rgb(255, 255, 255);">范围</font> | <font style="color:rgb(255, 255, 255);">格式</font> | <font style="color:rgb(255, 255, 255);">用途</font> |
| --- | --- | --- | --- | --- |
| <font style="color:rgb(51, 51, 51);">date</font> | <font style="color:rgb(51, 51, 51);">3</font> | <font style="color:rgb(51, 51, 51);">1000-01-01/9999-12-31</font> | <font style="color:rgb(51, 51, 51);">YYYY-MM-DD</font> | <font style="color:rgb(51, 51, 51);">日期值</font> |
| <font style="color:rgb(51, 51, 51);">time</font> | <font style="color:rgb(51, 51, 51);">3</font> | <font style="color:rgb(51, 51, 51);">'-838:59:59'/'838:59:59'</font> | <font style="color:rgb(51, 51, 51);">HH:MM:SS</font> | <font style="color:rgb(51, 51, 51);">时间值或持续时间</font> |
| <font style="color:rgb(51, 51, 51);"></font> | <font style="color:rgb(51, 51, 51);"></font> | <font style="color:rgb(51, 51, 51);"></font> | <font style="color:rgb(51, 51, 51);"></font> | <font style="color:rgb(51, 51, 51);"></font> |
| <font style="color:rgb(51, 51, 51);">year</font> | <font style="color:rgb(51, 51, 51);">1</font> | <font style="color:rgb(51, 51, 51);">1901/2155</font> | <font style="color:rgb(51, 51, 51);">YYYY</font> | <font style="color:rgb(51, 51, 51);">年份值</font> |
| <font style="color:rgb(51, 51, 51);">datatime</font> | <font style="color:rgb(51, 51, 51);">8</font> | <font style="color:rgb(51, 51, 51);">'1000-01-01 00:00:00' 到 '9999-12-31 23:59:59'</font> | <font style="color:rgb(51, 51, 51);">YYYY-MM-DD hh:mm:ss</font> | <font style="color:rgb(51, 51, 51);">混合日期和时间值</font> |
| <font style="color:rgb(51, 51, 51);">timestamp</font> | <font style="color:rgb(51, 51, 51);">4</font> | <font style="color:rgb(51, 51, 51);">'1970-01-01 00:00:01' UTC 到 '2038-01-19 03:14:07' UTC</font><br/><font style="color:rgb(51, 51, 51);">结束时间是第</font><font style="color:rgb(51, 51, 51);"> </font>**<font style="color:rgb(51, 51, 51);">2147483647</font>**<font style="color:rgb(51, 51, 51);"> </font><font style="color:rgb(51, 51, 51);">秒，北京时间</font><font style="color:rgb(51, 51, 51);"> </font>**<font style="color:rgb(51, 51, 51);">2038-1-19 11:14:07</font>**<font style="color:rgb(51, 51, 51);">，格林尼治时间 2038年1月19日 凌晨 03:14:07</font> | <font style="color:rgb(51, 51, 51);">YYYY-MM-DD hh:mm:ss</font> | <font style="color:rgb(51, 51, 51);">混合日期和时间值，时间戳</font> |


### <font style="color:rgb(51, 51, 51);">(3) 字符串类型：</font>
char(n)和varchar(n)中n指的是字符的总长度,并且在char中的n是固定长度，当字符数小于n时，MySQL会用空格在前面来补齐；但是varchar的n是表示最大长度，长度不够时，不会用空格来补齐。所以在使用char(n)和varchar(n)时必须指定字符长度。

text不需要指定长度，当不知道属性长度时，适合用text。

查询速度char最快，varchar次之，text最慢。

blob是二进制数据，blob和text存储方式不同，text是以文本方式存储的，blob是以二进制方式存储的。blob存储的数据只能整体读出。text可以指定字符集，blob不用指定字符集。

| <font style="color:rgb(255, 255, 255);">类型</font> | <font style="color:rgb(255, 255, 255);">大小</font> | <font style="color:rgb(255, 255, 255);">用途</font> |
| --- | --- | --- |
| <font style="color:rgb(51, 51, 51);">char(n)</font> | <font style="color:rgb(51, 51, 51);">0-255 bytes</font> | <font style="color:rgb(51, 51, 51);">定长字符串</font> |
| <font style="color:rgb(51, 51, 51);">varchar(n)</font> | <font style="color:rgb(51, 51, 51);">0-65535 bytes</font> | <font style="color:rgb(51, 51, 51);">变长字符串</font> |
| <font style="color:rgb(51, 51, 51);">tinyblob</font> | <font style="color:rgb(51, 51, 51);">0-255 bytes</font> | <font style="color:rgb(51, 51, 51);">不超过 255 个字符的二进制字符串</font> |
| <font style="color:rgb(51, 51, 51);">tinytext</font> | <font style="color:rgb(51, 51, 51);">0-255 bytes</font> | <font style="color:rgb(51, 51, 51);">短文本字符串</font> |
| <font style="color:rgb(51, 51, 51);">blob</font> | <font style="color:rgb(51, 51, 51);">0-65 535 bytes</font> | <font style="color:rgb(51, 51, 51);">二进制形式的长文本数据</font> |
| <font style="color:rgb(51, 51, 51);">text</font> | <font style="color:rgb(51, 51, 51);">0-65 535 bytes</font> | <font style="color:rgb(51, 51, 51);">长文本数据</font> |
| <font style="color:rgb(51, 51, 51);">mediumblob</font> | <font style="color:rgb(51, 51, 51);">0-16 777 215 bytes</font> | <font style="color:rgb(51, 51, 51);">二进制形式的中等长度文本数据</font> |
| <font style="color:rgb(51, 51, 51);">mediumtext</font> | <font style="color:rgb(51, 51, 51);">0-16 777 215 bytes</font> | <font style="color:rgb(51, 51, 51);">中等长度文本数据</font> |
| <font style="color:rgb(51, 51, 51);">longblob</font> | <font style="color:rgb(51, 51, 51);">0-4 294 967 295 bytes</font> | <font style="color:rgb(51, 51, 51);">二进制形式的极大文本数据</font> |
| <font style="color:rgb(51, 51, 51);">longtext</font> | <font style="color:rgb(51, 51, 51);">0-4 294 967 295 bytes</font> | <font style="color:rgb(51, 51, 51);">极大文本数据</font> |


## 2.创建表
在创建好数据库时，接下来的工作就是创建数据表。创建数据表是指在已经创建的数据库中建立新表。创建数据表的过程是规定数据列的属性的过程，同时也是实施数据的完整性（包括实体完整性、引用完整性和域完整性)约束的过程。

在创建数据表之前需要说明在那个数据库进行操作，语句为：

_**<font style="color:#601BDE;">use </font>**__**数据库名**__**<font style="color:#601BDE;"> ;</font>**_

使用语句创建数据表的语法结构为：

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732246427942-163740d5-17b5-4ac5-83fc-bf8d454f6f55.png)

创建表的语句为create table，语法规则如下：

_**<font style="color:#601BDE;">create table </font>**__**表名**_

_**<font style="color:#601BDE;">(</font>**_

_**字段名1，数据类型[列级别约束条件] [默认值]，**_****

_**字段名1，数据类型[列级别约束条件] [默认值]，**_****

_**……**_****

_**[表级别约束条件]**_****

_**<font style="color:#601BDE;">）;</font>**_

示例：创建一个employees表包含雇员ID，雇员名字，雇员薪水：

先创建一个数据库text，并选中

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732260744459-e940120d-352d-41d7-957c-e2c982cf557c.png)

之后创建雇员数据表

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732260779548-77959b9d-4a40-48ed-b75c-2c4c58869402.png)

 “employee_id int,“代表雇员名字，数据类型是int；

”employee_name varchar(10),”代表雇员名字，数据类型是varchar，字符不超过10个；  

 “salary float(8,2),“代表雇员的薪水，数据类型是float，该数据一共有8位，6位整数，2位小数。

这样一个数据表就创建成功了。

查看已创建的表的语句是：

_**<font style="color:#601BDE;">show tables;</font>**_

输入后就可以查看创建的employees的表前提得选中，不然会报错

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732363697280-9554df66-16d5-4059-9ef3-1136cde9625e.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732261198341-d9407d6f-fac6-4e49-a44d-6d34ee281472.png)

## 3.删除表
如果想要删除表，对应语句为：

_**<font style="color:#601BDE;">drop table </font>**__**表格名**__**<font style="color:#601BDE;">；</font>**_

示例：删除刚才创建的employees表：

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732261618978-3439ce11-cafa-4dff-88f9-ac49e062ab4a.png)

这时再查看表格时发现数据库已经是空的了,表明已经删除成功了：

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732261663619-1651eb3c-ddfa-45cc-a5c3-77147a63ca36.png)

## 4.修改表
### (1) 修改表_修改表名
修改数据表的语句为：

_**<font style="color:#601BDE;">alter table </font>**__**旧表名**__**<font style="color:#601BDE;"> rename </font>**__**新表名**__**<font style="color:#601BDE;">;</font>**_

示例：创建一个employees表包含雇员ID，雇员名字，雇员薪水，并修改表名称为emp：

选中text数据库并创建employees表

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732276874849-8667c2dd-4dd3-4c78-8fb7-af10e89edab5.png)

此时查看表格，表格名是employees

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732276874731-58bf3d61-e6d5-4dff-a35a-b4bc8a683380.png)

输入语句“alter table employees rename emp;”改动表格名字

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732276874582-1d63f34c-cc85-4da4-841d-17bf9ce192b4.png)

再次查看表格，发现名字变为emp，说明表格名字改动成功

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732276874573-3805a730-1e2b-46d0-b8e7-1956993e4733.png)

### (2) 修改表_修改列名
修改列名的语句是：

_**<font style="color:#601BDE;">alter table </font>**__**表名 **__**<font style="color:#601BDE;">change column</font>**__** 旧列名 新列名 类型**__**<font style="color:#601BDE;">;</font>**_

示例：将emp表中的employee_name修改为name：

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732278857379-c17ad910-4cb9-4305-a04f-4ab265920731.png)

### (3) 修改表_修改列类型
修改列类型的语句是：

_**<font style="color:#601BDE;">alter table </font>**__**表名 **__**<font style="color:#601BDE;">modify </font>**__**列名 新类型**__**<font style="color:#601BDE;">;</font>**_<font style="color:#601BDE;"></font>

<font style="color:#000000;">示例：将emp中的name的长度指定为40。</font>

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732279209652-6803d374-f09f-4e5f-bd88-947f4feb4e67.png)

### (4) 修改表_添加新列
添加新列的语句是：  
_**<font style="color:#601BDE;">alter table </font>**__**表名 **__**<font style="color:#601BDE;">add column </font>**__**新列名 类型**__**<font style="color:#601BDE;">;</font>**_

示例：在emp表中添加佣金列，列名为commission_pct

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732279664143-4d9187a1-fcfa-446a-bf28-2d7e30d78201.png)

### (5) 修改表_删除指定列
删除列的语句是：  
_**<font style="color:#601BDE;">alter table </font>**__**表名 **__**<font style="color:#601BDE;">drop column </font>**__**列名**__**<font style="color:#601BDE;">;</font>**_

示例：在emp表中删除commission_pct列

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732280408279-a95e6c03-8dbf-450d-aadf-8f2a9cd371f4.png)

## <font style="color:#000000;">5.MySQL的约束</font>
### <font style="color:#000000;">(1) 约束概述</font>
数据库约束是对表中的数据进行进一步的限制，确保数据的正确性、有效性和完整性。数据库的约束类型有：主键约束、外键约束、唯一性约束、非空约束和检查约束。

主键约束（Primary Key)：主键约束是使用最频繁的约束。它不允许为空、重复，以此保证数据的唯一性。在设计数据表时一般情况下，都会要求表中设置一个主键。主键是表的一个特殊字段，该字段能唯一标识该表中的每条信息。如果发现有重复值出现时，那么数据将无法添加到数据表当中。例如：学生信息表当中的学号是唯一的，这时就需要添加主键来进行约束。

外键约束(Foreign Key):<font style="color:rgb(77, 77, 77);">外键约束经常和主键约束一起使用，用来确保数据的一致性，用于限制两个表的关系，用于保证该字段的值必须来自于主表的关联列的值。它允许有空值、重复但是值必须是参照表中参照列中的所包含的值以保证数据的参照完整性。从表添加外键约束，用于引用主表中某列的值。比如学生表的专业编号，员工表的部门编号，员工表的工种编号。</font>

<font style="color:rgb(77, 77, 77);">唯一性约束（Unique)：用于约束该字段的值具有唯一性，可以有多个，可以没有，可以为空，允许为多个列添加唯一性约束，但是相同值只能出现一次。比如座位号</font>

<font style="color:rgb(77, 77, 77);">非空约束（Not Null):用于约束该字段的值不能为空,允许有空值，允许为多个列添加非空约束，保证了数据没有空值。比如姓名、学号等。</font>

<font style="color:rgb(77, 77, 77);">检查约束（Check)：检查约束也叫用户自定义约束，是用来检查数据表中，字段值是否有效的一个手段。</font>

<font style="color:rgb(77, 77, 77);">查询表中的约束信息的语句为：</font>

_**<font style="color:#601BDE;">show keys from</font>**__**<font style="color:rgb(77, 77, 77);"> 表名</font>**__**<font style="color:#D22D8D;">；</font>**_

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732434747673-be973269-afed-454a-b724-a733cf8ca018.png)

### <font style="color:#000000;">(2) 添加主键约束</font>
单一主键：使用一个列作为主键列，当列的值有重复时，则违反唯一约束。

联合主键：使用多个列作为主键列，当多个列的值都相同时，则违反唯一约束。

一般来说单一主键用的比较多

添加主键约束的语句为：

_**<font style="color:#601BDE;">alter table </font>**__**表名 **__**<font style="color:#601BDE;">add primary key (</font>**__**列名**__**<font style="color:#601BDE;">);</font>**_

示例：将emp表中的employee_id修改为主键。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732283270049-1fd226ea-2673-4fac-99eb-ee6328e8fe1a.png)

**<font style="color:#000000;">主键自增长：</font>**

MySQL中的自动增长要求：

+ 一个表中只能有一个列自动增长。
+ 自动增长的类型必须是整形。
+ 自动增长只能添加到具备主键约束与唯一性约束的列上。
+ 删除主键约束或唯一性约束，如果该列拥有自动增长能力，则需要先去掉自动增长然后再删除约束。

语句为：  
_**<font style="color:#601BDE;">alter table</font>**__** 表名 **__**<font style="color:#601BDE;">modify</font>**__** 添加主键的列名 类型 **__**<font style="color:#601BDE;">auto_increment;</font>**_

示例：将emp表的employees_id修改为自增：

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732364711171-6b93c5f4-d82b-4de4-b312-d5a90f98f04a.png)

### <font style="color:#000000;">(3) 删除主键约束</font>
删除主键的语句为：

_**<font style="color:#601BDE;">alter table </font>**__**表名**__**<font style="color:#601BDE;"> drop primary key;</font>**_

删除主键时，如果主键具备自动增长能力，要先去掉自动增长，然后删除主键。

去掉主键自动增长的语句是：

_**<font style="color:#601BDE;">alter table</font>**__** 表名**__**<font style="color:#601BDE;"> modify </font>**__**添加主键的列名 类型**__**<font style="color:#601BDE;"> ;</font>**_

示例：删除emp表中的employee_id主键约束

如果先输入删除主键的语句，则会报错

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732377063443-edcc9fa9-eef0-48ef-b58f-cd0781092a68.png)

因为employee_id有自动增长，所以会报错，要先去掉自动增长

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732377180774-1f01305b-6602-4cf3-984c-d179f8409bc9.png)

再删除主键约束

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732377213294-310cc4fa-18e1-4ac9-9b88-9caf5ded1c54.png)

### <font style="color:#000000;">(4) 添加外键约束</font>
添加外键约束的语句为：

_**<font style="color:#601BDE;">alter tables</font>**__** 表名 **__**<font style="color:#601BDE;">add constraint </font>**__**约束名 **__**<font style="color:#601BDE;">foreign key(</font>**__**列名**__**<font style="color:#601BDE;">) references</font>**__** 参照的表名**__**<font style="color:#601BDE;">（</font>**__**参照的列名**__**<font style="color:#601BDE;">);</font>**_

<font style="color:#000000;">示例：创建depaartments表包含department_id,department_name,location_id。</font>

<font style="color:#000000;">并修改depaartments表，向department_id列添加主键约束与自动递增：</font>

<font style="color:#000000;">创建depaartments表</font>

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732379841036-a95018f7-fadf-4658-9153-215d1b48ac70.png)

添加主键约束

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732379876215-d8e3267d-703e-4c51-8545-3080d89ba65f.png)

添加<font style="color:#000000;">自动递增</font>

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732380008614-d4995595-a719-4722-846c-8e5af6907f5e.png)

修改emp表，添加dept_id列

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732380153379-11f0c388-d9f2-4455-8b4d-124135097ce7.png)

向dept_id列添加外键约束

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732382236126-346fde09-f5e1-4839-a6c9-a835682d80be.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732382157825-af4c992d-a598-4165-beb2-5135bc9b6701.png)

不知道为什么会报错，给 dept_id加上主键自动增长改成一样的格式也是同样样报错

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732432771202-050c4a80-4a2e-423f-844a-fe21be570c51.png)

最后查了资料是在emp后面加上“_fk“组成约束名来”解决的

### (5) 删除外键约束
删除外键约束的语句为：

_**<font style="color:#601BDE;">alter table </font>**__**表名 **__**<font style="color:#601BDE;">drop foreign key </font>**__**约束名**__**<font style="color:#601BDE;">;</font>**_

示例：删除dept_id的外键约束。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732433413214-86d64c13-0ac0-417c-b149-d0e92f0329fa.png)

### (6) 添加唯一性约束
添加唯一性约束的语句是：

_**<font style="color:#601BDE;">alter table </font>**__**表名**__**<font style="color:#601BDE;"> add constraint </font>**__**约束名**__**<font style="color:#601BDE;"> unique(</font>**__**列名**__**<font style="color:#601BDE;">);</font>**_

示例：向emp表中的name添加唯一性约束。

 ![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732433691067-73a56022-a439-4634-a70b-a0932c94984b.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732434292270-e9dc08f5-48ea-4b62-93ba-7ffbd8c0979f.png)

### (7) 删除唯一性约束
删除唯一性约束的语句为：

_**<font style="color:#601BDE;">alter table </font>**__**表名 **__**<font style="color:#601BDE;">drop key </font>**__**约束名**__**<font style="color:#601BDE;">;</font>**_

示例：删除name的唯一性约束。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732433860926-af01a128-970c-492f-b634-ee7ff2fc0d1f.png)

### (8) 添加非空约束
添加非空约束的语句为：

_**<font style="color:#601BDE;">alter table </font>**__**表名 **__**<font style="color:#601BDE;">modify </font>**__**列名 类型**__**<font style="color:#601BDE;"> not null;</font>**_

示例：向emp表中的salary添加非空约束：

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732434145776-484479dd-f51a-48c0-8ecc-e697b03f23bc.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732434243632-933fab18-8d41-4c34-b881-384db2167e0d.png)

### (9) 删除非空约束
删除非空约束的语句为：

_**<font style="color:#601BDE;">alter table </font>**__**表名 **__**<font style="color:#601BDE;">modify</font>**__** 列名 类型 **__**<font style="color:#601BDE;">null;</font>**_

示例：删除emp表中salary的非空约束

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732434378778-bd19a88c-0949-4cd3-acad-d12d48717a7e.png)

### (10) 创建表时添加约束
一般来说除了外键约束不能在创建表时创建，其他约束均能在创建表时创建，创建时在列类型的后面加上约束类型即可。

示例：创建depts表包含department_id该列为主键且为自动增长，<font style="color:#000000;">department_name列不允许重复，location_id列不含有空值。</font>

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732435428151-d1ff4d7a-6362-4a1e-b0db-2c9f1331613f.png)



## 6.数据处理
### (1) 添加数据
选择插入的语句为：

_**<font style="color:#601BDE;">insert into </font>**__**表名**__**<font style="color:#601BDE;">(</font>**__**列名1**__**<font style="color:#601BDE;">，</font>**__**列名2**__**<font style="color:#601BDE;">，……)values(</font>**__**值1，值2**__**<font style="color:#601BDE;">……);</font>**_

注意有非空约束的一定要有数据；

示例：向departments 表中添加一条数据，部门名称为market,工作地点ID为1

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732435902720-c8208610-4631-434d-b770-30043c6882bb.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732436078740-18c97665-b6fc-446f-956a-a534f7822580.png)

### (2) 默认值处理
如果插入数据时未指定该列的值，则我们可以设置默认值



创建表时指定某列默认值的语句是：

_**<font style="color:#601BDE;">create table </font>**__**表名**__**<font style="color:#601BDE;">(</font>**__**列名 类型 **__**<font style="color:#601BDE;">default </font>**__**默认值**__**<font style="color:#601BDE;">，……);</font>**_

示例：创建emp3表，该表包含emp_id主键且自动增长，包含name，包含address且该列默认值为”Unknown"

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732436680329-b1ab360a-7e6c-447f-87f2-edd5fbfc795c.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732436753845-e4b1a20c-afbb-45fe-aee0-b10392e893a6.png)



修改表添加新列并指定默认值的语句为：

alter table 表名 add column 列名 类型 default 默认值;

示例：修改emp3表，添加job_id列且该列的默认值为0

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732437150417-d1f088ea-df47-4d05-b9ad-f36aa6667d02.png)



插入数据时的默认值处理

如果在插入数据时未指定该列的值，那么MySQL会将默认值添加到该列如果是完全项插入需要使用default来占位。

示例：向emp3插入数据，要求address列与job_id列使用默认值作为该列的值。

两种方式：

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732438164271-b66f6865-20c5-4294-b893-499050baf5ca.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732438341948-e902041d-ee06-4dcf-96ad-faa4e3c200ef.png)

### (3) 更新数据 
更新数据时一定要给定更新条件，否则表中所有数据都会更新

更新数据的语句为：

update 表名 set 列名=值，列名=值  where 条件;

示例：更新emp3表中的id为1的数据，添加address为北京

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732438697500-bee908dd-2bc4-484e-a09e-9917cd13baae.png)

### (4) 删除数据
删除数据一定要给定删除条件，否则所有数据都会删除

删除数据的语句为：

delate from 表名 where 条件;

示例：删emp3表中的emp_id为1的雇员信息

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732439401475-2730ad24-ef08-46cf-ae64-9e25cbeb4b27.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732439420775-4cdcda4b-5290-4ece-ac91-fbcf53114b66.png)

## 7.查询
### (1) select基本查询介绍
![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732439467176-44284ad7-4f11-4d50-b80a-719a90fc3242.png)

SELECT语句从数据库中返回信息。使用一个SELECT语句，可以做下面事情：

**列选择**：能够使用SELECT语句的列选择功能选择表中的列，这些列是想要用查询返回的。当查询时，能够返回列中的数据。

**行选择**：能够使用SELECT语句的行选择功能选择表中的行，这些行是想要用查询返回的。能够用不同的标准限制看见的行。

**链接**：能够使用SELECT语句的连接功能来集合数据，这些数据被存储在不同的表中，在它们之间可以创建连接，查询出我们关心的数据

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732440117182-ba1ca5f6-8b9a-4ab4-af91-f80c2b6c3756.png) **基本SELECT语句**

在最简单的形式中，select语句必须包含一下内容：

一个select子句，指定被显示的列

一个from子句，指定表，该表包含select子句中的字段列表

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732440274696-4ecb19d0-3d26-4f46-b99b-5d97a2ffb781.png)

### (2) 查询中的列选择
选择所有列的语句为：

select * from  表名;

用跟在select关键字后面的星号(*)，你能够显示表中所有数据的所有列。

示例：查询departments表中的所有数据。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732440616777-78ed42c5-ea58-4ec7-87c0-5c862ce37a0b.png)



选择指定的列的语句为：

select 列名1，列名2…… from 表名;

示例：查询departments表中的所有部门名称

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732440781231-60e71a82-6d58-4577-99ca-98d3ce29afbf.png)

### (3) 查询中的算数表达式
算数表达式有：加(+)、减(-)、乘(*)和除(/)

需要修改数据的显示方式，如执行计算，或者作假定推测，这些都可能用到算数表达式。一个算数表达式可以包含列名、固定的数字值和算数运算符。

在查询到的结果做算数表达式处理时，并不会影响我们表中的数据，并不会更新到我们表当中去

做算术表达式，使用算数运算符的语句为：

select 列名1，列名2 关于列名2的算数表达式 from 表名;

示例：查询雇员的年薪。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732442718455-308103f0-4167-4ab0-9f53-db4daf7c1e90.png)![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732442718436-d10b493a-2936-47e3-acc7-2b447ff2c113.png)





这周先写到这里吧，这周确实挺累的，有很多课结课了，作业一堆， 事情也挺多的。

心有所向，日复一日，必有精进！加油！


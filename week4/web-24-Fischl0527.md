** PHP学习及练习**

# 一、PHP开发入门
## 1.PHP概述
PHP最初是由 Rasmus Lerdorf于1994年为了维护个人网页而编写的一个简单程序。这个程序用来显示Rasmus Lerdorf的个人履历以及统计网页流量，因此最初称为个人主页(Personal Home Page)。后来受到GNU的影响，它更名为PHP(Hypertext Preprocessor，超文本预处理器）。

PHP作为服务器端Web程序开发语言，主要有以下两方面原因：

1.PHP是一种服务器端、HTML嵌入式的脚本语言，因此适合Web开发。

2.PHP是B/S(Browser/Server，浏览器/服务器)架构，即服务器启动后，用户可以不使用客户端软件，而是使用浏览器进行访问，这种方式既保持了图形化的用户界面，又大大减少了应用程序的维护量。

PHP的应用领域：

全球有60% 的网站都在使用PHP技术进行开发，包括Facebook、谷歌、百度、新浪等国内外一线互联网公司。PHP正吸引着越来越多的Web开发人员，其应用领域非常广泛，如网站开发、OA办公系统、电子商务、CRM管理系统、ERP系统、手机APP接口及API接口、网页游戏后台、服务器脚本等。

## 2.PHP开发环境搭建
下载WampServer

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732718696824-9b37b96c-6344-4024-a578-838f91661ba2.png)

安装WampServer

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732718730481-9bb1d09e-4c40-42d6-87fe-6a32147fa363.png)

打开WampServer

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732718730781-d1bad042-852d-43d9-8068-32f281cadc80.png)

成功编写第一个php程序！！！！！！

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732789008735-00ccaea5-d250-4b62-80ab-06b56b9fcf3d.png)

# 二、PHP编程基础
## 1.PHP基础知识
PHP的一些知识与语言相同，相同的部分不多赘述



php标记：开始要用一对标记将PHP代码包含起来，以便和HTML代码区分。\

一般用<?php和?>来分别作为开始结束标记



注释：可以使用c语言风格



标识符和关键字如下图：

![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732721072654-f2ce19d0-49bf-4bae-8695-bbe5ef5c3657.jpeg)



PHP变量及数据类型：在PHP中，变量是由$和变量名构成的，命名规则与标识符相同，且区分大小写。

![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732721922313-bf54784a-3e48-4a98-8419-2f37fa5f0cdf.jpeg)

boolean（布尔型)：该类型只能为true（真）和false（假）且不区分大小写。

例：$bool = true;将true值赋给$bool

integer型（整型）：存储整数

float（浮点型）：存储实数

string（字符串型）：字符串可以由单引号（单引号的这种形式只能转义单引号(\')和反斜杠(\\)。）、双引号 （可以转移一些字符，也可以解析变量）、定界符（<<<）（在之后用一个标识符表示开始，然后是包含的字符串，最后是同样的标识符结束字符串，并且后面除了分号不能有任何其他字符）



PHP检测数据类型：

![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732722851738-5112a28f-b4f4-4e02-b5ce-1781c58ea4a5.jpeg)

函数返回的布尔值true转换成字符串“1”，false转换成空字符串



PHP常见转义字符：

![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732722034101-b561fa9d-95a3-454a-8923-c0816235e328.jpeg)![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732722037706-dfcfcd45-6f30-44a5-a313-d50f1f3c0b5d.jpeg)

<br>：表示换行



PHP常量：指在程序执行过程中值不变的量，通过函数define()来定义

预定义常量：![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732723268009-1b9cf437-5078-4a20-86e9-1d71a5516208.jpeg)



数据类型转换：

其他类型转换成布尔型：整型0、浮点型0.0、字符串型""与"0"、不包含任何元素的数组、不包含任何成员变量的对象、NULL会被转换成false，其他值会被转化成true。

布尔型转化成整型：true转化成1，false转化成0

字符串类型转化成整型或浮点型：如果字符串是数字序列的字符，则这转换成该数字，否则出现警告

布尔型转化成字符串类型：true转换成"1"，false转换成""。

整型或浮点型转换成字符串类型：字面样式转换



PHP一些基本运算符参考c语言

==与===的区别是==先将操作数转换成相同类型在进行比较，两者值相同则返回true，而===只有值相等并且数据类型相同才返回true

NULL合并运算符：表达式1 ?? 表达式2 ;  意为表达式1的值存在且不为NULL则返回该值，否则返回表达式2的值

组合比较运算符：表达式1 <=> 表达式2;  意为当表达式1小于等于大于表达式2时分别返回-1、0、1

位运算符：![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732790878199-e18af6e7-321b-4481-88c7-c5d321f4b348.jpeg)

其他运算符：![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732790934912-1187285f-a65b-4e21-a98e-4d49297ac9a7.jpeg)



运算符的优先级：

![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732790995249-f956ed3a-43e6-47f4-aa16-961aa9cde519.jpeg)



选择语句，循环语句、跳转语句基本与c语言相通，在此不多赘述了



写了一道题：

![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732867587894-7e31367c-cef1-4ddd-8df2-8e59afea4dde.jpeg)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733042498129-7e39fc05-025d-4d88-afa4-7402f3796e0d.png)

## 2.PHP函数、数组
PHP的函数的定义：

_function 函数名（参数名1 [=值1],参数名2 [=值2],参数名3 [=值3],……)_

_{_

_函数体_

_[return 返回值；]_

_};_

[]中的内容可以省略。并且在书写时不带[]

_函数的调用：_

_function 函数名（参数名1 [=值1],参数名2 [=值2],参数名3 [=值3],……)_

常用函数：

**<font style="color:rgb(51, 51, 51);">urlencode() 函数：</font>**<font style="color:rgb(51, 51, 51);">urlencode() 函数编码URL 字符串函数，</font><font style="color:rgb(51, 51, 51);">此函数便于将字符串编码并将其用于 URL 的请求部分，同时它还便于将变量传递给下一页。</font>

<font style="color:rgb(51, 51, 51);">语法：</font>_<font style="color:rgb(51, 51, 51);">string urlencode ( string $str );</font>_

<font style="color:rgb(51, 51, 51);">此函数便于将字符串编码并将其用于 URL 的请求部分，同时它还便于将变量传递给下一页。编码 URL 字符串函数。</font>

<font style="color:rgb(51, 51, 51);">此函数便于将字符串编码并将其用于 URL 的请求部分，同时它还便于将变量传递给下一页。</font>

**<font style="color:rgb(51, 51, 51);">serialize() 函数：</font>**<font style="color:rgb(51, 51, 51);">用于序列化对象或数组，并返回一个字符串。函数序列化对象后，可以很方便的将它传递给其他需要它的地方，且其类型和结构不会改变。</font>

<font style="color:rgb(51, 51, 51);">语法：string serialize ( mixed $value );</font>

**__wakeup()函数：**__wakeup() 是 PHP 中一个特殊的魔术方法。它在反序列化一个对象时被自动调用，允许开发者在对象从序列化格式还原为可用的 PHP 对象之前对其进行某些特殊处理。这个方法可以接受任意的参数，但在实际使用中，它通常不需要参数。

**<font style="color:rgb(51, 51, 51);">eval() 函数：</font>**<font style="color:rgb(51, 51, 51);">eval() 函数把字符串按照 PHP 代码来计算。该字符串必须是合法的 PHP 代码，且必须以分号结尾。</font>

<font style="color:rgb(51, 51, 51);">语法：</font><font style="color:rgb(68, 68, 68);">eval(</font>_<font style="color:rgb(68, 68, 68);">phpcode</font>_<font style="color:rgb(68, 68, 68);">);</font>

**<font style="color:rgb(51, 51, 51);">include ()和 require()函数</font>**<font style="color:rgb(51, 51, 51);">：在 PHP 中，可以在服务器执行 PHP 文件之前在该文件中插入一个文件的内容。include 和 require 语句用于在执行流中插入写在其他文件中的有用的代码。include 和 require 除了处理错误的方式不同之外，在其他方面都是相同的：require 生成一个致命错误（E_COMPILE_ERROR），在错误发生后脚本会停止执行。include 生成一个警告（E_WARNING），在错误发生后脚本会继续执行。</font>

<font style="color:rgb(17, 17, 17);">语法：include 'filename';    或者   </font>_<font style="color:rgb(17, 17, 17);"> require 'filename';</font>_

**<font style="color:rgb(77, 77, 77);">mb_substr()函数：</font>**<font style="color:rgb(51, 51, 51);">mb_substr() 函数返回字符串的一部分，substr() 函数，它只针对英文字符，如果要分割的中文文字则需要使用 mb_substr()。如果 start 参数是负数且 length 小于或等于 start，则 length 为 0。</font>

<font style="color:rgb(51, 51, 51);">语法：mb_substr( string $str , int $start [, int $length = NULL [, string $encoding = mb_internal_encoding() ]] )</font>![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733042975644-854a4512-2bf5-4165-9ce5-cf624f54b92f.png)

**<font style="color:rgb(77, 77, 77);">mb_strpos()函数：</font>**<font style="color:rgb(17, 17, 17);"> — 查找字符串在另一个字符串中首次出现的位置 查找 string 在一个 string 中首次出现的位置。 基于字符数执行一个多字节安全的 strpos () 操作。 第一个字符的位置是 0，第二个字符的位置是 1，以此类推。 要被检查的 string。 在 haystack 中查找这个字符串。 和 strpos () 不同的是，数字的值不会被当做字符的顺序值。</font>

<font style="color:rgb(77, 77, 77);">语法：mb_strpos (haystack ,needle );</font>

<font style="color:rgb(77, 77, 77);">参数：haystack：要被检查的字符串。needle：要搜索的字符串。</font>

**<font style="color:rgb(77, 77, 77);">urldecode()函数：</font>**<font style="color:rgb(17, 17, 17);">urldecode() 方法用于解码 PHP 中的编码字符串。urldecode() 是 PHP 中用于解码编码字符串和 URL 的内置方法。 urldecode() 只能解码由 urlencode() 方法完成的编码字符串和 URL。 此方法的语法是： 其中 URL 是要解码的 URL 或字符串，此方法的返回值是一个字符串</font>

<font style="color:rgb(51, 51, 51);">语法：string urldecode ( string $str );</font>

**strcmp()函数：**<font style="color:rgb(51, 51, 51);">函数用于比较两个字符串（区分大小写）。如果 str1 小于 str2 返回 < 0； 如果 str1 大于 str2 返回 > 0；如果两者相等，返回 0。</font>

<font style="color:rgb(63, 63, 63);background-color:rgb(253, 252, 248);">语法：</font>strcmp(string1,stri<font style="color:rgb(51, 51, 51);">strcmp()</font>

**file_get_contents()函数：**<font style="color:rgb(77, 77, 77);">在PHP中，</font>file_get_contents<font style="color:rgb(77, 77, 77);">() </font>函数<font style="color:rgb(77, 77, 77);">是一个强大的工具，它既可以用于读取本</font>地文件的内容，也可以用于发起 HTTP 请求获取远程资源。

语法：file_get_contents(path,include_path,context,start,max_length);![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733043792480-c6f50939-046d-438d-aefa-3f39aeefdea4.png)

**<font style="color:rgb(51, 51, 51);">preg_match()函数：</font>**<font style="color:rgb(51, 51, 51);"> preg_match函数用于执行一个正则表达式匹配。</font>

<font style="color:rgb(51, 51, 51);">语法：</font>_<font style="color:rgb(51, 51, 51);">int preg_match ( string $pattern , string $subject [, array &$matches [, int $flags = 0 [, int $offset = 0 ]]] )</font>_

<font style="color:rgb(51, 51, 51);">参数说明：</font>

<font style="color:rgb(51, 51, 51);">$pattern: 要搜索的模式，字符串形式。</font>

<font style="color:rgb(51, 51, 51);">$subject: 输入字符串。</font>

<font style="color:rgb(51, 51, 51);">$matches: 如果提供了参数matches，它将被填充为搜索结果。 $matches[0]将包含完整模式匹配到的文本， $matches[1] 将包含第一个捕获子组匹配到的文本，以此类推。</font>

<font style="color:rgb(51, 51, 51);">$flags：flags 可以被设置为以下标记值：</font>

<font style="color:rgb(51, 51, 51);">PREG_OFFSET_CAPTURE: 如果传递了这个标记，对于每一个出现的匹配返回时会附加字符串偏移量(相对于目标字符串的)。 注意：这会改变填充到matches参数的数组，使其每个元素成为一个由 第0个元素是匹配到的字符串，第1个元素是该匹配字符串 在目标字符串subject中的偏移量。</font>

<font style="color:rgb(51, 51, 51);">offset: 通常，搜索从目标字符串的开始位置开始。可选参数 offset 用于 指定从目标字符串的某个未知开始搜索(单位是字节)。</font>

<font style="color:rgb(51, 51, 51);"></font>

数组的定义：

1.直接为数组赋值：_$数组名[key]= value ; _

2.使用array语句定义数组：_$数组名 = array(key1 => value1 , key2 => value2 ,……);_

数组的操作：

输出：var_dump()函数可以输出数组中的每个元素与值的数据类型，print_r()函数可以直接输出数组中的所有元素

删除：用unset语句可以删除整个数组，也可以删除数组中的某一个元素。用法为：unset(数组名);

运算：![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732978528950-a7cae304-4d6f-4632-82c7-716d3a89ec27.jpeg)![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732978533698-ae49f329-8d2b-44ed-a848-c74ba945a8d9.jpeg)

数组遍历：

用foreach语句遍历数组：

_foreach($数组名 as [$key =>] $value){   循环体   };_

举例：

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732979393040-4bd37911-15a5-49f4-9ec2-42bfd88f6f04.png)

数组的常用语句、函数：

**1.list语句：**<font style="color:rgb(0, 0, 0);background-color:rgb(253, 252, 248);">把数组中的值赋给一些变量。</font>

<font style="color:rgb(0, 0, 0);background-color:rgb(253, 252, 248);">语法：</font>_ list(var1,var2...);_

**2.each()函数：**<font style="color:rgb(0, 0, 0);background-color:rgb(253, 252, 248);">返回当前元素的键名和键值，并将内部指针向前移动，该元素的键名和键值会被返回带有四个元素的数组中。两个元素（1 和 Value）包含键值，两个元素（0 和 Key）包含键名。</font>

<font style="color:rgb(0, 0, 0);background-color:rgb(253, 252, 248);">语法：</font>_<font style="color:rgb(0, 0, 0);background-color:rgb(253, 252, 248);"> each(array);</font>_

**3.count()函数：**该函数可以统计数组中元素的个数

语法：_int count(array,mode);         _

mode为可选参数<font style="color:rgb(0, 0, 0);">可选。规定模式。可能的值：</font>

<font style="color:rgb(0, 0, 0);">0 - 默认。不对多维数组中的所有元素进行计数</font>

<font style="color:rgb(0, 0, 0);">1 - 递归地计数数组中元素的数目（计算多维数组中的所有元素）</font>

**<font style="color:rgb(0, 0, 0);">4.压入、弹出元素函数：</font>**![](https://cdn.nlark.com/yuque/0/2024/jpeg/50616406/1732980994939-8724b26b-5fbb-45d6-a93f-d44cf07c1466.jpeg)

**5.移除重复值：**<font style="color:rgb(0, 0, 0);background-color:rgb(253, 252, 248);">array_unique() 函数移除数组中的重复的值，并返回结果数组。当几个数组元素的值相等时，只保留第一个元素，其他的元素被删除。返回的数组中键名不变。</font>

<font style="color:rgb(63, 63, 63);background-color:rgb(253, 252, 248);">语法：</font>_<font style="color:rgb(0, 0, 0);background-color:rgb(253, 252, 248);">array_unique(array);</font>_

<font style="color:rgb(0, 0, 0);background-color:rgb(253, 252, 248);"></font>

<font style="color:rgb(0, 0, 0);background-color:rgb(253, 252, 248);">二维数组：</font>

<font style="color:rgb(0, 0, 0);background-color:rgb(253, 252, 248);">定义：</font>

_<font style="color:rgb(0, 0, 0);background-color:rgb(253, 252, 248);">array (</font>_

_<font style="color:rgb(0, 0, 0);background-color:rgb(253, 252, 248);">    array (elements...),</font>_

_<font style="color:rgb(0, 0, 0);background-color:rgb(253, 252, 248);">    array (elements...),</font>_

_<font style="color:rgb(0, 0, 0);background-color:rgb(253, 252, 248);">    ...</font>_

_<font style="color:rgb(0, 0, 0);background-color:rgb(253, 252, 248);">)</font>_

<font style="color:rgb(0, 0, 0);background-color:rgb(253, 252, 248);">二维数组的遍历可以通过foreach语句嵌套来遍历二维数组</font>

# <font style="color:#000000;">三、练习（</font>[<font style="color:#000000;">BUUCTF</font>](https://buuoj.cn/)<font style="color:#000000;">)</font>
![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732896037818-c8f3e200-efc1-4294-9419-1624bc9d691c.png)

## 1.<font style="color:rgb(33, 37, 41);">[极客大挑战 2019]Havefun</font>


![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732896036892-cebc68d7-8b8a-4a78-af84-7f3330417ef5.png)

进入这一题看到了一只很可爱的猫猫，~~如果我不是来做题的话，我会看上一整天，傻笑一整天……~~

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732896036764-231e32a0-03ce-4478-887a-a167b22bf327.png)

这道题页面上啥都没有，就想着看看源代码，进一步发掘有效信息

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732896038228-24b55826-ab57-4e88-bede-8a6e19d2b065.png)

打开之后是一堆晦涩难懂的内容，这代码确实不想看，感觉都是无效信息

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732896133010-0f76a182-8e5b-4642-be0a-8f0f6a6ed6b1.png)

还好我比较谨慎，耐心翻源代码，在页面最下面找到了绿油油的被注释掉的东西，这应该就是关键信息了，这是一段PHP代码，这段代码的意思是用get传参cat到变量…$cat里，输出变量$cat的值，之后是if语句，如果$cat里的值等于dog，那么就输出Syc{cat_cat_cat_cat}，大概率是flag。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732896037726-faf3fc09-25b1-4250-a4d6-052e431afe24.png)

所以我们在后面get请求去传参dog给cat变量，满足if语句的条件，flag就出现了。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732896037788-4166aac8-a18a-478d-95d1-f63dac382f9b.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732896036732-fecc93c1-6269-4c1e-9f2f-f8817f0267a4.png)

这道题挺适合我这样的小白的，也是做完BaseCTF2024新生赛后自己独立做出来的题目，为自己鼓掌

## 2.<font style="color:rgb(33, 37, 41);">[HCTF 2018]WarmUp</font>
![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732898677758-aaaab5dc-4888-4bed-8c7f-c97a9693cfa2.png)

进入页面后这一个滑稽属实绷不住，大晚上的![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732898723717-1999bff3-befa-420e-8a5a-1e6e31239600.png)，属实绷不住

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732898678058-7e3e05ee-b197-4f11-8fef-24da185f700b.png)

还是和上一题一样，这个页面没有有效信息，所以我看看源代码，又是这一个绿油油的注释，提示已经很明显了

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732898835734-fdde5a71-e710-4c26-8a59-ecf015751f61.png)

果然，在后面加上/source.php访问一下果然出现PHP代码了。这串代码看的我比较蒙，我简单理解一下：这段PHP代码先是用class定义emmm的类，之后定义函数checkFile，之后进行If语句，<font style="color:rgb(77, 77, 77);">i</font><font style="color:#000000;">f条件语句是关键，即需要满足</font><font style="color:#000000;">if(true && true && true)</font><font style="color:#000000;">，才会执行include函数，否则输出：</font>[https://i.loli.net/2018/11/01/5bdb0d93dc794.jpg](https://i.loli.net/2018/11/01/5bdb0d93dc794.jpg)，即<font style="color:#000000;">滑稽图。</font>

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732898977644-6b182ff1-8064-4f16-bf22-67fc0fd17234.png)

满足后面的<font style="color:#000000;">if(true && true && true)前两个true比较简单，但是最后的true得看</font>这个checkFile函数，这 函数确实难懂，但是我找到了<font style="color:#000000;">hint.php，这个应该也是关键信息，访问一下后出现了这个，说明flag藏在</font><font style="color:rgb(0, 0, 0);">fffllllaaaagggg里，</font>~~<font style="color:rgb(0, 0, 0);">这道题确实抽象的像极了我的室友，</font>~~<font style="color:rgb(77, 77, 77);">我们始终是在source.php页面下进行操作，目的是利用最后的include函数将flag文件包含出来，从而得到答案</font>

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732950610972-d7e9421b-80d4-48e6-a727-c1649b91e027.png)

<font style="color:rgb(77, 77, 77);">接着分析一下传入</font>hint.php之后出现"<font style="color:rgb(0, 0, 0);">flag not here, and flag in ffffllllaaaagggg</font>",PHP代码是怎么工作的：

这个题目是用class定义了一个名为emmm的类，在该类中有一个静态方法的checkFile用于检查要包含的文件是否在白名单($whitelist)中，白名单是一个关联数组$whitelist。在代码中，白名单允许包含的文件有"source"=>"source.php"和"hint"=>"hint.php"。                

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732975579511-1cdcc036-907a-4054-8898-7a6200ff6c19.png)

第一个if语句：当传入hint.php时进行第一个if语句判断，显然hint.php是字符串，不执行<font style="color:rgb(77, 77, 77);">输出"you can't see it"并返回false。</font>

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732975608173-9563f50a-eadb-4bc1-8bf6-3061f18c176a.png)

<font style="color:rgb(77, 77, 77);">第二个if语句：之后第二个if语句</font>检查hint.php是否在白名单内，显然它在白名单内，条件通过，继续执行后面的代码。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732975619636-08e505de-3d22-497f-804f-9e4864a7aaa2.png)

之后<font style="color:rgb(77, 77, 77);">对hint.php执行mb_substr函数，但是函数内一个参数是来自另一个函数mb_strpos的返回值，因此我们先看mb_strpos函数，使用.进行字符连接，即连接了一个问号字符 '?'，得到hint.php?在这个新的字符串中查找问号是否存在，那么很明显肯定能找到。那么返回值是"?"</font><font style="color:rgb(50, 50, 50);">首次出现位置的数值，</font><font style="color:rgb(77, 77, 77);">0开始算，</font><font style="color:rgb(50, 50, 50);">即8，所以</font><font style="color:rgb(77, 77, 77);">mb_substr函数的处理是返回从</font>hint.php？的第0个字符到第8个字符，其实还是返回hint.php。~~来回绕是吧!!!原样进去原样出来，这一步真是字如其名~~![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732898678058-7e3e05ee-b197-4f11-8fef-24da185f700b.png)~~666~~

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732975660428-90bc7fb1-0b6f-42f8-94b3-afef82136b6d.png)

<font style="color:rgb(77, 77, 77);">第三个if语句：</font>之后进行第三个if语句，显然hint.php还在白名单中，<font style="color:rgb(77, 77, 77);">继续执行后面的代码</font>

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732975684050-22d6938f-7c12-4cda-b45e-e79c2ad9c7e5.png)

<font style="color:rgb(77, 77, 77);">第四个if语句(包含语句前的内容)：将$_page进行URL解码之后重复之前的</font>![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732898678058-7e3e05ee-b197-4f11-8fef-24da185f700b.png)<font style="color:rgb(77, 77, 77);">处理步骤，如果$_page在白名单中存在，返回true。</font>

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732975699767-31dce89b-06c4-4a2a-b4c6-ac897f5e0678.png)

<font style="color:rgb(77, 77, 77);">如果上述条件都不满足，则输出"you can't see it"并返回false。</font>

<font style="color:rgb(77, 77, 77);">这就是函数的分析，我们只需要传入一个在白名单内的文件名（source.php或者hint.php），并添加上问号，这样可以保证每次找去用于检查的内容都在白名单，返回true。</font>

<font style="color:rgb(77, 77, 77);">并且我们当前的source.php一般是在html目录下，往上是www，var，然后到根目录，flag一般就放在根目录下面，这里还有一个hint.php?/或者source.php?/，因此需要返回四层才能到根目录并且</font><font style="color:rgb(48, 48, 48);">flag 是在 ffffllllaaaagggg 里的，</font><font style="color:rgb(77, 77, 77);">所以构造source.php?file=hint.php?/../../../../ffffllllaaaagggg即可得到falg</font>

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732953869865-a7711c0e-141a-43a7-8fb3-bc7acafb3131.png)

## 3.<font style="color:rgb(33, 37, 41);">[ACTF2020 新生赛]Include</font>
![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732954378529-15cecd79-06e6-45fa-b088-a9f4a5f61908.png)

看到这个题目，它给了tips，点开之后反问我<font style="color:rgb(0, 0, 0);">Can you find out the flag?</font>~~<font style="color:rgb(0, 0, 0);">卧艹，这能忍？来吧我已经迫不及待了!!!</font>~~

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732954378393-d92752a3-6ab0-4c53-a82f-6527e6f644a7.png)![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732954378381-cbbb2e5e-91db-4655-961a-ac023ddb980c.png)

和前面的思路一样，这个页面没有给任何有用的信息，所以看一下源代码，也没有什么有用的信息![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732954618823-f6824cfe-5d80-4d10-aea7-6342ec9eca7d.png)

正当我举足无措时，看了一下题目<font style="color:rgb(33, 37, 41);">[ACTF2020 新生赛]Include，include！！！</font>想到了以前写的笔记，flag大概率是被注释掉了，这里可能是要用到伪协议来显示注释的内容。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732955546382-5758b167-71ae-410c-9e26-bd845e693aba.png)



所以把file后面的内容换成php://filter/read=convert.base64-encode/resource=flag.php

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732956320196-a5bd1f1d-78f2-48d1-b5a4-4b1cb8639bc0.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732956271439-7d27d647-54aa-4561-9485-530f8a04f83e.png)

execute一下，出现一下内容，这显然这就是base64编码内容

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732956271430-e5b0384c-269f-489c-9c62-13fcbc568fbf.png)

解码之后就发现flag就是被注释掉了，拿falg提交完事

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732956506431-8c7fb8c7-6a3a-4ba3-bbac-2a313d361ba4.png)

## 4.<font style="color:rgb(33, 37, 41);">[NewStarCTF 2023 公开赛道]Begin of PHP</font>
![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732957803293-d267215c-eeab-4043-bdba-3378a4953619.png)

进入到题目里发现这里有一堆PHP代码

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732957849754-f870cb4e-0856-4111-8f85-9cea058c8af4.png)

分析代码：绕过<font style="color:rgb(0, 0, 0);">=Level 1=到=Level 5=就可输出flag，所以接下来就是绕过</font>

显然<font style="color:rgb(0, 0, 0);">=Level 1=</font>是md5绕过，之前的笔记有用啦！key1和key2原来的值不强等于而经过md5加密后的值弱相等，之后把$flag1赋值True，这里也可用数组绕过。![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732974442735-dfbe3275-d473-44d9-8d60-ec33fbe9b690.png)

所以参照上次写的笔记输入?key1=QNKCDZO&key2=240610708可得如下图所示的内容，说明绕过成功了，笔记是有用的，为自己鼓掌！！！

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732958829203-93227f1e-db5e-4ec0-af2f-321c10b540e6.png)

对于<font style="color:rgb(0, 0, 0);">=Level 2=，我们需要POST传参key3，出现了要md5密和sha1加密的内容强比较绕过，查了资料</font><font style="color:rgb(34, 34, 34);">sha1()函数和</font>md5<font style="color:rgb(34, 34, 34);">一样，都无法处理数组，如果传入的为数组，会返回NULL，所以就</font><font style="color:rgb(0, 0, 0);">数组绕过呗，试了试，就出现了以下内容，还真成功了，不愧是我。</font>![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732974465192-84cfa94b-7369-4840-8850-16ecc492087a.png)![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732959584400-658804cd-ead1-4858-a6d2-9a39bb99115d.png)

<font style="color:rgb(0, 0, 0);">=Level 3=的if是一开始是比较字符串的大小，要求是值为0，即两个字符串相等。但是后</font>面是file_get_contents函数，函数里放的是flag，我们不知道flag里的东西所以无法传入字符串，但是查了一下strcmp()函数的知识发现该函数依然无法操作数组，会返回0，所以GET参数key4为一个数组即key4[]=0,就绕过了![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732974480391-5778d845-3eb8-4dcc-83f6-26da25742bb0.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732968112955-35a1fe90-9d2e-4e98-a80f-97439e94ddd9.png)

<font style="color:rgb(0, 0, 0);">=Level 4= 的if是用的</font>is_numeric 函数来比较，它是用于检查一个变量是否是数字或数字字符串，<font style="color:rgb(77, 77, 77);">，是的话返回1，但是is_numeric()无法解析数组会返回false。</font>所以还是数组绕过,且数组的值大于2023，所以传入key5[]=2024绕过![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732974513576-0e792c87-2fa2-42d7-9da2-5272574cb1f8.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732973838669-614305f5-7af9-4fb2-b0f8-57af31f77599.png)

<font style="color:rgb(0, 0, 0);">=Level 5=的i</font><font style="color:rgb(0, 0, 0);">f，由</font><font style="color:rgb(51, 51, 51);">is_numeric() 函数不能匹配a-zA-Z0-9可知</font><font style="color:rgb(77, 77, 77);">这里要输入的POST内容不能是字母和数字，并且下一关只有flag5为真才输出flag，所以在这里需要给flag5赋值一个符号就行，给数组也行。</font>

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733045245412-04f283c6-1a3e-4a62-a138-1c4c13304116.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732975009403-21caa187-05cf-4882-b262-41837c46de85.png)

说实话，这道题从<font style="color:rgb(0, 0, 0);">=Level 1=到=Level 5=</font>也确实都可以使用数组绕过。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732975135750-eb38bf12-7a7f-4a8f-bfab-987ad6895a5d.png)

提交flag，游戏结束。

## 5.<font style="color:rgb(33, 37, 41);">[极客大挑战 2019]PHP</font>
![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733047357591-9be85885-17ed-478d-9ac9-cd4287551d32.png)

进去是一只可爱的猫猫，随着鼠标的移动，那个球也在移动，当球靠近猫猫时，猫猫还在布拉球，真是卡哇伊

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733047381419-1a8adf60-a6be-492d-b469-3bed373e38fb.png)

页面上没有什么信息，我的思路是先到元素和网页源代码看看有没有什么有用的信息![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733062959530-900f8a51-30ed-4d5f-8474-31f6705c427f.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733062693535-878d9200-59b9-451a-a0c1-3a359daa72fa.png)

下面是几个网址，看了一下，都是一堆代码，仔细看也没有关键信息，猜了一下，这大概是页面猫猫的代码吧

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733062736257-fef954cb-b4ca-43c8-af48-602d6abc5777.png)

即使有高亮部分也是注释或者其他的与题目无关的代码

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733063028477-c1f5148b-342a-4c54-846b-4729cc9900e0.png)

这道题一开始确实是没有思路，但是页面上的这句话”<font style="color:#74B602;">因为每次猫猫都在我键盘上乱跳，所以我有一个良好的备份网站的习惯</font><font style="color:rgb(0, 0, 0);">“</font>帮我打开了一下思路，查了查网站备份的相关知识

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733047819851-60d054db-f768-47bf-81db-64b53e8518e4.png)

所以我猜测flag应该是藏在了某个文件里了，我是从zip开始尝试的，毕竟zip是压缩包的后缀，比较熟悉的

在这里输入web.zip、website.zip、zipbackup.zip，back.zip都不行

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733063849858-2be289f8-a515-4fd1-a37a-02210d1ee735.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733063864694-b99e5fd4-0f36-48f6-a396-5298463e72dc.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733063808308-e1e7a84a-1842-4ed7-b2cd-22eaf99b1add.png)

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733063809578-cc020234-7d75-4962-b83a-e50c4604df9a.png)

到了www.zip试了一下，结果下载了一个压缩包，说明方向是正确的，网站备份文件就找到了，flag肯定就藏在里面

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733048235914-19e60206-4dc8-4206-82a4-1f6d5e4d4625.png)![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733048285085-88873da1-f8c2-46ee-84e5-e75573919a5b.png)

解压后是这样的，有flag.php，打开后的东西如下图所示，wc，dog？我要的是cat，这肯定是假的flag,

~~ 真狗，666~~，直接删了。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733048401573-69d04688-6da1-4905-ac56-d39a8f8121d1.png)

也找了其他的文件，最后在class.php这里找到了flag。<font style="color:rgb(77, 77, 77);">在这个里面我们可以知道如果password不等于100则接下来会执行到die退出程序，如果username不等于admin则会直接绕过flag执行输出”hello my friend~~sorry i can't give you the flag!“只有username=admin，password=100，才可拿到flag。</font>

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733048700721-e7d868e2-8b42-4c45-a085-a148a5c15c2d.png)

仔细分析一下代码：这里一开始是包含flag.php的，然后有一个类，两个私有变量$username，$password。之后构造函数建立了一个一 一对应的关系，wakeup会把username换成guest。所以username在wakeup函数那里就会变为guest就不可能是admin，所以我们的目标是绕过这个wakeup函数。查了一下资料，<font style="color:rgb(77, 77, 77);">一般做CTF题目时绕过wakeup的方法就是：先序列化字符串，然后使</font>**<font style="color:rgb(77, 77, 77);">序列化后</font>**<font style="color:rgb(77, 77, 77);">字符串中属性的个数大于真实对象中属性的个数，即可绕过wakeup魔术方法。</font>

所以写代码来序列化它一下(因为<font style="color:rgb(77, 77, 77);">username=admin，password=100，所以Name里的两个参数分别为'admin'、100</font>)。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733070746957-3e9f992e-c809-461d-902c-7a27d1379dac.png)

序列化的结果如下

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733070746781-d4998406-3c45-46d9-a4b6-bbd6a5796a01.png)

<font style="color:rgb(77, 77, 77);">因为序列化后字符串中属性的个数大于真实对象中属性的个数，即可绕过wakeup，</font>所以要把

”<font style="color:rgb(0, 0, 0);">O:4:"Name":</font><font style="color:#DF2A3F;">2</font><font style="color:#000000;">:</font><font style="color:rgb(0, 0, 0);">{s:14:"Nameusername";s:5:"admin";s:14:"Namepassword";i:100;}“中"Name":后面的</font><font style="color:#DF2A3F;">2</font><font style="color:rgb(0, 0, 0);">改为比2大的数（我用的是3）即可,注意空字符！！！(我在这里卡了半小时才发现问题)。所以修改后的序列化的字符如下：</font>

<font style="color:rgb(0, 0, 0);">O:4:"Name"</font><font style="color:#000000;">:</font><font style="color:#DF2A3F;">3</font><font style="color:rgb(0, 0, 0);">:{s:14:"%00Name%00username";s:5:"admin";s:14:"%00Name%00password";i:100;}</font>

其他文件也是要看一眼的，在index.php这里找到了PHP代码，知道了这是通过select来GET传参。![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733048783125-1d33677f-3d04-48ec-943d-a5a194d81b2d.png)

所以，提交

?select=O:4:"Name":3:{s:14:"%00Name%00username";s:5:"admin";s:14:"%00Name%00password";i:100;}

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733072348469-3b470e55-6ba0-4405-9648-278146c165af.png)

然后，flag就出来了，提交完事。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1733050002247-de8cb6f1-11b2-40e8-92a4-1bf7d2cf13b9.png)

这一周先写到这里啦，这一周又是改视频又是密码技术决赛志愿者，太累了，休息一下啦




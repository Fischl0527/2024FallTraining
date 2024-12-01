**BaseCTF2024新生赛复现 week1 4~6**

本次复现题目为**upload、md5绕过欸**、**Aura 酱的礼物**

复现这些题目时我是跟着这个视频一步一步来的:

<u><font style="color:rgb(0,0,255);"></font></u>[<u>https://www.bilibili.com/video/BV19wWEeoE1o/share_source=copy_web&vd_source=26a21a8ac3f19fd0d663fb58dee41081</u>](https://www.bilibili.com/video/BV19wWEeoE1o/?share_source=copy_web&vd_source=26a21a8ac3f19fd0d663fb58dee41081)

# 一、upload
![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1731851710813-826e7242-c871-4115-9469-bb417e479693.png)![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1731851710890-95965788-2a59-466e-a96d-06c26625475a.png)

upload是一个无过滤的一种文件上传，解这道题需要一句话木马  **<?php eval($_POST[0]);  **

意思是直接把POST的参数里的0传到eval函数里面。

**<?php **表示这是个文件的开头，说明后面的所有内容都是PHP的代码。

**eval()** 函数表示要动态执行。

**POST** 是获取到一些POST的信息。

**0** 表示要获取POST参数的0参数传到eval()函数里面。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1731851850359-7a75a2e7-1026-4dad-a99a-64b1a8b0adac.png)

之后直接上传一句话木马，可以看到它后端的逻辑，就是把所有的文件移动到upload文件夹下面，然后获取它原本的文件名，之后把他拼接起来，把我们的文件给他放在那。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1731852459201-9e0ac43b-e6e8-4145-8830-fb05ea59fd2b.png)![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1731852460704-dae9dc09-3ebd-4c8c-bd94-8a0689658485.png)

所以我们刚刚上传的文件就在upload的文件名eval这里，访问它就是空白页面

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1731852923679-1eb587a8-11cd-41d1-a387-dcd8729d703c.png)

之后打开HackBar，手动用system构造eval，然后单引号里输入cat /flag,再传递就行了，得到flag提交。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1731853038676-f1b1ed4b-fac4-4dc9-9948-1fe2f14afdca.png)



# 二、md5绕过欸
![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732346205513-226477c0-4973-4d43-9e1b-2824847485a8.png)

进去后发现这一串代码：

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732346244928-0994455a-981e-458f-a03f-c98d0a444738.png)

该题目考的是php弱比较



关于php弱比较：

php是一种弱类型语言，对数据的类型要求并不严格，可以让数据类型互相转换。

在php中有两种比较符号: 一种是 ==，另外一种是 ===，都是用来比较两个数值是否相等的操作符，但他们也是有区别的:

== ：弱等于。在比较前会先把两种字符串类型转成相同的再进行比较。简单的说，它不会比较变量类型，只比较值。至于怎么转换后续会再赘述。

=== ：强等于。在比较前会先判断两种字符串类型是否相同再进行比较，如果类型不同直接返回不相等。既比较值也比较类型。

当要比较的两种字符串的类型相同时，== 和 === 是相等的。



PHP转换规则：

若一个数字和一个字符串进行比较或者进行运算时，PHP会把字符串转换成数字再进行比较。若字符串以数字开头，则取开头数字作为转换结果，不能转换为数字的字符串（例如"aaa"是不能转换为数字的字符串，而"123"或"123aa"就是可以转换为数字的字符串）或null，则转换为0；

数字和“e"开头加上数字的字符串（例如"1e123”）会当作科学计数法去比较；0e在比较的时候会将其视作为科学计数法，所以无论0e后面是什么，0的多少次方还是0；

当字符串被当作一个数值来处理时，如果该字符串没有包含’<font style="color:#DF2A3F;">.</font>’,‘<font style="color:#DF2A3F;">e</font>’和<font style="color:#DF2A3F;">'E</font>’并且其数值在整形的范围之内，该字符串作为int来取值，其他所有情况下都被作为float来取值，并且字符串开始部分决定它的取值，开始部分为数字，则其值就是开始的数字，否则，其值为0。



原文链接：[https://blog.csdn.net/qq_45671431/article/details/105456684](https://blog.csdn.net/qq_45671431/article/details/105456684)



关于MD5：

<font style="color:rgb(51, 51, 51);">MD5信息</font>[<font style="color:rgb(51, 51, 51);">摘要算法</font>](https://baike.baidu.com/item/%E6%91%98%E8%A6%81%E7%AE%97%E6%B3%95/12011257?fromModule=lemma_inlink)<font style="color:rgb(51, 51, 51);">（英语：MD5 Message-Digest Algorithm），一种被广泛使用的</font>[<font style="color:rgb(51, 51, 51);">密码散列函数</font>](https://baike.baidu.com/item/%E5%AF%86%E7%A0%81%E6%95%A3%E5%88%97%E5%87%BD%E6%95%B0/14937715?fromModule=lemma_inlink)<font style="color:rgb(51, 51, 51);">，可以产生出一个128位（16字节）的</font>[<font style="color:rgb(51, 51, 51);">散列值</font>](https://baike.baidu.com/item/%E6%95%A3%E5%88%97%E5%80%BC/10398613?fromModule=lemma_inlink)<font style="color:rgb(51, 51, 51);">（hash value），用于确保</font>[<font style="color:rgb(51, 51, 51);">信息传输</font>](https://baike.baidu.com/item/%E4%BF%A1%E6%81%AF%E4%BC%A0%E8%BE%93/9897864?fromModule=lemma_inlink)<font style="color:rgb(51, 51, 51);">完整一致。MD5由美国密码学家</font>[<font style="color:rgb(51, 51, 51);">罗纳德·李维斯特</font>](https://baike.baidu.com/item/%E7%BD%97%E7%BA%B3%E5%BE%B7%C2%B7%E6%9D%8E%E7%BB%B4%E6%96%AF%E7%89%B9/700199?fromModule=lemma_inlink)<font style="color:rgb(51, 51, 51);">（Ronald Linn Rivest）设计，于1992年公开，用以取代</font>[<font style="color:rgb(51, 51, 51);">MD4</font>](https://baike.baidu.com/item/MD4/8090275?fromModule=lemma_inlink)<font style="color:rgb(51, 51, 51);">算法。这套算法的程序在 RFC 1321 标准中被加以规范。1996年后该算法被证实存在弱点，可以被加以破解，对于需要高度安全性的数据，专家一般建议改用其他算法，如</font>[<font style="color:rgb(51, 51, 51);">SHA-2</font>](https://baike.baidu.com/item/SHA-2/22718180?fromModule=lemma_inlink)<font style="color:rgb(51, 51, 51);">。2004年，证实MD5算法无法防止碰撞（</font>[<font style="color:rgb(51, 51, 51);">collision</font>](https://baike.baidu.com/item/collision/19660439?fromModule=lemma_inlink)<font style="color:rgb(51, 51, 51);">），因此不适用于安全性认证，如</font>[<font style="color:rgb(51, 51, 51);">SSL</font>](https://baike.baidu.com/item/SSL/320778?fromModule=lemma_inlink)<font style="color:rgb(51, 51, 51);">公开</font>[<font style="color:rgb(51, 51, 51);">密钥认证</font>](https://baike.baidu.com/item/%E5%AF%86%E9%92%A5%E8%AE%A4%E8%AF%81/9882212?fromModule=lemma_inlink)<font style="color:rgb(51, 51, 51);">或是</font>[<font style="color:rgb(51, 51, 51);">数字签名</font>](https://baike.baidu.com/item/%E6%95%B0%E5%AD%97%E7%AD%BE%E5%90%8D/212550?fromModule=lemma_inlink)<font style="color:rgb(51, 51, 51);">等用途。</font>

<font style="color:rgb(51, 51, 51);"></font>

关于echo:

<font style="color:rgb(77, 77, 77);">echo是一个至关重要的语言结构，它负责在浏览器中输出一个或多个字符串。</font>



代码复制到Visual Studio Code

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732346585045-2382e03c-04fd-4a87-bdad-54c367bf881a.png)

先分析代码：它是先引用了'flag.php'，之后是要传入GET参数的name、name2和post参数里面的passward、password2。在下面的判断中如果name不弱等于passward并且他们的md5值弱等于，就进入下一个判断，否则输出"错啦错啦"。在第二次的判断中如果name2不强等于passward2并且name2和passward2的md5值强等于，就输出flag，否则输出"再看看啊，马上绕过嘞！"



思路：这道题用md5绕过，弱比较可以使用数组或是以下md5后开头为0e的字符串任意两个来绕过：

1.  QNKCDZO
2.  240610708
3.  s878926199a
4.  s155964671a
5.  s214587387a
6.  0e215962017

因为在php中0e字符串都会被弱转换成0，所以这些字符原本是不一样的，但是经过md5转换后弱转换成一样的了，这样就算是绕过了。

强弱比较都可以直接用数组绕过，原理是：md5只针对的是字符串来进行处理，如果传入的其他的类型比如是数组，这时候就会返回一个null，同时会报错表示其不能对数组进行处理。所以他们数组的内容本来是不一致的，但是它们md5传回来都是null，是一样的，所以就算是绕过了。



所以在页面中打开KackBar传入name、name2、password和password2的对应的值就行了，值的内容如下：

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732349756713-7a94b59e-a331-4483-8845-338b67752a94.png)

此时flag就出现了，提交即可。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732349756849-229c1c14-cb79-449d-82cc-d1aadb87370a.png)![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732349756762-cfacd25f-78a5-4d6e-a661-d7985572da89.png)

# 三、Aura 酱的礼物
![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732350166790-a0a66c81-3131-4178-958c-20d02d25021b.png)

该题目说有推荐搜索关键词: 伪协议，SSRF，查了一下

<font style="color:rgb(77, 77, 77);"></font>

<font style="color:rgb(77, 77, 77);">关于伪协议：</font>

<font style="color:rgb(77, 77, 77);">伪协议包含：file:// 、 data:// 、 phar:// 、 php:// 、 gopher:// 、dict://等。PHP 带有很多内置 URL 风格的封装协议，可用于类似 </font>[fopen](https://so.csdn.net/so/search?q=fopen&spm=1001.2101.3001.7020)<font style="color:rgb(77, 77, 77);">()、 copy()、 file_exists() 和 filesize() 的文件系统函数。 除了这些封装协议，还能通过stream_wrapper_register() 来注册自定义的封装协议。伪协议常常用于文件包含漏洞之中。在php中能够造成文件包含的函数有include、require、include_once、require_once、highlight_file、show_source、file_get_contents、fopen、file、readfile。</font>

<font style="color:rgb(77, 77, 77);"></font>

<font style="color:rgb(77, 77, 77);">php支持的伪协议：</font>

<font style="color:rgb(77, 77, 77);">1 file:// — 访问本地文件系统</font>

<font style="color:rgb(77, 77, 77);">2 http:// — 访问 HTTP(s) 网址</font>

<font style="color:rgb(77, 77, 77);">3 ftp:// — 访问 FTP(s) URLs</font>

<font style="color:rgb(77, 77, 77);">4 php:// — 访问各个输入/输出流（I/O streams）</font>

<font style="color:rgb(77, 77, 77);">5 zlib:// — 压缩流</font>

<font style="color:rgb(77, 77, 77);">6 data:// — 数据（RFC 2397）</font>

<font style="color:rgb(77, 77, 77);">7 glob:// — 查找匹配的文件路径模式</font>

<font style="color:rgb(77, 77, 77);">8 phar:// — PHP 归档</font>

<font style="color:rgb(77, 77, 77);">9 ssh2:// — Secure Shell 2</font>

<font style="color:rgb(77, 77, 77);">10 rar:// — RAR</font>

<font style="color:rgb(77, 77, 77);">11 ogg:// — 音频流</font>

<font style="color:rgb(77, 77, 77);">12 expect:// — 处理交互式的流</font>



<font style="color:rgba(0, 0, 0, 0.75);">fill://：</font>

<font style="color:rgb(77, 77, 77);">用于访问本地文件系统，并且不受allow_url_fopen，allow_url_include影响</font><font style="color:rgba(0, 0, 0, 0.75);">，</font><font style="color:rgb(77, 77, 77);">file://协议主要用于访问文件(绝对路径、相对路径以及网络路径)，比如：http://www.xx.comfile=file:///etc/passsword</font>

<font style="color:rgba(0, 0, 0, 0.75);"></font>

<font style="color:rgba(0, 0, 0, 0.75);">data://：</font>

<font style="color:rgba(0, 0, 0, 0.75);">是数据流封装器，和php://相似，都是利用了流的概念，将原本的include的文件流重定向到了用户可控制</font>的输入流中，简单来说就是执行文件的包含方法包含了你的输入流，通过包含你输入的payload来实现目的。它可以让用户来控制输入流，当它与包含函数结合时，用户输入的data://流会被当作php文件执行。

示例用法：

1、data://text/plain,

http://127.0.0.1/include.php?file=data://text/plain,<?php%20phpinfo();?> 

2、data://text/plain;base64,

http://127.0.0.1/include.php?file=data://text/plain;base64,PD9waHAgcGhwaW5mbygpOz8%2b



php://filter：

php://filter 是一种元封装器， 设计用于数据流打开时的筛选过滤应用。 这对于一体式（all-in-one）的文件函数非常有用，类似 readfile()、 file() 和 file_get_contents()， 在数据流内容读取之前没有机会应用其他过滤器。简单通俗的说，这是一个中间件，在读入或写入数据的时候对数据进行处理后输出的一个过程。resource=<要过滤的数据流>这个参数是必须的。它指定了你要筛选过滤的数据流。



关于SSRF：

<font style="color:rgb(77, 77, 77);">一、SSRF是什么？</font>

<font style="color:rgb(77, 77, 77);">SSRF(Server-Side Request Forgery:服务器端请求伪造) 是一种由攻击者构造形成由服务端发起请求的一个安全漏洞。一般情况下，SSRF攻击的目标是从外网无法访问的内部系统。（正是因为它是由服务端发起的，所以它能够请求到与它相连而与外网隔离的内部系统）</font>

<font style="color:rgb(77, 77, 77);"></font>

<font style="color:rgb(77, 77, 77);">二、SSRF漏洞原理</font>

<font style="color:rgb(77, 77, 77);">SSRF 形成的原因大都是由于服务端提供了从其他服务器应用获取数据的功能且没有对目标地址做过滤与限制。</font>

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732350521482-c3fdd896-7ad7-42e1-92e7-8f3cfe94e318.png)

<font style="color:rgb(77, 77, 77);">比如,黑客操作服务端从指定URL地址获取网页文本内容，加载指定地址的图片，下载等等。利用的是服务端的请求伪造。ssrf是利用存在缺陷的web应用作为代理攻击远程和本地的服务器。</font>



<font style="color:rgb(77, 77, 77);">SSRF攻击可能存在任何语言编写的应用，接下来将举例</font><font style="color:rgb(0, 0, 0);">php</font><font style="color:rgb(77, 77, 77);">中可能存在SSRF漏洞的函数。</font>

<font style="color:rgb(77, 77, 77);">1.file_get_contents</font>

<font style="color:rgb(77, 77, 77);">2.sockopen()</font>

<font style="color:rgb(77, 77, 77);">3.curl_exec()</font>

<font style="color:rgb(77, 77, 77);"></font>

<font style="color:rgb(77, 77, 77);">参考文章：</font>[https://blog.csdn.net/qq_43378996/article/details/124050308](https://blog.csdn.net/qq_43378996/article/details/124050308)



关于本题要用到的URL格式：

URL 的格式为 scheme://user:password@address:port/path?query#fragment

scheme：表示当前是什么协议

user:password：表示我要拿什么用户密码来验证

@后面address：表示跟上路径地址

port：表示端口号，也就是靶机

path：路径

?后面的query：表示get参数

#后面的fragment：#后面的内容是不会穿给服务端的，是传给前端进行解析



关于<font style="color:rgb(0, 0, 0);">strpos() 函数：</font>

<font style="color:rgb(0, 0, 0);">strpos() 函数查找字符串在另一字符串中第一次出现的位置。</font><font style="color:rgb(0, 0, 0);">返回字符串在另一字符串中第一次出现的位置，如果没有找到字符串则返回 FALSE。</font>

<font style="color:rgb(0, 0, 0);"></font>

关于include()<font style="color:rgb(0, 0, 0);">函数：</font>

PHP的include函数用于在一个文件中包含另一个文件的内容<font style="color:rgb(17, 17, 17);">。</font>它可以用于创建可在多个页面重复使用的函数、页眉、页脚或元素。include语句会获取指定文件中存在的所有文本、代码或标记，并复制到使用include语句的文件中。与之类似的是require函数，它也用于包含其他文件的内容，但require只处理一次，而include每次都要进行读取和评估

<font style="color:rgb(0, 0, 0);"></font>

关于127.0.0.1 IP地址

首先我们要先知道一个概念，凡是以`127`开头的IP地址，都是回环地址（Loop back address），其所在的回环接口一般被理解为虚拟网卡，并不是真正的路由器接口。

所谓的回环地址，通俗的讲，就是我们在主机上发送给127开头的IP地址的数据包会被发送的主机自己接收，根本传不出去，外部设备也无法通过回环地址访问到本机。

而127.0.0.1作为{127}集合中的一员，当然也是个回环地址。只不过127.0.0.1经常被默认配置为localhost的IP地址。  
一般会通过ping 127.0.0.1来测试某台机器上的网络设备是否工作正常。



进入到题目中发现

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732351707464-0e3e9245-c1e3-4660-923a-f4186abe9fbe.png)、

<font style="color:#000000;">分析代码：</font>

<font style="color:#000000;">只有中间的 </font><font style="color:#000000;">file_get_contents</font><font style="color:#000000;">(</font><font style="color:#000000;">$pen</font><font style="color:#000000;">) == </font><font style="color:#000000;">'Aura' </font><font style="color:#000000;">才可绕过第一个</font>

<font style="color:#000000;">只有 </font><font style="color:#000000;">strpos</font><font style="color:#000000;">(</font><font style="color:#000000;">$challenge</font><font style="color:#000000;">, </font><font style="color:#000000;">'http://jasmineaura.github.io'</font><font style="color:#000000;">) == </font><font style="color:#000000;">0 </font><font style="color:#000000;">也就是challenge=http://jasmineaura.github.io才可绕过第二个</font>

<font style="color:#000000;">只有</font><font style="color:#000000;"> strpos</font><font style="color:#000000;">(</font><font style="color:#000000;">$blog_content</font><font style="color:#000000;">, </font><font style="color:#000000;">'已经收到Kengwang的礼物啦'</font><font style="color:#000000;">) !== </font><font style="color:#000000;">false</font><font style="color:#000000;"> ，也就是读出”</font><font style="color:#000000;">已经收到Kengwang的礼物啦</font><font style="color:#000000;">“才可绕过第三个</font>

<font style="color:#000000;"></font>

<font style="color:#000000;">首先对于第一个判断, 他需要读取一个</font>文件后内容是Aura,我们可以尝试通过data://伪协议来进行读取在文件读取的情况下, 利用 data:// 伪协议:

data://text/plain,一串内容                       可以读取出 一串内容

data://text/plain;base64,xxxxxxxx           其中 xxxxxxx 会被 Base64 解码后再读取出内容  


所以我们此处可以使用:“pen=data://text/plain,Aura“来进行绕过

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732352894474-9e2dae12-551f-4686-b745-a1a2cb311dff.png)

上传一下发现已经绕过成功了

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732352975779-1a51c0bc-35ac-469b-b379-c67dcb7ea4ad.png)

想要绕过下一个可以利用这个get参数让challenge=http://jasmineaura.github.io

即在后面&加上challenge=http://jasmineaura.github.io就行了

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732355046618-330e9d84-c908-4c74-9903-bcc6184d5989.png)![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732355046614-e16962a5-9005-4677-a0dc-83e3c6a1c5a9.png)

此时可以在前面加上@，前面的jasmineaura.github.io表示为用户和密码，密码可以为空。@后面跟上真实的路径，真实的路径可以为自己的服务器，在自己的服务器写下这个页面，也可以利用之前的题目的靶机来写，也可以用当前的页面，因为当前页面有这个内容的。

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732356226422-343b9796-ef31-4af0-9427-51f0bb0d20f1.png)

所以直接可以@127.0.0.1获取当前页面这样的花就可以进行绕过

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732356612379-40b36c3b-8644-4561-8b0a-67570043caa1.png)

可以发现”请去博客里面写下感想哦~"已经没有了说明已经绕过成功了



最后就是gift，include函数会解析文件里的php标签，而flag写在了注释的位置，所以这里需要将其伪协议和过滤器来进行 base64 编码后输出

php://格式为：php://filter/convert.base64-encode/resource=

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732357452464-3cf9b5db-20e9-4d1c-b7b4-704852365011.png)![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732357452537-90191b83-82bc-454c-b142-2f918f34d28a.png)

最后用base64解码，就解出来了

![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732357784745-51abd99d-fe2d-4c7e-b797-6f80241d3956.png)![](https://cdn.nlark.com/yuque/0/2024/png/50616406/1732357784743-ac94cca3-544a-41c3-80cc-ff70e71a48eb.png)



这样BaseCTF2024新生赛复现week1就算是做完了，休息一下咯




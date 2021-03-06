# 				Openssl 编程
​	OpenSSL实现了SSL协议的SSLv2和SSLv3，支持了其中绝大部分算法协议。OpenSSL也实现了TLSv1.0，TLS是SSLv3的标准化版，虽然区别不大，但毕竟有很多细节不尽相同。

​	虽然已经有众多的软件实现了OpenSSL的功能，但是OpenSSL里面实现的SSL协议能够让我们对SSL协议有一个更加清楚的认识，因为至少存在两点：一是OpenSSL实现的SSL协议是开放源代码的，我们可以追究SSL协议实现的每一个细节；二是OpenSSL实现的SSL协议是纯粹的SSL协议，没有跟其它协议（如HTTP）协议结合在一起，澄清了SSL协议的本来面目。

### 对称加密

​	OpenSSL一共提供了8种对称加密算法，其中7种是分组加密算法，仅有的一种流加密算法是RC4。这7种分组加密算法分别是AES、DES、Blowfish、CAST、IDEA、RC2、RC5，都支持电子密码本模式（ECB）、加密分组链接模式（CBC）、加密反馈模式（CFB）和输出反馈模式（OFB）四种常用的分组密码加密模式。其中，AES使用的加密反馈模式（CFB）和输出反馈模式（OFB）分组长度是128位，其它算法使用的则是64位。事实上，DES算法里面不仅仅是常用的DES算法，还支持三个密钥和两个密钥3DES算法。

### 非对称加密

​	OpenSSL一共实现了4种非对称加密算法，包括DH算法、RSA算法、DSA算法和椭圆曲线算法（EC）。DH算法一般用于密钥交换。RSA算法既可以用于密钥交换，也可以用于数字签名，当然，如果你能够忍受其缓慢的速度，那么也可以用于数据加密。DSA算法则一般只用于数字签名。

### 信息摘要

​	OpenSSL实现了5种信息摘要算法，分别是MD2、MD5、MDC2、SHA（SHA1）和RIPEMD。SHA算法事实上包括了SHA和SHA1两种信息摘要算法。此外，OpenSSL还实现了DSS标准中规定的两种信息摘要算法DSS和DSS1。

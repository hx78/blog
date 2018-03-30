## 深入理解Java注解类型(@Annotation) https://blog.csdn.net/javazejian/article/details/71860633

## java 中 char 和 byte 的区别 https://www.jianshu.com/p/13cda4b7305d
char 是字符，byte 是字节，都可以强制转换为一个整数。(char 强制转换为整数表示 这个字符对应的  Unicode 码的位置)

char 是无符号型的，大小范围为 0 -66535 （对应的 Unicode 码位置）

byte 是字节 ，有符号型的，大小范围是  -128-127  

char 可以表示中文，因为Unicode编码中包含了中文

byte 不可以表示中文。

char 转换为 byte，

> char t = '中';

> CharBuffer cb = CharBuffer.allocate(1);

> cb.put(t);

> cb.flip();

> ByteBuffer bb = Charset.forName("utf-8").encode(cb);

> byte [] b = bb.array();

转换后的byte长度，随字符编码不同而不同。

utf-8 编码 ：英文字母转byte 后占1个字节长度，中文占3个字节长度

gbk 编码：无论英文，中文都占2个字节长度

作者：坚强一点
链接：https://www.jianshu.com/p/13cda4b7305d
來源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。


## Java IO：byte[]、char[]、String三种对象的转换 http://huaxia524151.iteye.com/blog/786651
String与byte[]对象进行转换时应指定编码格式，否则有潜在的乱码问题。byte[] b = s.getBytes("utf-8"); String s = new String(b,"utf-8");
 
 Java的IO库提供了专门的管道来对这3个对象进行读写，他们是StringReader/Writer   CharArrayReader/Writer   ByteAyyayInputStream/OutputStream。String可以方便地转换成char[]或byte[]，因此可以将String当作是char[]和byte[]转换的桥梁，此外，Java IO库还专门提供了InputStreamReader类来将byte[]转换成char[]。
        

下述密码均摘自互联网

【字母表顺序】-数字 
　　加密的时候，经常要把A~Z这26个字母转换成数字，最常见的一种方法就是取字母表中的数字序号。A代表1，B代表2，C代表3... 

　　字母 A B C D E F G H I J K L M N O P Q R S T U V W X Y Z 
　　数字 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 

【进制转换密码】 
　　例如二进制：1110 10101 1101 10 101 10010 1111 1110 101 
　　转为十进制：14 21 13 2 5 18 15 14 5 
　　对应字母表：number 

【Mod算法】 
　　我们可以对字母序号进行数学运算，然后把所得的结果作为密文。当运算结果大于26或小于1的时候，
　　我们希望把这个数值转为1~26的范围，那么取这个数除以26的余数即可。
　　Mod就是求余数的运算符，有时也用“%”表示。例如 29 Mod 26 = 3，或写成 29 % 26 = 3，意思是29除以26的余数是3。 

【倒序】 
　　加密时为经常要对字符进行倒序处理。如果让你按abcdef...的顺序背出字母表的每个字母会很容易，
　　但是如果是zyxwvu...的顺序那就很难背出来了。一个很熟悉的单词，如果按相反的顺序拼写，可能就会感到很陌生。 

　　例如“love”字母倒过来拼就是“evol”。 

　　具体加密时倒序有很多种方案，需要灵活运用。例如： 

　　每个单词的倒序：siht si a tset - this is a test 
　　整句的倒序：tset a si siht - this is a test 
　　数字的倒序：02 50 91 02 - 20 05 19 20(test) 

【间隔】 
　　单词之间的间隔一般使用空格。在加密时常常要去掉空格，但有时某些字母或数字来替代空格也不失为一种好的加密方案。
　　错误空格位置也会起到很强的误导作用。 

　　例如：t hi sis at est - this is a test 

【字母频率】 
　　频率分析法可以有效的破解单字母替换密码。 

　　关于词频问题的密码，我在这里提供英文字母的出现频率给大家，其中数字全部是出现的百分比： 
　　a 8.2 b 1.5 c 2.8 d 4.3 
　　e 12.7 f 2.2 g 2.0 h 6.1 
　　i 7.0 j 0.2 k 0.8 l 4.0 
　　m 2.4 n 6.7 o 7.5 p 1.9 
　　q 0.1 r 6.0 s 6.3 t 9.1 
　　u 2.8 v 1.0 w 2.4 x 0.2 
　　y 2.0 z 0.1 

　　词频法其实就是计算各个字母在文章中的出现频率，然后大概猜测出明码表，最后验证自己的推算是否正确。
　　这种方法由于要统计字母出现频率，需要花费时间较长。参考《跳舞的小人》和《金甲虫》。 

【凯撒密码(Caesar Shifts, Simple Shift)】 

　　也称凯撒移位，是最简单的加密方法之一，相传是古罗马恺撒大帝用来保护重要军情的加密系统，它是一种替代密码。 

　　加密公式：密文 = (明文 + 位移数) Mod 26 
　　解密公式：明文 = (密文 - 位移数) Mod 26 

　　以《数字城堡》中的一组密码为例： 

　　HL FKZC VD LDS 

　　只需把每个字母都按字母表中的顺序依次后移一个字母即可——A变成B，B就成了C，依此类推。因此明文为： 

　　IM GLAD WE MET 

　　英文字母的移位以移25位为一个循环，移26位等于没有移位。所以可以用穷举法列出所有可能的组合。 

　　例如：phhw ph diwhu wkh wrjd sduwb 

　　利用电脑可以方便地列出所有组合，然后从中选出有意义的话： 

　　qiix qi ejxiv xli xske tevxc 
　　rjjy rj fkyjw ymj ytlf ufwyd 
　　skkz sk glzkx znk zumg vgxze 
　　tlla tl hmaly aol avnh whyaf 
　　ummb um inbmz bpm bwoi xizbg 
　　vnnc vn jocna cqn cxpj yjach 
　　wood wo kpdob dro dyqk zkbdi 
　　xppe xp lqepc esp ezrl alcej 
　　yqqf yq mrfqd ftq fasm bmdfk 
　　zrrg zr nsgre gur gbtn cnegl 
　　assh as othsf hvs hcuo dofhm 
　　btti bt puitg iwt idvp epgin 
　　cuuj cu qvjuh jxu jewq fqhjo 
　　dvvk dv rwkvi kyv kfxr grikp 
　　ewwl ew sxlwj lzw lgys hsjlq 
　　fxxm fx tymxk max mhzt itkmr 
　　gyyn gy uznyl nby niau julns 
　　hzzo hz vaozm ocz ojbv kvmot 
　　iaap ia wbpan pda pkcw lwnpu 
　　jbbq jb xcqbo qeb qldx mxoqv 
　　kccr kc ydrcp rfc rmey nyprw 
　　ldds ld zesdq sgd snfz ozqsx 
　　meet me after the toga party <- 
　　nffu nf bgufs uif uphb qbsuz 
　　oggv og chvgt vjg vqic rctva 

　　可知明文为：meet me after the toga party 

------------------------------------------------------------------------- 

【凯撒移位(中文版)】 

　　就是按照中文字在Unicode编码表中的顺序进行移位，可以用来加密中文的信息。 

　　例：[中文凯撒移位] 
　　转换成Unicode编码：中文凯撒移位 
　　移1位后成为： 丮斈凰撓秼低 
　　转换成中文：[丮斈凰挠秼低] 

【栅栏密码(The Rail-Fence Cipher)】 

　　也称栅栏易位(Columnar Transposition)，即把将要传递的信息中的字母交替排成上下两行，
　　再将下面一行字母排在上面一行的后边，从而形成一段密码。栅栏密码是一种置换密码。 

　　例如密文：TEOGSDYUTAENNHLNETAMSHVAED 

　　解密过程：先将密文分为两行 

　　T E O G S D Y U T A E N N 
　　H L N E T A M S H V A E D 

　　再按上下上下的顺序组合成一句话 

　　THE LONGEST DAY MUST HAVE AN END. 

　　............................................................. 
　　加密时不一定非用两栏，还是举《数字城堡》中的一个例子，密文为： 

　　PFEE SESN RETM MFHA IRWE OOIG MEEN NRMA ENET SHAS DCNS IIAA IEER BRNK FBLE LODI 

　　去掉空格：PFEESESNRETMMFHAIRWEOOIGMEENNRMAENETSHASDCNSIIAAIEERBRNKFBLELODI 

　　共64个字符，以8个字符为一栏，排列成8*8的方阵(凯撒方阵)： 

　　P F E E S E S N 
　　R E T M M F H A 
　　I R W E O O I G 
　　M E E N N R M A 
　　E N E T S H A S 
　　D C N S I I A A 
　　I E E R B R N K 
　　F B L E L O D I 

　　从上向下竖着读：PRIMEDIFFERENCEBETWEENELEMENTSRESMONSIBLEFORHIROSHIMAANDNAGASAKI 

　　插入空格：PRIME DIFFERENCE BETWEEN ELEMENTS RESMONSIBLE FOR HIROSHIMA AND NAGASAKI (广岛和长崎的原子弹轰炸的最主要区别) 

　　............................................................. 
　　栅栏密码也可以用于中文，不过比较容易破解。 

　　明文： 这是中文的栅栏密码 
　　密文(3*3方阵)：这文栏是的密中栅码 

　　由于中文用规则的栅栏比较容易破解，所以产生了一些变体，例如道家心法密籍《天仙金丹心法》中的一段加密方法。密文如下： 

　　○ 茫 天 ： 摹 然 月 终 为 鼎 半 是 真 灭 器 轮 假 不 但 伸 净 著 定 分 泥 万 ○ 无 ○ 光 人 经 法 一 从 尘 色 返 我 权 自 法 中 妙 大 空 照 生 屈 来 好 路 形 神 海 ○ 便 还 未 归 

　　○ 茫 
　　天 ： 摹 
　　然 月 终 为 
　　鼎 半 是 真 灭 
　　器 轮 假 不 但 伸 
　　净 著 定 分 泥 万 ○ 
　　无 ○ 光 人 经 法 一 从 
　　尘 色 返 我 权 自 法 中 妙 
　　大 空 照 生 屈 来 好 路 形 神 
　　海 ○ 便 还 未 归 

　　明文(从上向下竖着读)：天然鼎器净无尘，大海茫茫月半轮。著色空摹终是假，定光返照便为真。不分人我生还灭，但泥经权屈未伸。万法自来归一法，好从中路妙形神。 

　　............................................................. 
　　利用电脑进行加密或解密，建议使用“列举加密”或“列举解密”，电脑会自动尝试一些正好匹配的栏位进行列举。 

　　lyiroonevuclesey 

　　4栏： 
　　loveyousincerely 

　　8栏： 
　　lionvceeyroeulsy 

【Vigenère Cipher】 

　　由于频率分析法可以有效的破解单表替换密码，法国密码学家维吉尼亚于1586年提出一种多表替换密码，
　　即维吉尼亚密码，也称维热纳尔密码。维吉尼亚密码引入了“密钥”的概念，即根据密钥来决定用哪一行的密表来进行替换，
　　以此来对抗字频统计。 

　　加密算法：例如密钥的字母为[d]，明文对应的字母[b]。根据字母表的顺序[d]=4,[b]=2，那么密文就是[d]+[b]-1=4+2-1=5=[e]，
　　因此加密的结果为[e]。解密即做此逆运算。 

　　加密公式：密文 = (明文 + 密钥) Mod 26 - 1 
　　解密公式：明文 = [26 + (密文 - 密钥)] Mod 26 + 1 

　　也可以用查表法来进行加密：例如密钥的字母为[d]，明文对应的字母[b]，在下图的表格第一行找到字母"d"(深蓝色)，
　　再在左边第一列找到字母"b"(绿色)，两个字母的交叉点(b行d列)就是字母"E"，所以对应的密文字母为[e]。 

　　[-----------------图-----------------] 

　　 a b c d e f g h i j k l m n o p q r s t u v w x y z 
　　a A B C D E F G H I J K L M N O P Q R S T U V W X Y Z 
　　b B C D E F G H I J K L M N O P Q R S T U V W X Y Z A 
　　c C D E F G H I J K L M N O P Q R S T U V W X Y Z A B 
　　d D E F G H I J K L M N O P Q R S T U V W X Y Z A B C 
　　e E F G H I J K L M N O P Q R S T U V W X Y Z A B C D 
　　f F G H I J K L M N O P Q R S T U V W X Y Z A B C D E 
　　g G H I J K L M N O P Q R S T U V W X Y Z A B C D E F 
　　h H I J K L M N O P Q R S T U V W X Y Z A B C D E F G 
　　i I J K L M N O P Q R S T U V W X Y Z A B C D E F G H 
　　j J K L M N O P Q R S T U V W X Y Z A B C D E F G H I 
　　k K L M N O P Q R S T U V W X Y Z A B C D E F G H I J 
　　l L M N O P Q R S T U V W X Y Z A B C D E F G H I J K 
　　m M N O P Q R S T U V W X Y Z A B C D E F G H I J K L 
　　n N O P Q R S T U V W X Y Z A B C D E F G H I J K L M 
　　o O P Q R S T U V W X Y Z A B C D E F G H I J K L M N 
　　p P Q R S T U V W X Y Z A B C D E F G H I J K L M N O 
　　q Q R S T U V W X Y Z A B C D E F G H I J K L M N O P 
　　r R S T U V W X Y Z A B C D E F G H I J K L M N O P Q 
　　s S T U V W X Y Z A B C D E F G H I J K L M N O P Q R 
　　t T U V W X Y Z A B C D E F G H I J K L M N O P Q R S 
　　u U V W X Y Z A B C D E F G H I J K L M N O P Q R S T 
　　v V W X Y Z A B C D E F G H I J K L M N O P Q R S T U 
　　w W X Y Z A B C D E F G H I J K L M N O P Q R S T U V 
　　x X Y Z A B C D E F G H I J K L M N O P Q R S T U V W 
　　y Y Z A B C D E F G H I J K L M N O P Q R S T U V W X 
　　z Z A B C D E F G H I J K L M N O P Q R S T U V W X Y 

　　假如对如下明文加密： 

　　to be or not to be that is the question 

　　当选定“have”作为密钥时，加密过程是：密钥第一个字母为[h]，明文第一个为[t]，因此可以找到在h行t列中的字母[a]，依此类推，
　　得出对应关系如下： 

　　密钥：ha ve ha veh av eh aveh av eha vehaveha 
　　明文：to be or not to be that is the question 
　　密文：ao wi vr isa tj fl tcea in xoe lylsomvn 

【Polybius密码(Polybius Cipher)】 

　　也称棋盘密码，是利用波利比奥斯方阵(Polybius Square)进行加密的密码方式，产生于公元前两世纪的希腊，
　　相传是世界上最早的一种密码。 

　　假设我们需要发送明文讯息 “Attack at once”， 用一套秘密混杂的字母表填满波利比奥斯方阵，像是这样： 

　　 A D F G X 
　　A b t a l p 
　　D d h o z k 
　　F q f v s n 
　　G g j c u x 
　　X m r e w y 

　　i和j视为同一个字，使字母数量符合 5 × 5 格。之所以选择这五个字母，是因为它们译成摩斯密码时不容易混淆，
　　可以降低传输错误的机率。使用这个方格，找出明文字母在这个方格的位置，再以那个字母所在的栏名称和列名称代替这个字母。
　　可将该讯息转换成处理过的分解形式。 

　　明文：A T T A C K A T O N C E 
　　密文：AF AD AD AF GF DX AF AD DF FX GF XF 

　　A,D,F,G,X也可以用数字1,2,3,4,5来代替，这样密文就成了： 

　　13 12 12 13 43 25 13 12 23 35 43 53 

------------------------------------------------------------------------- 

【ADFGX/ADFGVX密码(ADFGX/ADFGVX Cipher)】 

ADFGX 
　　1918年，第一次世界大战将要结束时，法军截获了一份德军电报，电文中的所有单词都由A、D、F、G、X五个字母拼成，
　　因此被称为ADFGX密码。ADFGX密码是1918年3月由德军上校Fritz Nebel发明的，是结合了Polybius密码和置换密码的双重加密方案。
　　A、D、F、G、X即Polybius方阵中的前5个字母。 

　　明文：A T T A C K A T O N C E 
　　经过Polybius变换：AF AD AD AF GF DX AF AD DF FX GF XF 

　　下一步，利用一个移位密钥加密。假设密钥是“CARGO”，将之写在新格子的第一列。再将上一阶段的密码文一列一列写进新方格里。 

　　C A R G O 
　　_________ 
　　A F A D A 
　　D A F G F 
　　D X A F A 
　　D D F F X 
　　G F X F X 

　　最后，密钥按照字母表顺序“ACGOR”排序，再按照此顺序依次抄下每个字母下面的整列讯息，形成新密文。如下： 

　　FAXDF ADDDG DGFFF AFAXX AFAFX 

　　在实际应用中，移位密钥通常有两打字符那么长，且分解密钥和移位密钥都是每天更换的。 

ADFGVX 
　　在1918年6月，再加入一个字V扩充。变成以6×6格共36个字符加密。这使得所有英文字母（不再将I和J视为同一个字）以及数字0到9都可混合使用。
　　这次增改是因为以原来的加密法发送含有大量数字的简短信息有问题。 

【乘法密码(Multiplication Cipher)】 

　　乘法密码也是一种简单的替代密码，与凯撒密码相似，凯撒密码用的是加法，而乘法密码用的自然是乘法。
　　这种方法形成的加密信息保密性比较低。 

　　加密公式：密文 = (明文 * 乘数) Mod 26 

　　对于乘数密码，只有当乘数与26互质时，加密之后才会有唯一的解，因此乘数只可能有如下11种的选择： 

　　乘数 = 3,5,7,9,11,15,17,19,21,23,25 

　　仿射密码和希尔密码因为都用到了乘法，所以乘数也受到相同的局限。 

------------------------------------------------------------------------- 

【仿射密码(Affine Shift)】 

　　仿射密码就是凯撒密码和乘法密码的结合。 

　　加密公式：密文 = (明文 * 乘数 + 位移数) Mod 26 

------------------------------------------------------------------------- 

【希尔密码(Hill Cipher)】 

　　希尔密码就是矩阵乘法密码，运用基本矩阵论原理的替换密码。每个字母当作26进制数字：A=0, B=1, C=2... 一串字母当成n维向量，
　　跟一个n×n的密钥矩阵相乘，再将得出的结果模26。希尔密码的优点是完全隐藏了字符的频率信息，弱点是容易被已知明文攻击击破。 

加密 
　　例如：密钥矩阵 
　　1 3 
　　0 2 

　　明文：HI THERE 

　　去空格，2个字母一组，根据字母表顺序换成矩阵数值如下，末尾的E为填充字元： 

　　HI TH ER EE 
　　8 20 5 5 
　　9 8 18 5 

　　HI 经过矩阵运算转换为 IS，具体算法参考下面的说明： 

　　|1 3| 8 e1*8+3*9=35 MOD26=9 =I 
　　|0 2| 9 e0*8+2*9=18 MOD26=18=S 

　　用同样的方法把“HI THERE”转换为密文“IS RPGJTJ”，注意明文中的两个E分别变为密文中的G和T。 

解密 
　　解密时，必须先算出密钥的逆矩阵，然后再根据加密的过程做逆运算。 

　　逆矩阵算法公式： 
　　|A B| = 1/(AD-BC) * | D -B| 
　　|C D| |-C A| 

　　例如密钥矩阵= 
　　|1 7| 
　　|0 3| 
　　AD-BC=1*3-0*7=3 3*X=1 mod26 所以 X=9 
　　因此 
　　|1 7| 的逆矩阵为： 9 * |3 -7| 
　　|0 3| |0 1| 

　　假设密文为“FOAOESWO” 

　　FO AO ES WO 
　　 6 1 5 23 
　　15 15 19 15 

　　9* |3 -7| | 6| = 9*(3*6-7*15)=-783 mod26 = 23=W 
　　 |0 1| |15| = 9*(0*6+1*15)= 135 mod26 = 5 =E 

　　所以密文“FOAOESWO”的明文为“WEREDONE” 

------------------------------------------------------------------------- 

【Playfair密码(Playfair Cipher)】 

　　Playfair将明文中的双字母组合作为一个单元对待，并将这些单元转换为双字母组合。
　　加密后的字符出现的频率在一定程度上被均匀化。 

　　5*5变换矩阵(I或J视为同一字符)： 

　　C I P H E 
　　R A B D F 
　　G K L M N 
　　O Q S T U 
　　V W X Y Z 

　　加密规则：按成对字母加密 

　　相同对中的字母加分隔符(如x) 
　　ballon -> ba lx lo on 
　　同行取右边：he->ec 
　　同列取下边：dm->mt 
　　其他取交叉：kt->mq od->tr 

　　例如：ballon -> ba lx lo on -> db sp gs ug 

【摩斯电码】 

　　摩斯电码(摩尔斯电码)是一种发报用的信号代码，是一种替代密码，用点(Dot)和划(Dash)的组合来表示各个英文字母或标点。 

　　国际标准摩斯电码表 

　　1 *---- A *- N -* [.] *-*-*- 
　　2 **--- B -*** O --- [,] --**-- 
　　3 ***-- C -*-* P *--* [:] ---*** 
　　4 ****- D -** Q --*- ['] *----* 
　　5 ***** E * R *-* [?] **--** 
　　6 -**** F **-* S *** [-] -****- 
　　7 --*** G --* T - [()] -*--*- 
　　8 ---** H **** U **- [@] *--*-* 
　　9 ----* I ** V ***- [—] -***- 
　　0 ----- J *--- W *-- 分数线 -**-* 
　 K -*- X -**- 
　 L *-** Y -*-- 终了[\r] ***-*- 
　 M -- Z --** 始信[\n] -*-*- 

　　例：Hello (斜线代表字母之间的间隔) 
　　****/*/*-**/*-**/---/ 

【置换密码(Transposition Cipher)】 

　　也称易位密码。 
------------------------------------------------------------------------- 

【替代密码(Monoalphabetic Substitution)】 

　　也称单表替换密码。 

【字母表数字 】 
　　用1-26这些数字分别表示A-Z的字母。 

　　字母 A B C D E F G H I J K L M N O P Q R S T U V W X Y Z 
　　数字 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 

【字母表代码】 
　　同字母表数字，只是把10以下的数字添0补位。 

　　字母 A B C D E F G H I J K L M N O P Q R S T U V W X Y Z 
　　数字 01 02 03 04 05 06 07 08 09 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 

【反字母表】 
　　就是丹·布朗在《达·芬奇密码》一书中提到的埃特巴什码(Atbash Cipher)。它的原理是取一个字母，
　　指出它位于字母表正数第几位，再把它替换为从字母表倒数同样的位数后得到的字母。如：E被替换为V，N被替换为M等。 

　　明码表 A B C D E F G H I J K L M N O P Q R S T U V W X Y Z 
　　密码表 Z Y X W V U T S R Q P O N M L K J I H G F E D C B A 

　　明文：sophia 
　　密文：hlksrz 

【随机乱序字母】 
　　即单字母替换密码。重排密码表二十六个字母的顺序，密码表会增加到四千亿亿亿多种，
　　能有效的防止用筛选的方法检验所有的密码表。这种密码持续使用几个世纪，直到阿拉伯人发明了频率分析法。 

　　明码表 A B C D E F G H I J K L M N O P Q R S T U V W X Y Z 
　　密码表 Q W E R T Y U I O P A S D F G H J K L Z X C V B N M 

　　明文：forest 
　　密文：gbmrst 

【棋盘密码】 
　　即Polybius密码。 

【键盘密码】 
　　加密的原理同棋盘密码，只是利用了键盘作为方阵。 

　　键盘的字母分布： 

　　~!@#$%^&*()_+| 
　　`1234567890-=\ 
　　 QWERTYUIOP{} 
　　 qwertyuiop[] 
　　 ASDFGHJKL:" 
　　 asdfghjkl;' 
　　 ZXCVBNM<>? 
　　 zxcvbnm,./ 

　　密文：72 81 12 63 01 12 63 
　　明文：jianpan 

　　低下头看看键盘就知道了，密文就是键盘上的26个字母的坐标，72即第7列第2行，第7列正好是数字键[7]的位置，往下2个就是字母[J]。 
【键盘移位】 
　　密文：kosm[sm 
　　明文：jianpan 

　　就是键盘上的字母往右一个。例如[j]键的右面是[k]，[i]键的右面是[o]，依此类推。 
【软键盘密码】 
　　密文1：まはす にはつ へつ たっゃの せちなゃ ひつなゃ てなゃ ひつな ゅつ ぬす 
　　密文2：ㄈㄘㄍ ㄋㄘㄛ ㄠㄛ ㄗㄟㄙㄕ ㄐㄧㄇㄙ ㄨㄛㄇㄙ ㄣㄇㄙ ㄨㄛㄇ ㄩㄛ ㄎㄍ 
　　密文3：црв мрж уж езып гёлы сжлы илы сжл ьж нв 
　　密文4：＃←☆ △←◇ 〓◇ ●◆＿→ ★◎■＿ ↑◇■＿ □■＿ ↑◇■ ￣◇ ▲☆ 
　　明文：zhe shi li yong ruan jian pan jia mi de(这是利用软键盘加密的) 

　　用智能ABC或微软拼音输入法，把小键盘打开，选择日本平假名字符，输入“zhe shi”就会出现“まはす にはつ”，
　　如果切换到俄文字符就会出现“црв мрж”…… 
【数字小键盘密码】 
　　数字小键盘的字母分布： 
　　7 8 9 
　　4 5 6 
　　1 2 3 

　　密文：852 74123 741236987 74269 78974123456 7412369 
　　明文：I L O V E U 

　　对照小键盘，依次打这些字母，看组成的形状就行了。 
　　关于Alt+小键盘数字的加密方法，参看：百度/Google/网页字符。 

【手机键盘密码】 
　　根据手机键盘上的数字和对应的字母进行加密。 
　　密文：42 21 71 71 93 
　　明文：HAPPY 
　　“42”：4键对应的是GHI，GHI第2个就是H；“21”：2键对应的是ABC，ABC第1个就是A。 
　　加密时往往只出现数字键，而不给出具体的字母位置，这时解密时就要列举所有可能的组合，从中选出有意义的单词来。 
　　例如密文：42779，这时就要从 GHI ABC PQRS PQRS WXYZ 中提出有意义的字符：HAPPY 
　　另一种方法是根据形状加密的，和数字小键盘密码相同，按照密码里的数字比划一下就划出来了。 
　　比如密文173946，对应的明文是H，17是左边一竖，39是右边一竖，46是中间一横。 

【百度/Google/网页字符】 

　　下面解释一下在百度、Google搜索中文的关键词时，地址栏上出现的奇怪字符。 

百度字符(GB2312) 
　　例如在百度搜索“你好”两个字，会转到一个地址为 http://www.baidu.com 的网页。 

　　密文(GB码16进制)：%C4%E3%BA%C3 
　　密文(GB码十进制)：50403 47811 
　　明文：你好 

　　百度用的是GB2312的中文编码，是16进制的。GB2312是标准的简体中文编码。“你”字的GB码为C4E3，“好”字的GB码为BAC3。
　　“你好”转换成十进制为50403和47811。 

Google字符(URI) 
　　例如在Google搜索“你好”两个字，会转到一个地址为 http://www.google.cn 的网页。 

　　密文(URI)：%E4%BD%A0%E5%A5%BD 
　　明文：你好 

　　URI全称Uniform Resource Identifier(通用资源标识符)。Internet可用的每种资源 - HTML文档、图像、视频片段、程序等 - 
　　由一个通过URI进行定位。 

网页编码(Unicode) 
　　论坛里常玩的一个把戏，就是让你回帖时写一堆像天书一样的奇怪字符，而回帖之后就能看到相应的文字。 

　　密文(Unicode16进制)：楼主是个天才 
　　密文(Unicode10进制)：楼主是个天才 
　　明文：楼主是个天才 

　　这里使用的是Unicode编码(十进制)，Unicode是一种全世界范围的文字编码，网页都支持这种编码。 

Alt+数字小键盘 
　　按住Alt键，在任意文本框中，用键盘右边的数字小键盘输入55021，然后松开Alt键，这时你看到了什么？ 

　　用同样的方法分别输入“你好”两个字的GB代码(十进制)50403、47811，这时你将在文本框中看到这两个字。 

　　注意在qq的对话框中，要使用Unicode代码(十进制)20320、22909。 
【元音密码】
元音密码的原则很简单，即将五个元音字母分别标号1，2，3，4，5，然后将26个英文字母的对应表码写成如下的形式：
a  b  c  d  e  f  g  h  i  j  k  l  m  n  o  p  q  r  s  t  u  v  w  x  y  z1 11 12 13  2 21 22 23  3 31 32 33 34 35  4 41 42 43 44 45  5 51 52 53 54 55然后进行加密即可。

题目：45.23.2.33.1.44.45.44.3.22.23.45
对应上表解出明文：the last sight（最后一面）.
需要说明的是，元音字母因为密文中只含有1，2，3，4，5五个数字而且时常出现个位数，因此很容易破解，
有时候可以将1，2，3，4，5变为10，20，30，40，50等，也可变成如同棋盘密码密文的形式来对解密者进行干扰。
【云影密码】
此密码运用了1248代码，因为本人才疏学浅，尚未发现有过使用的先例，因此暂归为原创密码，若有密码界前辈认为不妥，
请指出此密码或类似密码的普遍使用历史并附寄一份到我站内邮箱，我将以最快速度核查并改正。由于这个密码，我和片风云影初识，为了纪念，将其命名为“云影密码”，原文请见谜题大全精华区。
原理很简单，有了1，2，4，8这四个简单的数字，你可以以加法表示出0-9任何一个数字，例如0=28，7=124，9=18。
这样，再用1-26来表示A-Z，就可以用作密码了。
为了不至于混乱，我个人引入了第五个数字0，来用作间隔，以避免翻译错误，所以还可以称“01248密码”。

题目：12401011801180212011401804
第一步，分割，即124  1  118  118  212  114  18  4
第二步，基本翻译，例如124可以表示7，也可以表示16（但不可能是34，因为不会超过26），所以可以放在一边，翻译其他没有异议的，
可得：124  a  s  s  w  o  18  d
第三步，推测得出明文。可以推测后面的18表示r，前面的为p最合适。

明文：password（密码）.(五)四位乘法密码——（密文：I Q V L N J O P X；密钥：1234）
自古密文的传递者最担心的就是密文和密钥同时落入敌手，这样，密码的效应也就所剩无几了，
所以通常会将两样东西以不同的方式在不同的时间进行传送。但是，后来有一个叫前天淫次郎的日本鬼子发明了一种加密方式，
这种加密方式使得即使密钥落入敌手也不会轻易暴露，一时很令敌手头疼。
这种加密方式的关键是密钥，简短但是实用。下面介绍其使用及破译方法：
首先，任意选取一个个十百位数均无零的四位数，如题目中的密钥，即1234；
其次，将上述四位数做平方处理，即1234×1234=1522756,取中间三位数，即227；
再次，用所得数字与1234相乘，即227×1234=280118，取“中间三位”（之前传递和接收密文的双方要有所约定比如遇到像280118这样的数字，
是取‘801’还是取‘011’），这里取801；
依次类推，直到所得的三位数所含数字总个数大于或等于密文的字母个数为止，即801×1234=988434，取884。
这样，最终得到的一组码是227801884。
最后，将这组码标在密文下，向前推相应的位数即可得到明文，即

密文：I Q V L N J O P X
密钥：2 2 7 8 0 1 8 8 4
明文：g o o d n i g h t(Good night!)
【费娜姆密码】（密码：00110110010001001100100010000010110；密钥：study）

二战时德军使用过的一种密码，其实是利用了二进制的表示法来替代字母，有如下的表格作为基础：

A 1000001 B 1000010 C 1000011 D 1000100 E 1000101 F 1000110 G 1000111 H 1001000 I 1001001 J 1001010

K 1001011 L 1001100 M 1001101 N 1001110 O 1001111 P 1010000 Q 1010001 R 1010010 S 1010011 T 1010100

U 1010101 V 1010110 W 1010111 X 1011000 Y 1011001 Z 1011010

那么，比如我们要加密“Hello”，密钥用“study”，则以如下方式进行加密：

H E L L O = 1001000 1000101 1001100 1001100 1001111
S T U D Y = 1010011 1010100 1010101 1000100 1011001

加密原则：1+1=0，0+0=0，1+0=1

于是得密文：00110110010001001100100010000010110

那么解题目中的密文，需要遵循以下几个原则和步骤，

1，划分，即每七个数字为一组；

2，对应，找出密文每个字母对应的数字，再与上述数字对应；

3，转换，遵循上述加密原则，逆用即可；

4，解密，得出新的一组数字，对应字母，得出明文。

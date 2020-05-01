### `sed`用法介绍
sed [-nefr] [动作] 
选项与参数：
-n ：使用安静(silent)模式。在一般sed 的用法中，所有来自STDIN 的资料一般都会被列出到萤幕上。
      但如果加上-n 参数后，则只有经过sed 特殊处理的那一行(或者动作)才会被列出来。
-e ：直接在指令列模式上进行sed 的动作编辑；
-f ：直接将sed 的动作写在一个档案内， -f filename 则可以执行filename 内的sed 动作；
-r ：sed 的动作支援的是延伸型正规表示法的语法。(预设是基础正规表示法语法)
-i ：直接修改读取的档案内容，而不是由萤幕输出。

动作说明： [n1[,n2]]function
n1, n2 ：不见得会存在，一般代表『选择进行动作的行数』，举例来说，如果我的动作
         是需要在10 到20 行之间进行的，则『 10,20[动作行为] 』

function 有底下这些咚咚：
a ：新增， a 的后面可以接字串，而这些字串会在新的一行出现(目前的下一行)～
c ：取代， c 的后面可以接字串，这些字串可以取代n1,n2 之间的行！
d ：删除，因为是删除啊，所以d 后面通常不接任何咚咚；
i ：插入， i 的后面可以接字串，而这些字串会在新的一行出现(目前的上一行)；
p ：列印，亦即将某个选择的资料印出。通常p 会与参数sed -n 一起运作～
s ：取代，可以直接进行取代的工作哩！通常这个s 的动作可以搭配正规表示法！
      例如1,20s/old/new/g 就是啦！

## `sed`使用示例

### 例1 将`/etc/passwd`的内容列出并且打印行号，同时删除第2行至第5行
指令：
```
nl /etc/passwd | sed '2,5d'
```
拓展1.1 将`/etc/passwd`的内容列出并且打印行号，同时删除第2行

指令
```
nl /etc/passwd | sed '2d'
```

拓展1.2 将`/etc/passwd`的内容列出并且打印行号，同时删除第3行至最后一行

指令
```
nl /etc/passwd | sed '3,$d'
```
### 例2 将`/etc/passwd`的内容列出并且打印行号，在第2行后加上"drink tea"
指令
```
nl /etc/passwd | sed '2a drink tea'
```
拓展2.1 将`/etc/passwd`的内容列出并且打印行号，在第2行前加上"drink beer"

指令
```
nl /etc/passwd | sed '2i drink beer'
```

### 例3 将`/etc/passwd`的内容列出并且打印行号，并在第2行后加入两行字"Drink tea or . ......"和"drink beer?"
指令
```
nl /etc/passwd | sed '2a Drink beer or . ......\
drink beer?'
```

### 例4 将`/etc/passwd`的内容列出并且打印行号，并将第2-5行的内容替换为"No 2-5 number"
指令
```
nl /etc/passwd | sed '2,5c No 2-5 number'
```

### 例5 仅列出`/etc/passwd`文件的第5-7行
指令
```
nl /etc/passwd | sed -n '5,7p'
```

### 例6 查找部分数据并替换
格式：
```
sed 's/要被替换的字符串/新的字符串'


/sbin/ifconfig eth0 | grep 'inet ' | sed 's/^.*inet //g' \
| sed 's/ *netmask. *$//g'

cat /etc/man_db.conf | grep 'MAN'| sed 's/#.*$//g' | sed '/^$/d'
```





















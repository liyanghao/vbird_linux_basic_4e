### 例题1 查找指定字符串
任务1：从文件`regular_express.txt`中查找包含字符串`the`的行。
指令：
```
grep -n 'the' regular_express.txt
```

任务2：从文件`regular_express.txt`中查找不包含个字符串`the`的行。
指令：
```
grep -vn 'the' regular_express.txt
```
任务3：从文件`regular_express.txt`中查找包含不分大小写的字符串`the`的行。
指令：
```
grep -in 'the' regular_express.txt
```

### 例题2 中括号`[]`表示集合字符
任务1：从文件`regular_express.txt`中查找包含字符串`test`或者`taste`的行。
指令：
```
grep -n 't[ae]st' regular_express.txt
```

任务2：从文件`regular_express.txt`中查找包含字符串`oo`的行。
指令：
```
grep -n 'oo' regular_express.txt
```

任务3：从文件`regular_express.txt`中查找包含字符串`oo`，但字符串`oo`前面没有字符`g`的行。
指令：
```
grep -n '[^g]oo' regular_express.txt
```

任务4：从文件`regular_express.txt`中查找包含字符串`oo`，但字符串`oo`前面没有小写字符的行。
指令：
```
grep -n '[^a-z]oo' regular_express.txt
```

任务5：从文件`regular_express.txt`中包含数字的行。
指令：
```
grep -n '[0-9]' regular_express.txt
```

### 例题3 行首字符`^`和行尾字符`$`
任务1：从文件`regular_express.txt`中查找行首包含字符串`the`的行。
指令：
```
grep -n '^the' regular_express.txt
```

任务2：从文件`regular_express.txt`中查找行首是小写字符的行。
指令：
```
grep -n '^[a-z]' regular_express.txt
```

任务3：从文件`regular_express.txt`中查找行首不是英文字符的行。
指令：
```
grep -n '^[^a-zA-Z]' regular_express.txt
```

任务4：从文件`regular_express.txt`中查找以小数点`.`结尾的行。
指令：
```
grep -n '\.$' regular_express.txt
```

### 例题4 `.`表示任意一个字符，`*`表示有重复字符

任务1 从文件`regular_express.txt`中查找包含字符串`g???d`的行。
指令：
```
grep -n 'g..d' regular_express.txt
```

任务2 从文件`regular_express.txt`中查找包含字符串`oo`或者`ooo`或者`oooo`的行。
指令：
```
grep -n 'o*' regular_express.txt
```
解释：
- `o*`：表示空字符串或者至少包含一个字符o

任务3 从文件`regular_express.txt`中查找包含至少两个以上字符`o`的行。
指令：
```
grep -n 'ooo*' regular_express.txt
```

任务4 从文件`regular_express.txt`中查找包含`gog`、`goog`、`gooog`的行。
指令：
```
grep -n 'goo*g' regular_express.txt
```
任务5 从文件`regular_express.txt`中查找包含开头结尾都是字符`g`、中间字符可有可无的行。
指令：
```
grep -n 'g.*g' regular_express.txt
```
解释：
- `.*`：表示零个或者多个任意字符


任务6 从文件`regular_express.txt`中查找包含任意数字的行。
指令：
```
grep -n '[0-9][0-9]*' regular_express.txt
```

### 例题5 `{}`用于表示限定连续字符数

任务1 从文件`regular_express.txt`中查找包含连续两个字符`o`的行。
指令：
```
grep -n 'o\{2\}' regular_express.txt
```

任务2 从文件`regular_express.txt`中查找包含`g后跟2到5个o再接一个g的字符串`的行。
指令：
```
grep -n 'go\{2,5\}g' regular_express.txt
```

任务3 从文件`regular_express.txt`中查找包含`2个o以上的goooo...g`的行。
指令：
```
grep -n 'go\{2,\}g' regular_express.txt
```



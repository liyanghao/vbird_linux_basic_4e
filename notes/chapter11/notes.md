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

### 例题2 利用中括号`[]`来查找集合字符串
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


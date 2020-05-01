### 例题1 搜寻特定字符串
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
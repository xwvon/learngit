# Git中AutoCRLF与SafeCRLF换行符的问题
最近发现在使用**window10**用git命令行提交代码的时候会被转换成CRLF，因为window的回车换行（CRLF）与类Unix平台的换行符（LF）不一样，解决的方法是打开命令行设置**git**的全局配置
+ 提交时转换为LF，检出时转换为CRLF
```
git config --global core.autocrlf true #默认
```
+ 提交时转换为LF，检出时不转换
```
git config --global core.autocrlf input
```
+ 提交和检出都不进行转换
```
git config --global core.autoarlf false
```
可以配置**safecrlf**是否提交包含混合换行符的文件
+ 拒绝提交包含混合换行符的文件
```
git config --global core.safecrlf true
```
+ 允许提交包含混合换行符的文件
```
git config --global core.safecrlf false
```
+ 提交包含混合换行符的文件时发出警告
```
git config --global core.safecrlf warn
```

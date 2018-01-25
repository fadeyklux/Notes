Chapter5 操作文件和目录
========================
```shellscript
cp
copy files and directories
mv
move/rename files and directories
mkdir
create directories
rm
remove files and direc
ln
create hard and symbolic links
```
## 5.1 wildcards
wildcards    | meaning
-------------|------------
\*           | 匹配任意多个字符（包括零个）
?            | 匹配任意一个字符（不包括零个）
[characters] | 匹配任意一个属于字符集中的字符
[!characters]| 匹配任意一个不是字符集中的字符
[:class:]    | 匹配任意一个属于指定字符类中的字符

Character Class | Meaning
------------ | -----
[:alnum] | Matches any alphanumeric character
[:alpha:] | Matches any alphabetic character
[:digit:] | Matches any numeral
[:lower:] | Matches any lowercase letter
[:upper:] | Matches any uppercase letter
## 5.2 mkdir
```
mkdir directory...

mkdir dir1 or mkdir dir1 dir2 dir3
```
## 5.3 cp
```
cp item1 item2
cp item... directory
```
## 5.4 Useful parameters
Option            | Meaning
------------------|----------
-a --archive      |
-i --interaritive |before overwriting an existing file, prompt the user for confirmation.
-r --recursive    |
-u --update       |
-v --verbose      |  Recursively copy directories and their contents. 
## 5.5 rm


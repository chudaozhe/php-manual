# String 字符串
一个字符串 string 就是由一系列的字符组成，其中每个字符等同于一个字节。这意味着 PHP 只能支持 256 的字符集，因此不支持 Unicode 。详见字符串类型详解。

## 语法
一个字符串可以用 4 种方式表达：

### 单引号
定义一个字符串的最简单的方法是用单引号把它包围起来（字符 '）。

### 双引号
如果字符串是包围在双引号（"）中， PHP 将对以下特殊的字符进行解析：
用双引号定义的字符串最重要的特征是变量会被解析

### Heredoc 结构
支持变量解析
```
<?php
$a='a';
echo <<<AAA
ww11
222
$a $a
AAA;
```
### Nowdoc 结构
不支持变量解析
```
<?php
echo <<<'AAA'
ww11
222
AAA;
```
## 变量解析

### 简单语法
```
<?php
$juice = "apple";

echo "He drank some $juice juice.".PHP_EOL;
```
### 复杂（花括号）语法
```
<?php
// 显示所有错误
error_reporting(E_ALL);

$great = 'fantastic';

// 无效，输出: This is { fantastic}
echo "This is { $great}";

// 有效，输出： This is fantastic
echo "This is {$great}";
```

## 存取和修改字符串中的字符
注意: PHP 8.0.0 之前, 出于同样的目的，可以使用大括号访问 string，例如 $str{42}。 从 PHP 7.4.0 起，此大括号语法被弃用，自 PHP 8.0.0 开始不再受支持。
```
<?php
// 取得字符串的第一个字符
$str = 'This is a test.';
echo $str[0];//T
```
## 有用的函数和运算符
字符串可以用 '.'（点）运算符连接起来，注意 '+'（加号）运算符没有这个功能。更多信息参考字符串运算符。

对于 string 的操作有很多有用的函数。

可以参考字符串函数了解大部分函数，高级的查找与替换功能可以参考 Perl 兼容正则表达式函数。

另外还有 URL 字符串函数，也有加密／解密字符串的函数（Sodium 和 Hash）。

最后，可以参考字符类型函数。
## 转换成字符串

## 字符串类型详解


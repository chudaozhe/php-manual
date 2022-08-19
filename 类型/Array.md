# Array 数组
PHP 中的 array 实际上是一个有序映射。映射是一种把 values 关联到 keys 的类型。此类型针对多种不同用途进行了优化； 它可以被视为数组、列表（向量）、哈希表（映射的实现）、字典、集合、堆栈、队列等等。 由于 array 的值可以是其它 array 所以树形结构和多维 array 也是允许的。

## 语法
```
// 使用短数组语法
$array = [
    "foo" => "bar",
    "bar" => "foo",
];
```

### 用方括号语法访问数组单元
数组单元可以通过 array[key] 语法来访问。
> 在 PHP 8.0.0 之前，方括号和花括号可以互换使用来访问数组单元（例如 $array[42] 和 $array{42} 在上例中效果相同）。 花括号语法在 PHP 7.4.0 中已弃用，在 PHP 8.0.0 中不再支持。

### 用方括号的语法新建／修改
```
$arr[key] = value;
$arr[] = value;
// key 可以是 int 或 string
// value 可以是任意类型的值
```
## 实用函数
有很多操作数组的函数，参见 数组函数 一节。

## 数组做什么和不做什么

### 为什么 $foo[bar] 错了？

### 那么为什么这样做不好？

## 转换为数组
```
<?php
var_dump((array)'aa');

//输出
array(1) {
  [0]=>
  string(2) "aa"
}
```
## 比较
可以用 array_diff() 函数和 数组运算符 来比较数组。

## 数组解包
PHP 7.4.0 开始可以使用 ... 解包 array。
```
<?php
// string key
$arr1 = ["a" => 1];
$arr2 = ["a" => 2];
$arr3 = ["a" => 0, ...$arr1, ...$arr2];
var_dump($arr3); // ["a" => 2]

// integer key
$arr4 = [1, 2, 3];
$arr5 = [4, 5, 6];
$arr6 = [...$arr4, ...$arr5];
var_dump($arr6); // [1, 2, 3, 4, 5, 6]

//在 PHP 8.1 之前，带有 string 键的 array 无法解包：
$arr1 = [1, 2, 3];
$arr2 = ['a' => 4];
$arr3 = [...$arr1, ...$arr2, ...[5]];
var_dump($arr3);
array(5) {
  [0]=>
  int(1)
  [1]=>
  int(2)
  [2]=>
  int(3)
  ["a"]=>
  int(4)
  [3]=>
  int(5)
}
```
## 示例


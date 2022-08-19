##if

##else

## elseif/else if
如果用冒号来定义 if/elseif 条件，那就不能用两个单词的 else if
```
<?php
/* 正确的使用方法： */
$a=$b=1;
if ($a > $b):
    echo $a." is greater than ".$b;
elseif ($a == $b): // 注意使用了一个单词的 elseif
    echo $a." equals ".$b;
else:
    echo $a." is neither greater than or equal to ".$b;
endif;
```

## 流程控制的替代语法
PHP 提供了一些流程控制的替代语法，包括 if，while，for，foreach 和 switch。替代语法的基本形式是把左花括号（{）换成冒号（:），把右花括号（}）分别换成 endif;，endwhile;，endfor;，endforeach; 以及 endswitch;。
```
<?php
if ($a == 5):
    echo "a equals 5";
    echo "...";
elseif ($a == 6):
    echo "a equals 6";
    echo "!!!";
else:
    echo "a is neither 5 nor 6";
endif;
```
> 不支持在同一个控制块内混合使用两种语法。

## while
while 循环是 PHP 中最简单的循环类型。它和 C 语言中的 while 表现地一样。while 语句的基本格式是：
```
while (expr)
statement
```

下面两个例子完全一样，都显示数字 1 到 10：
```
<?php
/* 示例 1 */

$i = 1;
while ($i <= 10) {
    echo $i++;  /* 在自增前（后自增）打印的值将会是 $i */
}

/* 示例 2 */

$i = 1;
while ($i <= 10):
    print $i;
    $i++;
endwhile;
```

## do-while
至少执行一次
```
<?php
$i = 0;
do {
   echo $i;//0
} while ($i > 0);
```

## for
考虑以下的例子，它们都显示数字 1 到 10：
```
<?php
/* 示例 1 */

for ($i = 1; $i <= 10; $i++) {
    echo $i;
}

/* 示例 2 */

for ($i = 1; ; $i++) {
    if ($i > 10) {
        break;
    }
    echo $i;
}

/* 示例 3 */

$i = 1;
for (;;) {
    if ($i > 10) {
        break;
    }
    echo $i;
    $i++;
}

/* 示例 4 */

for ($i = 1, $j = 0; $i <= 10; $j += $i, print $i, $i++);

有时经常需要像下面这样例子一样对数组进行遍历：
<?php
$people = Array(
        Array('name' => 'Kalle', 'salt' => 856412), 
        Array('name' => 'Pierre', 'salt' => 215863)
        );

for($i = 0, $size = count($people); $i < $size; ++$i)
{
    $people[$i]['salt'] = rand(000000, 999999);
}
```

## foreach
```
<?php
$arr = array(1, 2, 3, 4);
foreach ($arr as &$value) {
    $value = $value * 2;
}
// 现在 $arr 是 array(2, 4, 6, 8)
unset($value); // 最后取消掉引用
```

### 用 list() 给嵌套的数组解包
```
<?php
$array = [
    [1, 2],
    [3, 4],
];

foreach ($array as list($a, $b)) {
    // $a 包含嵌套数组的第一个元素，
    // $b 包含嵌套数组的第二个元素。
    echo "A: $a; B: $b\n";
}

output:
A: 1; B: 2
A: 3; B: 4
```

## break
break 结束执行当前的 for、foreach、while、do-while、switch 结构。

break 接受一个数字的可选参数，决定跳出几重循环。 默认值是 1，仅仅跳出最近一层嵌套结构。

```
$i = 0;
while (++$i) {
    switch ($i) {
        case 5:
            echo "At 5<br />\n";
            break 1;  /* 只退出 switch. */
        case 10:
            echo "At 10; quitting<br />\n";
            break 2;  /* 退出 switch 和 while 循环 */
        default:
            break;
    }
}
```

## continue
```
<?php
foreach ($arr as $key => $value) {
    if (!($key % 2)) { // 忽略偶数成员
        continue;
    }
    do_something_odd($value);
}

```

## switch
```
switch ($i) {
    case 0:
        echo "i equals 0";
        break;
    case 1:
        echo "i equals 1";
        break;
    case 2:
        echo "i equals 2";
        break;
}
```

## match
8.0新增
```
$food = 'cake';

$return_value = match ($food) {
    'apple' => 'This food is an apple',
    'bar' => 'This food is a bar',
    'cake' => 'This food is a cake',
};

var_dump($return_value);
```

## declare
```

```

## return
```

```
## require
```

```
## include
```

```
## require_once
```

```
## include_once
```

```
## goto
```

```
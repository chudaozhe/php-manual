# Iterable 可迭代对象
Iterable是 PHP 7.1 中引入的一个伪类型。它接受任何 array 或实现了 Traversable 接口的对象。这些类型都能用 foreach 迭代， 也可以和 生成器 里的 yield from 一起使用。

示例 #3 可迭代返回类型示例
```
<?php

function bar(): iterable {
    return [1, 2, 3];
}
```

```
<?php
function gen(): iterable {
    yield 1;
    yield 2;
    yield 3;
}

foreach(gen() as $item){
    echo $item.PHP_EOL;
}
```
# Enum 枚举
8.1新增的

## 枚举基础
枚举是在类、类常量基础上的约束层， 目标是提供一种能力：定义包含可能值的封闭集合类型。
```
<?php
enum Suit:string
{
    case Hearts='h';
    case Diamonds='d';
    case Clubs='c';
    case Spades='s';
}

function do_stuff(Suit $s)
{
    var_dump($s->name);//Spades
    var_dump($s->value);//s
}

do_stuff(Suit::Spades);
```

## 类型转换
将 enum 转换为 object 不会有变化。 将 enum 转换为 array， 纯粹枚举会创建单个 name 键的数组； 回退枚举创建带 name 和 value 键的数组。 其他类型转换都会导致错误。

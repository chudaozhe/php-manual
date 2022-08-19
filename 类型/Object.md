# Object 对象

## 对象初始化
要创建一个新的对象 object，使用 new 语句实例化一个类：
```
<?php
class foo
{
    function do_foo()
    {
        echo "Doing foo."; 
    }
}

$bar = new foo;
$bar->do_foo();
```

## 转换为对象
```
<?php
$obj = (object) 'ciao';
echo $obj->scalar;  // 输出 'ciao'
```
# Callback / Callable 类型

回调可以通过 callable 类型声明来表示。

一些函数如 call_user_func() 或 usort() 可以接受用户自定义的回调函数作为参数。回调函数不止可以是简单函数，还可以是对象的方法，包括静态类方法。

## 传递

示例 #1 回调函数示例
```
<?php 

// 回调函数示范
function my_callback_function() {
    echo 'hello world!';
}

// 回调方法示范
class MyClass {
    static function myCallbackMethod() {
        echo 'Hello World!';
    }
}

// 类型 1：简单的回调
call_user_func('my_callback_function'); 

// 类型 2：静态类方法回调
call_user_func(array('MyClass', 'myCallbackMethod')); 

// 类型 3：对象方法回调
$obj = new MyClass();
call_user_func(array($obj, 'myCallbackMethod'));

// 类型 4：静态类方法回调
call_user_func('MyClass::myCallbackMethod');

// 类型 5：父级静态类回调
class A {
    public static function who() {
        echo "A\n";
    }
}

class B extends A {
    public static function who() {
        echo "B\n";
    }
}

call_user_func(array('B', 'parent::who')); // A

// 类型 6：实现 __invoke 的对象用于回调
class C {
    public function __invoke($name) {
        echo 'Hello ', $name, "\n";
    }
}

$c = new C();
call_user_func($c, 'PHP!');
```

示例 #2 使用 Closure 的示例
```
<?php
// 闭包
$double = function($a) {
    return $a * 2;
};

// 这是数字范围
$numbers = range(1, 5);

// 这里使用闭包作为回调，
// 将范围内的每个元素数值翻倍
$new_numbers = array_map($double, $numbers);

print implode(' ', $new_numbers);//2 4 6 8 10
```
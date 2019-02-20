# A tour of the dart language
---

## A basic dart program

```dart
// 双斜线注释
// Define a function
printInteger(int aNumber) {
  print('The number is $aNumber.'); // print to console
}
// 语句以分号结束

// This is where the app starts
main() {
  var number = 42; // use var to declare and initialze a variable
  printInteger(number); // call a function
}
```


## 变量

```dart
var name = 'Bob';
```

变量存储的是引用，上述名称为name的变量存储的就是一个值为Bob的String对象的引用。

使用`var`来声明的变量可以根据其赋值来推断类型。

如果一个变量的取值可能存在多种类型，使用`dynamic`来声明。

```dart
dynamic name = 'Bob';
```

## 缺省值

任何未初始化的变量的初始值为`null`，因为在dart中`everything is object`。

```dart
int lineCount;
assert(lineCount == null);
```

上述`assert`语句在生产环境中将被忽略，在开发环境中可以辅助开发。

## 常量

使用`final`或者`const`来声明常量。

## 内置数据类型

* 数值：`int`,`double`

```dart
var x = 1;
var hex = 0xDEADCEEF;

var y = 1.1;
var exponents = 1.4e5;

double z= 1; // integer can be automatically converted to double

// String -> int
var one = int.parse('1');
assert(ont == 1);

// String -> double
var onePointOne = double.parse('1.1');
assert(onePointOne == 1.1);

// int -> String
String oneAsString = 1.toString();
assert(onAsString == '1');

// double -> String
String piAsString = 3.14159.toStringAsFixed(2);
assert(piAsString == '3.14');
```

* 字符串：`String`

使用单引号或者双引号来创建字符串。

```dart
var s1 = 'Single quotes work well for string literals';
var s2 = "Double quotes work just as well";
var s3 = 'It\'s easy to escape the string delimiter.';
var s4 = "It's even easier to use the other delimiter.";
```

可以使用`${expression}`来将一个表达式置于字符串中。

```dart
var s = 'string interpolation';

assert('Dart has $s, which is very handy.' == 
    'Dart has string interpolation, ' + 'which is very handy.');

assert('That deserves all caps. ' + '${s.toUpperCase()} is very handy!' == 
    'That deserves all caps. ' + 'STRING INTERPOLATION is very handy!');
```

使用`+`或者简单的将多个字符串放置在一起，就可以实现字符串拼接。

对于多行字符串，可以使用三个单引号或者三个双引号来创建，

```dart
var s1 = '''
You can create
multiple line strings like this one.
''';

var s2 = """This is also a 
multiple line string.""";
```

使用`r`前缀来创建raw字符串。

```dart
var s = r'In a raw string, not even \n gets special treatment.';
```

* 布尔类型： `bool`

```dart
// 检验是否为空字符串
var fullName = '';
assert(fullName.isEmpty);

// 检验是否为0
var hitPoints = 0;
assert(hitPoints <= 0>);

// 检验是否为null
var unicorn;
assert(unicorn == null);

// 检验是否为NaN
var iMeanToDoThis = 0/0;
assert(iMeanToDoThis.isNaN);
```

* List

```dart
var list = [1, 2, 3];
assert(list.length == 3);
assert(list[1] == 2);

list[1] = 1;
assert(liost[1] == 1);
```

* map

```dart
var gifts = {
  // key : value
  'first' : 'partridge',
  'second' : 'turtledoves',
  'fifth' : 'golden rings'
};

var nobleGases = {
  2 : 'helium',
  10 : 'neon',
  18 : 'argon',
};

// 可以使用Map()创建一个map对象，然后初始化
var gifts = Map();
gifts['first'] = 'partridge';
gifts['second'] = 'turtledoves';
gifts['fifth'] = 'golden rings';

var nobleGases = Map();
nobleGases[2] = 'helium';
nobleGases[10] = 'neon';
nobleGases[18] = 'argon';
```

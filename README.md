# JS 的基本语法

## 什么是表达式和语句

---

1. **表达式**

```
var a = 1+2
```

- 这句话先用 var 命令，声明变量 a ，然后将 1+2 的运算结果赋值给了变量 a 。 这里 `1+2` 就是表达式(expression),指一个为了得到返回值的计算公式。
- add(1,2)表达式的值为函数的<font color=red>返回值</font>
- console.log 表达式的值为函数本身
- console.log(3)表达式的值为 **_<font color=red>undefined</font>_**,但是打印出来是 **<font color=red>_3_</font>** .

2. **语句**

- `var a=1` 是一个语句
- 表达式和语句的区别：
  语句和表达式的区别在于，前者主要为了进行某种操作，一般情况下不需要返回值；后者则是为了得到返回值，一定会返回一个值。凡是 JavaScript 语言中预期为值的地方，都可以使用表达式。比如，赋值语句的等号右边，预期是一个值，因此可以放置各种表达式。语句以分号结尾，一个分号就表示一个语句结束。多个语句可以写在一行内。

3. **大小写是不同**

- 分号前面可以没有任何内容，JavaScript 引擎将其视为空语句

```JavaScript
;;;
```

- 上面的代码就表示 3 个空语句。
- 表达式不需要分号结尾。一旦在表达式后面添加分号，则 JavaScript 引擎就将表达式视为语句，这样会产生一些没有任何意义的语句。

4. **大部分空格是没有实际意义的，除了 <font color=red>return</font> 后面**

## 标识符的规则

---

### 含义：标识符（identifier）指的是用来识别各种值的合法名称。最常见的标识符就是变量名，以及后面要提到的函数名。JavaScript 语言的标识符对大小写敏感，所以 a 和 A 是两个不同的标识符。

### 规则

- 第一个字符，可以是任意 Unicode 字母（包括英文字母和其他语言的字母），以及美元符号（<font color=yellow>\$</font>）和下划线（<font color=yellow>\_</font>）。
- 第二个字符及后面的字符，除了 Unicode 字母、美元符号和下划线，还可以用数字 <font color=yellow>0-9</font>。

### 变量名是标识符

```JavaScript
 var = 1
 var \$ = 1
 var **\_\_\_** = 1 <!--一般会被骂死，因为不清楚下划线有多少-->
 var 你好 = 'hi'
 arg0
 _tmp
 $elem
 Π
```

### 不合法的标识符

```JavaScript
1a //第一个标识符不能是数字
23 //同上
*** //标识符不能包含星号
a+b //标识符不能含有+
-d //标识符不能包含减号或者连接线
```

### 注释

```JavaScript
// .....  只能注释一行
/*....*/  全部都是注释的内容，不限行数
```

## if else 语句

---

1. <font color=red>**_if_** </font> 结构先判断一个表达式的值，然后根据值的真伪，执行不同的语句。所谓值，指的是 JavaScript 的两个特殊值，<font color=red>**_true_** </font> 表示真，<font color=red>**_false_** </font> 表示伪。

2. if(<font color=red>**_表达式_** </font>){<font color=red>**_语句 1_**</font>}else{<font color=red>**_语句 2_**</font>}

- 如果表达式成立，则执行语句 1；
- 如果表达式不成立，则执行语句 2.

```JavaScript
a = 1;
if (a === 2){
    console.log('a');
}else{
    console.log('a不等于2')
}
```

3. if...else 结构

- <font color=red>**_if_**</font> 代码块后面，还可以跟一个 <font color=red>**_else_**</font> 代码块，表示不满足条件时，所要执行的代码

```JavaScript
if (m === 3){
    //满足条件，执行语句1
}else{
    //不满足条件，执行语句2
}
```

4. if...else 语句连写

```JavaScript
if ( a ===0 ){
    // 满足条件，执行语句1
}else if ( a ===1 ) {
    // 满足条件，执行语句2
}else if ( a ===2 ) {
    // 满足条件，执行语句3
}else{
    // ....
}
```

- <font color=red>**_else_**</font> 代码块总是与离自己最近的那个 <font color=red>**_if_**</font> 语句配对。

```JavaScript
var m = 1;
var n = 2;
if ( m !== 1 )
if ( n === 2 )console.log('hello');
else console.log('world')
```

- 上面代码不会有任何输出， <font color=red>**_else_**</font> 代码块不会得到执行，因为它跟着的是最近的那个 <font color=red>**_if_**</font> 语句，相当于下面这样。

```JavaScript
if(m !==1){
  if(n===2){
      console.log('hello');
  }else{
      console.log('world');
  }
}
```

如果想让 <font color=red>**_else_**</font> 代码块跟随最上面的那个<font color=red>**_if_**</font> 语句，就要改变大括号的位置。

```JavaScript
if(m !==1){
  if(n===2){
      console.log('hello');
      }
}else{
      console.log('world');
}

//world
```

5. 三元运算符 ？：

- JavaScript 还有一个三元运算符（即该运算符需要三个运算子）?:，也可以用于逻辑判断。

```
(条件)？表达式1：表达式2
```

- 上面代码中，如果“条件”为 <font color=red>**_true_**</font> ，则返回“表达式 1”的值，否则返回“表达式 2”的值。

```JavaScript
var even(n % 2 === 0) ? true : false;
```

- 上面代码中，如果 n 可以被 2 整除，则 even 等于 true，否则等于 false。它等同于下面的形式。

```JavaScript
var even;
if (n % 2 ===0){
    even = true;
}else{
    even = false;
}
```

- 这个三元运算符可以被视为 <font color=red>**_*if...else...*_**</font> 的简写形式，因此可以用于多种场合。

```JavaScript
var msg = '数字'+n+'是'+(n % 2 ===0 ? '偶数';'奇数')；
```

- 上面代码利用三元运算符，在字符串之中插入不同的值。

## while for 语句

---

- <font color=red>**_While_**</font> 语句包括一个循环条件和一段代码块，只要条件为真，就不断循环执行代码块。

```JavaScript
while(条件1){
    语句1;
}
// 或者
while (条件2)
    语句2;

```

- 判断表达式真假
- 当表达式为真，执行语句，执行完再次判断表达式的真假
- 当表达式为假，执行后面的语句

```JavaScript
var i = 0;
while( i < 10 ){
    console.log(i)
    i = i+1;
}
```

- 上面的代码将循环 10 次，直到 i 等于 10 为止。
- 但是加上`console.log('done')`，就只会打印到 9，直接 done 结束。

* <font color=red>**_for_**</font> 语句是循环命令的另一种形式，可以指定循环的起点、终点和终止条件。它的格式如下。

```JavaScript
for (初始化表达式；条件；递增表达式)
  语句
// 或者
for (初始化表达式；条件；递增表达式){
    语句
}
```

- for 语句后面的括号里面，有三个表达式。

- 初始化表达式（initialize）：确定循环变量的初始值，只在循环开始时执行一次。
- 条件表达式（test）：每轮循环开始时，都要执行这个条件表达式，只有值为真，才继续进行循环。
- 递增表达式（increment）：每轮循环的最后一个操作，通常用来递增循环变量。
- 判断

```JavaScript
var a = 0.1;    //初始化
while(a !==1);  //判断
console.log(a); //循环体
a=a+0.1         //递增
```

- for 语法

```JavaScript
for (语句1;表达式2；语句3){
    循环体
}
```

- 先执行语句 1
- 然后判断表达式 2
- 如果为真，执行循环体，然后执行语句 3
- 如果为假，直接退出循环，执行后面的语句（不是语句 3）
- <font color=blue; size=3>**注意**</font>：for 语句四个部分，无论省略任何一个，或者全部都省略，都有可能造成死循环。

## break 和 continue

---

- <font color=blue; size=3>**break**</font>语句和<font color=blue; size=3>**continue**</font>语句都具有跳转作用，可以让代码不按既有的顺序执行。

- <font color=blue; size=3>**break**</font> 语句用于跳出代码块或循环。

```JavaScript
for ( var i = 0; i < 10 ; i++ ){
    if(i % 2 === 1 ){
        break
    }
}
```

- 上面代码当 i % 2 得到结果后，break 之后不会在走 i ++,直接跳到 for 后面去了

```JavaScript
for (var i = 0; i < 5 ; i++){
    console.log(i);
    if (i ===3)
    break;
}
// 0
// 1
// 2
// 3
```

- 上面代码执行到 i 等于 3，就会跳出循环

* <font color=blue>**_continue_**</font> 语句用于立即终止本轮循环，返回循环结构的头部，开始下一轮循环。

```JavaScript
for (var i = 0; i < 10 ; i++){
    if(1 % 2 === 1 ){
        continue
    }else{
        console.log(i)
    }
}
// 0
// 2
// 4
// 6
// 8
```

- 上面代码只有在 i 为偶数时，才会输出 i 的值。如果 i 为奇数，则直接进入下一轮循环。

* <font color=blue; size=3>**注意**</font>：有的语言用 next 取代 continue
* 如果存在多重循环，不带参数的 break 语句和 continue 语句都只针对最内层循环。

## 标签（label）

---

- JavaScript 语言允许，语句的前面有标签（label），相当于定位符，用于跳转到程序的任意位置，标签的格式如下。

```JavaScript
label:
标签
```

- 标签可以是任意的标识符，但不能是保留字，语句部分可以是任意语句。

- 标签通常与 break 语句和 continue 语句配合使用，跳出特定的循环。

```JavaScript
top:
for (var i = 0; i < 3; i++){
    for(var j = 0; j < 3; j++){
        if(i === 1 && j ===1 ) break top;
        console.log('i=' + i + ',j' +j);
    }
}
// i=0;j=0
// i=0;j=1
// i=0;j=2
// i=1;j=0
```

- 上面代码为一个双重循环区块，break 命令后面加上了 top 标签（注意，top 不用加引号），满足条件时，直接跳出双层循环。如果 break 语句后面不使用标签，则只能跳出内层循环，进入下一次的外层循环。

* 标签也可以用于跳出代码块

```JavaScript
foo:{
    console.log(1);
    break foo;
    console.log('本行不会输出');
}
console.log(2);

// 1
// 2
```

- break foo 会跳出复制代码块

* continue 语句也可以与标签配合使用。

```JavaScript
top:
for (var i = 0; i < 3; i++){
    for(var j = 0; j < 3; j++){
        if(i === 1 && j ===1 ) continue top;
        console.log('i=' + i + ',j' +j);
    }
}
// i=0;j=0
// i=0;j=1
// i=0;j=2
// i=1;j=0
// i=2;j=0
// i=2;j=1
// i=2;j=2
```

- 上面代码中，continue 命令后面有一个标签名，满足条件时，会跳过当前循环，直接进入下一轮外层循环。如果 continue 语句后面不使用标签，则只能进入下一轮的内层循环。

> 参考链接：https://wangdoc.com/javascript/basic/grammar.html

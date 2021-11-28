# 					TypeScript学习

## 1.什么是TS

### 1.TypeScript (简称: TS) 是JavaScript的超集(JS 有的TS都有)。

TypeScript = Type + JavaScript (为JS添加了类型系统)。

```typescript
// TypeScript 代码:有明确的类型，即: number ( 数值类型)
let age: number = 18
// JavaScript 代码:无明确的类型
let age = 18
```

![image-20210818175838971](https://i.loli.net/2021/08/21/jo2FzQAm1V4ypuk.png)

TypeScript是微软开发的开源编程语言，设计目标是开发大型应用。

可以在任何浏览器、任何计算机、任何操作系统上运行。

### 2.TS优势

JS的类型系统存在"先天缺陷”，绝大部分错误都是类型错误( Uncaught TypeError )。

●优势一:类型化思维方式，使得开发更加严谨，提前发现错误,减少改Bug时间。

●优势二:类型系统提高了代码可读性,并使维护和重构代码更加容易。

●优势三:补充了接口、枚举等开发大型应用时JS缺失的功能。

●Vue 3源码使用TS重写，释放出重要信号: TS 是趋势。

●Angular默认支持TS; React与TS完美配合，是很多大型项目的首选。

### 3.安装

```js
npm i -g typescript
```

输入安装命令: npm i -g typescript敲回车,来安装(注意:需要联网)

typescript:就是用来解析TS的工具包。提供了**tsc**命令,实现了TS > JS的转化。

### 4.简化执行TS

问题:每次修改代码后，都要重复执行两个命令才能执行TS代码，太繁琐。

执行Ts代码的两个步骤:

1 tsc hello. ts

2 node hello.js

**3.安装包@types/node**

**简化方式:使用ts-node包，"直接” 在Node.js中执行TS代码**。

**●安装命令: npm i-g ts-node.**

**●使用方式: ts-node hello.ts。**

ts-node包内部偷偷的将TS-> JS,然后，执行JS代码。

## 2.TS基础(js基础 狗头保命)

### 1.注释

注释有两种形式: 1单行注释2 多行注释。

单行：快捷键: ctrl + /

多行：快捷键: shift + alt+ a

### 2.输出语句

Nodejs会执行我们写的代码,为了能够知道代码执行的结果，就需要使用输出语句，将结果打印出来。

console.log('Hello TS')

●console 表示控制台，在Node.js中，指的是终端(黑窗口)。

●小括号中的内容,表示要打印的信息。

### 3.变量

#### 1.什么是变量

变量，是用来存储数据的容器，并且是可以变化的。

#### 2.变量的使用

变量的使用分为两步：1 声明变量并指定类型 2 给变量赋值。

```typescript
let age: number;
age = 18
```

声明变量的同时就赋值（变量的初始化）：

```typescript
let age:number=18;
```



#### 3.类型注解

```typescript
let age: number = 18 
//代码中的 : number 就是类型注解。
```

**类型注解：是一种为变量添加类型约束的方式。**

**重要：约定了什么类型，就只能给变量赋什么类型的值。**



#### 4.变量的命名规范

**变量名称只能出现：数字、字母、下划线（_）、美元符号（$），并且不能以 数字 开头。**

**注意：变量名称区分大小写。**

```typescript
//代码就是程序员的脸面，规范的代码，能让人觉得专业、优雅。
//推荐：变量名称要有意义，顾名思义。
// 有意义，推荐 
let age: number = 18 
// 无意义，不推荐 
let a: number = 18
```

**推荐：使用驼峰命名法（首字母小写，后面每个单词首字母大写）。**

```typescript
let cityName 
let yourAge
```

总结： 

l 规则：变量名称只能出现 数字、字母、下划线（_）、美元符号（$），并且不能以 数字 开头。 

注意：变量名称区分大小写。 

l 规范：变量名称要有意义，顾名思义。 

推荐：使用驼峰命名法（首字母小写，后面每个单词首字母大写）。



#### 5.数据类型概述

**TypeScript 中的数据类型分为两大类：1 原始类型（基本数据类型） 2 对象类型（复杂数据类型）。**

常用的基本数据类型有 5 个：**number** / **string** / **boolean** / undefined / null。

```typescript
// 变量 age 的类型是 number（数字类型）
let age: number = 18
// 此处的 'Hello TS' 是 string（字符串类型）
console.log('Hello TS')
```



#### 6.基本数据类型

##### 1.数字类型

数字类型：包含整数值和浮点型（小数）值。

```typescript
// 数字类型：整数 
let age: number = 18 
// 数字类型：小数 
let score: number = 99.9
```

##### **2 字符串类型**

字符串：由零个或多个字符串联而成的，用来表示文本信息。

字符串可以使用单引号（'）或双引号（"），推荐：使用单引号。

字符串类型的类型注解为：**string**，声明变量时要添加类型注解。

```typescript
let food: string = '糖葫芦'
```

##### **3 布尔类型**

布尔类型，用来表示真或假。 

只有两个值，分别是： true 和 false。true 表示真，false 表示假。

布尔类型的类型注解为：**boolean** 。

```typescript
// 真 
let isStudying: boolean = true 
// 假 
let isPlayingGame: boolean = false
```

##### **4 undefined、null**

共同特点：只有一个值，值为类型本身。 

**undefined** 类型的值为： undefined。 

**null** 类型的值为：null。 

```typescript
// 类型注解为：undefined 
let u: undefined = undefined 
// 类型注解为：null 
let n: null = null
```

**undefined：表示声明但未赋值的变量值（找不到值）。**

**null：表示声明了变量并已赋值，值为 null（能找到，值就是 null）。**

![image-20210818202042545](https://i.loli.net/2021/08/21/tXDxk8wEoLYCMQT.png)

**总结**

TypeScript 中常用的基本数据类型有 5 个。 

分别是：number（数字类型）/ string（字符串类型）/ boolean（布尔类型）/ undefined / null。 

重点是：**number** / **string** / **boolean**。 

补充概念：这些类型的**值**，也叫做字面量， 也就是从字面上就能看出来它是什么。

```typescript
18 // 数字字面量 
'保温杯里泡枸杞' // 字符串字面量 
true / false // 布尔字面量 
undefined 
null
```

### 4.运算符

#### 1.运算符概述

运算符也称为操作符，用来实现赋值(=).算术运算、比较等功能的符号。



#### 2.算术运算符

算术运算符包含:加(+)、减(-)、乘(*)、除(/) .

算术运算符:进行算术运算时使用的符号，用于两个数值之间的计算。

**注意：+ 号，不仅可以用于加法计算，还能实现字符串拼接。**

**规律：加号两边只要有一边是字符串，就执行字符串拼接。**



注意：除加号以外，其他**算术运算符只应该跟数字类型一起使用**。

其他方式：将字符串类型**转换**为数字类型。

记住：在字符串前面添加 **+** 号，可以将 **string** 转化为 **number**（字符串内容为数字时才有意义）。

#### 3.赋值运算符

赋值运算符：将等号右边的值赋值给它左边的变量，比如：等号（**=**）。

除了等号（**=**）之外，还包括：加等（**+=**）、减等（**-=**）、乘等（***=**）、除等（**/=**）。



#### 4.自增和自减运算符

自增（**++**）运算符是 += 1 的简化形式；自减（**--**）运算符是 -= 1 的简化形式。

更简洁的方式：**++**

```js
age++
```

解释：age**++** 会让变量 age 的值加 1。 

作用：自增（**++**）运算符用来实现变量的值加 1；自减（**--**）运算符实现变量的值减 1。 

注意：**++** 或 **--**，只能让变量的值增加或减少 **1**。

#### 5.比较运算符

比较运算符：用于比较两个数据的值，并返回其比较的结果，结果为布尔类型。

比较运算符包含 6 个：

大于（**>**） 

大于等于（**>=**） 

小于（**<**） 

 小于等于（**<=**） 

 等于（**===**） 或(==)

 不等于（**!==**）

#### 6.逻辑运算符

逻辑运算符通常用于**布尔类型**的计算，并且**结果也是布尔类型**。

与（逻辑与），用 **&&** 符号来表示。当 **&&** 两边的值**同时**为true，结果才为true；否则，为false。

或（逻辑或），用 **||** 符号来表示。当 **||** 两边的值**只要有一个**为true，结果就为true；否则，为false。

非（逻辑非），符号为 **!**（叹号），表示**取反**，即：truefalse 而 falsetrue。

总结： 

两个条件同时满足时，再执行操作，用什么？ 逻辑与 **&&** 

只要有一个条件满足时，就执行操作，用什么？ 逻辑或 **||** 

逻辑非，表示什么作用？ 取反 **!**



### 5.语句

#### 1.条件语句

条件语句：根据判断条件的结果（真或假），来执行不同的代码，从而实现不同功能。

条件执行时，首先判断条件是否满足。 

如果 **条件满足**，就做某件事情（情况1） 

如果 **条件不满足**，就做另外一件事情（情况2）

![image-20210820110834369](https://i.loli.net/2021/08/21/N6GzPTAcL8pdmEh.png)

**条件语句，也叫分支语句，不同的情况就是不同的分支**。

```typescript
let a:number=1;
if(a==0){
    return 1
}else if(a==1){
    return 0
}else{
    return 3
}
```



#### 2.三元运算符

```typescript
let a:number=1;
let b:boolean = a==1? true : false;
console.log(b)//true
```



#### 3.循环语句

```typescript
for(let i:number=0;i<10;i++){
    console.log(666)
}
```

**break** 和 **continue** 常用在循环语句中，用来改变循环的执行过程。

**for** 循环执行的特点是：连续且不间断。

**break** 能够让循环提前结束（终止循环）。

```typescript
for (let i: number = 1; i <= 5; i++) {
    if (i === 3) {
        break 
    }
    console.log('正在吃第' + i + '个包子') 
}
```

![image-20210820112244712](https://i.loli.net/2021/08/21/qQvAhnwc3RkBJHU.png)

**continue** 能够让循环间断执行（跳过本次循环，继续下一次循环）。

```typescript
for (let i: number = 1; i <= 5; i++) {
    if (i === 3) {
        continue 
    }
    console.log('正在吃第' + i + '个包子') 
}
```

![image-20210820112406848](https://i.loli.net/2021/08/21/HTJQqpI1W8ojkGE.png)



**for循环执行顺序**

![image-20210820151947786](https://i.loli.net/2021/08/21/1aUKyDEshH6PAnw.png)

![image-20210820152009225](https://i.loli.net/2021/08/21/YZzQOKnMq74NeLA.png)

### 6.断点调试

**借助断点调试，观察代码的执行过程。**

**安装code debugger插件**

![image-20210820160912844](https://i.loli.net/2021/08/21/GEeaLjxOS8y29dP.png)





### 7.数组

数组，是用于存放多个数据的集合。

注意：数组中，通常是相同类型的数据。

```typescript
let names: string[] = ['迪丽热巴', '古力娜扎', '马尔扎哈']
```

**创建数组有两种语法形式。** 

**语法一（推荐）：**

```typescript
let names: string[] = []

//[]（中括号）表示数组。如果数组中没有内容，就是一个空数组。
```

**数组的类型注解由两部分组成：类型+[]。此处表示字符串类型的数组（只能出现字符串类型）。**

数组，多个元素之间使用逗号（,）分隔。 

数组中的每一项内容称为：元素。



**语法二（不推荐）：**

```typescript
let names: string[] = new Array()
let names: string[] = new Array('迪丽热巴', '古力娜扎', '马尔扎哈')
```



#### 1.数组长度和索引

**数组长度：表示数组中元素的个数，通过数组的 length 属性来获取。**

**数组中元素的序号，称为：索引（下标），数组中的元素与索引一一对应。**

**注意：数组索引是从 0 开始的。**

**该数组的长度（length）和最大索引之间有什么关系？ 最大索引为：length - 1**



#### 2.**取值** 

从数组中，获取到某一个元素的值，就是从数组中取值。

数组中的元素与索引是一一对应的，通过索引获取到某一个元素的值。

**语法：**

**数组名称[索引]** 

```typescript
let strarr:string[]=['a','b','c'];
console.log(strarr[1])//b
```

####  **3.存值**

如果要修改数组中某个元素的值，就要使用数组存值。

技巧：先获取到要修改的元素，然后，再存值。

**语法：**

**数组名称[索引] = 新值**

```typescript
let strarr:string[]=['a','b','c'];
strarr[2]='d'
```

#### 4.**添加元素**

存值的语法是：数组名称[**索引**] = 新值，根据索引是否存在，**有两种功能：1 修改元素 2 添加元素。**

**添加元素的通用写法：数组名称[数组长度] = 新值**

```typescript
let strarr:string[]=['a','b','c'];
strarr[strarr.length]='d'
console.log(strarr)
```

![image-20210820164308796](https://i.loli.net/2021/08/21/WJvSawDGn59mHAC.png)

#### 5.遍历数组

遍历数组，也就是把数组中的所有元素挨个获取一次（比如，计算数组中所有数字的和）。

注意1：因为数组索引是从**0**开始的，所以计数器**i**的默认值为**0**。 

注意2：应该根据数组长度来计算，公式为数组长度减一，也就是：nums.length – 1（最大索引）。 

优势：不管数组中元素的数量怎么变化，for循环的判断条件不需要改动。

```typescript
let arr:number[]=[1,2,3,4,5];
let sum:number=0;
for(let i:number=0;i<arr.length;i++){
    sum+=arr[i]
}
console.log(sum)
```

![image-20210820164904531](https://i.loli.net/2021/08/21/9EtsZ2JzMcfmDiQ.png)

总结： 

遍历数组，也就是把数组中的所有元素挨个获取一次。 

问题1：如果要遍历数组应该使用什么语句？ **for**循环语句 

问题2：for循环计数器的默认值是多少？ 默认值为：**0** 

问题3：for循环的判断条件是什么？ **i < nums.length**



### 8.函数基础

使用**函数**来**包装（封装）相似的代码**，在需要的时候调用函数，相似的代码不再重复写。

**所谓函数，就是声明一次但却可以调用任意多次的一段代码**。 

```typescript
function sum(nums:number[]){
    let sum:number=0;
    for(let i:number=0;i<nums.length;i++){
        sum+=nums[i];
    }
    return sum
}
console.log(sum([1,2,3,4,5]))//输出：15
```

**意义**：实现代码**复用**，提升开发效率。 

**封装**：将一段代码包装起来，隐藏细节。



#### 1.函数的使用

函数的使用分为两步：1 声明函数 2 调用函数 （类比变量）。

**第一步**：声明函数 

function 函数名称() { 

函数体 

}

**函数名称：推荐以动词开头，因为函数表示做一件事情，实现一个功能。**

**函数体：表示要实现功能的代码，复用的代码。**



**第二步**：调用函数

函数名称()

**注意：只有调用函数后，函数中的代码才会执行。**

总结： 

1. 函数的基本使用分为哪两步？ 1 声明函数 2 调用函数 

2. 声明函数的关键字是什么？ **function** 

3. 不调用函数，函数中的代码会执行吗？ 不会



#### 2. 函数参数

```typescript
// 调用函数时，告诉函数要唱的歌曲名称 
sing('五环之歌') 
sing('探清水河') 
// 声明函数时，接收传入的歌曲名称 
function sing(songName: string) {
	console.log(songName) 
}
```

**函数参数的作用：增加了函数的灵活性、通用性，针对相同的功能，能够适应更多的数据（值）**。

函数参数分为两部分：**1 形参** **2 实参**。 

```typescript
function sing(songName: string) { } 
```



1.形参：声明函数时指定的参数，放在声明函数的小括号中（挖坑）。

**语法**：形参名称: 类型注解，类似于变量声明，但是没有赋值。

**作用**：指定函数可接收的数据。



2.实参：调用函数时传入的参数，放在调用函数的小括号中（填坑）。

**实参是一个具体的值（比如：‘字符串’、18、[]等），用来赋值给形参。**



形参和实参的总结： 

1.声明函数时的参数，叫什么？作用？ 形参，指定函数能够接收什么数据。 

2.调用函数时的参数，叫什么？作用？ 实参，是一个具体的值，用来赋值给形参。



#### **3 其他说明**

1. 根据具体的功能，函数参数可以有多个，参数之间使用逗号（,）来分隔。 

```typescript
function fn(name: string, age: number) { } 

fn('刘老师', 18) 
```

2. 实参和形参按照顺序，一一对应。 

```typescript
function fn(name: string, age: number) { } 

fn('刘老师', 18) // name -> '刘老师', age -> 18 
```

3. 实参必须符合形参的类型要求，否则会报错！ 

```typescript
function sing(songName: string) {} 

sing(18) // 报错！ 形参要求是 string 类型，但是，实参是 number 类型。
```

**技巧：调用函数时，鼠标放在函数名称上，会显示该函数的参数以及类型。**



#### 4.函数返回值

**函数返回值的作用**：将函数内部计算的结果返回，以便于使用该结果继续参与其他的计算。 

**注意：**如果没有指定函数的返回值，那么，函数返回值的默认类型为 **void**（空，什么都没有）。

**步骤：1 指定返回值类型 2 指定返回值**

1. 指定返回值类型

```typescript
function fn(): 类型注解 { }
```

在声明函数的小括号后面，通过 : 类型注解 指定。

```typescript
function fn(): number { }
```

2. 指定返回值 

```typescript
function fn(): 类型注解 { 
    return 返回值
}
```

在函数体中，使用 **return** 关键字来返回函数执行的结果。

**注意：返回值必须符合返回值类型的类型要求，否则会报错！**



1. 使用变量接收函数返回值 

```typescript
let result: 类型注解 = fn() 
```

使用变量接收函数返回值的时候，相当于：直接将返回值赋值给变量。 

```typescript
let result: number = 18 
```

**注意**：变量（result）的类型与函数（fn）的返回值类型要一致。 

然后，就可以使用这个变量（返回值），继续进行其他计算了。 

2. 直接使用函数调用的结果（返回值），进行其他计算 

```typescript
console.log( fn() * 10 )
```



#### **5. return 的说明**

1. 将函数内部的**计算结果返回**。 

```typescript
function fn(): number { 

return 18 

console.log('我不会执行，放在这，没有意义') 

} 
```

2. **终止函数代码执行**，即：return 后面的代码不会执行。 

3. return 只能在函数中使用，否则会报错。



4. return 可以单独使用（后面可以不跟内容），用来刻意终止函数的执行。 

```typescript
function play(age: number): void { 

if (age < 18) { 

return 

}

console.log('网吧上网好爽啊，王者、吃鸡两不误') 

}
```

play(16) // 情况1：进入if后return，后续代码不执行 

play(20) // 情况2：不进if，直接打印内容： 网吧上网好爽啊，王者、吃鸡两不误 

**注意：**如果函数没有返回值，默认返回值类型是：**void**（空），可省略不写。 

```typescript
function play(age: number) { /* ... */ }
```



**return** 的总结：

1. 能否在函数外面使用 return？ 不能 
2. return 后面不跟内容，单独使用，表示什么？ **刻意终止函数代码执行** 
3. return 后面的代码会执行吗？ **不会执行** 
4. 函数没有返回值，默认返回值类型是什么？ **void**



#### **函数基础总结**

函数，即：声明一次但却可以调用任意多次的一段代码。 

通过将要实现的功能，使用函数封装起来，实现代码**复用**，提升开发效率。

函数的三种主要内容： 1 参数 2 函数体 3 返回值。

![image-20210820181522400](https://i.loli.net/2021/08/21/Z2eBN9DQv6mbVtj.png)

### 9.函数进阶

#### **1. 函数调试** 

![image-20210820183734190](https://i.loli.net/2021/08/21/yC58lOTqDBbWc2a.png)

```typescript
function work() { 

console.log('早上9点开始工作') 

play() 

console.log('晚上6点结束工作') 

}

function play() { 

console.log('早上9:30开始吃鸡') 

console.log('晚上5:30结束吃鸡') 

}

work() 
```

**结论1：**函数里面，还可以继续调用其他函数。 

**结论2：**函数，按照顺序一行行的执行代码，当遇到调用其他函数时，先完成该函数调用，再继续执行代码。



#### **2. 变量作用域**

**一个变量的作用域指的是：代码中定义变量的区域，它决定了变量的使用范围。** 

在 TS（或JS）中，函数可以形成作用域，叫做：函数作用域。 

根据范围的不同，变量可以分为两种：**1 局部变量** **2 全局变量。** 

```typescript
function fn() { 

// 变量 num 是局部变量 

let num: number = 1 

console.log(num) // 此处能访问到变量 num 

}

fn() 

console.log(num) // 问题：此处能访问到变量 num 吗？ 不能
```

**局部变量**：表示在函数内部声明的变量，该变量只能在函数内部使用（局部地区有雨）。

**全局变量**：表示在函数外部声明的变量，该变量在当前 ts 文件的任何地方都可以使用。

```typescript
// 变量 num 是全局变量 

let num: number = 1 

function fn() { 

console.log(num) // 问题：此处能访问到变量 num 吗？ 能

}

fn() 

console.log(num) // 问题：此处能访问到变量 num 吗？ 能
```

### 10.对象（重点）

生活中，对象是一个具体的事物，比如：你的电脑、你的手机、古力娜扎、周杰伦（周董）等都是对象。 

程序员都知道：万物皆对象。 

这些具体的事物，都有自己的**特征**和**行为**：

**特征：**

你的电脑：尺寸、重量、价格等 

你的手机：品牌、屏幕大小、颜色等 

古力娜扎：年龄、身高、三围等 

**行为：**

你的电脑：浏览网页、写代码等 

你的手机：播放视频、吃鸡等 

古力娜扎：演电影、配音等



TypeScript 中的对象，是对生活中具体事物的抽象，使得我们可以通过代码来描述具体的事物。 

**TS 中的对象，也是由特征和行为组成的，它们有各自专业的名称：属性（特征）和方法（行为）。**

理解 TS 中的对象：一组相关属性和方法的**集合**，并且是**无序**的。

```typescript
// 演示对象： 

{ 

name: '周杰伦', 

gender: '男', 

height: 175, 

sing: funtion () { 

console.log('故事的小黄花 从出生那年就飘着') 

} 

}
```

总结： 

对象：一组相关属性和方法的**集合**，并且是**无序**的。 

在 TS 中，如果要描述一个事物或一组相关数据，就可以使用对象来实现。



#### **1.创建对象**

对象的语法：

```typescript
let person = {}
```

此处的 **{}**（花括号、大括号）表示对象。而对象中没有属性或方法时，称为：空对象。

对象中的属性或方法，采用键值对的形式，键、值之间使用冒号（:）来配对。

```typescript
let person = { 
键1: 值1, 
键2: 值2 
}
```

**键（key）=>名称 ，值（value）=> 具体的数据。**

**多个键值对之间，通过逗号（,）来分隔（类比数组）。**

```typescript
let person = { 
name: '刘老师', 
age: 18 
}
```

**属性和方法的区别**：值是不是函数，如果是，就称为方法；否则，就是普通属性。

**注意：**函数用作方法时可以省略function后面的函数名称，也叫做匿名函数。 

函数没有名称，如何调用？ 此处的sayHi相当于函数名称，将来通过对象的sayHi就可以调用了。 

如果一个函数是单独出现的，没有与对象关联，我们称为函数；否则，称为方法。



总结： 

**对象中的属性或方法，采用键值对的形式，因此，对象是无序键值对的集合**。 

1. 使用什么符号创建对象？  花括号（{}）
2. 键（key）、值（value）之间通过什么符号配对？ 冒号（:） 
3. 多个属性或方法之间使用什么符号分隔？ 逗号（,） 
4. 属性和方法的区别？ 值是不是函数



#### 2.接口

##### **1 对象的类型注解** 

TS 中的对象是结构化的，结构简单来说就是对象有什么属性或方法。

![image-20210820191109392](https://i.loli.net/2021/08/21/fJpw4cBaNdV5yCR.png)

对象类型注解的语法类似于对象自身的语法。

**注意**：**键值**对中的值是**类型**！（因为这是对象的类型注解）。 

**注意**：多个**键值对之间使用分号（;）分隔，并且分号可省略。**



**总结：** 

TS 中的对象是结构化的，在使用对象前，就可以根据需求，提前设计好对象的结构。 

对象的结构化类型（类型注解）：**建立一种契约，约束对象的结构**。

**注意点：**类型注解中键值对的值为**类型**！



##### **2 对象方法的类型注解**

技巧：鼠标放在变量名称上，VSCode就会给出该变量的类型注解。 

```typescript
let person: { 

sayHi: () => void 

sing: (name: string) => void 

sum: (num1: number, num2: number) => number 

} 
```

箭头（=>）左边小括号中的内容：**表示方法的参数类型**。 

箭头（=>）右边的内容：**表示方法的返回值类型**。 

**方法类型注解的关键点：1 参数 2 返回值。** 

注意：技巧是辅助，更重要的是理解。



##### **3 接口的使用** （重点）

直接在对象名称后面写类型注解的**坏处**：

1. 代码结构不简洁 
2. 无法复用类型注解。

**接口**：为对象的类型注解命名，并为你的代码建立契约来约束对象的**结构**。

![image-20210820192941643](https://i.loli.net/2021/08/21/6LnTXGFwgdtpa8q.png)

**推荐：**使用**接口来作为对象的类型注解**。

**interface 表示接口，接口名称约定以I开头。**

```typescript
interface IPerson {
    name:string;
    age:number;
    callname:(name:string)=>void;
}
let p1:IPerson ={
    name:'孙悟空',
    age:18,
    callname:(a:string)=>{
        console.log(a)
    }
}
p1.callname(p1.name)
```

#### 3.取值

取值，即：拿到对象中的属性或方法并使用。 

获取对象中的属性，称为：访问属性。 

获取对象中的方法**并调用**，称为：调用方法。

**访问属性** 

```typescript
let jay = { name: '周杰伦', height: 175 } 
```

需求：获取到对象（jay）的name属性。

```typescript
console.log(jay.name) 
```

**说明**：通过点语法（.）就可以访问对象中的属性。 

**技巧：**在输入点语法时，利用VSCode给出来的提示，利用上下键快速选择要访问的属性名称。



**调用方法** 

```typescript
let jay = { 
sing: function () { 
		console.log('故事的小黄花 从出生那年就飘着') 
	} 
} 
```

需求：调用对象（jay）的sing方法，让他唱歌。 

```typescript
jay.sing() 
```

**说明**：通过点语法（.）就先拿到方法名称，然后，通过小括号调用方法。

**补充说明：** 

```typescript
console.log(参数1, 参数2, ...) 
```

实际上，console是一个对象，而log是该对象提供的一个方法。 

并且，log方法可以**有多个参数**。 

```typescript
console.log('我叫', jay.name)
```



**总结：** 

通过什么符号，来访问对象中的属性或方法？ 点语法（.） 

注意：方法需要调用，所以，通过点语法拿到方法名称后，**不要忘记使用小括号调用！**

技巧：通过点语法，访问对象属性时，利用VSCode出来的提示，快速选择要访问的属性或方法。 

该技巧很实用，特别是访问别人创建的对象时（比如：console对象）。 



#### **4.存值** 

存值，即修改（设置）对象中属性的值。 

```typescript
let jay = { name: '周杰伦', height: 175 } 
```

需求：将对象（jay）的name属性的值修改为'周董'。 

```typescript
jay.name = '周董' 
```

解释：先通过点语法获取到name属性，然后，将新值'周董'赋值给该属性。 

```typescript
console.log(jay.name) // 周董 
```

**注意：设置的新值，也必须符合该属性的类型要求！** 

**注意：几乎不会修改对象中的方法。**



#### 总结

对象是对现实生活中具体事物（特征和行为）的抽象，可以使用对象来描述这些具体的事物。 

对象包含：1 属性 2 方法。 

简单来说：对象就是无序键值对的集合。 

对象是结构化的，它的类型注解就是从对象的结构（属性、方法）出发，进行类型约束和检查。 

**推荐：使用接口来作为对象的类型注解，建立一种契约，约束对象的结构。** 

TS中的数据类型分为两大类：1 原始类型（基本数据类型） 2 对象类型（复杂数据类型）。 

常用的基本数据类型有 5 个：number / string / boolean / undefined / null。 

复杂数据类型：object（对象、数组）、function（函数）。



### **11.内置对象**

**注意：内置对象中提供了非常多的方法或属性，以满足开发中各种各样的需求。** 

编程不是死记硬背，而是掌握一定的技巧，查文档就是最重要的一个。 

文档地址：[MDN]([MDN Web Docs (mozilla.org)](https://developer.mozilla.org/zh-CN/))（更标准） / [W3school]([w3school 在线教程](https://www.w3school.com.cn/index.html))（国内）



**总结：** 

内置对象，是 TS/JS 自带的一些基础对象，提供了TS开发时所需的基础或必要的能力。 

学什么？学内置对象中的属性或方法。 

怎么学？查文档，文档地址：MDN（更标准） / W3school（国内）

## 3.**TS 的类型推论(重点)**

在 TS 中，某些没有明确指出类型的地方，类型推论会帮助提供类型。 

换句话说：由于类型推论的存在，这些地方，类型注解可以省略不写！ 

发生类型推论的**2种常见场景：**

1. 声明变量并初始化时 
2. 决定函数返回值时。 

```typescript
let age: number = 18 // => let age = 18

function sum(num1: number, num2: number): number { return num1 + num2 } 

// => 

function sum(num1: number, num2: number) { return num1 + num2 }
```



**注意：这两种情况下，类型注解可以省略不写！** 

**推荐：**能省略类型注解的地方，就省略（偷懒、充分利用TS类型推论的能力，提升开发效率）。 

学习的时候，培养大家去建立类型思维；出师了，可以去繁就简。



## 4.**浏览器中运行TS** 

注意：浏览器中只能运行 JS，**无法直接运行** **TS**，因此，需要将 TS 转化为 JS 然后再运行。

浏览器中运行 TS 的步骤： 

1. 使用命令 **tsc** index.ts 将 ts 文件转化为 js 文件。

2. 在页面中，使用 script 标签引入生成的 js 文件（注意是 js 文件）。

```html
<script src="./index.js"></script>
```

问题：每次修改 ts 文件后，都要重新运行 tsc 命令将 ts 转化为 js 。 

解决方式：使用 tsc 命令的监视模式。

```js
tsc --watch index.ts
```

**解释**： --watch 表示启用监视模式，只要重新保存了 ts 文件，就会自动调用 tsc 将 ts 转化为 js。



## 5.**DOM 操作** 

**DOM（Document Object Modal）：文档对象模型。** 

DOM 是浏览器提供的（**浏览器特有**），专门用来**操作网页内容**的一些 JS 对象。 

**目的**：让我们可以使用 JS/TS 代码来操作页面（HTML）内容，让页面“动”起来，从而实现 Web 开发。 

HTML：超文本标记语言，用来创建网页结构。 

**两者的关系**：浏览器根据 HTML 内容创建相应的 DOM 对象，也就是：每个 HTML 标签都有对应的 DOM 对象。

![image-20210821122153375](https://i.loli.net/2021/08/21/1RIiq2FmL8KrT6b.png)

### 1.学习四个常用 DOM 操作：

**1 获取 DOM 元素（DOM 对象） 2 设置样式 3 设置内容 4 绑定（解绑）事件**。 

DOM 操作的套路（技巧）：先找人 后做事。 

1. 做事：设置样式、内容、绑定（解绑）事件。 
2. 找人：获取 DOM 元素。 

比如： 将 p 标签中的内容修改为：天青色等烟雨而我在等你。 

步骤： 1 获取 p 元素 2 设置内容。



### **2 获取元素** 

常用方法有两个： 

**querySelector(selector)** 作用：获取某一个 DOM 元素。 

**querySelectorAll(selector)** 作用：同时获取多个 DOM 元素。



1. **获取一个 DOM 元素：** 

```typescript
document.querySelector(selector) 
```

document 对象：文档对象（整个页面），是操作页面内容的入口对象。 

selector 参数：是一个 CSS 选择器（标签、类、id 选择器等）。 

作用：查询（获取）与选择器参数匹配的 DOM 元素，但是，只能获取到第一个！ 

推荐：使用 id 选择器（唯一）。

```typescript
let title = document.querySelector('#title')
```

2. **获取多个 DOM 元素：** 

```typescript
document.querySelectorAll(selector) 
```

作用：获取所有与选择器参数匹配的 DOM 元素，返回值是一个列表。 

推荐：使用 class 选择器。 

示例：

```typescript
let list = document.querySelectorAll('.a') 
```

解释：获取页面中所有 class 属性包含 a 的元素。



### 3.类型断言（重点）

**类型断言** 

**问题**：调用 querySelector() 通过 id 选择器获取 DOM 元素时，拿到的元素类型都是 Element。 

因为无法根据 id 来确定元素的类型，所以，该方法就返回了一个**宽泛**的类型：元素（Element）类型。 

不管是 h1 还是 img 都是元素。 

**导致新问题：无法访问 img 元素的 src 属性了。** 

**因为：Element 类型只包含所有元素共有的属性和方法（比如：id 属性）。**



**解决方式：**使用类型断言，来手动指定**更加具体**的类型（比如，此处应该比 Element 类型更加具体）。 

语法：

```typescript
值 as 更具体的类型 
```

比如：

```typescript
let img = document.querySelector('#image') as HTMLImageElement 
```

解释：我们确定 id="image" 的元素是图片元素，所以，**我们将类型指定为 HTMLImageElement。** 

技巧：通过 **console.dir() 打印 DOM 元素**，在属性的最后面，即可看到该元素的类型。



**总结**： 

类型断言：手动指定**更加具体（精确）**的类型。 

使用场景：当你比 TS 更了解某个值的类型，并且需要指定更具体的类型时。 

```typescript
// document.querySelector() 方法的返回值类型为： Element 

// 如果是 h1 标签： 

let title = document.querySelector('#title') as HTMLHeadingElement 

// 如果是 img 标签： 

let image = document.querySelector('#image') as HTMLImageElement 

//技巧：通过 console.dir() 打印 DOM 对象，来查看该元素的类型。
```

### 4.**操作文本内容** 

读取：

```typescript
dom.innerText 
```

设置：

```typescript
dom.innerText = '等你下课' 
```

**注意**：需要通过类型断言来指定 DOM 元素的具体类型，才可以使用 innerText 属性。

**注意：**设置内容时，会**覆盖原来的内容**。如何实现追加内容（比如，青花瓷 =>青花瓷 – 周杰伦）？ 

```typescript
dom.innerText = dom.innerText + ' – 周杰伦' 

// 简化 

dome.innerText += ' – 周杰伦'
```



### 5.**操作样式** 

两种方式： 

1. dom.style 属性：行内样式操作，可以设置每一个样式属性（比如，字体大小、文字颜色等）。 
2. dom.classList 属性：类样式操作，也就是操作类名，比如，添加类名、移除类名等。

1. **style 属性（行内样式）** 

**读取：**

```typescript
dom.style.样式名称 
```

**设置：**

```typescript
dom.style.样式名称 = 样式值 
```

说明：所有的样式名称都与 CSS 相通，但**命名规则为驼峰命名法。** 

```typescript
dom.style.fontSize = '30px' 

dom.style.display = 'none'
```

```typescript
//测试
let box=document.getElementsByTagName('div')[0] as HTMLDivElement;
box.innerHTML='你好ts'
box.style.fontSize='25px'
box.style.backgroundColor='red'
box.style.width="300px"
box.style.height="300px"
console.dir(box)
```

2. **classList 属性（类样式）** 

包含三个常用方法：添加、移除、判断是否存在。 

**添加：**

```typescript
dom.classList.add(类名1, 类名2, ...) 
```

**参数表示：要添加的类名，可以同时添加多个。** 

比如：

```html
<p class="a"></p> 
```

```typescript
dom.classList.add('b', 'c') // 添加 class 样式 ==> class="a b c"
```

**移除：**

```typescript
dom.classList.remove(类名1, 类名2, ...) 
```

**参数表示：要移除的类名，可以同时移除多个。** 

比如：

```html
<p class="a b c"></p> 
```

```typescript
dom.classList.remove('a', 'c') // 移除 class 样式 ==> class="b"
```



**判断类名是否存在：** 

```typescript
let has = dom.classList.contains(类名) 
```

**参数表示：要判断存在的类名。** 

比如：

```html
<p class="b"></p> 
```

```typescript
dom.classList.contains('a') // false 

dom.classList.contains('b') // true
```



**总结：** 

类样式（classList）的操作有三种： 

```typescript
// 添加 

dom.classList.add('a', 'b') 

// 移除 

dom.classList.remove('b', 'c') 

// 判断是否存在 

let has = dom.classList.contains('a')
```



### **6. 操作事件** 

在浏览网页时，我们经常会通过移入鼠标、点击鼠标、敲击键盘等操作，来使用网站提供的功能。 

如果要让我们自己实现这样的功能，就需要通过操作事件来实现了。 

实际上，移入鼠标、点击鼠标、敲击键盘等，都是常见的 DOM 事件。 

操作事件的两个方法： 

```typescript
addEventListener //添加（绑定）事件。 

removeEventListener// 移除（解绑）事件。
```

1. addEventListener 添加事件 

作用：给 DOM 元素添加事件。 

```typescript
dom.addEventListener(事件名称, 事件处理程序) 
```

事件名称：字符串，比如：'click'（鼠标点击事件）、'mouseenter'（鼠标进入事件）。 

事件处理程序：回调函数，指定要实现的功能，该函数会在触发事件时调用。 

示例：鼠标点击按钮，打印内容。 

```typescript
btn.addEventListener('click', function () { 

console.log('鼠标点击事件触发了') 

})

```

**事件对象（event），是事件处理程序（回调函数）的参数。** 

表示：与当前事件相关的信息，比如：**事件类型（type）**、**触发事件的 DOM 元素（target）等**。 

```typescript
btn.addEventListener('click', function (event) { 
	console.log(event.type) // click 
	console.log(event.target) // btn 元素 
})
```

2. removeEventListener 移除事件 

**作用**：移除给 DOM 元素添加的事件，移除后，事件就不再触发了。 

```typescript
dom.removeEventListener(事件名称, 事件处理程序) 
```

事件名称：同添加事件的第一个参数。 

事件处理程序：**必须要跟添加事件时的事件处理程序是同一个**，否则无法移除！



正确方式： 

```typescript
function handleClick() {} 

btn.addEventListener('click', handleClick) 

btn.removeEventListener('click', handleClick) 
```

**说明**：添加和移除事件时，事件处理程序是同一个，都是函数 handleClick。 

错误演示： 

```typescript
btn.addEventListener('click', function () {}) 

btn.removeEventListener('click', function () {}) 
```

**注意：**以上两个函数虽然长的一样，却是不同的函数（双胞胎，不是同一个人）。



**如果事件只需要触发一次，可以在添加事件时处理。** 

处理方式：传入第三个参数，将 once 属性设置为 true。 

```typescript
btn.addEventListener('click', function () {}, { once: true }) 
```

once ：如果值为 true，会在触发事件后，自动将事件移除，达到只触发一次的目的。



## **6.函数声明形式的事件处理程序说明**

1. 可以先使用函数，再声明函数。 

```typescript
btn.addEventListener('click', handleClick) 

function handleClick() {} 

//原因：函数声明在当前 ts 文件中的任意位置都有定义。 

// 1 先调用函数 

fn() 

// 2 再声明函数 

function fn() {}
```

2. **使用事件对象参数时，应该指定类型注解，否则，访问事件对象的属性时没有任何提示**。 

```typescript
btn.addEventListener('click', handleClick) 

function handleClick(event: MouseEvent) { 

console.log(event.target) 

} 
```

**技巧：**使用原始方式（匿名回调函数）查看参数类型。

## 7.高级

### 1、基本类型

- 类型声明

  - 类型声明是TS非常重要的一个特点

  - 通过类型声明可以指定TS中变量（参数、形参）的类型

  - 指定类型后，当为变量赋值时，TS编译器会自动检查值是否符合类型声明，符合则赋值，否则报错

  - 简而言之，类型声明给变量设置了类型，使得变量只能存储某种类型的值

  - 语法：

    - ```typescript
      let 变量: 类型;
      
      let 变量: 类型 = 值;
      
      function fn(参数: 类型, 参数: 类型): 类型{
          ...
      }
      ```

- 自动类型判断

  - TS拥有自动的类型判断机制
  - 当对变量的声明和赋值是同时进行的，TS编译器会自动判断变量的类型
  - 所以如果你的变量的声明和赋值时同时进行的，可以省略掉类型声明

- 类型：

  |  类型   |       例子        |              描述              |
  | :-----: | :---------------: | :----------------------------: |
  | number  |    1, -33, 2.5    |            任意数字            |
  | string  | 'hi', "hi", `hi`  |           任意字符串           |
  | boolean |    true、false    |       布尔值true或false        |
  | 字面量  |      其本身       |  限制变量的值就是该字面量的值  |
  |   any   |         *         |            任意类型            |
  | unknown |         *         |         类型安全的any          |
  |  void   | 空值（undefined） |     没有值（或undefined）      |
  |  never  |      没有值       |          不能是任何值          |
  | object  |  {name:'孙悟空'}  |          任意的JS对象          |
  |  array  |      [1,2,3]      |           任意JS数组           |
  |  tuple  |       [4,5]       | 元素，TS新增类型，固定长度数组 |
  |  enum   |    enum{A, B}     |       枚举，TS中新增类型       |

- number

  - ```typescript
    let decimal: number = 6;
    let hex: number = 0xf00d;
    let binary: number = 0b1010;
    let octal: number = 0o744;
    let big: bigint = 100n;
    ```

- boolean

  - ```typescript
    let isDone: boolean = false;
    ```

- string

  - ```typescript
    let color: string = "blue";
    color = 'red';
    
    let fullName: string = `Bob Bobbington`;
    let age: number = 37;
    let sentence: string = `Hello, my name is ${fullName}.
    
    I'll be ${age + 1} years old next month.`;
    ```

- 字面量

  - 也可以使用字面量去指定变量的类型，通过字面量可以确定变量的取值范围

  - ```typescript
    let color: 'red' | 'blue' | 'black';
    let num: 1 | 2 | 3 | 4 | 5;
    ```

- any

  - ```typescript
    let d: any = 4;
    d = 'hello';
    d = true;
    ```

- unknown

  - ```typescript
    let notSure: unknown = 4;
    notSure = 'hello';
    ```

- void

  - ```typescript
    let unusable: void = undefined;
    ```

- never

  - ```typescript
    function error(message: string): never {
      throw new Error(message);
    }
    ```

- object（没啥用）

  - ```typescript
    let obj: object = {};
    
    let c:{name:string,[propName:string]:any}={name:'张三',age:18}
    let d:(a:number,b:number)=>number;
    d=(a,b)=>{
        return a+b
    }
    console.log(d(1,2))
    ```

- array

  - ```typescript
    let list: number[] = [1, 2, 3];
    let list: Array<number> = [1, 2, 3];
    ```

- tuple

  - ```typescript
    let x: [string, number];
    x = ["hello", 10]; 
    ```

- enum

  - ```typescript
    enum Color {
      Red,
      Green,
      Blue,
    }
    let c: Color = Color.Green;
    
    enum Color {
      Red = 1,
      Green,
      Blue,
    }
    let c: Color = Color.Green;
    
    enum Color {
      Red = 1,
      Green = 2,
      Blue = 4,
    }
    let c: Color = Color.Green;
    ```

- type

  关键字

  ```typescript
  let a:[string,number]=['hello',10]
  console.log(a)
  type myType= 1|2|3|4;//自定义类型
  let c:myType=2
  type mytype1=[string,string]
  let arr:mytype1=['hello','nh']
  ```

  

- 类型断言

  - 有些情况下，变量的类型对于我们来说是很明确，但是TS编译器却并不清楚，此时，可以通过类型断言来告诉编译器变量的类型，断言有两种形式：

    - 第一种

      - ```typescript
        let someValue: unknown = "this is a string";
        let strLength: number = (someValue as string).length;
        ```

    - 第二种

      - ```typescript
        let someValue: unknown = "this is a string";
        let strLength: number = (<string>someValue).length;
        ```

        

### 2、编译选项

- 自动编译文件

  - 编译文件时，使用 -w 指令后，TS编译器会自动监视文件的变化，并在文件发生变化时对文件进行重新编译。

  - 示例：

    - ```powershell
      tsc xxx.ts -w
      ```

- 自动编译整个项目

  - 如果直接使用tsc指令，则可以自动将当前项目下的所有ts文件编译为js文件。

  - 但是能直接使用tsc命令的前提时，要先在项目根目录下创建一个ts的配置文件 tsconfig.json

  - tsconfig.json是一个JSON文件，添加配置文件后，只需只需 tsc 命令即可完成对整个项目的编译

  - 配置选项：

    - include

      - 定义希望被编译文件所在的目录

      - 默认值：["\*\*/\*"]

      - 示例：

        - ```json
          "include":["src/**/*", "tests/**/*"]
          // /** 任意文件夹
          // /* 任意文件
          ```

        - 上述示例中，所有src目录和tests目录下的文件都会被编译

    - exclude

      - 定义需要排除在外的目录

      - 默认值：["node_modules", "bower_components", "jspm_packages"]

      - 示例：

        - ```json
          "exclude": ["./src/hello/**/*"]
          ```

        - 上述示例中，src下hello目录下的文件都不会被编译

    - extends

      - 定义被继承的配置文件

      - 示例：

        - ```json
          "extends": "./configs/base"
          ```

        - 上述示例中，当前配置文件中会自动包含config目录下base.json中的所有配置信息

    - files

      - 指定被编译文件的列表，只有需要编译的文件少时才会用到

      - 示例：

        - ```json
          "files": [
              "core.ts",
              "sys.ts",
              "types.ts",
              "scanner.ts",
              "parser.ts",
              "utilities.ts",
              "binder.ts",
              "checker.ts",
              "tsc.ts"
            ]
          ```

        - 列表中的文件都会被TS编译器所编译

      - compilerOptions

        - 编译选项是配置文件中非常重要也比较复杂的配置选项

        - 在compilerOptions中包含多个子选项，用来完成对编译的配置

          - 项目选项

            - target

              - 设置ts代码编译的目标版本

              - 可选值：

                - ES3（默认）、ES5、ES6/ES2015、ES7/ES2016、ES2017、ES2018、ES2019、ES2020、ESNext

              - 示例：

                - ```json
                  "compilerOptions": {
                      "target": "ES6"
                  }
                  ```

                - 如上设置，我们所编写的ts代码将会被编译为ES6版本的js代码

            - lib

              - 指定代码运行时所包含的库（宿主环境）

              - 可选值：

                - ES5、ES6/ES2015、ES7/ES2016、ES2017、ES2018、ES2019、ES2020、ESNext、DOM、WebWorker、ScriptHost ......

              - 示例：

                - ```json
                  "compilerOptions": {
                      "target": "ES6",
                      "lib": ["ES6", "DOM"],
                      "outDir": "dist",
                      "outFile": "dist/aa.js"
                  }
                  ```

            - module

              - 设置编译后代码使用的模块化系统

              - 可选值：

                - CommonJS、UMD、AMD、System、ES2020、ESNext、None

              - 示例：

                - ```typescript
                  "compilerOptions": {
                      "module": "CommonJS"
                  }
                  ```

            - outDir

              - 编译后文件的所在目录

              - 默认情况下，编译后的js文件会和ts文件位于相同的目录，设置outDir后可以改变编译后文件的位置

              - 示例：

                - ```json
                  "compilerOptions": {
                      "outDir": "dist"
                  }
                  ```

                - 设置后编译后的js文件将会生成到dist目录

            - outFile

              - 将所有的文件编译为一个js文件

              - 默认会将所有的编写在全局作用域中的代码合并为一个js文件，如果module制定了None、System或AMD则会将模块一起合并到文件之中

              - 示例：

                - ```json
                  "compilerOptions": {
                      "outFile": "dist/app.js"
                  }
                  ```

            - rootDir

              - 指定代码的根目录，默认情况下编译后文件的目录结构会以最长的公共目录为根目录，通过rootDir可以手动指定根目录

              - 示例：

                - ```json
                  "compilerOptions": {
                      "rootDir": "./src"
                  }
                  ```

            - allowJs

              - 是否对js文件编译

            - checkJs

              - 是否对js文件进行检查

              - 示例：

                - ```json
                  "compilerOptions": {
                      "allowJs": true,
                      "checkJs": true
                  }
                  ```

            - removeComments

              - 是否删除注释
              - 默认值：false

            - noEmit

              - 不对代码进行编译
              - 默认值：false

            - sourceMap

              - 是否生成sourceMap
              - 默认值：false

              

          - 严格检查

            - strict
              - 启用所有的严格检查，默认值为true，设置后相当于开启了所有的严格检查
            - alwaysStrict
              - 总是以严格模式对代码进行编译
            - noImplicitAny
              - 禁止隐式的any类型
            - noImplicitThis
              - 禁止类型不明确的this
            - strictBindCallApply
              - 严格检查bind、call和apply的参数列表
            - strictFunctionTypes
              - 严格检查函数的类型
            - strictNullChecks
              - 严格的空值检查
            - strictPropertyInitialization
              - 严格检查属性是否初始化

          - 额外检查

            - noFallthroughCasesInSwitch
              - 检查switch语句包含正确的break
            - noImplicitReturns
              - 检查函数没有隐式的返回值
            - noUnusedLocals
              - 检查未使用的局部变量
            - noUnusedParameters
              - 检查未使用的参数

          - 高级

            - allowUnreachableCode
              - 检查不可达代码
              - 可选值：
                - true，忽略不可达代码
                - false，不可达代码将引起错误
            - noEmitOnError
              - 有错误的情况下不进行编译
              - 默认值：false

### 3、webpack

- 通常情况下，实际开发中我们都需要使用构建工具对代码进行打包，TS同样也可以结合构建工具一起使用，下边以webpack为例介绍一下如何结合构建工具使用TS。

- 步骤：

  1. 初始化项目

     - 进入项目根目录，执行命令 ``` npm init -y```
       - 主要作用：创建package.json文件

  2. 下载构建工具

     - ```npm i -D webpack webpack-cli webpack-dev-server typescript ts-loader clean-webpack-plugin```
       - 共安装了7个包
         - webpack
           - 构建工具webpack
         - webpack-cli
           - webpack的命令行工具
         - webpack-dev-server
           - webpack的开发服务器
         - typescript
           - ts编译器
         - ts-loader
           - ts加载器，用于在webpack中编译ts文件
         - html-webpack-plugin
           - webpack中html插件，用来自动创建html文件
         - clean-webpack-plugin
           - webpack中的清除插件，每次构建都会先清除目录

  3. 根目录下创建webpack的配置文件webpack.config.js

     - ```javascript
       const path = require("path");
       const HtmlWebpackPlugin = require("html-webpack-plugin");
       const { CleanWebpackPlugin } = require("clean-webpack-plugin");
       
       module.exports = {
           optimization:{
               minimize: false // 关闭代码压缩，可选
           },
       
           entry: "./src/index.ts",
           
           devtool: "inline-source-map",
           
           devServer: {
               contentBase: './dist'
           },
       
           output: {
               path: path.resolve(__dirname, "dist"),
               filename: "bundle.js",
               environment: {
                   arrowFunction: false // 关闭webpack的箭头函数，可选
               }
           },
       
           resolve: {
               extensions: [".ts", ".js"]
           },
           
           module: {
               rules: [
                   {
                       test: /\.ts$/,
                       use: {
                          loader: "ts-loader"     
                       },
                       exclude: /node_modules/
                   }
               ]
           },
       
           plugins: [
               new CleanWebpackPlugin(),
               new HtmlWebpackPlugin({
                   title:'TS测试'
               }),
           ]
       
       }
       ```

  4. 根目录下创建tsconfig.json，配置可以根据自己需要

     - ```json
       {
           "compilerOptions": {
               "target": "ES2015",
               "module": "ES2015",
               "strict": true
           }
       }
       ```

  5. 修改package.json添加如下配置

     - ```json
       {
         ...略...
         "scripts": {
           "test": "echo \"Error: no test specified\" && exit 1",
           "build": "webpack",
           "start": "webpack serve --open chrome.exe"
         },
         ...略...
       }
       ```

  6. 在src下创建ts文件，并在并命令行执行```npm run build```对代码进行编译，或者执行```npm start```来启动开发服务器

     

### 4、Babel

- 经过一系列的配置，使得TS和webpack已经结合到了一起，除了webpack，开发中还经常需要结合babel来对代码进行转换以使其可以兼容到更多的浏览器，在上述步骤的基础上，通过以下步骤再将babel引入到项目中。

  1. 安装依赖包：

     - ```npm i -D @babel/core @babel/preset-env babel-loader core-js```
     - 共安装了4个包，分别是：
       - @babel/core
         - babel的核心工具
       - @babel/preset-env
         - babel的预定义环境
       - @babel-loader
         - babel在webpack中的加载器
       - core-js
         - core-js用来使老版本的浏览器支持新版ES语法

  2. 修改webpack.config.js配置文件

     - ```javascript
       ...略...
       module: {
           rules: [
               {
                   test: /\.ts$/,
                   use: [
                       {
                           loader: "babel-loader",
                           options:{
                               presets: [
                                   [
                                       "@babel/preset-env",
                                       {
                                           "targets":{
                                               "chrome": "58",
                                               "ie": "11"
                                           },
                                           "corejs":"3",
                                           "useBuiltIns": "usage"
                                       }
                                   ]
                               ]
                           }
                       },
                       {
                           loader: "ts-loader",
       
                       }
                   ],
                   exclude: /node_modules/
               }
           ]
       }
       ...略...
       ```

     - 如此一来，使用ts编译后的文件将会再次被babel处理，使得代码可以在大部分浏览器中直接使用，可以在配置选项的targets中指定要兼容的浏览器版本。





# 第二章：面向对象

面向对象是程序中一个非常重要的思想，它被很多同学理解成了一个比较难，比较深奥的问题，其实不然。面向对象很简单，简而言之就是程序之中所有的操作都需要通过对象来完成。

- 举例来说：
  - 操作浏览器要使用window对象
  - 操作网页要使用document对象
  - 操作控制台要使用console对象

一切操作都要通过对象，也就是所谓的面向对象，那么对象到底是什么呢？这就要先说到程序是什么，计算机程序的本质就是对现实事物的抽象，抽象的反义词是具体，比如：照片是对一个具体的人的抽象，汽车模型是对具体汽车的抽象等等。程序也是对事物的抽象，在程序中我们可以表示一个人、一条狗、一把枪、一颗子弹等等所有的事物。一个事物到了程序中就变成了一个对象。

在程序中所有的对象都被分成了两个部分数据和功能，以人为例，人的姓名、性别、年龄、身高、体重等属于数据，人可以说话、走路、吃饭、睡觉这些属于人的功能。数据在对象中被成为属性，而功能就被称为方法。所以简而言之，在程序中一切皆是对象。

## 1、类（class）

要想面向对象，操作对象，首先便要拥有对象，那么下一个问题就是如何创建对象。要创建对象，必须要先定义类，所谓的类可以理解为对象的模型，程序中可以根据类创建指定类型的对象，举例来说：可以通过Person类来创建人的对象，通过Dog类创建狗的对象，通过Car类来创建汽车的对象，不同的类可以用来创建不同的对象。

- 定义类：

  - ```typescript
    class 类名 {
    	属性名: 类型;
    	
    	constructor(参数: 类型){
    		this.属性名 = 参数;
    	}
    	
    	方法名(){
    		....
    	}
    
    }
    ```

- 示例：

  - ```typescript
    class Person{
        name: string;
        age: number;
    
        constructor(name: string, age: number){
            this.name = name;
            this.age = age;
        }
    
        sayHello(){
            console.log(`大家好，我是${this.name}`);
        }
    }
    ```

- 使用类：

  - ```typescript
    const p = new Person('孙悟空', 18);
    p.sayHello();
    ```

## 2、面向对象的特点

- **封装**

  - 对象实质上就是属性和方法的容器，它的主要作用就是存储属性和方法，这就是所谓的封装

  - 默认情况下，对象的属性是可以任意的修改的，为了确保数据的安全性，在TS中可以对属性的权限进行设置

  - **只读属性**（readonly）：

    - 如果在声明属性时添加一个readonly，则属性便成了只读属性无法修改

  - **TS中属性具有三种修饰符**：

    - **public**（默认值），可以在类、子类和对象中修改
    - **protected** ，可以在类、子类中修改
    - **private** ，可以在类中修改

  - 示例：

    - public

      - ```typescript
        class Person{
            public name: string; // 写或什么都不写都是public
            public age: number;
        
            constructor(name: string, age: number){
                this.name = name; // 可以在类中修改
                this.age = age;
            }
        
            sayHello(){
                console.log(`大家好，我是${this.name}`);
            }
        }
        
        class Employee extends Person{
            constructor(name: string, age: number){
                super(name, age);
                this.name = name; //子类中可以修改
            }
        }
        
        const p = new Person('孙悟空', 18);
        p.name = '猪八戒';// 可以通过对象修改
        ```

    - protected

      - ```typescript
        class Person{
            protected name: string;
            protected age: number;
        
            constructor(name: string, age: number){
                this.name = name; // 可以修改
                this.age = age;
            }
        
            sayHello(){
                console.log(`大家好，我是${this.name}`);
            }
        }
        
        class Employee extends Person{
        
            constructor(name: string, age: number){
                super(name, age);
                this.name = name; //子类中可以修改
            }
        }
        
        const p = new Person('孙悟空', 18);
        p.name = '猪八戒';// 不能修改
        ```

    - private

      - ```typescript
        class Person{
            private name: string;
            private age: number;
        
            constructor(name: string, age: number){
                this.name = name; // 可以修改
                this.age = age;
            }
        
            sayHello(){
                console.log(`大家好，我是${this.name}`);
            }
        }
        
        class Employee extends Person{
        
            constructor(name: string, age: number){
                super(name, age);
                this.name = name; //子类中不能修改
            }
        }
        
        const p = new Person('孙悟空', 18);
        p.name = '猪八戒';// 不能修改
        ```

  - **属性存取器**

    - 对于一些不希望被任意修改的属性，可以将其**设置为private**

    - 直接将其设置为private将导致无法再通过对象修改其中的属性

    - 我们可以在类中定义一组读取、设置属性的方法，这种对属性读取或设置的属性被称为属性的存取器

    - 读取属性的方法叫做setter方法，设置属性的方法叫做getter方法

    - 示例：

      - ```typescript
        class Person{
            private _name: string;
        
            constructor(name: string){
                this._name = name;
            }
        
            get name(){
                return this._name;
            }
        
            set name(name: string){
                this._name = name;
            }
        
        }
        
        const p1 = new Person('孙悟空');
        console.log(p1.name); // 通过getter读取name属性
        p1.name = '猪八戒'; // 通过setter修改name属性
        ```

  - **静态属性**

    - 静态属性（方法），也称为类属性。使用静态属性无需创建实例，通过类即可直接使用

    - 静态属性（方法）使用static开头

    - 示例：

      - ```typescript
        class Tools{
            static PI = 3.1415926;
            
            static sum(num1: number, num2: number){
                return num1 + num2
            }
        }
        
        console.log(Tools.PI);
        console.log(Tools.sum(123, 456));
        ```

  - this

    - 在类中，使用this表示当前对象

- **继承（重点）**

  - 继承时面向对象中的又一个特性

  - 通过继承可以将其他类中的属性和方法引入到当前类中

    - 示例：

      - ```typescript
        class Animal{
            name: string;
            age: number;
        
            constructor(name: string, age: number){
                this.name = name;
                this.age = age;
            }
        }
        
        class Dog extends Animal{
        
            bark(){
                console.log(`${this.name}在汪汪叫！`);
            }
        }
        
        const dog = new Dog('旺财', 4);
        dog.bark();
        ```

  - **通过继承可以在不修改类的情况下完成对类的扩展**

  - **重写**

    - 发生继承时，如果子类中的方法会替换掉父类中的同名方法，这就称为方法的重写

    - 示例：

      - ```typescript
        class Animal{
            name: string;
            age: number;
        
            constructor(name: string, age: number){
                this.name = name;
                this.age = age;
            }
        
            run(){
                console.log(`父类中的run方法！`);
            }
        }
        
        class Dog extends Animal{
        
            bark(){
                console.log(`${this.name}在汪汪叫！`);
            }
        
            run(){
                console.log(`子类中的run方法，会重写父类中的run方法！`);
            }
        }
        
        const dog = new Dog('旺财', 4);
        dog.bark();
        ```

      - 在子类中可以使用**super**来完成对父类的引用

  - **抽象类**（abstract class）

    - 抽象类是专门用来被其他类所继承的类，它只能被其他类所继承不能用来创建实例

    - ```typescript
      abstract class Animal{
          abstract run(): void;
          bark(){
              console.log('动物在叫~');
          }
      }
      
      class Dog extends Animals{
          run(){
              console.log('狗在跑~');
          }
      }
      ```

    - **使用abstract开头的方法叫做抽象方法，抽象方法没有方法体只能定义在抽象类中，继承抽象类时抽象方法必须要实现**

    

## 3、接口（Interface）

接口的作用类似于抽象类，不同点在于接口中的所有方法和属性都是没有实值的，换句话说接口中的所有方法都是抽象方法。接口主要负责定义一个类的结构，接口可以去限制一个对象的接口，对象只有包含接口中定义的所有属性和方法时才能匹配接口。同时，可以让一个类去实现接口，实现接口时类中要保护接口中的所有属性。

- 示例（检查对象类型）：

  - ```typescript
    interface Person{
        name: string;
        sayHello():void;
    }
    
    function fn(per: Person){
        per.sayHello();
    }
    
    fn({name:'孙悟空', sayHello() {console.log(`Hello, 我是 ${this.name}`)}});
    
    ```

- 示例（实现）

  - ```typescript
    interface Person{
        name: string;
        sayHello():void;
    }
    
    class Student implements Person{
        constructor(public name: string) {
        }
    
        sayHello() {
            console.log('大家好，我是'+this.name);
        }
    }
    ```

  - 



## 4、泛型（Generic）

定义一个函数或类时，有些情况下无法确定其中要使用的具体类型（返回值、参数、属性的类型不能确定），此时泛型便能够发挥作用。

- 举个例子：

  - ```typescript
    function test(arg: any): any{
    	return arg;
    }
    ```

  - 上例中，test函数有一个参数类型不确定，但是能确定的时其返回值的类型和参数的类型是相同的，由于类型不确定所以参数和返回值均使用了any，但是很明显这样做是不合适的，首先使用any会关闭TS的类型检查，其次这样设置也不能体现出参数和返回值是相同的类型

  - 使用泛型：

  - ```typescript
    function test<T>(arg: T): T{
    	return arg;
    }
    ```

  - 这里的```<T>```就是泛型，T是我们给这个类型起的名字（不一定非叫T），设置泛型后即可在函数中使用T来表示该类型。所以泛型其实很好理解，就表示某个类型。

  - 那么如何使用上边的函数呢？

    - 方式一（直接使用）：

      - ```typescript
        test(10)
        ```

      - 使用时可以直接传递参数使用，类型会由TS自动推断出来，但有时编译器无法自动推断时还需要使用下面的方式

    - 方式二（指定类型）：

      - ```typescript
        test<number>(10)
        ```

      - 也可以在函数后手动指定泛型

  - 可以同时指定多个泛型，泛型间使用逗号隔开：

    - ```typescript
      function test<T, K>(a: T, b: K): K{
          return b;
      }
      
      test<number, string>(10, "hello");
      ```

    - 使用泛型时，完全可以将泛型当成是一个普通的类去使用

  - 类中同样可以使用泛型：

    - ```typescript
      class MyClass<T>{
          prop: T;
      
          constructor(prop: T){
              this.prop = prop;
          }
      }
      ```

  - 除此之外，也可以对泛型的范围进行约束

    - ```typescript
      interface MyInter{
          length: number;
      }
      
      function test<T extends MyInter>(arg: T): number{
          return arg.length;
      }
      ```

    - 使用T extends MyInter表示泛型T必须是MyInter的子类，不一定非要使用接口类和抽象类同样适用。

# 暴露数据和引入数据

## 1.方法一

```typescript
/**
 * 新建一个db.ts 将数据库方法封装并且暴露出来
 * 暴露一个获取数据的方法
 */
export function getData():any[]{
    return [
        {
            name:'123',
            ahe:20
        },
        {
            name:'123425',
            age:30
        }
    ]
}

export function saveData():boolean{
    console.log('保存数据成功！')
    return true;
}

/**
 * 在index.ts文件中引入
 * 在这里引入我暴露的函数
 */

 import {getData} from './modules/db'

 console.log(getData());

  saveData();
```

## 2.方法二

```typescript
/**
 * 暴露一个获取数据的方法
 */
function getData():any[]{
    return [
        {
            name:'123',
            ahe:20
        },
        {
            name:'123425',
            age:30
        }
    ]
}

function saveData():boolean{
    console.log('保存数据成功！')
    return true;
}

export {getData, saveData}

/**
 * 在index.ts文件中引入
 * 在这里引入我暴露的函数
 */

 import {getData} from './modules/db'

 console.log(getData());

  saveData();

```

## 3.方法三

```typescript
/**
 * 使用export default 暴露数据
 */
function getData():any[]{
    return [
        {
            name:'123',
            ahe:20
        },
        {
            name:'123425',
            age:30
        }
    ]
}

function saveData():boolean{
    console.log('保存数据成功！')
    return true;
}

export default getData;

/**
 * export default 引入数据
 */

 import getData from './modules/db'


 console.log(getData());
```


# tsconfig.json配置详解

**常用：**

```json
{
  "compilerOptions": {
    "allowUnreachableCode": true, //不报告执行不到的代码错误。
    "allowUnusedLabels": false,	//不报告未使用的标签错误
    "alwaysStrict": false, //以严格模式解析并为每个源文件生成 "use strict"语句
    "baseUrl": ".", //工作根目录
    "experimentalDecorators": true, //启用实验性的ES装饰器
    "jsx": "react", //在.tsx文件里支持JSX
    "sourceMap": true, //是否生成map文件
    "module": "commonjs", //指定生成哪个模块系统代码
    "noImplicitAny": false, //是否默认禁用any
    "removeComments": true, //是否移除注释
    "types": [ //指定引入的类型声明文件，默认是自动引入所有声明文件，一旦指定该选项，则会禁用自动引入，改为只引入指定的类型声明文件，如果指定空数组[]则不引用任何文件
      "node", //引入node的类型声明
    ],
    "paths": { //指定模块的路径，和baseUrl有关联，和webpack中resolve.alias配置一样
      "src": [ //指定后可以在文件之直接 import * from 'src';
        "./src"
      ],
    },
    "target": "ESNext", //编译的目标是什么版本的
    "outDir": "./dist", //输出目录
    "declaration": true, //是否自动创建类型声明文件
    "declarationDir": "./lib", //类型声明文件的输出目录
    "allowJs": true, //允许编译javascript文件。
    "lib": [ //编译过程中需要引入的库文件的列表
      "es5",
      "es2015",
      "es2016",
      "es2017",
      "es2018",
      "dom"
    ]
  },
  //指定一个匹配列表（属于自动指定该路径下的所有ts相关文件）
  "include": [
    "src/**/*"
  ],
  // 指定一个排除列表（include的反向操作）
  "exclude": [
    "demo.ts"
  ],
  //指定哪些文件使用该配置（属于手动一个个指定文件）
  "files": [
    "demo.ts"
  ]
}
```

**备用：**

```json
{
  "compilerOptions": {
    /* Basic Options */
    "target": "es5" /* target用于指定编译之后的版本目标: 'ES3' (default), 'ES5', 'ES2015', 'ES2016', 'ES2017', 'ES2018', 'ES2019' or 'ESNEXT'. */,
    "module": "commonjs" /* 用来指定要使用的模块标准: 'none', 'commonjs', 'amd', 'system', 'umd', 'es2015', or 'ESNext'. */,
    "lib": ["es6", "dom"] /* lib用于指定要包含在编译中的库文件 */,
    "allowJs": true,                       /* allowJs设置的值为true或false，用来指定是否允许编译js文件，默认是false，即不编译js文件 */
    "checkJs": true,                       /* checkJs的值为true或false，用来指定是否检查和报告js文件中的错误，默认是false */
    "jsx": "preserve",                     /* 指定jsx代码用于的开发环境: 'preserve', 'react-native', or 'react'. */
    "declaration": true,                   /* declaration的值为true或false，用来指定是否在编译的时候生成相应的".d.ts"声明文件。如果设为true，编译每个ts文件之后会生成一个js文件和一个声明文件。但是declaration和allowJs不能同时设为true */
    "declarationMap": true,                /* 值为true或false，指定是否为声明文件.d.ts生成map文件 */
    "sourceMap": true,                     /* sourceMap的值为true或false，用来指定编译时是否生成.map文件 */
    "outFile": "./",                       /* outFile用于指定将输出文件合并为一个文件，它的值为一个文件路径名。比如设置为"./dist/main.js"，则输出的文件为一个main.js文件。但是要注意，只有设置module的值为amd和system模块时才支持这个配置 */
    "outDir": "./",                        /* outDir用来指定输出文件夹，值为一个文件夹路径字符串，输出的文件都将放置在这个文件夹 */
    "rootDir": "./",                       /* 用来指定编译文件的根目录，编译器会在根目录查找入口文件，如果编译器发现以rootDir的值作为根目录查找入口文件并不会把所有文件加载进去的话会报错，但是不会停止编译 */
    "composite": true,                     /* 是否编译构建引用项目  */
    "incremental": true,                   /* 是否启用增量编译*/
    "tsBuildInfoFile": "./",               /* 指定文件用来存储增量编译信息 */
    "removeComments": true,                /* removeComments的值为true或false，用于指定是否将编译后的文件中的注释删掉，设为true的话即删掉注释，默认为false */
    "noEmit": true,                        /* 不生成编译文件，这个一般比较少用 */
    "importHelpers": true,                 /* importHelpers的值为true或false，指定是否引入tslib里的辅助工具函数，默认为false */
    "downlevelIteration": true,            /* 当target为'ES5' or 'ES3'时，为'for-of', spread, and destructuring'中的迭代器提供完全支持 */
    "isolatedModules": true,               /* isolatedModules的值为true或false，指定是否将每个文件作为单独的模块，默认为true，它不可以和declaration同时设定 */

    /* Strict Type-Checking Options */
    "strict": true /* strict的值为true或false，用于指定是否启动所有类型检查，如果设为true则会同时开启下面这几个严格类型检查，默认为false */,
    "noImplicitAny": true,                 /* noImplicitAny的值为true或false，如果我们没有为一些值设置明确的类型，编译器会默认认为这个值为any，如果noImplicitAny的值为true的话。则没有明确的类型会报错。默认值为false */
    "strictNullChecks": true,              /* strictNullChecks为true时，null和undefined值不能赋给非这两种类型的值，别的类型也不能赋给他们，除了any类型。还有个例外就是undefined可以赋值给void类型 */
    "strictFunctionTypes": true,           /* strictFunctionTypes的值为true或false，用于指定是否使用函数参数双向协变检查 */
    "strictBindCallApply": true,           /* 设为true后会对bind、call和apply绑定的方法的参数的检测是严格检测的 */
    "strictPropertyInitialization": true,  /* 设为true后会检查类的非undefined属性是否已经在构造函数里初始化，如果要开启这项，需要同时开启strictNullChecks，默认为false */
   "noImplicitThis": true,                /* 当this表达式的值为any类型的时候，生成一个错误 */
    "alwaysStrict": true,                  /* alwaysStrict的值为true或false，指定始终以严格模式检查每个模块，并且在编译之后的js文件中加入"use strict"字符串，用来告诉浏览器该js为严格模式 */

    /* Additional Checks */
    "noUnusedLocals": true,                /* 用于检查是否有定义了但是没有使用的变量，对于这一点的检测，使用eslint可以在你书写代码的时候做提示，你可以配合使用。它的默认值为false */
    "noUnusedParameters": true,            /* 用于检查是否有在函数体中没有使用的参数，这个也可以配合eslint来做检查，默认为false */
    "noImplicitReturns": true,             /* 用于检查函数是否有返回值，设为true后，如果函数没有返回值则会提示，默认为false */
    "noFallthroughCasesInSwitch": true,    /* 用于检查switch中是否有case没有使用break跳出switch，默认为false */

    /* Module Resolution Options */
    "moduleResolution": "node",            /* 用于选择模块解析策略，有'node'和'classic'两种类型' */
    "baseUrl": "./",                       /* baseUrl用于设置解析非相对模块名称的基本目录，相对模块不会受baseUrl的影响 */
    "paths": {},                           /* 用于设置模块名称到基于baseUrl的路径映射 */
    "rootDirs": [],                        /* rootDirs可以指定一个路径列表，在构建时编译器会将这个路径列表中的路径的内容都放到一个文件夹中 */
    "typeRoots": [],                       /* typeRoots用来指定声明文件或文件夹的路径列表，如果指定了此项，则只有在这里列出的声明文件才会被加载 */
    "types": [],                           /* types用来指定需要包含的模块，只有在这里列出的模块的声明文件才会被加载进来 */
    "allowSyntheticDefaultImports": true,  /* 用来指定允许从没有默认导出的模块中默认导入 */
    "esModuleInterop": true /* 通过为导入内容创建命名空间，实现CommonJS和ES模块之间的互操作性 */,
    "preserveSymlinks": true,              /* 不把符号链接解析为其真实路径，具体可以了解下webpack和nodejs的symlink相关知识 */

    /* Source Map Options */
    "sourceRoot": "",                      /* sourceRoot用于指定调试器应该找到TypeScript文件而不是源文件位置，这个值会被写进.map文件里 */
    "mapRoot": "",                         /* mapRoot用于指定调试器找到映射文件而非生成文件的位置，指定map文件的根路径，该选项会影响.map文件中的sources属性 */
    "inlineSourceMap": true,               /* 指定是否将map文件的内容和js文件编译在同一个js文件中，如果设为true，则map的内容会以//# sourceMappingURL=然后拼接base64字符串的形式插入在js文件底部 */
    "inlineSources": true,                 /* 用于指定是否进一步将.ts文件的内容也包含到输入文件中 */

    /* Experimental Options */
    "experimentalDecorators": true /* 用于指定是否启用实验性的装饰器特性 */
    "emitDecoratorMetadata": true,         /* 用于指定是否为装饰器提供元数据支持，关于元数据，也是ES6的新标准，可以通过Reflect提供的静态方法获取元数据，如果需要使用Reflect的一些方法，需要引入ES2015.Reflect这个库 */
  }
  "files": [], // files可以配置一个数组列表，里面包含指定文件的相对或绝对路径，编译器在编译的时候只会编译包含在files中列出的文件，如果不指定，则取决于有没有设置include选项，如果没有include选项，则默认会编译根目录以及所有子目录中的文件。这里列出的路径必须是指定文件，而不是某个文件夹，而且不能使用* ? **/ 等通配符
  "include": [],  // include也可以指定要编译的路径列表，但是和files的区别在于，这里的路径可以是文件夹，也可以是文件，可以使用相对和绝对路径，而且可以使用通配符，比如"./src"即表示要编译src文件夹下的所有文件以及子文件夹的文件
  "exclude": [],  // exclude表示要排除的、不编译的文件，它也可以指定一个列表，规则和include一样，可以是文件或文件夹，可以是相对路径或绝对路径，可以使用通配符
  "extends": "",   // extends可以通过指定一个其他的tsconfig.json文件路径，来继承这个配置文件里的配置，继承来的文件的配置会覆盖当前文件定义的配置。TS在3.2版本开始，支持继承一个来自Node.js包的tsconfig.json配置文件
  "compileOnSave": true,  // compileOnSave的值是true或false，如果设为true，在我们编辑了项目中的文件保存的时候，编辑器会根据tsconfig.json中的配置重新生成文件，不过这个要编辑器支持
  "references": [],  // 一个对象数组，指定要引用的项目
}
```

# 装饰器



```typescript
//定义联合类型
type Data = string | number | object;

interface MyNode {
  data: Data;
  next: MyNode;
}

class LinkedList<t extends Data>{
  public length: number = 0;
  public header: MyNode = null;
  protected node = class implements MyNode {
    data: Data;
    next: MyNode = null;
    constructor(data: Data) {
      this.data = data;
    }
  }
  //尾插法
  append(data: t) {
    //1.创建新节点
    const newNode = new this.node(data);
    //2.追加新节点
    if (this.length == 0) {
      this.header = newNode
    } else {
      let currentNode: MyNode = this.header;
      while (currentNode.next != null) {
        currentNode = currentNode.next;
      }
      //最后一个节点指向新节点
      currentNode.next = newNode;
    }
    //3.追加完新节点后，链表长度+1
    this.length++;
  }
  @toStr()
  toString(): string {
    let currentNode: MyNode = this.header;
    let res: string = '';
    while (currentNode) {
      res += currentNode.data + '-->'
      currentNode = currentNode.next
    }
    return res.slice(0, -3);
  }
  //插入
  insert(position:number,data:t){

  }
}

//创建tostring装饰工厂
function toStr() {
  return function (target: any, propertyKey, descriptor: PropertyDescriptor) {
    const method = descriptor.value;
    //获取当前target上的描述，直接打印target用处不大
    console.log(Object.getOwnPropertyDescriptors(target))
    //在descriptor.value函数里，this指向当前类的实例,其他地方this指空
    descriptor.value = function (...args: any[]) {
      args = args.map(item => String(item))
      console.log('参数=>', args)
      try {
        let olddescriptor = Object.getOwnPropertyDescriptors(target)
        //console.log(olddescriptor)
        console.log(this)
      } finally {
        return method.apply(this, args)
      }
    }
  }
}



//测试
const linkedlist = new LinkedList<string>();
linkedlist.append('A')
linkedlist.append('B')
linkedlist.append('C')
console.log(linkedlist.toString())

```



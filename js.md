1.数据类型
1.ES6中有8种数据类型：

基本数据类型：

    String：任意字符串
    Number：任意的数字
    boolean：true/false
    bigInt
    undefined：undefined
    null：null
    Symbol

引用数据类型：

    Object

普通对象，数组，正则，日期，Math数学函数等都属于Object；
2.判断

    typeof：返回数据类型的字符串表达，首字母都是小写

可以判断：undefined,数值,字符串,布尔值,symbol（基本数据类型不能判断null，引用数据类型只能判断function）

不能判断：null和object object和array

//举个例子
typeof 1 // 'number'
typeof '1' // 'string'
typeof undefined // 'undefined'
typeof true // 'boolean'
typeof Symbol() // 'symbol'
typeof null // 'object'
typeof [] // 'object'
typeof {} // 'object'
typeof console // 'object'
typeof console.log // 'function'

`instanceof` 运算符用于检测构造函数的 `prototype` 属性是否出现在某个实例对象的原型链上

object instanceof constructor

// 定义构建函数
let Car = function() {}
let benz = new Car()
benz instanceof Car // true
let car = new String('xxx')
car instanceof String // true
let str = 'xxx'
str instanceof String // false

//原理

function myInstanceof(left, right) {
    // 这里先用typeof来判断基础数据类型，如果是，直接返回false
    if(typeof left !== 'object' || left === null) return false;
    // getProtypeOf是Object对象自带的API，能够拿到参数的原型对象
    let proto = Object.getPrototypeOf(left);
    while(true) {                  
        if(proto === null) return false;
        if(proto === right.prototype) return true;//找到相同原型对象，返回true
        proto = Object.getPrototypeof(proto);
    }
}

//可以判断:undefined,null

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <!--
1. 分类
  * 基本(值)类型
    * String: 任意字符串
    * Number: 任意的数字
    * boolean: true/false
    * undefined: undefined
    * null: null
  * 对象(引用)类型
    * Object: 任意对象
    * Function: 一种特别的对象(可以执行)
    * Array: 一种特别的对象(数值下标, 内部数据是有序的)
2. 判断
  * typeof:
    * 可以判断: undefined/ 数值 / 字符串 / 布尔值 / function
    * 不能判断: null与object  object与array
  * instanceof:
    * 判断对象的具体类型
  * ===
    * 可以判断: undefined, null
    -->
    <script>
        // 1.基本数据类型
        // typeof 返回数据类型的字符串表达
        var a
        console.log(a, typeof a, typeof a === 'undefined', a === undefined);//undefined 'undefined' true true
        console.log(undefined === 'undefined');//false
        console.log(undefined === 'undefined');//false
        a = 4
        console.log(typeof a === 'number');//true
        a = 'abc'
        console.log(typeof a === 'String');//false
        a = true
        console.log(typeof a === 'boolean');//true
        a = null
        console.log(typeof a, a === null);//object true
        console.log('****************************************************');

    ```javascript
    // 2.对象
    var b1 = {
        b2: [1, 'abc', console.log],
        b3: function () {
            console.log('b3');
            return function () {
                return 'return的函数'
            }
        }
    }
    
    console.log(b1 instanceof Object, b1 instanceof Array);//true false
    console.log(b1.b2 instanceof Array, b1.b2 instanceof Object);//true true
    console.log(b1.b3 instanceof Function, b1.b3 instanceof Object);//true true
    console.log(typeof b1.b3, typeof b1.b3 === 'function');//function true
    console.log(typeof b1.b2[2], typeof b1.b2[2] === 'function');//function true
    b1.b2[2]('hello')//hello
    console.log(b1.b3()());//return的函数 
    ```
    </script>
    </body>

</html>



typeof与instanceof都是判断数据类型的方法，区别如下：

    typeof会返回一个变量的基本类型，instanceof返回的是一个布尔值
    instanceof 可以准确地判断复杂引用数据类型，但是不能正确判断基础数据类型
    而typeof 也存在弊端，它虽然可以判断基础数据类型（null 除外），但是引用数据类型中，除了function 类型以外，其他的也无法判断

可以看到，上述两种方法都有弊端，并不能满足所有场景的需求

如果需要通用检测数据类型，可以采用Object.prototype.toString，调用该方法，统一返回格式“[object Xxx]”的字符串


function getType(obj){
  let type  = typeof obj;
  if (type !== "object") {    // 先进行typeof判断，如果是基础数据类型，直接返回
    return type;
  }
  // 对于typeof返回结果是object的，再进行如下的判断，正则返回结果
  return Object.prototype.toString.call(obj).replace(/^\[object (\S+)\]$/, '$1'); 
}

2.数据，变量，内存

切记：变量赋值是将内容赋值（拷贝）一份给另一个值
1. 什么是数据?

    存储在内存中代表特定信息的‘东西’，本质上是0101
    数据的特点：可传递，可运算
    一切皆数据
    内存中所有操作的目标：数据
        算术运算
        逻辑运算
        内存中所有操作的目标：数据
            算术运算
            逻辑运算
            赋值
            运算函数

2.什么是内存?

    内存条通电以后产生的可存储数据的空间（临时的）
    
    内存的产生和死亡：内存条（电路板）>通电>产生内存空间==>存储数据==>处理数据==>断电==>内存空间和数据都消失
    
    内存的空间是临时的，而硬盘的空间是持久的
    
    **分配内存：**声明变量和函数或创建对象时，js引擎会自动为此分配一定大小的内存来存放对应的数据
    
    **释放内存：**清空内存中的数据，标识内存可以再分配使用（内存释放就不能复用）
        自动释放：栈空间的局部变量
        垃圾回收器回调：堆空间的垃圾对象
    
    一块小内存的2个数据：
        内部存储的数据
        地址值
    
    内存分类：
        栈：全局变量/局部空间
        堆：对象

3.什么是变量?

    可变化的量，由变量名和变量值组成
    每个变量都对应一块小内存，变量名用来查找对应的内存，变量值就是内存中的值

4.内存,数据, 变量三者之间的关系

    内存用来存储数据的空间
    变量是内存的标识，
1. 什么是数据?
  - 存储在内存中代表特定信息的‘东西’，本质上是0101
  - 数据的特点：可传递，可运算
  - 一切皆数据
  - 内存中所有操作的目标：数据
    - 算术运算
    - 逻辑运算
    - 内存中所有操作的目标：数据
      - 算术运算
      - 逻辑运算
      - 赋值
      - 运算函数
2. 什么是内存?
  - 内存条通电以后产生的可存储数据的空间（临时的）
  - 内存的产生和死亡：内存条（电路板）==>通电==>产生内存空间==>存储数据==>处理数据==>断电==>内存空间和数据都消失
  - 一块小内存的2个数据：
    - 内部存储的数据
    - 地址值
  - 内存分类：
    - 栈：全局变量/局部空间
    - 堆：对象
3. 什么是变量?
  - 可变化的量，由变量名和变量值组成
  - 每个变量都对应一块小内存，变量名用来查找对应的内存，变量值就是内存中的值
4. 内存,数据, 变量三者之间的关系
  - 内存用来存储数据的空间
  - 变量是内存的标识，
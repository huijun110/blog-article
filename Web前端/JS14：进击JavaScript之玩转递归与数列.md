1、 什么是递归
------------------------------
在程序中，所谓的递归，就是函数自己直接或间接调用自己

### 1.1 直接调用自己
```
function f() {
    console.log( 1 );
    f();
}
```
### 1.2 间接调用自己
```
function f1(){
    f2();
}
function f2() {
    f1();
}
```
就递归而言，最重要的是跳出结构，因为只有跳出结构才可以有结果。

### 1.3 所谓的递归就是化归思想
递归的调用，写递归函数，最终还是要转换为自己这个函数

加入有一个函数f，如果他是递归函数的话，也就是说函数体内的问题还是转化为 f 的形式。

递归思想就是将一个问题转换为一个已解决的问题来实现

例子：1,2,3,4，...,100，累加的结果

* 首先假定递归函数已经写好，假设是foo，即foo(100) 就是求1到100的和
* 寻找递推关系，就是n与n-1，或n-2之间的关系：foo( n ) == n + foo( n -1 )
```
var res = foo( 100 );
var res = foo( 99 ) + 100;
```
* 将递推结果转换为递归体
```
function foo ( n ) {
    return n + foo( n -1 );
}
```
1. 将求100转换为求99
2. 将求99转换为求98
3. ...
4. 将求2转换为求1
5. 求1结果就是1
6. 即：foo( 1 ) 是1

* 将临界条件加到递归体中
```
function foo( n ) {
    return ( n ==1 ) return 1;
    return n + foo( n -1 );
}
```

2、 递归求值举例
-----------------------------------
### 2.1 等差数列1

数列：求 1, 3, 5, 7, 9, ... 第 n 项的结果与前 n 项和. 序号从 0 开始

**求第 n 项的值**

* 首先假定递归函数已经写好, 假设是 fn. 那么 第 n 项就是 fn( n )
* 找递推关系: fn( n ) == f( n - 1 ) + 2
* 递归体
```
function fn( n ) {
    return fn( n-1 ) + 2;
}
```
* 找临界条件
    * 求 n -> n-1
    * 求 n-1 -> n-2
    * ...
    * 求 1 -> 0
    * 求 第 0 项, 就是 1
* 加入临界条件
```
function fn( n ) {
    if ( n == 0 ) return 1;
    return fn( n-1 ) + 2;
}
```
**前N项的和**

* 假设已完成, sum( n ) 就是前 n 项和
* 找递推关系: 前 n 项和 等于 第 n 项 + 前 n-1 项的和
* 得到递归体
```
function sum( n ) {
    return fn( n ) + sum( n - 1 );
} 
```
* 找临界条件
    * n == 1 结果为1
* 得到递归函数
```
function sum( n ) {
    if ( n == 0 ) return 1;
    return fn( n ) + sum( n - 1 );
} 
```

### 2.2 等差数列2
数列：2, 4, 6, 8, 10 第 n 项与 前 n 项和

**第n项**
```
function fn( n ) {
   if ( n == 0 ) return 2; 
   return fn( n-1 ) + 2; 
}
```
**前n项和**
```
function sum( n ) { 
   if ( n == 0 ) return 2; 
   return sum( n - 1 ) + fn( n ); 
}
```

### 2.3 差分数列
数列: 1, 1, 2, 4, 7, 11, 16, … 求 第 n 项, 求前 n 项和.

**求第 n 项，从0开始**

* 假设已经得到结果 fn, fn( 10 ) 就是第 10 项
* 找递推关系
    * 第 0 项和第 1 项，相差0 => fn( 0 ) + 0 = fn( 1 )
    * 第 1 项和第 2 项，相差1 => fn( 1 ) + 1 = fn( 2 )
    * 第 2 项和第 3 项，相差2 => fn( 1 ) + 2 = fn( 2 )
    * ... 
    * 第 n-1 项和第 n 项，相差n-1 => fn( n -1 ) + n -1 = fn( n )
* 递归体也就清楚了, 临界条件是 n == 0 => 1
```
function fn ( n ){
    if( n == 0 ) return 1;
    return fn( n -1 ) + n - 1;
}
```

**如果从 1 开始表示, 那么第 n 项为**

* 假设已经得到结果 fn, fn( 10 ) 就是第 10 项
* 找递推关系
    * 第 1 项和第 2 项，相差0 => fn( 1 ) + 0 = fn( 2 )
    * 第 2 项和第 3 项，相差1 => fn( 2 ) + 1 = fn( 3 )
    * 第 3 项和第 4 项，相差2 => fn( 3 ) + 2 = fn( 4 )
    * ...
    * 第 n-1 项和第第 n 项，相差 n - 1 => fn( n -1 ) + n -2 = fn( n )
* 临界条件 n == 1 => 1

**前n项和**
```
function sum( n ) {
    if ( n == 1 ) return 1;
    return sum( n - 1 ) + fn( n ); 
}
```

### 2.4 斐波那契数列
这是最常见，面试最爱问的知识之一，斐波那契数列为：1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, … 

**求其第 n 项**
递推关系 fn(n) == fn( n- 1) + fn( n - 2)，于是，递归函数为
```
function fib ( n ) {
    if( n ==0 || n == 1 ) return 1;
    return fib( n -1 ) + fib( n -2 );
}
```

3、高级递归
-------------------------------
### 3.1 阶乘
计算阶乘是递归程序设计的一个经典示例。阶乘是一个运算,计算某个数的阶乘就是用那个数去乘包括 1 在内的所有比它小的数。例如，factorial(5) 等价于 `5*4*3*2*1`，而 factorial(3) 等价于 `3*2*1`。 

5! 就是  `1 * 2 * 3 * 4 * 5`. 0 的阶乘是1, 阶乘 从 1 开始。

**求 n 的阶乘**
```
function foo( n ){
    if( n == 1 ) return 1;
    return foo( n -1 ) * n; 
}
console.log(foo(5));    //120
```
跟前面的1到100的求和的递归函数很相似，只是一个变种

### 3.2 求幂
求幂就是求 某一个数 几次方
2*2 2 的 平方, 2 的 2 次方

**求 n 的 m 次方**
最终要得到一个函数 power( n, m )
n 的 m 次方就是 m 个 n 相乘 即 n 乘以 (m-1) 个 n 相乘
```
function power( n, m ) {
    if( m == 1 ) return n;
    return power( n , m -1 ) * n;
}

console.log(power(2,3)); //8
```

4、递归深拷贝
-------------------------------
如果要实现深拷贝，那么就需要考虑将对象的属性，与属性的属性，....都拷贝过来

### 4.1 简单实现
如果要实现：

* 假设已经实现clone( o1,o2 )，将对象 o2 的成员拷贝一份交给 o1
* 简单的算法，将 o2 的属性拷贝到 o1 中去
```
function clone( o1,o2 ){
    for( var k in o2 ){
        o1[ k ] = o2[ k ]; 
    }
}
```
* 找递推关系，或叫化归为已解决的问题
    - 假设方法已经实现，问一下，如果o2[ k ] 是对象
    - 继续使用这个方法
    - 因此需要考虑的是o2[ k ] 如果是引用类型，再使用一次clone()函数
    - 如果o2[ k ] 不是引用类型，那么就直接赋值

```
function clone( o1, o2 ) {
        for ( var k in o2 ) {
            if ( typeof o2[ k ] == 'object' ) {
                o1[ k ] = {};
                clone( o1[ k ] , o2[ k ] );
            } else {
                o1[ k ] = o2[ k ];
            }
        }
}

var person1 = {
       name: '张三',
       children: [
            { name: '张一' },
            { name: '张二' },
            { name: '王三' }
       ]
};

var person2 = {};
clone( person2, person1 );
```

### 4.2 复杂实现 clone( o ) -> newObj

```
function clone( o ) {
    var temp = {};
    for( var k in o ) {
        if( typeof o[ k ] == 'object' ){
             temp[ k ] = clone( o[ k ] );
        } else {
             temp[ k ] = o[ k ];
        }
    }
    return temp;
}

var person1 = {
     name: '张三',
     children: [
        { name: '张一' },
        { name: '张二' },
        { name: '王三' }
    ]
};
 
 var person2 = clone(person1);
// 修改一个看另一个是否也修改
person2.name = '李四';
 
person2.children[ 0 ].name = '王小虎';
person2.children[ 1 ].name = '张大虎';
person2.children[ 2 ].name = '李长虎';
```

### 4.3 递归实现getElementsByClassName方法

有如下DIV结构：
```html
<div>
	<div>1
		<div class="c">2</div>
		<div>3</div>
	</div>
	<div class="c">4</div>
	<div>5
		<div>6</div>
		<div class="c">7</div>
	</div>
	<div>8</div>
</div>
```
1. 如果实现一个方法`byClass( node, 'c', list )`，表示在某个节点上查找符合 class 属性为 c 的元素
2. 在当前元素的子元素中查找，如果有符合要求的吗，存储早一个数组中
3. 首先遍历子节点，然后看子节点是否还有子节点，如果没有直接判断，如果有再递归
```
function byClass( node, className, list ){
    var nodes = node.childNodes;
    for( var i=0; i<ndoes.length; i++ ){
         if( nodes[ i ].className == className ){
             list.push( nodes[ i ] );
         }
         if( nodes[ i ].childNodes.length > 0 ){
             byClass( nodes[ i ], className, list );
         }
    }
}

var arr = [];
byClass( document.body, 'c', arr );
console.log(arr);
```
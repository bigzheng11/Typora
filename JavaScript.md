javascript是世界上最流行的**脚本语言**



## 注意事项:

1.**js书写位置**-在< script></ script>标签中输入写js代码，可放在任意处，一般放在**head**中

```html
<script>
</script>
```

2.**引入js文件**-通过此种方法，引入js文件中的代码

```html
<script src="Js/JsOne.js">
</script>
```

## 基本语法

#####  Math 对象:

```javascript
Math.PI	//圆周率
Math.floor() //向下取整,往小取值
Math.ceil() //向上取整,往大了取整
Math.round() //四舍五入
Math.abs()  //绝对值,'-1'-->1(隐式转换)
Math.max()/Math.min()//最大值,最小值

Math.random()//[0,1)
	Math.floor(Math.random()*(max-min+1))+min;//取得范围内的随机整数
```



##### Date对象:

Date()是一个构造函数,必须使用new来创建对象

```javascript
var date=new Date()
console.log(date)//Mon Jan 17 2022 18:29:38 GMT+0800 (中国标准时间)
```

![image-20220117185007568](https://raw.githubusercontent.com/bigzheng11/Typora/master/image-20220117185007568.png)

获得**毫秒数**(时间戳)

```javascript
//1.
var date = new Date();
console.log(date.valueOf()); //毫秒
console.log(date.getTime());
//2.
var date1 = +new Date(); //+new Date()返回的就是总的毫秒数
console.log(date1);
//3.
console.log(Date.now());
```







alert("弹出栏")；

Math.abs()	绝对值

prompt(info)		//浏览器弹出输入框，用户可以输入

字符串:

\ 转义字符

var msg=\` aaa 

sss

ddd`

```javascript
   var name = "bigzheng";
   var msg = `你好呀，${name}`;
```

字符串的拼接



字符串长度

console.log(str.length)



##### 大小写转换

console.log(str.toUpperCase())	大写

console.log(str.toLowerCase())	小写



console.log(str.indexOf('x'))	获取第一次出现的x的下标

console.log(str.lastIndexOf('x')) 从后往前找



console.log(str.substring(1)) 	截取下标为1以及后面全部的字符串

console.log(str.substring(1，3)) 截取下标为1以及下标为2的字符串[1,3)









## 数据类型

### 1.number：

```javascript
123			//整数
123.1		//浮点数
1.23e3		//科学计数法
-99			//负数
NaN			//not a number
	console.log(isNaN(12))	//是数字则false，不是数字则true
Infinity	//无限大
```



```javascript
//String强制转换成number
parseInt('78')		//string转换成整数型,去除小数
	parseInt('120px')	//120,去除了px
parseFloat('44.22')
console.log(- * / )			//js的隐式转换
	console.log('123'-0)	//number型123
	console.log('123'-'120')//number型3
	
```



js中不区分大小写以及其他

### 2.字符串

##### 字符串的不可变:

​		给字符串赋值时,原先的字符串不会改变,会新开辟一个内存空间,原先的不会删除,变量指向新空间,

​		故,字符串较为占用资源

------

String简单数据类型为什么会有  length 属性呢

**基本简单包装**:  把简单数据类型**包装成** 复杂数据类型

```javascript
var str='andy';
console.log(str.length)
//1.把简单数据类型包装成复杂数据类型
var temp=new String('andy');
//2.把临时变量的值给str
str=trmp;
//3.销毁临时变量
temp=null;
```

------



```javascript
//字符串的拼接
console.log('沙漠'+'骆驼')	//'沙漠骆驼'
console.log('沙漠'+18)	//'沙漠18'
console.log('沙漠'+true)	//'沙漠true'
console.log(18+18)	//36	number

//concat拼接字符串
var str='andy';
console.log(str.concat('red'));//'a'
```



```javascript
//转换成字符串
var num=1;			//1.toString()
alter(num.toString());
var num=1;			//2.String强制转换
alter(Sting(num))
var num=1;			//与字符转拼接
alter(num+"我是字符串")
```

```javascript
var str='andy';
//根据位置返回字符
str.charAt(0)				//根据索引返回字符
	console.log(str.charAt(3))// y

str.charCodeAt(0)			//根据索引返回ASCII码,判断用户按下了哪个键

str[index]					//h5新增
```

```javascript
var str = "改革春风吹满地";
console.log(str.substr(2, 5));//截取下标为2以及其后5位
//春风吹满地
```



### 3.布尔值

true  false

```javascript
//代表空,否定的值会被转换为false,其余为true
console.log(Boolean(''));		//false
console.log(Boolean('0'));		//false
console.log(Boolean('NaN'));	//false
console.log(Boolean('null'));	//false
console.log(Boolean('undefined'));	//false
console.log(Boolean('小白'));		//true
console.log(Boolean('12'));		 //true
```

### 4.逻辑运算

```javascript
&&	与   两个都为真，即为真	
    console.log(前者 &&后者 && 后者)//若前者为真,则返回后者/若前者为假,则返回前者 --短路运算
||	或	一个真，即为真
    
!	非	真即假，假即真
```



### 5.比较运算符

```javascript
=		赋值
==		等于（类型不一样，值一样，也会判断为true）
    1=="1"
===		绝对等于（类型和值严格相等）
```



NaN===NaN -->false，这个与所有的数值都不相等，包括自己

isNaN(xx)	判断xx是否为NaN



### 6.null和undefined

- null			空
- undefined	未定义



### 7.数组

一系列相同类型的对象

```javascript
var arr=[1,2,3,4,"22",true,null]
new Array(1,2,3,4,"22",true,null)
arr.length	//获取数组长度，可强制改变数组长度，过短则数据丢失

arr.push(1,"a")//数组末尾添加新元素
arr.pop()	//弹出尾部的一个元素,无参数,f

arr.unshift("a")	//压入头部元素
arr.shift()	//弹出头部的元素

arr.sort()//数组的排序
arr.reverse()//元素反转(逆序)

arr.concat([1,2,3])	//在原数组后方添加数组，返回一个新数组

console.log(arr instanceof Array);//判断是否为数组
console.log(Array.isArray(arr));//判断是否为数组
```

##### 连接符join

```javascript
["C","B","A"]
arr.join("-")
"C-B-A"
```

打印拼接数组，使用指定的字符串连接



##### 万能方法splice()

```javascript
var arr = ['Microsoft', 'Apple', 'Yahoo', 'AOL', 'Excite', 'Oracle']; 

// 从索引2开始删除3个元素,然后再添加两个元素: 
arr.splice(2, 3, 'Google', 'Facebook'); 
// 返回删除的元素 ['Yahoo', 'AOL', 'Excite'] 

arr; 
// ['Microsoft', 'Apple', 'Google', 'Facebook', 'Oracle'] 

// 只删除,不添加: 
arr.splice(2, 2); // ['Google', 'Facebook'] 

arr; 
// ['Microsoft', 'Apple', 'Oracle'] 

// 只添加,不删除: 
arr.splice(2, 0, 'Google', 'Facebook'); 
// 返回[],因为没有删除任何元素 

arr; 
// ['Microsoft', 'Apple', 'Google', 'Facebook', 'Oracle'] 
```

##### slice截取数组/复制数组:

```javascript
var arr = ['A', 'B', 'C', 'D', 'E', 'F', 'G']; 
arr.slice(0, 3); 
// 从索引0开始，到索引3结束，但不包括索引3: ['A', 'B', 'C'] 

arr.slice(3); 
// 从索引3开始到结束: ['D', 'E', 'F', 'G'] 

arr.slice();
//从头到尾截取，复制数组

```



### 8.对象{}

javascript对象分三类:

1. 自定义对象
2. 内置对象
3. 浏览器对象

所有键都是字符串，值是任意对象

##### 定义：

```javascript
//1.
var person={
	name:"qinjiang",
	age:3,
	tags:["js","java","ssss"]
    sayHi:function(){
        console.log('haha')
    }
}
//2.
var obj=new Object();	//创建了一个空的对象
//3.利用构造函数创建对象(一次性创建多个对象)
```



##### 取值:

```javascript
//1.
>person.name
>"qinjiang"
//2.
>person['age']
>3
//3.调用方法
person.sayHi();
```



##### 改变/添加/删除新属性：

```javascript
person.age = 18; // age修改为18		修改
delete person.age; // 删除age属性 		删除
person.userName = "admin";//添加userName属性	添加

delete person['name']; // 删除name属性 键为字符串
person.name; // undefined

person.sayHi=function(){}
```



##### 判断属性值是否在对象中:	xxx in xxx

```javascript
var xiaoming = { 				//包括父类
    name: '小明', 
    birth: 1990, 
    school: 'No.1 Middle School', 
    height: 1.70, 
    weight: 65, 
    score: null 
};
'name' in xiaoming; // true 
'grade' in xiaoming; // false 
'toString' in xiaoming //true 父类元素

xiaoming.hasOwnProperty()	//判断只有自己含有的元素，不包括父类
```



## 流程控制

##### if判断

```javascript
var age = 3; 

if (age >= 18) { 
alert('adult'); 
} else if (age >= 6) { 
alert('teenager'); 
} else { 
alert('kid'); 
} 
```



##### for循环

```javascript
var x = 0; 
var i; 
for (i=1; i<=10000; i++) { 
x = x + i; 
}
x; // 50005000 
```

```javascript
//无限循环
var x=0;		
for(;;){
    if(x>100){
        break;
    }
    x ++;
}
```

```javascript
//遍历数组
var arr = ['Apple', 'Google', 'Microsoft'];	
var i,x;
for (i=0;i<arr.length;i++){
    x=arr[i];
    console.log(x);
}
```

```javascript
//遍历对象的所有属性	for...in..
var o={
	name:"jake",
	age:20,
	city:"beijing"
};
for (var k in o){
	console.log(k);//得到属性名
    console.log(o[k])	//得到属性值,k是变量不加''
}

for (var key in o){
	if(o.hasOwnProperty(key)){
	console.log(key);	//'name','age','city'
	}
}
//由于array数组也是对象，内部的每个元素被视为对象属性，故遍历出来的是下标
```

##### while循环

```javascript
var x = 0; 
var n = 99; 
while (n > 0) { 
    x = x + n; 
    n = n - 2; 
}
x; // 2500
```

```javascript\
//do...while...先执行一次,再判断条件
var n = 0; 
do {
n = n + 1; 
} while (n < 100); 
n; // 100 
```



##### 循环中continue和break关键字

continue:跳出**本次**循环,继续下一次循环,不再执行下面的语句

```javascript
for (var i = 1; i <= 5; i++) {
    if (i == 3) {
     continue;
    }
    console.log("本次是第" + i + "次循环");
   }
//本次是第1次循环
//本次是第2次循环
//本次是第4次循环
//本次是第5次循环
```

break:立刻跳出**整个**循环





##### 三元表达式

```javascript
//条件表达式 ? 表达式1 : 表达式2
//若条件表达式为true,则返回表达式1
	//条件表达式为false,则返回表达式2
var num =10;
var result =num>5 ? '是的' : "不是"	//是的
```

##### switch

```javascript
switch(表达式){	//表达式 = = = value时,才会执行
    case value1:
        执行语句1;
        break;		//若没有break则会执行下一个case,而不退出
    case value2:
        执行语句2;
        break;
    .....
    default:		//前者都没有匹配到时,才会执行default语句
        执行最后语句;
}
```





## Map和Set(无下标)

##### map，以二维数组的形式形成键值对集合

```javascript
var m=new Map([["michael",95],['Bob',75],['jack',90]]);
m.get('michael');	//95
```

```javascript
var m=new Map()；	//空map
m.set('jack',98)；	//添加新元素
m.has('jack');		//是否存在key'jack',返回true
m.get('jack');		//98
m.delete('jack');	//删除key'jack'
m.get('jack');		//undefined
```



##### Set,无序不重复集合

```javascript
var set1=new Set([1,2,3,3,'3']);	//定义set集合
s;//set1{1,2,3,'3'}		//set集合不能重复
```

```javascript
s.add(4);			//添加元素
s;	//set{1,2,3,4}
s.add(4);
s;	//仍然是set{1,2,3,4}
s.delete(3);		//删除元素
s;	//set{1,2,4}

```



## Iterable

array可以使用下标循环遍历，但map和set不可以

使用iterable可以统一遍历

```javascript
//for  ...  of	...
var a = ['A', 'B', 'C'];
var s=new Set(['A','B','C']);
var m=new Map([[1,'x'],[2,'y'],[3,'z']]);

for (var x of a){	//遍历array
    console.log(x);
}
for (var x of s){
    console,log(x);	//遍历set
}
for (var x of m){	//遍历map
    console.log(x[0]+'='+x[1]);
}
```

```javascript
//iterable内置forEach方法
a.forEach(function(element,index,array){
    //element:指向当前元素的值
    //index:指向当前索引
    //array:指向array对象本身
    console.log(element+',index='+index);
});
```



## 函数

**javascript中函数允许接收任意个参数，也由此衍生出了各种情况**

```javascript
//定义方式一
function abs(x){
    if(typeof x!='number'){		//typeof判断类型
        throw	'Not a number'	//throw 抛出异常
    }
    if(x>=0){
        return x;
    }else if(x<0){
        return	-x;
    }
}
```

```javascript
//定义方式二
var abs = function(x){
    if(x>=0){
        return x;
    }else if(x<0){
        return	-x;
    }
}
```

```javascript
//调用函数
abs(10)		//10
abs(-10)	//10
```



`arguments`伪数组(有数组的属性,但不能使用数组的方法),只在函数内部起作用，并且永远指向当前函数的调用者传入的所有参数

<u>利用`arguments`你可以获得传入的所有参数，即使函数不定义任何参数，还是可以拿到参数的值，常用于判断传入的参数个数</u>

```javascript
//foo(a[,b],c)
//接收2-3个参数，若收到两个，则b默认为null
function foo(a,b,c){
    if(arguments.length==2){
        c=b;
        b=null;
    }
}
```

注意:

​	1.return只能返回**一个**值,若想返回多个值可以利用数组

## 作用域

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>全局作用域</title>
    <script>
      var num = 10;
      //全局作用域:整个script标签,或者是一个单独的js文件
        
      function fn() {
        //局部作用域:在函数内部
        var num = 20;
      }
    </script>
  </head>
  <body></body>
</html>

```

注意:

​	1.在**函数内部**没有声明,直接赋值的变量,也是全局变量(num=20;)

​	全局变量:只有在浏览器关闭的时候才会销毁,比较占内存资源

​	局部变量:程序执行完毕的时候就会销毁,比较节约资源



```html
//作用域链:内部函数访问外部函数的变量,采取的是**链式查找**的方式来决定哪个值,(就近原则)

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>全局作用域</title>
    <script>
      function f1() {
        var num = 123;
        function f2() {
          console.log(num);//返回1
        }
        f2();
      }
      var num = 456;
      f1();
    </script>
  </head>
  <body></body>
</html>

```


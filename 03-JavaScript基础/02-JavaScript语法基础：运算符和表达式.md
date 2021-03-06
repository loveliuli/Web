
> 本文首发于[博客园](https://www.cnblogs.com/smyhvae/p/8306146.html)，并在[GitHub](https://github.com/smyhvae/Web)上持续更新**前端的系列文章**。欢迎在GitHub上关注我，一起入门和进阶前端。

> 以下是正文。

我们在[上一篇文章](http://www.cnblogs.com/smyhvae/p/8303507.html)里讲到了JS中**变量**的概念，本篇文章讲一下**运算符**和表达式。


比如说`+`、`*`、`/`、`(` 都是**运算符**，而`（3+5）/2`则是**表达式**。

运算符有很多分类：数学运算符、逻辑运算符、自增运算符、赋值运算等。

##  数学运算符

常见的数学运算符有以下几种：

![](http://img.smyhvae.com/20180117_1651.png)


**求余的举例**：

假设用户输入345，怎么分别得到3、4、5这三个数呢？

**答案**：

```
	得到3的方法：345 除以100，得到3.45然后取整，得到3。即：parseInt(345/100)

	得到4的方法：345 除以100，余数是45，除以10，得到4.5，取整。即：parseInt(345 % 100 / 10)

	得到5的方法：345 除以10，余数就是5。即：345 % 10
```

### 数学运算符的运算规则

（1）先算乘除、后算加减。

（2）小括号：能够影响计算顺序，且可以嵌套。没有中括号、没有大括号，只有小括号。

（3）百分号：取余。只关心余数。

举例1：(取余)

```
	console.log(3 % 5);
```

输出结果为3。

举例2：（运算符优先级）

```
	var a = 1 + 2 * 3 % 4 / 3;
```

结果分析：

原式 =  1 + 6 % 4 / 3 = 1 + 2 / 3 = 1.66666666666666

### 乘方

如果想计算 `a 的 b 次方`，可以使用如下函数：

```
	Math.pow(a, b);
```

Math的中文是“数学”，pow是“power 幂”。

**举例1：**

![](http://img.smyhvae.com/20180117_1730.png)

代码实现：

```
	var a = Math.pow(3, Math.pow(2, 2));
	console.log(a);
```

**举例2：**

![](http://img.smyhvae.com/20180117_1740.png)

代码实现：

```
	var a = Math.pow(Math.pow(3, 2), 4);
	console.log(a);
```

### 开方

如果想计算数值a的开二次方，可以使用如下函数：

```
	 Math.sqrt(a);
```

sqrt即“square 开方”。比如：

```
	var a = Math.sqrt(36);
```

## 布尔值、关系运算符、逻辑运算符

### 布尔值

我们在上一篇文章中学习到的变量类型中包括：数值型、字符串型。今天再来学习一个类型：**布尔类型**。

布尔类型的值，就两个：true、false。

布尔值直接使用就可以了，千万不要加上引号。

代码：

```javascript
	var a = true;
	console.log(typeof a);
```

控制台输出结果：

```
	boolean
```

### 关系运算符

关系运算符有很多种，比如：

```
	>	大于号
	<	小于号
	>= 	大于或等于
	<=  小于或等于
	== 	等于
	=== 全等于
	!=	不等于
	!== 不全等于
```

关系运算符，得到的结果都是布尔值：要么是true，要么是false。

**`==`符号的强调**：

注意`==`这个符号，它是**判断是否等于**，而不是赋值。

（1）`== `这个符号，还可以验证字符串是否相同。例如：

```
	console.log("我爱你中国" == "我爱你中国");		//输出结果为true
```

（3）`== `这个符号并不严谨，会将不同类型的东西，转为相同类型进行比较。例如：

```
	console.log("6" == 6);		//true
```

如果要保证**完全等于**，我们就要用三个等号`===`。例如：


```
	console.log("6" === 6);		//false
	console.log(6 === 6);		//true
```

上述内容分析出：

- `==`两个等号，不严谨，"6"和6是true。

- `===`三个等号，严谨，"6"和6是false。

另外还有：**`==`的反面是`!=`，`===`的反面是`!==`。**。例如：

```
	console.log(3 != 8);	//true
	console.log(3 != "3");	//false，因为3=="3"是true，所以反过来就是false。
	console.log(3 !== "3");	//true，应为3==="3"是false，所以反过来是true。
```

### 逻辑运算符

逻辑运算符有三个：

- && 	与（且）:两个都为真，结果才为真

- ||	或

- !		非：只要有一个是真，结果就是真

能参与逻辑运算的，都是布尔值，得到的答案仍然是布尔值。

**连比的写法：**

来看看逻辑运算符连比的写法。

举例1：

```
	console.log(3 < 2 && 2 < 4);
```

输出结果为false。

举例2：（判断一个人的年龄是否在18~60岁之间）

```
	var a = prompt("请输入您的年龄");
	alert(a>=18 && a<= 65);
```



## 我的公众号

想学习<font color=#0000ff>**代码之外的软技能**</font>？不妨关注我的微信公众号：**生命团队**（id：`vitateam`）。

扫一扫，你将发现另一个全新的世界，而这将是一场美丽的意外：

![](http://img.smyhvae.com/2016040102.jpg)




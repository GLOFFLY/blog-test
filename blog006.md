# js基础语法
![hello](./hello.png)

## 表达式、语句和标识符

1. 表达式总会有一个值，表达式add(1,2)的值就是函数执行的返回值
2. 语句不一定要有值，var a = 1仅仅是赋值，或者var a是声明一个变量（现在推荐用let声明变量）
3. 标识符相当于一个名字，变量、函数以及函数参数都是标识符
4. 标识符的命名规则: 第一个字符，可以是 Unicode 字母或$或_或中文后面的字符，后面还可以跟数字(即：数字不能在第一位)如:var aA,a123456,_a;

## 代码注释问题

注释并不是多就好，写程序读程序，起码的英文阅读能力还是要有的。所以一些正常的业务代码，要注意起名规范贴切，方便自己记忆也方便他人识别。太多不必要的注释会造成干扰，这就是一个信噪比的问题，少即是多。好的注释应该是：踩坑注释、遇到bug时的注释

## 条件语句
- if/else语法如下：
```javascript
if(条件为true){
    // 执行这里
} esle if(如果为true) {
     // 执行这里
} else {
    // 上面的都不为true，执行这里
}
```
- 省略括号的情况
省略后面的括号，只会执行第一句代码，不是第一行
```javascript
if(true)
console.log(1)
console.log(2)
```
但是有一种情况可以执行多条代码，添加"," 逗号表示这句没有完
```javascript
let a = 2
if (a === 2)
    console.log('a是2'),console.log('a是2嘛？')
```
所以建议不要省略括号，很容易出错
- switch
```javascript
switch(条件) {
    case 条件1:
        ....
        break;
    case 条件2:
        ....
        break;
    default:break;
}
```
注意: 使用switch时很容易忽略加break
## 三元表达式
```javascript
表达式1 ? 表达式2 :  表达式3
效果相当于：
if (表达式1) {
    表达式2
} else {
  表达式3
}
```
常用于简化if/else，很多类库会经常看到这样的写法，要明白是什么意思

## 短路逻辑

表达式1&&表达式2和表达式1 ||表达式2经常被误解的一个地方是，这个操作会转换成布尔类型，其实把它理解成为选择哪个表达式返回就可以了。

表达式1&&表达式2中，如果表达式1为假，那么就返回表达式1，否则就返回表达式2

表达式1||表达式2中，如果表达式1为假，那么就返回表达式2，否则就返回表达式1

## 循环语句while、for
```javascript
while(表达式){
    语句
}

for(语句1;语句2;语句3) {
    语句4
    /*
    for执行步骤：
    语句1，一般用来初始变量
    语句2，会先判断，如果不满足就跳出循环
    循环体语句4
    语句3，是步长，增长了多少
    */
}
```

- let和for结合

注意let在循环中的使用，let存在临时死区
```javascript
for(let a=0;a < 5;a++){
    console.log(a)
}
// 输出0到4
console.log(a) //报错(原因：let生命的a变量的生命周期仅在for循环内，for循环执行完就释放了a变量)
```
即便用了setTimeout
```javascript
for(let a=0;a < 5;a++){
setTimeout(() => console.log(a))
}
// 也会输出0到4
//方方：之前很长一段时间，我都错误的认为在ES5之前里的for+setTimeout没有输出0到4是错误，其实我才是错误
```
## break和continue

break跳出最近的for循环
continue跳过当前一次的循环

## label语法

面试可能会问
```javascript
f: {
    console.log(1)
    break f;
    console.log("这里不会打印")
}
console.log(2)
//执行效果：chrome内是f为对象，firefox内是f为label代码块
```
![end](./end.png)

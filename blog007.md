# JS对象的基本用法
![hello](./hello.png)
## JS对象的语法
1. 定义：无序的数据集合、键值对的集合
2. 声明对象的写法：
```javascript
    let obj = {'name': 'ben', 'age':18}（更简单）
    let obj = new Object ({'name':'ben'})（更规范）
    console.log({'name': 'ben', 'age':18})
```
3. 内容：
    - 属性名：每个key都是对象的属性名
    - 属性值：每个value都是对象的属性值
    - 注意点：所有属性名都会自动变成字符串，所以键名是字符串，而不是标识符，可以包含任意字符（可以是空字符串，也可以是空格字符串）引号可以省略。

4. 变量作属性名
    通常用常量作属性名let p1 = 'name' let obj = {p1:'ben'},第二句写成let obj = {[p1]:'ben'}就是变量作属性名（不加[]的属性自动变成字符串,加了[]则会当成变量，先求值，值如果不是字符串，则会自动变成字符串）

5. 对象的隐藏属性
    - JS中每一个对象都有一个隐藏属性
    - 这个存储着其共有属性组成的对象的地址
    - 这个共有属性组成的对象叫做原型
    - 也就是说，隐藏属性存储着原型的地址

## 删除属性

- delete obj.xxx或者delete obj.['xxx']，即可删除obj的xxx属性
- 不含属性名    'xxx' in obj===false
- 含有属性名，但是值为undefined    'xxx' in obj&&obj.xxx===undefined
- 注意obj.xxx===undefined 不能判定'xxx'是否为obj的属性（因为xxx定义的值有可能就undefined）
- delete删除的是属性名和属性值，undefined仅仅删除的属性值

## 查看所有属性

- 查看自身所有属性：Object.keys(obj)
- 查看自身+共有属性：console.dir(obj)
- 判断一个属性是自身的还是共有的：obj.hasOwnProperty('toString')

## 原型

1. 每个对象都有原型
    - 原型里存着对象的共有属性
    - 比如obj的原型就是一个对象
    - obj.__proto__存着这个对象的地址
    - 这个对象里有toString/constructor/valueOf等属性
2. 对象的原型也是对象
    - 对象的原型也有原型
    - obj={}的原型即为所有对象的原型
    - 这个原型包含所有对象的共有属性，是对象的根
    - 这个原型也有原型，是null

## 查看属性
- 中括号语法：obj['key']
- 点语法：obj.key
- 注意obj[key]//变量key值一般不为'key'
注：优先使用中括号语法，点语法会误导你认为key不是字符串

## 修改属性
- 直接赋值
```javascript
    let obj = {name:'ben'}//name是字符串
    obj.name = 'ben'//name是字符串
    obj['name']='ben'
    obj[name]='ben'//错因为name的值不确定
    obj['na'+'me']='ben'
    let key = 'name';obj[key] = 'ben'
    let key = 'name';obj.key = 'ben'//错，因为obj.key等价于obj['key']
```
- 批量赋值
```javascript
    Object.assign(obj,{age:18,gender:'femal'})
```
## 修改共有属性
- 无法通过自身修改或增加共有属性
```javascript
    let obj = {},obj2 ={}//共有toString
    obj.toString = 'xxx'只会修改自身属性obj2,toString还是在原型上
```
注：一般不要修改原型，会产生问题，如果一定要修改请使用Object.prototype.toString='xxx'

## 修改隐藏属性

- 推荐使用Object.create
```javascript
let obj = Object.create(common)
obj.name = 'ben'
```
！！！规范：如果要改就一开始改，不要后来再改！！！
![end](./end.png)~
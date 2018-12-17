# AngularJs基础1
<!-- TOC -->

- [AngularJs基础1](#angularjs基础1)
    - [AngularJs简介](#angularjs简介)
    - [AngularJs表达式](#angularjs表达式)
    - [AngularJs指令](#angularjs指令)
        - [ng-repeat](#ng-repeat)

<!-- /TOC -->
## AngularJs简介
AngularJS 是一个 JavaScript 框架。它可通过 `<script>` 标签添加到 HTML 页面。
AngularJS 通过 指令 扩展了 HTML，且通过 表达式 绑定数据到 HTML。

- AngularJS 把应用程序数据绑定到 HTML 元素。
- AngularJS 可以克隆和重复 HTML 元素。
- AngularJS 可以隐藏和显示 HTML 元素。
- AngularJS 可以在 HTML 元素"背后"添加代码。
- AngularJS 支持输入验证。
## AngularJs表达式
这是AngularJs绑定数据的一种方式，通过表达式将数据绑定到html。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<script src="http://cdn.static.runoob.com/libs/angular.js/1.4.6/angular.min.js"></script> 
</head>
<body>
 
<div ng-app="">
     <p>我的第一个表达式: {{ 5 + 5 }}</p>
</div>
 
</body>
</html>
```
ng-app 指令告诉 AngularJS，`<div>` 元素是 AngularJS 应用程序 的"所有者"。

表达式可以是数字，字符串，对象，数组等变量。
```html
<div ng-app="" ng-init="quantity=1;cost=5">
    <p>总价： {{ quantity * cost }}</p>
</div>

<div ng-app="" ng-init="firstName='John';lastName='Doe'">
    <p>姓名： {{ firstName + " " + lastName }}</p>
</div>

<div ng-app="" ng-init="person={firstName:'John',lastName:'Doe'}">
    <p>姓为 {{ person.lastName }}</p>
</div>

<div ng-app="" ng-init="points=[1,15,19,2,40]">
    <p>第三个值为 {{ points[2] }}</p>
</div>
```

## AngularJs指令

AngularJS 通过内置的指令来为应用添加功能。

AngularJS 允许你自定义指令。

AngularJS 指令是扩展的 HTML 属性，带有前缀 ng-。

- ng-app 指令初始化一个 AngularJS 应用程序。

- ng-init 指令初始化应用程序数据。

- ng-model 指令用于绑定应用程序数据到 HTML 控制器(input, select, textarea)的值。

```html
<div ng-app="" ng-init="firstName='John'">
 
     <p>在输入框中尝试输入：</p>
     <p>姓名：<input type="text" ng-model="firstName"></p>
     <p>你输入的为： {{ firstName }}</p>
 
</div>
```

### ng-repeat
ng-repeat 指令会重复一个 HTML 元素：
```html
<div ng-app="" ng-init="names=['Jani','Hege','Kai']">
  <p>使用 ng-repeat 来循环数组</p>
  <ul>
    <li ng-repeat="x in names">
      {{ x }}
    </li>
  </ul>
</div>
```
效果：
```html
<div ng-app="" ng-init="names=['Jani','Hege','Kai']">
  <p>使用 ng-repeat 来循环数组</p>
  <ul>
    <li>Jani</li>
    <li>Hege</li>
    <li>Kai</li>
  </ul>
</div>
```

用在对象数组上：
```html
<div ng-app="" ng-init="names=[
{name:'Jani',country:'Norway'},
{name:'Hege',country:'Sweden'},
{name:'Kai',country:'Denmark'}]">
 
<p>循环对象：</p>
<ul>
  <li ng-repeat="x    in names">
    {{ x.name + ', ' + x.country }}
  </li>
</ul>
 
</div>
```

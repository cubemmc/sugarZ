---
title: JS中对于时间以及时间戳的各种操作
abbrlink: 6f949845
date: 2019-09-17
tags:
  - Javascript
  - date
categories: date
---
项目开发中，有时需要将服务端返回的时间数据格式化，服务端返回的时间格式不同，前端对时间的操作方法也不一样。
以下是我在项目开发中遇到的一些对时间进行相关操作的总结。
<!-- more -->
#### 时间戳 -> 当前时间
时间戳 -> 当前时间(形如'2018-12-28 17:41:22')
>时间戳为10位(精确到秒)，需*1000；
>时间戳为13位(精确到毫秒)，无需乘1000。

假设前端同学获取到的时间戳是```let time = 1545990082242```，
然后调用函数```toTimeDate(time)```，返回当前时间。
toTimeDate 函数具体实现方法如下：

```
let time = 1545990082242;
console.log(toTimeDate(time)); // 输出 2018-12-28 17:41:22
function toTimeDate(timetamp) {
  var date = new Date(timetamp); // 输出 date=Fri Dec 28 2018 17:41:22 GMT+0800 (中国标准时间)
  var year = date.getFullYear(); // 输出年 2018
  var month = date.getMonth()+1; // 输出月 12
  var dates = date.getDate(); // 输出日 28
  var hour = date.getHours(); // 输出时 17
  var minute = date.getMinutes(); // 输出分 41
  var second = date.getSeconds(); // 输出秒 22
  return `${year}-${month}-${dates} ${hour}:${minute}:${second}`;
}
```

#### 当前时间 -> 时间戳
当前时间(形如'2018-12-28 17:41:22') -> 时间戳
>安卓系统中，```-```或者```/```符号都可以；
>iOS系统，只能识别```/```符号。

具体实现方法如下：
```
var date = new Date('2018-11-28 17:41:22'); // 输出date= Fri Dec 28 2018 17:41:22 GMT+0800 (中国标准时间)
// 有三种方案获取时间戳
var time1 = date.getTime()； // 方案一：精确到毫秒，输出 1545990082123
var time2 = date.valueOf()； // 方案二：精确到毫秒，输出 1545990082123
var time3 = Date.parse(date)； // 方案三：精确到秒，输出 1545990082000
```

#### 国际标准时间 -> 时间戳
国际标准时间(形如'2019-03-15T09:15:32.473Z') -> 时间戳


#### 获取当前时间的前/后一天
实现方法如下：
```
let curDate = new Date(); // Tue Sep 17 2019 13:55:11 GMT+0800 (中国标准时间)
// 当前时间的前一天
let preDate = new Date(curDate.getTime() - 24 * 60 * 60 * 1000); // Mon Sep 16 2019 13:55:11 GMT+0800 (中国标准时间)
// 当前时间的后一天
let nextDate = new Date(curDate.getTime() + 24 * 60 * 60 * 1000); // Wed Sep 18 2019 13:55:11 GMT+0800 (中国标准时间)
```

#### 获取具体某月的天数
通过Date对象可以获取到具体某月的天数是多少，而且不需要判断年份是否是闰年。
实现方法如下：
```
let dt = new Date(2015, 2, 0);
let monthDate = dt.getDate();
console.log(monthDate); // 28
```
其中Date对象里的三个参数一次表示 某年、某月、0。Date对象的月份是从0开始的，也就是说1月份用0表示，所以上述的0就表示为3月份的第0天，但是JS中日期的范围是1～31，所以当日期设为0时，会向前一天，也就是上个月的最后一天。
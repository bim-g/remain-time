# PASSED-TIME
    Welcom
This is a simple module that allow you to get the difference between two  time left from a previous past time to now. 
eg:`2min`left
this module support `es5` and `es2015`
# Introduction 
The idea is to allow with a simple module be able to get the interval of time that left from a previous time until now.

* whats you can do with
    - you can get how much times left form a previus time untill now
    - you can get the inteval of time according to a defined time
    such as this`week`, `lastweek`,`days of this month`

* whats it can do.
    apart from those module, other expected are not avaible.

# Installation
install the module, open your terminal and tape this command

```shell
    npm install time-passed
```
installation success, you can `require` the module or `import` depend on the `js` version you are using.
# Integration
The module is very easy to use.
- step one : Date Format
you need to have a date with this format`Y-M-dd` eg: `2020-12-15` and if there is time the following format is required to avoid crash, `Y-M-dd h:m:s` eg `2020-12-15 15:40:00`.

- step two : integration
include the module and form there you can pas the date as parametter, as show in the example bellow.
`require` or `import` are both support
- for ES5 or ES2017

* getTimePassed
this method allow to get how much time passed until nom.
```javascript
    const {TimePassed} = require("passed-time");
    // import {TimePassed} from "passed-time"; 
    let date="2020-12-15 21:40:10";
    const pt= new TimePassed(date)
    console.log(pt.getTimePassed());
    // 1h
```
* in case you would like to get more detail
you can diffine the configuration detail to true
```javascript
    const {TimePassed} = require("passed-time");
    // import {PassedTime} from "passed-time"; 
    let date="2020-12-15 21:40:10";
    const pt= new TimePassed(date)
    console.log(pt.getTimePassed({detail:true}));
    // 1h23m01s
```
you can display allow available module as shown on the exemple bellow
```javascript
    const {  TimePassed } = require('passed-time');

    let dat="2020-12-16 23:32";

    let past = new TimePassed(dat);

    let config={
        detail:true
    };

    let time = {
        a:past.getTimePassed(config),
        b:past.getDayOfMonth(),
        c:past.getLastWeek(),
        d:past.getThisWeek(),
        d:past.getTriSemester(),
    };
    console.log(time);
```
checkout ou the response will looks like
```shell
    {
        a: 'yesterday at 23h',
        b: 30,
        c: { from: 2020-12-06T21:32:00.000Z, to: 2020-12-12T21:32:00.000Z },
        d: { from: 2020-12-16T21:32:00.000Z, to: 2020-09-16T21:32:00.000Z }
    }
```
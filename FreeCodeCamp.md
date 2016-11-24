#FreeCodeCamp Note

##HTML

- `<h1><h2>....<h6>` remember to close ;
- `<img src="url" alt="describe-what-will-be-rendered" />`
- `<a href="url-you-want-to-go">Your Description</a>` ,in addition to `href="#"` will be dead link ;
- `<ul><li></li></ul>` **||** `<ol><li></li></ol>` ;
- `<form action="url"></form>` use to submit data ;
- `<p>   <span>    <br>    <hr>`

##Bootstrap

- Use Responsive Design: add class `container-fluid` to upper `div` tag.
- responsive img: add class `img-responsive` to `img` tag.
- `form-control` to make `form` resposive.
- change `font` :
    - `font-family` >arg_ `Monospace`,`Sans-Serif`;
    - `font-size`   >arg_ `px`,`em` [ref](https://www.w3.org/Style/Examples/007/units.en.html);
    - `font-color`  >arg_ `red`,`rgb()` || `rgba()` ,`#fff`
- `border` :
    - `border-color`  >arg_ same like `font-color` above;
    - `border-width`  >arg_ `px` ;
    - `border-style`  >arg_ `dotted`,`solid`,`double`,`dashed` [ref](http://www.w3school.com.cn/cssref/pr_border-style.asp); 
    - `border-radius` >arg_ `50%`,`10px`
- Text : 
    - Center Text: `center-text` class do that ;
    - `text-primary`, `text-danger`
- Button
    - Use Bootstrap Style Button: add class `btn` to `button` tag and `input` tag that has been qualified by `type="button"` ;
    - Make Button block(width 100%): `btn-block` ;
    - `btn-primary`,`btn-info`,`btn-danger`
- Responsive Grid System:
    - `row` : nest all `col-xx-*` div ; 
    - `col-md-*`,`col-xs-*` [ref](https://i.imgur.com/FaYuui8.png) 
- Awesome Font:
    - Use `i` tag : `<i class="fa fa-info-circle"></i>`
- Navbar
    + [TL;DW](http://getbootstrap.com/components/#navbar)(too-long-dont-write)
- fixed width: `textarea` could be fixed width, qualify by `max-width:100%`


##jQuery

- `$(ducument).ready(funtion(){})` ;
- Target Elements by `ID` `CLASSS` `TAG` 
    + `$("button").doSomething();` 
    + `$(".class").doSomething();` 
    + `$("#id").doSomething();` 
- addClass to target element: `$(".class").addClass("classname");` 
- removeClass from target element: `$(".class").removeClass("classname");` 
- change the css of an element: `$("#id").css("color","red");` 
- disable an element: `$("#id").prop("disabled",true);` 
- change text inside an element(could add tags): `$(".class").html("<em>Hi</em>");` 
- change text inside an element(tags disabled): `$(".class").text("Hi");` 
- remove an element: `$("#id").remove();` 
- use appendTo to move elements: `$(".class").appendTo("somewhere");` 
- clone an element: `$(".class").clone().appendTo("somewhere");` 
- target the parent: `$("#id").parent().css();` 
- target the children: `$("#id").children();` 
- target a Specific child of an element: `$(".class:nth-child(n)").doSomething();` 
- target even numbered elements: `$(".class:even/odd").doSomethinged();` 


##JavaScript

- Array
    + `push(item)` & `unshift(item)` : the first one push element to array on the end,the another add on the beggin;
    + `pop()` & `shift()` :  the first one pop element from the end of array,the another shift on the begin ;
    + `map()` &  `filter()` : `map( function(val,index,array) {})` has three arugments that can be used ;
    + `reduce()` : `reduce(function(pre,cur,index,array) {},initialValue)` , `initialValue` can be worked with the element of array ; 
    + `sort()` [ref](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort) :  `sort(function(pre,cur) {})` alter the array in place. 
    + `join("separator")` : uses the argument you pass in  separate the all of array words to a new Stirng **if not arg be passed in, default separated by comma**;
    + `reverse()` 
    + `concat(array)`
    + `slice()` [ref](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice): returns a shallow copy of a portion of an array into a new array object selected from begin to end (end not included). The original array will not be modified. **object reference: the original arr and new arr refer to the same object,can be changed by both of them.**
        * `arr.slice()` ;
        * `arr.slice(begin)` ;
        * `arr.slice(begin, end)`
    + `splice()` : changes the content of an array by removing existing elements and/or adding new elements.
        * `array.splice(start)` ;
        * `array.splice(start, deleteCount)` ;
        * `array.splice(start, deleteCount, item1, item2, ...)` 
```javascript
var myFish = ["angel", "clown", "mandarin", "surgeon"];
var removed = myFish.splice(2, 0, "drum");

// myFish is ["angel", "clown", "drum", "mandarin", "surgeon"] 
// removed is [], no elements removed
```


> sort can be passed a compare function as a callback. The compare function should return a negative number if a should be before b, a positive number if a should be after b, or 0 if they are equal.

```javascript
    var arr = [1,2,3]
    var narr = arr.reduce(function(pre,cur){ return pre+cur} , 1)
    //output: 7
```

- Global Scope : 

> Variables which are used without the var keyword are automatically created in the global scope. This can create unintended consequences elsewhere in your code or when running a function again. You should always declare your variables with var.

- Equality Operator:

In order for JavaScript to compare two different data types (for example, `numbers` and `strings`), it must convert one type to another.

```javascript
   1   ==  1    // true
   1   ==  2    // false
   1   == '1'   // true
  "3"  ==  3    // true
```

- Strict Equality Operator : 

 strict equality tests both the __data type__ and __value__ of the compared elements.

-  Inequality Operator :

```javascript
    1 != 2      // true
    1 != "1"    // false
    1 != '1'    // false
    1 != true   // false
    0 != false  // false
```

- Strict Inequality Operator :　

```javascript
    3 !== 3   // false
    3 !== '3' // true
    4 !== 3   // true
```

- Regular Expression :

```javascript
/** /  -- the start of expression 
    \d -- find digital number
    +  -- find once or more 
    /g -- global search  
    /i -- ignore case  
    \s -- find whitespace [ " " - space, 
                            \r  - the carriage return,
                            \n  - newline,
                            \t  - tab
                            \f  - the form feed ]


    ***********************************************************
    Invert Regular Expression : 
       invert any match by using the uppercase version of regular expression selector. 

    \S -- find any that isn't whitespace
**/
var expression = "/\d+/gi";
var expression = "/\s"
String.match(expression).length;
```


**String**

- `split()` : uses the argument you pass in as a delimiter to determine which points the string should be split at;
```javascript
var str = "abcd"
str.split()     // output: ["abcd"]
str.split("")   // output:['a','b','c','d']
```

- `substring(indexStart[, indexEnd])` : returns a subset of a string between one index and another, or through the end of the string ;   

- `str.substr(start [, length])` : returns the characters in a string beginning at the specified location through the specified number of characters ;

-  `String.fromCharCode(num1[,num2,num...])` : returns a string created by using the specified sequence of Unicode values.
```javascript
    String.fromCharCode(65, 66, 67);  // "ABC"
```
   
- `charCodeAt(index)` [ref](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt) : 

> The charCodeAt() method returns an integer between 0 and 65535 representing the UTF-16 code unit at the given index (the UTF-16 code unit matches the Unicode code point for code points representable in a single UTF-16 code unit, but might also be the first code unit of a surrogate pair for code points not representable in a single UTF-16 code unit, e.g. Unicode code points > 0x10000). If you want the entire code point value, use codePointAt(). 

```javascript
'ABC'.charCodeAt(0); // returns 65
```

##JavaScript Note

- The only values that are **not truthy** in JavaScript are the following (a.k.a. falsy values):
    + `null`
    + `undefined`
    + `0`
    + `""(the empty string)`
    + false
    + NaN

- Arguments Object [ref](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments) : three ways to convert arguments to a array
    + `var args = Array.prototype.slice.call(arguments);` ;
    + `var args = [...arguments];` ;
    + `var args = Array.from(arguments);` 

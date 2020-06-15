## Var - Let - Const

### 1. Declaration vs Initialization

#### Variable declaration 
##### introducing a new identifier

var abc
```
console.log(abc) // undefined    
```

#### Variable initialization
##### assigning a value to that variable
```
abc = "letters" 
console.log(abc) // letters
```

### 2. Scoping
##### scope defines where  variables and functions can be accessed inside your program.

#### Global Scope
declaration of a variable occurs outside of a function

```
var name = "John";
function sayMyName(){
    console.log(name);
}
sayMyName();
console.log(name);

/*
output

John
John

You can access your variable all over your application
*/

```

#### Function Scope
declaration of a variable occurs outside inside of a function

```
function sayMyName2(){
    var name2 = "John";
    console.log(name2);
}
sayMyName2();
console.log(name2);

/*
output

John
ReferenceError: name is not defined;

You can't access your variable all over your application, only inside their scope hence name2 variable is only available inside the function it was declared
*/

```

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

You can't access your variable all over your application, only inside their scope hence name2 

variable is only available inside the function it was declared
*/

```
#### Block Scope
block = one or more statements delimited by a group of curly braces   
block scope variable = that variable it exists only inside the block it has been declared;

```
{
    var name_22 = 'Max';
}
    console.log(name_22);

    /*
    Max

    so var is not blocked scoped, you can access a variable outside the block is is defined;
    */


```


### 3.Hoisting
Is the process of initialization at creation of variables with value of _undefined_, default value and moving the variable at the top of their scope.

```
console.log(name_3) //undefined;
var name_3 = "Jane" ;

trying to access a variable before it's assignation will result in _undefined_ since the declaration  is moved at the top of their scope and initialized with the default value, but not the assignation.
```

### Var vs Let vs Const


| Identifier    | Scope         | Update* |Redeclare**  |Hoisting***   |    
| ------------- |:-------------:| ------: |-----------: |-------------:| 
| VAR           | Function scope|   ✓     |    ✓       |   undefined  |  
| LET           | Block scope   |   ✓     | SyntaxError |ReferenceError| 
| CONST         | Block scope   |TypeError | SyntaxError|ReferenceError|


#### SCOPE
_Let_ / _Const_ are block scoped unlike _var_ so a variable declared with _Let_/_Const_ it can be accessed only inside that block

```
{
    let name_22 = 'Max';
}
    console.log(name_22);

    /*
    Reference Error, name_22 is not defined

    so let is blocked scoped, you can't access a variable outside the block is defined;
    */

```

#### UPDATE
*var*

 ```
 var a = "first_letter";
 console.log(a);
 a = "second_letter";
 console.log(a);
 ////
 first_letter
 second_letter
```

*let*

```
 let b = "first_letter";
 console.log(b);
 b = "second_letter";
 console.log(b);
 ////
 first_letter
 second_letter
 ```

 *const*

```
 const c = "first_letter";
 console.log(c);
 c = "second_letter";
 console.log(c);
 ////
 first_letter
 TypeError: Assignment to constant variable.
 ```

But you can update a property of a constant

```
const user = {
    name: 'John',
    age: '99'
}
console.log(user.age)

user.age=100;
console.log(user.age);

////
99
100

```

#### Redeclare
*var*

 ```
 var a = "first_letter";
 console.log(a);
 var a = "second_letter";
 console.log(a);
 ////
 first_letter
 second_letter
```

*let*

```
 let b = "first_letter";
 console.log(b);
 let b = "second_letter";
 console.log(b);
 ////
 first_letter
 SyntaxError: Identifier 'b' has already been declared
 ```

 *const*

```
 const c = "first_letter";
 console.log(c);
 const c = "second_letter";
 console.log(c);
 ////
 first_letter
 SyntaxError: Identifier 'c' has already been declared
 ```

 #### Hoisting
*var*

 ```
 console.log(a);
 var a = "first_letter";
 
 ////
 undefined
```

*let*

```
 console.log(b);
 let b = "first_letter";
 ////
 ReferenceError: Cannot access 'b' before initialization
  ```

 *const*

```
 console.log(c);
 const c = "first_letter";
 
 ////
 ReferenceError: Cannot access 'c' before initialization
 ```
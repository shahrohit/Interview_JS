# INTERVIEW QUESTION OF JAVASCRIPT

## What is difference between `undefined` and `null` ?

Javascript has two distinct value for nothing i.e `null` and `undefined`

### `undefined` :

value of variable is `not defined`. undefined is not a constant or keyword. undefined is a type with one value undefined.

#### Different ways to get Undefined :

1. A declared variable without assigning a value have undefined type.

```Javascript
let a;
console.log(a) // undefined
```

2. Implicit returns of functions due to missing return statements.

```Javascript
function fun(){}
console.log(fun()) // undefined
```

3. Return statements that do not explicitly return anything.

```Javascript
function fun(){
  return;
}
console.log(fun()) // undefined
```

4. Accessing non-existent properties in an object

```Javascript
let obj = {
  name = "Javascript"
}
console.log(obj.age) // undefined

```

5. Function parameters that have not passed.

```Javascript
function fun(name){
  console.log(name) // undefined
}
fun();
```

6. Anything that has been set to the value of undefined.

```Javascript
let val = undefined;
console.log(val); // undefined
```

### `null` :

null means empty or non-existent value which is used by programmers to indicate “no value”. null is a primitive value and you can assign null to any variable.

Officially, the `typeof null` in JavaScript returns `"object".` But it doesnot behave like a typical object

```Javascript
let val = null;
console.log(val) // null
console.log(typeof val); // object
```

## What is the difference between `==` vs `===` ?

The difference between `Abstract Equaltiy(==)` and `Strict Equaltiy(===)` that : `==` compares the values after coercion and `===` compares the value without coercion.
Suppose we have to compare x == y values.

The `==` has some conditions to perform before comparing the two values.

1. If x and y have `same type`. Then compare them with the `===` operator.
2. If x is `null` and y is `undefined` then return `true`.
3. If x is `undefined` and y is `null` then return `true`.
4. If x is type `number` and y is type `string` Then return `x == toNumber(y)`.
5. If x is type `string` and y is type `number` Then return `toNumber(x) == y.`
6. If x is type `boolean` Then return `toNumber(x) == y`.
7. If y is type `boolean` Then return `x == toNumber(y)`.
8. If x is either `string,symbol or number` and y is type `object` Then return `x == toPrimitive(y)`.
9. If x is either `object` and x is either `string,symbol` Then return `toPrimitive(x) == y.`
10. Return `false`.

`Note :` toPrimitive uses first the valueOf method then the toString method in objects to get the primitive value of that object.

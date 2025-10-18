# Scope, Closures and Hoisting

## Reading
Read the following articles:
 * [IIFE - Glossary | MDN](https://developer.mozilla.org/en-US/docs/Glossary/IIFE)
 * [Understanding Scope in Javascript | Scotch.io](https://scotch.io/tutorials/understanding-scope-in-javascript)
 * [Javascript variables hoisting in details](https://dmitripavlutin.com/javascript-hoisting-in-details/)
 * [Functions | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
 * [Javascript Scoping and Hoisting](http://www.adequatelygood.com/JavaScript-Scoping-and-Hoisting.html)

Bonus:
 * [The (Not So) Secret Lifecycle of Variables | YDKJSY](https://github.com/getify/You-Dont-Know-JS/blob/2nd-ed/scope-closures/ch5.md)


Make sure you understand the following topics:
- Scope in JavaScript
- Closures
- Hoisting

## Exercises
Without running the code, do the following for each snippet:
- Say whether it executes without an error
- If it executes, list exactly what is logged to the console (in order).

### 1) var hoisting inside an IIFE
```js
(function() {
    console.log(foo);
    var foo = 'ready';
})()
```

### 2)
```js
(function() {
    var x = 2;
    console.log('x = ' + x + ', y = ' + y);
    var y = 7;
})()
```

### 3)
```js
(function () {
    x = 1;
    console.log('x = ' + x);
    var x;
})()
```

### 4)
```js
(function() {
    for (var i = 0; i < 2; i++) {
        console.log('i = ' + i);
    }

    console.log('After loop. i = ' + i);
})()
```

### 5)
```js
(function() {
    if (true) {
        var foo = 10;
    }

    console.log(foo)
})()
```

### 6)
Answer both variants
```js
// A
(function() {
    var hero = 'Batman'
    if (true) {
        var hero = 'The Flash';
    }

    console.log(hero)
})()
```

```js
// B
(function() {
    var hero = 'Batman'
    if (false) { // changed to false
        var hero = 'The Flash';
    }

    console.log(hero)
})()
```

### 7)
```js
var foo = 1;
function bar() {
    if (!foo) {
        var foo = 10;
    }
    console.log(foo);
}
bar();
```

### 8)
```js
var a = 1;
function b() {
    a = 10;
    return;
    function a() { }
}
b();
console.log(a);
```

### 9)
```js
var x = 1;
console.log(x);
if (true) {
    var x = 2;
    console.log(x);
}
console.log(x);
```

### 10)
```js
(function () {
    var foo = 1;

    (function () {
        console.log(foo);
        var foo = 2;
        var baz = 3;
    })();

    console.log(foo);
})();
```

Additional tasks:

1. If the code is valid, organize it as the interpreter would
2. If we add `console.log(baz)` in the bottom, after `console.log(foo)`, would the code be valid? if yes, what would be the output?

### 11)
```js
(function () {
    var name = 'Baggins';

    (function () {
        console.log('Original name was ' + name);

        var name = 'Underhill';

        console.log('New name is ' + name);
    })();
})();
```

### 12)
Answer both variations
```js
// A
(function() {
    var test = "I'm global";

    function testScope() {
        var test = "I'm local";
        console.log(test);
    }

    console.log(test);
    testScope();
    console.log(test);
})();
```

```js
// B
(function() {
    var test = "I'm global";

    function testScope() {
        test = "I'm local"; // this line was changed
        console.log(test);
    }

    console.log(test);
    testScope();
    console.log(test);
})();
```

### 13)
```js
// B
(function() {
    var baz = function() {
        var foo = 5;

        function bar() {
            console.log(foo);
        }

        return bar;
    }

    var returnedFunction = baz();
    returnedFunction();
})();
```

### 14)
```js
(function() {
    var bar = 5;

    function baz() {
        function quux() {
            console.log(bar);
        }

        quux();
    }

    baz();
})();
```

### 15)
```js
(function() {
    var bar = 5;

    function baz() {
        var bar = 10;

        function quux() {
            console.log(bar);
        }

        quux();
    }

    baz();
})();
```

### 16)
Answer both variants
```js
// A
(function() {
    var quux = function() {
        console.log("I'm function expression");
    };

    function quux() {
        console.log("I'm function declaration")
    }

    quux();
})();
```

```js
// B
(function() {
    quux();

    var quux = function() {
        console.log("I'm function expression");
    };

    function quux() {
        console.log("I'm function declaration")
    }
})();
```

### 17)
```js
function test() {
    foo();
    bar();
    var foo = function() {
        console.log("'foo' function invoked");
    }
    function bar() {
        console.log("'bar' function invoked");
    }
}
test();
```

### 18)
```js
(function () {
    function foo() {
        console.log('foo function');
    }

    var foo;

    console.log(typeof foo);
})();
```

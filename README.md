# clah

**Simple JavaScript Inheritance with bound callbacks**

All credit for the inheritance system goes to John Resig. I adapted it to work both with [Node.js](http://nodejs.org) or in a browser, and added a function to generate bound callbacks.

```js
// define a class
var Person = Class.extend({

  // this is the constructor
  init : function(name) {
    this.name = name;
  },

  hello : function() {
    console.log("Hello, I'm " + this.name + "!");
  }
});

// define a subclass
var Pirate = Person.extend({

  // you can override methods
  hello : function() {
    console.log("Ahoy! Me be " + this.name + ".");
  }
});

new Person('Jim').hello();    // #=> "Hello, I'm Jim!"
new Pirate('John').hello();   // #=> "Ahoy! Me be John."

// create a bound callback
var jane = new Person('Jane');
var callback = jane.callback('hello');

callback();   // #=> "Hello, I'm Jane!"
```

## Installation

With [NPM](https://npmjs.org):

    npm install clah

In a browser:

    <script type='text/javascript' src='/path/to/your/assets/clah.min.js'></script>

Download: [Production (minified)](https://raw.github.com/AlphaHydrae/clah/master/lib/class.min.js), [Development (uncompressed)](https://raw.github.com/AlphaHydrae/clah/master/lib/class.js).

[Original Blog Post](http://ejohn.org/blog/simple-javascript-inheritance/)

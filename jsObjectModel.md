# What we talk about when we talk about the JavaScript object model

by Vaidehi Joshi ([@vaidehijoshi](https://twitter.com/vaidehijoshi))

Creator of [BaseCS](https://medium.com/basecs)

```javascript
let cat = {};
```

## Properties

We can think about properties as variables assigned to the object. Each property has a **property descriptor**, which holds internal metadata for each property _on_ a JS object. Property descriptors are themselves javascript objects.

We can manipulate an object using the configuration of its descriptors.

```javascript
cat.sound;
cat["sound"];
Object.getOwnPropertyDescriptor(cat, "sound");
// {
//  value: "meow",
//  writable: true,
//  enumerable: true,
//  configurable: true
// }
```

### Data Property

Has a _value_, which may be editable (`writable`).

```javascript
cat.sound = function() {
  return "hi!";
};
cat.sound = function() {
  return "I can write over this property!";
};
```

### Getters & Setters (Accessor Properties)

`value` and `writable` property descriptors do not exist on Getter and Setters.

```javascript
function Cat(name) {
  this.name = name;
}

Cat.prototype = {
  get sound() {
    return `Hi, my name is ${this.name}`;
  }
};

const alfred = new Cat("alfred");
alfred.sound; // "Hi, my name is Alfred"

Object.getOwnPropertyDescriptor(cat, "sound"); // { get: f(), set: undefined, enumerable: true, configurable: true }
```

### Enumerable and Configurable

These show up on every property descriptors.

`enumerable`: Will this show up when we enumerate over the object? (e.g. in a loop or using `Object.keys()`)

`configurable`: Can this property be modified or deleted? If `false`, it cannot be deleted or changed.

#### `configurable`

By default, all Objects are _extensible_ — new properties can be added to the object

`Object.seal()`: Don't let new properties be added or existing ones removed, but allow existing properties to be altered

`Object.freeze()`: Don't let properties be added, removed, or changed

Gotchas with `Object.freeze()`:

- A getter's value isn't going to be frozen
- Properties with _other javascript objects_ as their value also need to be explicitly frozen (e.g. deep freeze 🥶)

#### `enumerable`

An object's _parent's_ properties are _not_ emumerable. Only its _own_ properties are enumerable.

### Reflect

[When possible use `Reflect`, not `Object` (ES2015)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Reflect/Comparing_Reflect_and_Object_methods)

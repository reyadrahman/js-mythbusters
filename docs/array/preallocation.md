# Preallocation

It's typical to use an `Array` as a temporal container of data.

!> If you need to work with binary data, use a [Buffer](https://www.npmjs.com/package/buffer).

Instead of allocating a new `Array` every time, a good approach in terms of
performance is to reuse the same array instance.

To clean the elements of an `Array` the most evident approach is to use `.pop`
in a loop to remove them all.

```js
const array = [1, 2, 3, 4, 5]
while (array.length) array.pop()
console.log(array) // []
```

However, a better and simpler method is to use [`Array.prototype.length`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/length). This property is writable, and will remove all the elements if you set its value to `0`.

```js
const array = [1, 2, 3, 4, 5]
array.length = 0
console.log(array) // []
```

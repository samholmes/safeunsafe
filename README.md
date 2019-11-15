# Motivation

Optional Chaining is accessing properties on an variable that may be undefined
without throwing areference errors. Optional Chaining is a proposed JavaScript
feature at an expiremental stage as of writing. The motivation behind this library
is to provide an alternative to the proposed optional chaining operator.

# Install

```js
npm i safeunsafe
```

# Usage

```js
const safe = require('safeunsafe')

const obj = {
	foo: 'bar',
}

console.log(safe(obj).foo.unsafe) // Prints 'bar'
console.log(safe(undefined).foo.unsafe) // Prints undefined
console.log(safe(obj).foo.bar.baz.unsafe) // Prints undefined
```

Simply pass a variable to the safe function and retrieve the final value using
the `unsafe` property.

A second argument is available to rename the unsafe property in situations where
this identifier is apart of the object.

```js
const obj = {
	unsafe: 'Hello',
}

console.log(safe(obj, 'done').unsafe.done) // Prints 'Hello'
```

# License

MIT

Copyright 2019 Samuel Holmes

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

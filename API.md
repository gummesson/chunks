# Chunks

## API

### Collections

#### Chunks.forEach / Chunks.each

~~~ javascript
Chunks.forEach(obj, iterator[, scope]);
~~~

Executes the `iterator` on every item in the `obj`. The `scope` is the value of `this`.

##### Example

~~~ javascript
var results = [];

Chunks.forEach([1, 2, 3], function(v) {
  results.unshift(v);
});
// [3, 2, 1]
~~~

#### Chunks.map

~~~ javascript
Chunks.map(obj, iterator[, scope]);
~~~
Returns a new and transformed array by executing the `iterator` on every item in the `obj`. The `scope` is the value of `this`.

##### Example

~~~ javascript
Chunks.map([1, 2, 3], function(v) {
  return v + 1;
});
// [2, 3, 4]
~~~

#### Chunks.filter

~~~ javascript
Chunks.filter(obj, iterator[, scope]);
~~~

Returns a new and transformed array by executing the `iterator` on every item in the `obj`. Only the items that evalute to `true` in the `iterator` will be added to the array. The scope is the value of `this`.

##### Example

~~~ javascript
Chunks.filter([1, 2, 3], function(v) {
  return v % 2;
});
// [1, 3]
~~~

#### Chunks.reduce

~~~ javascript
Chunks.reduce(obj, iterator, memo[, scope]);
~~~

Returns a single value by executing the `iterator` on every item in the `obj` and passing the previous value, `memo`, to the `iterator`. The scope is the value of `this`.

##### Example

~~~ javascript
Chunks.reduce([1, 2, 3], function(m, v) {
  return m + v;
}, 0);
// 6
~~~

#### Chunks.some

~~~ javascript
Chunks.some(obj, iterator[, scope]);
~~~

Returns either `true` or `false` by executing the `iterator` on every item in the `obj`. It'll return `true` if one of the items in the `obj` matches the `iterator`. The scope is the value of `this`.

##### Example

~~~ javascript
Chunks.some([1, 2, 3], function(v) {
  return v === 3;
});
// true
~~~

#### Chunks.every

~~~ javascript
Chunks.every(obj, iterator[, scope]);
~~~

Returns either `true` or `false` by executing the `iterator` on every item in the `obj`. It'll return `true` if all of the items in the `obj` matches the `iterator`. The scope is the value of `this`.

##### Example

~~~ javascript
Chunks.every([1, 2, 3], function(v) {
  return v > 2;
});
// false
~~~

#### Chunks.find

~~~ javascript
Chunks.find(obj, item);
~~~

Returns the index of the `item` in the `obj`. It returns the index of the item, or `-1` if nothing is found.

It delegates to `indexOf` whenever it can, albeit without the option of choosing the start index (hence the different name).

##### Example

~~~ javascript
Chunks.find([1, 2, 3], 2);
// 1
~~~

#### Chunks.contains

~~~ javascript
Chunks.contains(obj, item);
~~~

Determines if the `obj` contains the `item`. It returns either `true` or `false`.

##### Example

~~~ javascript
Chunks.contains([1, 2, 3], 2);
// true
~~~

#### Chunks.size

~~~ javascript
Chunks.size(obj);
~~~

Returns the size of the `obj`.

##### Example

~~~ javascript
Chunks.size(['a', 'b', 'c']);
// 3
~~~

### Types

#### Chunks.isArray

~~~ javascript
Chunks.isArray(obj);
~~~

Determines if the `obj` is an array. It returns either `true` or `false`.

##### Example

~~~ javascript
Chunks.isArray([1, 2, 3]);
// true
~~~

#### Chunks.isObject

~~~ javascript
Chunks.isArray(obj);
~~~

Determines if the `obj` is an object. It returns either `true` or `false`.

##### Example

~~~ javascript
Chunks.isObject({one: 1, two: 2, three: 3});
// true
~~~

### Arrays

#### Chunks.first

~~~ javascript
Chunks.first(arr);
~~~

Returns the first item in the `arr`.

##### Example

~~~ javascript
Chunks.first([1, 2, 3]);
// 1
~~~

#### Chunks.last

~~~ javascript
Chunks.last(arr);
~~~

Returns the last item in the `arr`.

##### Example

~~~ javascript
Chunks.last([1, 2, 3]);
// 3
~~~

#### Chunks.flatten

~~~ javascript
Chunks.flatten(arr);
~~~

Returns a new and transformed array by flattening the nested arrays in the `arr`.

##### Example

~~~ javascript
Chunks.flatten([[1, 2, 3], [4, 5, 6]]);
// [1, 2, 3, 4, 5, 6]
~~~

### Objects

#### Chunks.keys

~~~ javascript
Chunks.keys(obj);
~~~

Return a new array with keys from the `obj`.

##### Example

~~~ javascript
Chunks.keys({one: 1, two: 2, three: 3});
// ['one', 'two', 'three']
~~~

#### Chunks.values

~~~ javascript
Chunks.values(obj);
~~~

Return a new array with values from the `obj`.

##### Example

~~~ javascript
Chunks.values({one: 1, two: 2, three: 3});
// [1, 2, 3]
~~~

#### Chunks.has

~~~ javascript
Chunks.has(obj, key);
~~~

Determine if the `obj` has the `key`. It returns either `true` or `false`.

##### Example

~~~ javascript
Chunks.has({one: 1, two: 2, three: 3}, 'two');
// true
~~~

#### Chunks.extend

~~~ javascript
Chunks.extend(obj, src);
~~~

Merge the properties in the `obj` together with the properties in the `src`.

##### Example

~~~ javascript
Chunks.extend({one: 1, two: 3}, {two: 2, three: 3});
// {one: 1, two: 2, three: 3}
~~~

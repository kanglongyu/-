### JavaScript数组常用API方法汇总

#### 1、push() 

​		方法将一个或多个元素添加到数组的末尾，并返回该数组的新长度。

```javascript
const animals = ['pigs', 'goats', 'sheep'];

const count = animals.push('cows');
console.log(count);
// expected output: 4
console.log(animals);
// expected output: Array ["pigs", "goats", "sheep", "cows"]

animals.push('chickens', 'cats', 'dogs');
console.log(animals);
// expected output: Array ["pigs", "goats", "sheep", "cows", "chickens", "cats", "dogs"]
```

#### 2、pop()

​		方法从数组中删除最后一个元素，并返回该元素的值。此方法更改数组的长度。

```javascript
const plants = ['broccoli', 'cauliflower', 'cabbage', 'kale', 'tomato'];

console.log(plants.pop());
// expected output: "tomato"

console.log(plants);
// expected output: Array ["broccoli", "cauliflower", "cabbage", "kale"]

plants.pop();

console.log(plants);
// expected output: Array ["broccoli", "cauliflower", "cabbage"]
```

#### 3、shift() 

​		方法从数组中删除第一个元素，并返回该元素的值。此方法更改数组的长度。

```javascript
const array1 = [1, 2, 3];

const firstElement = array1.shift();

console.log(array1);
// expected output: Array [2, 3]

console.log(firstElement);
// expected output: 1
```

#### 4、unshift() 

​		方法将一个或多个元素添加到数组的开头，并返回该数组的新长度(该方法修改原有数组)。

```javascript
const array1 = [1, 2, 3];

console.log(array1.unshift(4, 5));
// expected output: 5

console.log(array1);
// expected output: Array [4, 5, 1, 2, 3]
```

#### 5、concat() 

​		方法用于合并两个或多个数组。此方法不会更改现有数组，而是返回一个新数组。

```javascript
const array1 = ['a', 'b', 'c'];
const array2 = ['d', 'e', 'f'];
const array3 = array1.concat(array2);

console.log(array3);
// expected output: Array ["a", "b", "c", "d", "e", "f"]
```

#### 6、join()

​		 方法将一个数组（或一个类数组对象）的所有元素连接成一个字符串并返回这个字符串。如果数组只有一个项目，那么将返回该项目而不使用分隔符。

```javascript
const elements = ['Fire', 'Air', 'Water'];

console.log(elements.join());
// expected output: "Fire,Air,Water"

console.log(elements.join(''));
// expected output: "FireAirWater"

console.log(elements.join('-'));
// expected output: "Fire-Air-Water"
```

#### 7、indexOf()

​		方法返回在数组中可以找到一个给定元素的第一个索引，如果不存在，则返回-1。

```javascript
const beasts = ['ant', 'bison', 'camel', 'duck', 'bison'];

console.log(beasts.indexOf('bison'));
// expected output: 1

// start from index 2
console.log(beasts.indexOf('bison', 2));
// expected output: 4

console.log(beasts.indexOf('giraffe'));
// expected output: -1
```

#### 8、includes() 

​		方法用来判断一个数组是否包含一个指定的值，根据情况，如果包含则返回 true，否则返回false。

```js
const array1 = [1, 2, 3];

console.log(array1.includes(2));
// expected output: true

const pets = ['cat', 'dog', 'bat'];

console.log(pets.includes('cat'));
// expected output: true

console.log(pets.includes('at'));
// expected output: false
```

#### 9、reverse() 

​		方法将数组中元素的位置颠倒，并返回该数组。此方法会改变原始数组

```js
const array1 = ['one', 'two', 'three'];
console.log('array1:', array1);
// expected output: "array1:" Array ["one", "two", "three"]

const reversed = array1.reverse();
console.log('reversed:', reversed);
// expected output: "reversed:" Array ["three", "two", "one"]

// Careful: reverse is destructive -- it changes the original array.
console.log('array1:', array1);
// expected output: "array1:" Array ["three", "two", "one"]
```

#### 10、slice() 

​		方法返回一个新的数组对象，这一对象是一个由 begin 和 end 决定的原数组的浅拷贝（包括 begin，不包括end）。原始数组不会被改变。

```js
const animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];

console.log(animals.slice(2));
// expected output: Array ["camel", "duck", "elephant"]

console.log(animals.slice(2, 4));
// expected output: Array ["camel", "duck"]

console.log(animals.slice(1, 5));
// expected output: Array ["bison", "camel", "duck", "elephant"]
```

#### 11、splice() 

​		splice() 方法向/从数组中添加/删除项目，然后返回被删除的项目。通过添加并删除，也可以达到替换元素的目的。

​		注释：该方法会改变原始数组。

```js
const months = ['Jan', 'March', 'April', 'June'];
months.splice(1, 0, 'Feb');
// inserts at index 1
console.log(months);
// expected output: Array ["Jan", "Feb", "March", "April", "June"]

months.splice(4, 1, 'May');
// replaces 1 element at index 4
console.log(months);
// expected output: Array ["Jan", "Feb", "March", "April", "May"]
```

#### 12、forEach() 

​		方法对数组进行循环遍历。

```js
var arr4 = [10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20];
arr4.forEach((item, index, a) => {
   // 参数item: 数组中每一项的内容
   // 参数index: 数组索引
   // 参数a: 指的是数组本身
   console.log(item + " " + index + " " + (a === arr4));
});
```

#### 13、map() 

​		方法创建一个新数组，其结果是该数组中的每个元素都调用一个提供的函数后返回的结果。

```js
const array1 = [1, 4, 9, 16];

// pass a function to map
const map1 = array1.map(x => x * 2);

console.log(map1);
// expected output: Array [2, 8, 18, 32]
```

#### 14、filter() 

​		方法创建一个新数组, 其包含通过所提供函数实现的测试的所有元素。

```js
const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

const result = words.filter(word => word.length > 6);

console.log(result);
// expected output: Array ["exuberant", "destruction", "present"]
```

#### 15、every() 

​		方法测试一个数组内的所有元素是否都能通过某个指定函数的测试。它返回一个布尔值。

```js
const isBelowThreshold = (currentValue) => currentValue < 40;

const array1 = [1, 30, 39, 29, 10, 13];

console.log(array1.every(isBelowThreshold));
// expected output: true
```

#### 16、some() 

​		方法测试数组中是不是至少有1个元素通过了被提供的函数测试。它返回的是一个Boolean类型的值。

```js
const array = [1, 2, 3, 4, 5];

// checks whether an element is even
const even = (element) => element % 2 === 0;

console.log(array.some(even));
// expected output: true
```

#### 17、findIndex()

​		方法返回数组中满足提供的测试函数的第一个元素的索引。否则返回-1。

```js
const array1 = [5, 12, 8, 130, 44];

const isLargeNumber = (element) => element > 13;

console.log(array1.findIndex(isLargeNumber));
// expected output: 3
```

#### 18、find() 

​		方法返回数组中满足提供的测试函数的第一个元素的值。否则返回 undefined。

```js
const array1 = [5, 12, 8, 130, 44];

const found = array1.find(element => element > 10);

console.log(found);
// expected output: 12
```

#### 19、sort() 

​		方法对数组的元素进行排序，并返回数组，数组内传入指定规则的函数。默认排序顺序是在将元素转换为字符串，然后比较它们的UTF-16代码单元值序列时构建的，由于它取决于具体实现，因此无法保证排序的时间和空间复杂性。

```js
// 升序 
arr1.sort(function (x,y) {
    return x-y
})
console.log(arr1); // [1, 2, 3, 4, 5, 6, 7, 8, 9]
// 降序
arr1.sort(function (x, y){
    return y-x
})
console.log(arr1); // [9, 8, 7, 6, 5, 4, 3, 2, 1]
```

#### 20、fill() 

​		方法用一个固定值填充一个数组中从起始索引到终止索引内的全部元素。不包括终止索引。

```js
const array1 = [1, 2, 3, 4];

// fill with 0 from position 2 until position 4
console.log(array1.fill(0, 2, 4));
// expected output: [1, 2, 0, 0]

// fill with 5 from position 1
console.log(array1.fill(5, 1));
// expected output: [1, 5, 5, 5]

console.log(array1.fill(6));
// expected output: [6, 6, 6, 6]
```

#### 21、reduce()

​		待完善

#### 22、from()

​		待完善


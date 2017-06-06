# Comments
注释通常来说是个好东西，但是很多新手会用错了方法，他们会将注释解释为“这段代码是用来干嘛”

但是应该避免太多的“解释性”的注释

严谨点来说的话，风格优雅的代码不需要任何注释都能轻易阅读清楚

从而就有一个很好的注释规则：如果代码缺少了注释，就会难以让人快速地知道它的用途，那建议最好重写这段代码

有时候用一个函数来代替一段代码是非常有益的，例如：
```js
function showPrimes(n) {
	nextPrime:
	for (let i = 2; i < n; i++) {

		// check if i is a prime number
		for (let j = 2; j < i; j++) {
			if (i % j === 0) continue nextPrime;
		}

		alert(i);
	}
}
```

更好的写法：
```js
function showPrimes(n) {

	for (let i = 2; i < n; i++) {
		if (!isPrime(i)) continue;

		alert(i);
	}
}

function isPrime(n) {
	for (let i = 2; i < n; i++) {
		if (n % i == 0) return false;
	}
	return true;
}
```

现在我们就能明白代码也可以不需要注释也能拥有非常好的可读性，这种代码也叫作自我描述性代码

请看下面的代码：
```js
// here we add whiskey
for (let i = 0; i < 10; i++) {
	let drop = getWhiskey();
  smell(drop);
  add(drop, glass);
}

// here we add juice
for (let t = 0; t < 3; t++) {
  let tomato = getTomato();
  examine(tomato);
  let juice = press(tomato);
  add(juice, glass);
}
```

我们可以将上述代码重构成如下代码所示：
```js
addWhiskey(glass);
addJuice(glass);

function addWhiskey(container) {
  for (let i = 0 ; i < 10; i++) {
    let drop = getWhiskey();
    //...
  }
}

function addJuice(container) {
  for (let t = 0; t < 3; t++) {
    let tomato = getTomato();
    //...
  }
}
```

重构后的代码不再带有注释，同样代码在分割后结构更完美，每个函数做什么事，返回什么值都很清晰明了。

## Good comments 好的注释
怎么样的注释才是好注释呢？

### Describe the architecture 结构描述
提供组件的高级描述，它们如何交互，不同情况下的控制流程是怎么样的，总而言之，也就是代码的鸟瞰图。

### Document a function usage
下面有一种特殊的语法`JSDoc`，用来描述函数的作用，参数，返回值

http://usejsdoc.org/


例如：
```js
/**
 * Returns x raised to the n-th power.
 *
 * @param {number} x The number to raise.
 * @param {number} n The power, must be a natural number.
 * @return {number} x raised to the n-th power.
 */
function pow(x, n) {
  ...
}
```

这种注释的写法可以使开发人员不需要阅读代码即可明白函数的作用，目的等等
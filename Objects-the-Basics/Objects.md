# Objects
我们可以从`Data types`的章节中直到，`JavaScript`中有7种语言类型，其中6种被称为原始类型。因为它们的值很简单，不是字符串就是数字或者其他。

然而，对象用于存储各种键值对和更复杂的实体。在`JavaScript`中，对象几乎渗透到了语言的各个方面。因此我们必须先了解它们才能对`JavaScript`进行更进一步的研究。

对象可以用大括号`{...}`附加上一系列的属性选项来创建。每个属性都是一对键值对，其中键`key`为字符串，也称为属性名称，而值`value`可以为任何东西。

我们可以将对象想象成一个文件柜。每一块数据通过键`key`来存储在各自的文件夹中，这样我们就可以很容易通过文件的名字来添加或者删除文件了。

![object](image/object.png)

空对象可以用如下两种语法来创建：

```js
let user = new Object(); // "object constructor" syntax
let user = {}; // "object literal" syntax
````

![object-user-empty](image/object-user-empty.png)

通常，我们使用大括号来创建空对象。

# Literals and properties
我们可以在大括号中添加键值对。

```js
let user = {
    name: "John",
    age: 30
}
```

一个属性值有一个键在`":"`的左边，和一个值在它的右边。

在`user`对象中就有两个属性：

1. 第一个属性有一个名字键：`"name"`和一个值：`"John"`
2. 第二个属性有一个名字键：`"age"`个一个值：`30`

`user`对象也可以想象成一个放着有两个文件的抽屉。

![object-user](image/object-user.png)

我们可以随时从抽屉中增加，查阅和取出文件。

属性值可以通过`.`来进行访问

```js
alert(user.name);
alert(user.age);
```

属性值可以为任意类型。让我们来添加一个布尔值：

```js
user.isAdmin = true;
```

![object-user-isadmin](image/object-user-isadmin.png)

我们可以使用`delete`来移除属性

```js
delete user.age;
```

![object-user-delete](image/object-user-delete.png)

我们还可以使用多字属性名，但它们必须使用引号括起来：

```js
let user = {
    name: "John",
    age: 30,
    "like birds": true
}
```

![object-user-props](image/object-user-props.png)

## Trailing comma
在列表中的最后一个属性带有`,`：

```js
let user = {
    name: "John",
    age: 30,
}
```

这个叫尾逗号或者悬挂都好。因为所有行都是类似的，这样可以更加容易添加/移除/移动属性。
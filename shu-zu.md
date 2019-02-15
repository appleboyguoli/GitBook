Swift中的数组

* 数组是一堆有序的由相同类型元素构成的集合
* 数组中的元素是有序的，可以重复出现
* Swift用Array表示数组，是一个泛型集合
* 与OC数组的区别
* * Array是一个结构体，而不是一个类
  * 可以放普通类型

数组的初始化

* 数组分为：可变数组和不可变数组
* * 使用let修饰的数组是不可变数组
  * 使用var修饰的数组是可变数组

```swift
//第一种定义方式
var array:Array<String> = Array()
array.append("zhangguoli")

//定义一个可变数组，必须初始化才可以使用
var array1: [String] = [String]()
//自己做类型推断
var array1 = [String]()

//定义一个不可变数组
var array2: [String] = ["zhangsan", 18]
let array2:[Any] = ["zhangsan",12]
print(array2)
```

判断数组是否为空

```swift
var array = [String]()
array.isEmpty() //判断是否为空，为空则为true
```

插入元素

```swift
var array = [String]()
array.insert("guoli",at:10)
```

删除元素

```swift
var array = [String]()
array.remove(at:3)
array.removeFirst()
array.removeLast()
```

修改元素

```swift
var array = [String]()
array[0] = "A"
```

数组遍历

```swift
let array3 = ["123","234","345"]

//元素遍历
for item in array3 {
    print(item)
}

//下标遍历
for i in 0..<array3.count {
    print(array3[i])
}

//局部遍历
for item in array3[0..<2] {
    print(item)
}

//元祖方式遍历
for (index,value) in array3.enumerated() {
    print("索引为\(index)的元素值为\(value)")
}

```




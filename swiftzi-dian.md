### 字典的介绍

* 字典是由键值对\(key:value\)组成的集合
* 字典中的元素之间是无序的
* 字典是由两部分构成的，一个是键集合，一个值集合
* 字典是通过访问键间接访问值的
* 键集合不能有重复的元素，而值集合可以有重复的元素
* Swift中的字典类型是Dictionary，也是一个泛型集合

##### 字典的初始化

* Swift中也存在可变和不可变字典
* * 使用let修饰的字典是不可变字典
  * 使用var修饰的字典是可变字典

```swift
//定义一个可变字典
var dict1: [String: Any] = [String: Any]()

//定义一个不可变字典
let dict2: [String: Any] = ["name": "zhangsan","age":10]
```

* 在声明一个Dictionary类型的时候可以使用下面的语句之一

```swift
var dict3: Dictionary<Int, String>
var dict3: [Int: String]
```

```swift
//如果字典中存在那么修改，如果没有那么添加
 dict2["sex"] = "male"
 dict2.updateValue(18, forKey: "age")
```

* 字典的删除

```swift
dict2.removeValue(forKey: "name")
```

* 字典的遍历

```swift
for item in dict2 {
    print(item)
}

for (key, value) in dict2 {
    print("key is \(key) value is \(value)")
}
```




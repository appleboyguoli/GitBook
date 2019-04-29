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

//初始化一个空字典
var dict1:Dictionary<Int,String> = [:]//其中键是Int型  值是String型
var dict2:[String:String] = [:]//其中键、值都是String型
var dict3 = [String:String]()
var dict4 = Dictionary<String,String>()
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
//元素遍历
for item in dict2 {
    print(item)
}

//键值对遍历
for (key, value) in dict2 {
    print("key is \(key) value is \(value)")
}

//元祖遍历
for (index, value) in dict2.enumerated() {
    print("index is \(index) value is \(value)")
}
```

* 字典的合并

```swift
var a = ["name":"zhangsan","id":"123456"]
var b = ["sex":"male","class":"grad3 1"]

for (key, value) in b {
    a[key] = value
}
print(a)
```

字典keys和values的值获取



```
//
```

```
当只是需要使用某个字典的键集合或者值集合来作为某个接收Array 可以直接使用keys或者values属性构造一个新数组

        let dictKeyArray =
 [String](dict.keys)
        let dictValuesArray 
=
 [Any](dict.values)
        print(
"
dictKeyArray = \(dictKeyArray) \n dictValuesArray = \(dictValuesArray)
"
)

```

```swift
//当只是需要使用某个字典的键集合或者值集合来作为某个接收Array 可以直接使用keys或者values属性构造一个新数组
let dictKeyArray = [String](dict.keys)
let dictValuesArray = [Any](dict.values)        
print("dictKeyArray = \(dictKeyArray) \n dictValuesArray = \(dictValuesArray)")
```

字典的遍历

```swift
//字典的遍历，使用for - in 循环来遍历字典中的键值对，每个字典中的数据项都以（key，value）元组的形式返回，可以使用临时常量或者变量来分解这些元组
for dictValure in dict {
        print("字典遍历的结果:\(dictValure)")
}
/**
 输出结果：
 字典遍历的结果:(key: "name", value: "sunfusheng")
 字典遍历的结果:(key: "age", value: 20)         字典遍历的结果:(key: "blog", value: "sunfusheng.com")
 */
        
        
//可以单独遍历出字典里的所有keys 或 values值
//(1)获取字典中所有的键
for dictKey in dict.keys {
    print("dictKey = \(dictKey)")
}

```




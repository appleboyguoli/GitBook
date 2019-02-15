  


//字符

```swift
varchar:Character ="A"
print(char)
```

//字符串

```swift
varstr:String= "Hello World"
print(str)
```

//类方法初始化

```swift
varstr2: String = String("ABC")
print(str2)
```

//多行格式的字符串

```swift
var shi:String = """
     静夜思
作者：李白
床前明月光，疑是地上霜。
举头望明月，低头思故乡。
"""
print(shi)
```



//字符串的用法

//1.差值

```swift
var age = 10
print("小明今年\(age)岁")
```

//2,遍历字符串

```swift
for character inshi {
print(character)
}
```

//3,长度

```swift
print(shi.count)
```



//4，拼接

```swift
print(str+str2)

```



//5,截取某字符串前5个字符

```swift
print(str.prefix(5))
//也可以换种写法
let index2 = str.index(str.endIndex,offsetBy:-5)
let sub2 = str[index2..<str.endIndex]
print(sub2)


let index3 = str.index(str.startIndex, offsetBy: 5)
let sub3 = str[str.startIndex..<index3]
print("sub3 is \(sub3)")
```



//6,截取某字符串第3个到第8个字符

```swift
let index4 = str.index(str.startIndex, offsetBy: 3)
let index5 = str.index(str.startIndex, offsetBy: 8)
letsub38 = str[index4..<index5]
print(sub38)
```




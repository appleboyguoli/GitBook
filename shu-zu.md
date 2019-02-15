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

数组的合并

```swift
//相同类型的合并
let a = ["1","2","3"]
let b = ["a","b","c"]
let c = a + b
print(c)

//不同类型的合并的时候使用Any来声明数组
let a: [Any] = ["1","2","3"]
let b: [Any] = ["a","b","c"]
let d: [Any] = [1, 2, 3]
let e: [Any] = b + d
print(e)
```

数组的排序

```swift
//数组的排序
//使用sort方法和闭包对数组进行排序
var arraySort1 : Array<Int> = [3, 6, 1, 7, 2, 4, 9, 5, 8]
//从大到小对数组进行排序
func sortBigSmall(num1: Int, num2: Int)-> Bool{
    return num1 > num2
}
arraySort1.sort(by: sortBigSmall)
print(arraySort1)


//可以不用指定参数类型，编译器会帮我们判断
var arraySort2: Array<Int> = [3, 6, 1, 7, 2, 4, 9, 5, 8]
arraySort2.sort { (num1, num2) -> Bool in
    return num1 < num2
}
print(arraySort2)


//3. 可以省略参数名，直接根据数字来引用参数
var arraySort3: Array<Int> = [3, 6, 1, 7, 2, 4, 9, 5, 8]
arraySort3.sort(by:{
    return $0 > $1
})
print(arraySort3)


//4. 如果闭包只有一行代码，可以省略return
var arraySort4: Array<Int> = [3, 6, 1, 7, 2, 4, 9, 5, 8]
arraySort4.sort(by:{
     $0 > $1
})
print(arraySort4)


//5. 如果闭包是函数调用的最后一个参数，可以将闭包放到括号外面，提高代码的可读性
var arraySort5: Array<Int> = [3, 6, 1, 7, 2, 4, 9, 5, 8]
arraySort5.sort(){
    $0 > $1
}
print(arraySort5)

//6. 换行也是可选的，代码可以继续简洁
var arraySort6: Array<Int> = [3, 6, 1, 7, 2, 4, 9, 5, 8]
arraySort6.sort(){$0 > $1}
print(arraySort6)


struct UserInfo{
    var name = String()
    var phone = String()
    
    init(name: String, phone: String) {
        self.name = name
        self.phone = phone
    }
}

var userList = [UserInfo]()
userList.append(UserInfo(name: "张三", phone: "1333443434344"))
userList.append(UserInfo(name: "李四", phone: "1333443434344"))
userList.append(UserInfo(name: "王五", phone: "1333443434344"))

//按照姓名进行降序排序
userList.sort { (user1, user2) -> Bool in
    return user1.name > user2.name
}
for item in userList {
    print(item)
}


//这事我们的Model
class imageFile{
    var fileName = String()
    var fileID = Int()
}

//使用
var images: [imageFile] = []
images.sorted { (image1, image2) -> Bool in
    return image1.fileID > image2.fileID
}

images.sort(by: { image1, image2 in return image1.fileID > image2.fileID })

images.sort(by: { image1, image2 in image1.fileID > image2.fileID })

images.sort(by: { $0.fileID > $1.fileID })
images.sort(by: { $0.fileID > $1.fileID })
images.sorted(by: { $0.fileName > $1.fileName})

```



提前记录下NSDictionay的排序

```swift
let dictionary = [
    "A" : [1, 2],
    "Z" : [3, 4],
    "D" : [5, 6]
]

let sortedKeys = Array(dictionary.keys).sorted() // ["A", "D", "Z"]

//按照Key进行排序
let sortedKeysAndValues = dictionary.sorted {$0.0 > $1.0}
print(sortedKeysAndValues) // [(A, [1, 2]), (D, [5, 6]), (Z, [3, 4])]

//按照value进行排序
let sortedKeysAndValues = dictionary.sorted {$0.1 > $1.1}
print(sortedKeysAndValues)
```




# Swift函数

* 函数的基本定义

```swift
func 函数名(参数列表)->返回值类型{
    函数体
    返回结果
}

例：
func sum(num1: Int, num2: Int) -> Int{
    return num1 + num2
}
```

* 无参数有返回值的函数

```swift
func readMessage() -> String{
    return "这是一条来自10086的短信"
}
```

* 无参数无返回值的函数

```swift
//没有参数，返回值为空
func excute()->Void{
    //函数体
}

//可以用()来代替void
func excute() -> (){
    //函数体
}

//可以直接省略->()
func excute(){
    //函数体
}
```

* 有参数没有返回值

```swift
func callPhone(phoneNumber: String){
    print("打电话给\(phoneNumber)")
}
callPhone(phoneNumber:"18888888888888")
```

* 返回值是复杂类型

```swift
//返回值是复杂类型
func triple(info: String) -> (name:String,age:Int){
    let infos = info.components(separatedBy: ",")
    return(infos[0],Int(infos[1])!);
}

let p = triple(info: "zhangsan,20")
p.name
p.age
```



* 函数给我们留下的坑
* * 注意一，函数的参数虽然没有使用var和let修饰，但它是常量，不能再函数内修饰

```swift
func say(message: String){
    //报错: Cannot assign to value 'message' is a 'let' constants
    message = "Hello Swift"
    print("说话内容: \(message)")
}

```

* * 注意二：每一个函数的形式参数都包含_形式参数标签_和形式参数名两部分



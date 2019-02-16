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

* 无参数的函数

```swift
func sum1() -> Int{
    return 10
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




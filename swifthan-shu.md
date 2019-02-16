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
  * * 形式参数标签用在调用函数的时候
    * 形式参数名用在函数的实现当中
    * 在调用函数的时候每一个形式参数前边都要写形式参数标签
    * 默认情况下，形式参数使用它们的形式参数名作为形式参数标签
    * 如果不想要形式参数标签，可以再参数名称前加\_

  ```swift
  //a 与 b为形式参数标签，num1与num2为形式参数名
  func minus(a num1: Int, b num2: Int) -> Int{
      return num1 - num2
  }

  minus(a: 10, b: 3)

  func multi(_ num1: Int, _ num2: Int) -> Int{
      return num1 * num2
  }

  multi(10, 3)
  ```
* 默认参数

* ```swift
  //默认参数
  func makeCoffee(type: String = "卡布奇诺") -> String{
      return "您点了一杯\(type)咖啡"
  }
  print(makeCoffee(type: "拿铁"))
  print(makeCoffee())
  ```
* 可变参数

* ```swift
  //可变参数
  func total(numbers: Int...) -> Int{
      //numbers 是什么类型
      var sum = 0

      for item  in numbers {
          sum += item
      }
      return sum
  }

  print(total())
  print(total(numbers: 1,2,3,4))
  print(total(numbers: 10,13))
  ```
* 引用类型

* ```swift
  //inout 关键字，inout表示接收的是传过来的地址
  func swapInt(a: inout Int, b: inout Int){
      let temp = a
      a = b
      b = temp
  }

  var a = 10
  var b = 20
  print("a = \(a) b = \(b)")

  swap(&a, &b)
  print("a = \(a) b = \(b)")
  ```

* 函数的嵌套
* ```swift
  //函数的嵌套
  let value = 55
  func test(){
      func demo(){
          print("demo \(value)")
      }
      print("test")
      demo()
  }

  test()
  ```

* 函数的类型
* * 每个函数都有属于自己的类型，由函数的参数类型和返回类型组成
  * 下面的例子定义了两个简单的数学函数，addTwoInts和multiplyTwoInts，这两个函数都传入两个Int类型，返回一个合适的Int值，因此这两个函数的类型是\(int, int\) -&gt; Int
* ```

  ```




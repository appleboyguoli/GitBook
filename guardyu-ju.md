# Guard语句

Swift2.0时候推出了Guard语句。只会在判断语句为false的时候执行后续代码块，否则会跳过整个guard语句。

基本语法：

```swift
guard let 常量名 = 可选变量 else{

}
```

//示例

```swift
//条件为真的时候，会直接跳过else，执行后面的语句。
//条件为false的时候，会执行else语句。

func online(age: Int){
    guard age == 20 else {
        print("guard else 语句")
        return
    }
    print("else 之后")
}

online(age: 30)


//guard let 解包

var age: Int?
age = 20

func optionAge(){
    guard let age = age else{
        print("guard else 语句")
        return }
    print(age)
    print("else 之后")
}

optionAge()
```



guard 语句出现的条件

因为我们经常会写if嵌套

```swift
f 条件1
  {
        
      if 条件2
                  {  //do something}
         else
                  {   //do something }
    
  }
else
 {    //do something     }
```

这种情况就可以考虑来用guard来处理。

```swift
    guard 条件2 else
   {
         //do something 
        return
    }
    
    guard 条件2 else
   {
         //do something 
        return
    }
    
     //do something 

```

举例

```swift
我们举一个电影院检票的例子：
//票务
struct Ticket
{
    var movieName:String//该场电影名字
    var TimeValid:Bool = true//电影票有效
}

func checkTicket(ticket:Ticket?,currentMovieName:String)
{

    guard let _ = ticket,ticket?.movieName == currentMovieName else {

        print("非此场电影")
        return
    }
    guard ticket?.TimeValid else {

        print("该票已过期")
        return
    }

    //TODO:
    print("可以看电影了")

}
```




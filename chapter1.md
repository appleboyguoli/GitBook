# Swift可选类型

Swift的可选类型，option ，为啥要出现这么个鬼东西？

以为在Swift里，变量或者常量声明的时候必须初始化。有了这个可选类型就不需要初始化了

可选类型的含义是变量或者常量或者有值，或者为nil。

声明可选类型的时候必须要指定其数据类型。因为可能为空。

Option类型的变量又分为显示解包和隐式解包

```swift
//这个变量声明必须初始化，这样编译器才可以做出类型推断
var name: String?

//如果name声明了可选类型不赋值，那么name为nil，而不是name！为nil
//所以可以直接通过name来判断是否为空
if name != nil{
    print(name)
}
name = "zhangguoli"

//加上叹号显示解包
print(name!)

//用if进行隐式解包
if let name = name {
    print(name)
}
```




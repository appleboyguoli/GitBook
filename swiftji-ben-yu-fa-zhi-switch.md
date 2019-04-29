```swift
 //Switch简单的用法
        switch name {
        case "zhangguoli":
            print(name!)
        default:
            print("default")
        }

        //Swift 多条件判断
        let someCharacter: Character = "0"
        switch someCharacter {
        case "a", "e", "i", "o", "u":
            print("\(someCharacter) is a vowel")
        case "b", "c", "d", "f", "g", "h", "j", "k", "l", "m":
            print("\(someCharacter) is a highwel")
        default:
            print("\(someCharacter) is not a vowel or a consonant")
        }

        //元祖匹配
        let tumple = (70,80)
        switch tumple {
        case (70..<80, 70..<80):
            print("你的成绩合格啦")
        case (70...100, let secondScore):
            print("你的第一门成绩合格啦, 第二门的成绩为\(secondScore)")
        case (_, 70...100):
            print("你的第二门成绩合格啦")
        case (90...100, 90...100):
            print("你的成绩优秀")
        default:
            print("你的成绩木有及格")
        }



        //where子句配合Switch
        let tumple1 = (70,90)
        switch tumple1 {
        case (70..<80, let secondScore) where secondScore < 80:
            print("你的第一门成绩合格啦, 第二门的成绩为\(secondScore)")
        case (70..<80, let secondScore) where secondScore > 80:
            print("你的第一门成绩合格啦, 第二门的成绩为\(secondScore)")
        default:
            print("你的成绩木有及格")
        }


        //字符串匹配中使用Where子句
        let tempString = "ABC"
        switch tempString {
        case let temp where temp > "ABCD":
            print("\(temp) > ABCD")
        case let temp where temp > "AB":
            print("\(temp) > AB")
        default:
            print("what?!!")
        }
```




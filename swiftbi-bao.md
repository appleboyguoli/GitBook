# Swift闭包

```swift
        //闭包
        let squareClosure = {
            (number: Int) -> Int in
            return number * number
        }
        print(squareClosure(10))


        //最简单的闭包
        let simpleClosure = {print("Hello 闭包")}
        simpleClosure()


        //多个参数并带返回值的闭包
        let mutiClosure = {
            (number1: Int, number2: Int) -> Int in
            return number1 * number2
        }
        print(mutiClosure(10,12))
```

闭包的简单应用。

例：从数组中挑出合适的数据组成新的数组

```swift
    //从数组中筛选出合适的数据组成新的数组

    func getScore(score:[Int],con:(Int) -> Bool) -> [Int]{
        //定义一个新的数组
        var newScore:[Int] = [Int]()

        for item in score {
            if con(item){
                newScore.append(item)
            }
        }
        return newScore
    }


    print(getScore(score: [65, 75, 85, 95], con: {(s:Int)->Bool in return s > 80}))

    //闭包的缩写
    print(getScore(score: [65, 75, 85, 95], con: {(s:Int)->Bool in return s > 80}))
    print(getScore(score: [65, 75, 85, 95], con: {(s:Int) in return s > 80})) 
    print(getScore(score: [65, 75, 85, 95], con: {s in return s > 80}))
    print(getScore(score: [65, 75, 85, 95], con: {s in s > 80}))
    print(getScore(score: [65, 75, 85, 95], con: {$0 > 80}))

    //数组过滤
    let arr = [65, 75, 85, 95,100]
    print(arr.filter({$0>80}))

    //数组的遍历
    arr.forEach({print($0)})
```




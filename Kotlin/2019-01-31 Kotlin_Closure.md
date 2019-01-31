# 2019-01-31

## Kotlin의 Closure

* 주요 특징
    - 외부 범위에서 선언된 변수에 접근 할 수 있다
    - 클로저에서 해당 변수를 수정할 수 있다
    
    ```
    var sum = 0
    ints.filter { it > 0 }.forEach {
        sum += it                       // 외부 변수 sum에 접근
    }
    print(sum)                          // 변경된 sum 값 출력
    ```
    
* 그 밖의 특징
    - 함수 내의 변수들을 계속 유지할 수 있다
    ```
    fun Closure(num: Int): (Int) -> Int {
        var sum: Int = num
        return fun (num2: Int): Int {
            sum += num2
            return sum
        }
    }

    fun main(args: Array<String>) {
        var fn = Closure(10)
        println(fn(10))     // 20
        println(fn(10))     // 30
        println(fn(10))     // 40
    }

    ```
    
    - 람다로 함수를 받을 수 있다
    ```
    fun Closure2(pFunc: (Int) -> Int): () -> Int {
        var result: Int = 0
        return {
            result = pFunc(result)
            result
        }
    }

    fun main(args: Array<String>) {
        var dec = Closure2 { num -> num - 1 }       // 함수를 넘기는 경우

        fun Add(num: Int) = num + 10
        var add = Closure2(::Add)                   // 함수의 주소값을 넘기는 경우
    }
    ```
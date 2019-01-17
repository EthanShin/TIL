# 2019-01-17

## Kotlin의 Jump

* Kotlin의 점프 종류 3가지
    - return
    - break
    - continue

* label
    - C언어의 Goto와 같은 역할
    - 함수형 언어에서는 필수
    - 구성방법: 레이블명@
    ```
    abc@ for (i in 0..2) {
        for (j in 0..10) {
            if (j==5) break@abc
            println("i -> $i, j -> $j")
        }
        println("j loop end")
    }
    println("i loop end")
    
    ```
    
    - return@레이블 반환값
    ```
    var lambdaReturn = Exit@ {
        if (true) {
            return@Exit 3
        }
        1000
    }
    ```

    - forEach등의 경우 레이블명 작성하지 않아도 사용 가능
    ```
    (0..10).forEach { if (it > 3) return@forEach else println(it) }
    ```
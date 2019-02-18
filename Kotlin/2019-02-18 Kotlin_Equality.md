# 2019-02-18

## Kotlin의 Equality

* 사용목적
    - 같은 값이나 객체인지 확인한다.

* 특징
    - *==* 연산자로 값을 비교한다. 널 여부도 함께 확인할 수 있다.
    - *===* 연산자로 객체를 비교한다.
    - *!=*, *!==* 연산자로 같지 않은 경우를 확인할 수 있다.

* 예제
    ```Kotlin
    val a = hashMapOf("ethan" to 29)
    val b = a
    val c = hashMapOf("ethan" to 29)

    if (a == b) println("동일한 값")
    if (a == c) println("동일한 값")
    if (a === b) println("동일한 객체")
    if (a !== c) println("동일하지 않은 객체")
    ```
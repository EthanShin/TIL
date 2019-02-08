# 2019-02-08

## Kotlin의 Lazy

* 사용목적
    - 메모리 효율
    - 안드로이드 위젯 초기화 시 유리

* 특징
    - val로 선언
    - 사용 시점에서 1회 초기화 실행
    - 초기화 실행 시, 일련의 코딩도 가능
    - primitive형 사용 가능

* 예제
    - 선언
    ```Kotlin
    val lazy1: String by lazy {
        "Hello"
    }

    val lazy2: Int by lazy {
        123
    }
    ```

    - 실행
    ```Kotlin
    println(lazy1)

    var v = 1 + lazy2
    ```
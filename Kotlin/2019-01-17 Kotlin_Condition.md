# 2019-01-17

## Kotlin의 Condition

* if
    - Any type 사용가능
    - is, in 등과 함께 사용 가능
    ```
    if(a == "Test") {
        println(a)
    } else if (a is Float) {
        println("Float")
    } else if (a in (0..9)) {
        println("0-9까지의 숫자: $a")
    } else if (a == null) {
        println("null")
    }
    ```

* for
    - for(변수 in 배열 or 범위) { }
    ```
    for (i in (0..9)) {
        println("i -> $i")
    }

    (0..9).forEach {
        println("it -> $it")
    }
    ```

* while
    - while(조건) { }
    ```
    var i: Int = 0
    while(i < 9) {
        i++
        println("$i 입니다.")
    }
    ```
    
* when
    - when(변수) {조건 -> 실행}
    ```
    var o: Any = 0
    when(o) {
        "Test"      -> {println("문자: $o")}
        is Float    -> {println("Float: $o")}
        in (0..9)   -> {println("0-9까지의 숫자: $o")}
        else        -> {println("???")}
    }
    ```

* 결과를 바로 변수로 대입 가능
    - 리턴 값의 타입이 달라도 처리 가능
    ```
    var a = "ABCDE"
    val result = when(a) {
        is String   -> {true}
        else        -> {false}
    }

    val result2 = if(a.length > 3) true
    else "short"
    ```

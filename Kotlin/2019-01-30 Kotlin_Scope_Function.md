# 2019-01-30

## Kotlin의 주요함수

* let
    - 함수의 결과를 { }에 넘긴다
    - 결과를 변수로 지정하지 않을 경우 it로 접근할 수 있다
    ```
    "example1".let { println(it) }
    "example2".let { s -> println(s) }
    ```
    
* apply
    - 객체를 생성하면서 초기화할 때 사용한다
    ```
    var person = Person().apply { sName = "Ethan"; nAge = 29 }

    ```
    
* run
    - { }의 마지막 값을 넘긴다
    - 객체 생성과 동시에 사용 못한다
    ```
    person.run { sName = "Byeongki"; sName }.let { println(it) }
    run { 123 + 4 }.let { println(it) }
    ```

* also
    - 값을 받기는 하나 넘기지는 않는다
    ```
    100.let { println(it); it }         // 100
        .also { println(it + 100) }     // 200
        .also { println(it + 10) }      // 110
        .let { println(it) }            // 100
    ```
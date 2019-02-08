# 2019-02-08

## Kotlin의 Properties

* 사용목적
    - 캡슐화

* 특징
    - 자기자신을 가리키는 예약어: field

* 예제
    - 선언
    ```Kotlin
    var pwd: String = ""
        get() { return field }
        set(s: String) { field = s }
    ```

    - 실행
    ```Kotlin
    pwd = "a123456"
    ```

* 확장 프로퍼티
    - 클래스의 확장 기능을 활용하여 프로퍼티를 만들 수 있다
    ```Kotlin
    class EmptyClass {
        var message: String = ""
    }

    var EmptyClass?.newProp: String
        get() { return this!!.message }
        set(value) { this!!.message = value + "-" + this!!.message }
    ```
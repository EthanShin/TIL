# 2019-01-21

## Kotlin의 Class

* vs Java
    - 파일명과 클래스명이 같지 않아도 된다
    - Java 코드를 Kotlin 코드로 변경할 때, nullable에 대한 처리 필요

* Class의 정의
    - class 클래스명 { }
    ```
    class MyClass { }
    ```

* Constructor
    - class를 정의할 때, 괄호를 이용해 생성자를 처리할 수 있다
    ```
    class MyClass(name: String) { }
    ```

    - constructor함수를 이용하여 별도 혹은 추가로 생성자를 작성할 수 있다
    ```
    class MyClass(name: String) {
        var sName: String = "Test"
        var sAge: Int = 1

        constructor(name: String, age: Int): this(name) {
            sName = name
            sAge = age
        }
    }
    ```

* init
    - constructor에는 코드가 포함될 수 없기 때문에 init에 초기화 코드를 작성해야한다
    - constructor보다 먼저 호출된다
    ```
    class InitSample(name: String) {
        var sName: String = ""
        init {
            sName = name
        }
    }
    ```

* 상속
    - 부모클래스의 정의: open 키워드 사용
    ```
    open class ParentClass(msg: String) { }
    ```

    - 자식클래스의 정의
    ```
    class ChildClass(m: String): ParentClass(m) { }
    ```
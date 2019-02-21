# 2019-02-20

## Kotlin의 Nested Class

* 사용목적
    - 클래스가 다른 하나의 클래스에서만 쓰일 때 사용한다.

* 특징
    - 클래스 안에 중첩된 클래스를 작성할 수 있다.

* 예시
    ```Kotlin
    fun main(args: Array<String>) {
        val demo = Outer.Nested().foo()
        println(demo)   // 2
    }

    class Outer {
        val bar: Int = 1
        class Nested {
            fun foo() = 2
        }
    }
    ```

    - Nested Class는 Outer Class의 멤버에 접근하지 못한다.
    ```Kotlin
    class Outer {
        val bar: Int = 1
        class Nested {
            fun foo() = bar // Error: Unresolved reference: bar
        }
    }
    ```
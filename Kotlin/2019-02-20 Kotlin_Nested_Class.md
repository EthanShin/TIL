# 2019-02-20

## Kotlin의 Nested Class

* 특징
    - 클래스 안에 중첩된 클래스를 작성할 수 있다.

* 예시
    ```Kotlin
    fun main(args: Array<String>) {
        val demo = Outer.Nested().foo()
        println(demo)   // 2
    }

    class Outer {
        private val bar: Int = 1
        class Nested {
            fun foo() = 2
        }
    }
    ```
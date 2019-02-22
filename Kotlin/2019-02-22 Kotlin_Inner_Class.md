# 2019-02-22

## Kotlin의 Inner Class

* 사용목적
    - 외부 클래스의 멤버에 접근 할 필요가 있을 때 사용한다.

* 특징
    - 내부 클래스 앞에 *inner* 키워드를 입력한다.
    - 내부 클래스의 객체를 생성하기 위해서는 외부 클래스의 객체를 먼저 생성해야 한다.

* 예시
    ```Kotlin
    fun main(args: Array<String>) {
        val demo = Outer().Inner().foo()
        println(demo)   // 1
    }

    class Outer {
        val bar: Int = 1
        inner class Inner {
            fun foo() = bar
        }
    }
    ```

    - 외부 클래스의 객체를 통하지 않으면 오류가 발생한다.
    ```Kotlin
    val demo = Outer.Inner().foo()
    // Error: Constructor of inner class Inner can be called only with receiver of containing class
    ```
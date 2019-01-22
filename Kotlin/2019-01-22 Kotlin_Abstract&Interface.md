# 2019-01-21

## Kotlin의 Abstract

* 불완전한 클래스
    - 해당 클래스를 상속받아 메소드를 완성할 것을 강제한다
    - 자식클래스에서 override로 정의한다
    ```
    abstract class A {
        abstract fun doA()
    }

    class B: A() {
        override fun doA() {
            println("doA")
        }
    }
    ```

## Kotlin의 Interface

* 설계도
    - Interface에서 정의된 메소드를 완성할 것을 강제한다  
    - 다중 상속을 지원한다
    ```
    interface A {
        fun doA()
    }

    interface A1 {
        fun doA1()
    }

    class B: A, A1 {
        override fun doA() {

        }

        override fun doA1() {

        }
    }
    ```

## Abstract Class와 Interface의 차이점

* Abstract Class는 클래스이고, Interface는 클래스가 아니다
* Abstract Class는 일부분이 미완성되어 있으나, Interface는 뼈대만 있는 모습이다
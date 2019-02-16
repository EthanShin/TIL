# 2019-02-16

## Kotlin의 Typealias

* 사용목적
    - 타입의 형태가 복잡하거나 길 때, 간략하게 표현할 수 있다.

* 특징
    - 제너릭 타입, 함수형 타입, 클래스 등에도 지정할 수 있다.
    - 컴파일 시점에서 모두 원래 타입으로 변환되므로 실행 시점의 부하가 없다.

* 예제
    - 콜렉션 타입명을 축소
    ```Kotlin
    typealias StudentList = List<Student>

    typealias StudentGrade = Map<Student, Int>
    ```

    - 함수형 타입명을 축소
    ```Kotlin
    typealias MyHandler = (Int, Int) -> Int

    fun example(func: MyHandler) {
        println(func(10, 10))
    }
    ```

    - 클래스명을 축소
    ```Kotlin
    Class A {
        inner class Inner
    }

    typealias AInner = A.Inner
    ```
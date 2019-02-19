# 2019-02-19

## Kotlin의 Annotations

* 사용목적
    - 소스코드에 메타데이터를 붙인다.

* 특징
    - *annotation* 키워드를 입력한다.
    - 추가 속성은 meta-annotation을 사용하여 지정할 수 있다
        - @Target: 요소의 종류(클래스, 함수, 속성, 표현식 등)를 지정한다.
        - @Retention: 컴파일 된 파일에 저장 여부와 런타임시 반영 여부를 지정한다.
        - @Repeatable: 단일 요소에 동일한 annotation을 여러번 사용할 수 있다.
        - @MustBeDocumented: 공용 API의 일부이며 생성 된 API 설명서에 표시된 클래스 또는 메서드 서명에 포함되어야한다고 지정한다.
    - file, property, field, get/set, receiver, param, setparam, delegate에 적용 대상을 사용하여 지정할 수 있다.

* 예제
    - 정의
    ```Kotlin
    annotation class Fancy
    ```

    - 멤버 변수에 기본값 설정
    ```Kotlin
    annotation class Fancy (
        val name: String = "Ethan Shin"
    )

    @Fancy
    class Foo { ... }
    ```

    - 멤버 변수에 값 대입
    ```Kotlin
    annotation class Fancy (
        val name: String
    )

    @Fancy("Ethan Shin")
    class Foo { ... }
    ```

    - 두개 이상의 멤버 변수에 값 대입
    ```Kotlin
    annotation class Fancy (
        val name: String
        val age: Int
    )

    @Fancy(name = "Ethan Shin", age = 29)
    class Foo { ... }
    ```

    - 클래스, 함수, 파라미터에 지정
    ```Kotlin
    @Fancy class Foo {
        @Fancy fun baz(@Fancy foo: Int): Int {
            return (@Fancy 1)
        }
    }
    ```

    - 프로퍼티에 사용
    ```Kotlin
    class Foo {
        
        @setparam: Fancy
        @set: Fancy
        var foo: String = "foo"
    }
    ```

    - 하나의 요소에 여러 개의 어노테이션을 사용할 때는 대괄호를 사용
    ```Kotlin
    class Bar {
        @set: [Fancy Foo]
        var bar: String = "bar"
    }
    ```
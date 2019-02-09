# 2019-02-09

## Kotlin의 Interop

* 사용목적
    - **자바에서 코틀린 코드 사용**
    - 코틀린에서 자바 코드 사용

* 특징
    - 자바에서 코틀린 코드를 사용할 때, 파일명Kt 형식으로 클래스가 생성된다
    - 코틀린 코드의 변수는 get/set 형식의 메소드로 사용된다
        - 메소드 형식으로 변환하지 않으려면 @JvmField 어노테이션을 사용한다
        - 스태틱 메소드를 사용하고 싶다면 @JvmStatic 어노테이션을 사용한다
    - 자바로 만든 클래스에 확장함수 추가가 가능하다

* 예제
    - 자바로 만들어진 클래스에 확장함수 추가
    ```Kotlin
    fun javaActivity.kotlinEventHandler() {
        ...
    }
    ```

    - 변수 사용
    ```Kotlin
    // 자바에서 클래스.getName() 형태로 사용 가능
    var name = "get/set"

    // 자바에서 클래스.age, 클래스.test() 형태로 사용 가능
    @JvmField var age = 32
    @JvmStatic fun test() {
        ...
    }
    ```
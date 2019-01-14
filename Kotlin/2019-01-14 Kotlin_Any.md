# 2019-01-14

## Kotlin의 Any

* Any type
    - 동적타입을 지원
    ```
    var everybody: Any

    everybody = 123
    everybody = "String"
    everybody = 10.0f
    """
    ```

* is, !is
    - 데이터타입을 체크할 때 사용
    ```
    if(everybody !is String) {
        if(everybody is Float) {
            println("Float type")
        }
    }
    ```

* 값 비교
    - ==
    - .equals()
    ```
    println(everybody == 10.0f)         //true
    println(everybody.equals(10.0f))    //true
    ```

## Kotlin의 그외 타입

* Unit type
    - 값이 없음
    - 함수의 형태를 정의할 때 사용
    ```
    var pFunc: () -> Unit = {}
    //입력값과 출력값이 없는 함수
    ```

* Nothing type
    - 존재하지 않음
    - TODO함수
    ```
    TODO("구현하십시오. 프로그램이 종료됩니다.")
    //문자열을 출력하고 프로그램이 종료된다.
    ```

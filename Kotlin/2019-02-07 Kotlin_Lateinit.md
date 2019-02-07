# 2019-02-07

## Kotlin의 Lateinit

* 사용하는 이유
    - 메모리 효율
    - 에러 방치 차원

* 특징
    - var만 사용 가능
    - 초기화 이전에 사용 불가
    - primitive형 사용 불가

* 예제
    - 선언
    ```
    lateinit var late: String
    ```

    - 초기화
    ```
    late = "abc"
    ```

    - 초기화 확인
    ```
    if (::a.isInitialized) {
        println(a)
    }
    ```
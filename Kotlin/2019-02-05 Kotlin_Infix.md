# 2019-02-05

## Kotlin의 Infix

* 중위표기법
    - 중위표기법은 연산자가 오퍼랜드 사이에 놓여지는 표시법이다
    - 흔히 수학에서 A + B, C * D 처럼 표현한 것이 중위표기법이다

* Infix 함수
    - 확장함수나 멤버함수로 구현되어야 한다
    - 한 개의 파라미터 가져야한다
    - 파라미터는 변할 수 있는 값이거나 디폴트 값을 가져서는 안된다

    ```
    // 함수구현
    infix fun Int.shl(x: Int): Int { ... }
    
    // 사용법
    1 shl 2
    1.shl(2)
    ```
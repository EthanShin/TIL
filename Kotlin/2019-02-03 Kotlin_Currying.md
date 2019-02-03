# 2019-02-03

## Kotlin의 Currying

* Currying
    - 함수형 프로그래밍 기술 중 하나
    - 다중 인자를 받는 함수를 호출 할 때, 파라미터를 부분적으로 나누어 받는 함수
    - 함수정의: fun(a): return_value = fun(b) = fun(c): return_value { }

    ```
    fun WorkForMoney(moneyByHour: Double): (Int) -> (String) -> String
        = fun (time: Int)
        = fun (job: String): String {
            return if(time > 8 * 5 * 4)
                "[${job}]은 많은 근무시간을 갖고 있습니다."
            else
                "[${job}]의 수익은 ${moneyByHour * time}입니다."
        }
    ```

    - 함수사용법: fun(a)(b)(c)
    ```
    val develop: (Double) -> (Int) -> (String) -> String = ::WorkForMoney
    val designer: (Int) -> (String) -> String = WorkForMoney(25000.0)

    listOf <() -> String> (
        { develop(25000.0)(8 * 5 * 4)("개발자") },
        { designer(8 * 5 * 4)("디자이너") }
    ).map { it().let { result -> println(result) } }
    ```
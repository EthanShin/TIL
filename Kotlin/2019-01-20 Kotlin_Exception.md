# 2019-01-20

## Kotlin의 Exception

* try-catch
    - 필수가 아니라 선택
    ```
    try {
        100 / 0
    } catch(e: Exception) {
        println(e)
    } finally {
        println("finally")
    }
    ```

* !!
    - null 일 때, NullPointerException 발생시키고 프로그램 종료
    ```
    var number: Int? = null
    var sum = number!! + 100
    ```

* ?
    - null 일때 해당부분을 실행하지 않는다
    ```
    var sum = number?.let {
        it + 100
    }
    ```
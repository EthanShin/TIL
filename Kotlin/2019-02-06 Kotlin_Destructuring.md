# 2019-02-06

## Kotlin의 Destructuring

* Destructuring Declarations
    - 반환값을 여러 변수로 분리하는 것이다
    - 일반적으로 Data class, List Pair Collection의 반환값을 다룰 때 사용한다

    ```
    data class Result(val result: Int, val status: Status)
    fun function(...): Result {
        return Result(result, status)
    }

    val (result, status) = function(...)
    ```
    ```
    var (example1, example2, example3) = listOf(10, "abc", 100.0f, "def", 123)

    // example1 = 10
    // example2 = abc
    // example3 = 100.0
    // 리스트의 순서대로 할당된다
    ```

* partition 함수
    - list의 elements를 분할 할때 사용한다
    - 첫번째 리스트에는 true에 해당하는 요소가, 두번째 리스트에는 false에 해당하는 요소가 들어간다.

    ```
    val lst = (0..10).map { Student("name -${it}", (it % 3) + 1 ) }
    val (l1, l2) = lst.partition { it.grade == 2 }
    ```
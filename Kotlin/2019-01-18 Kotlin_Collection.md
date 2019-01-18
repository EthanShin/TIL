# 2019-01-18

## Kotlin의 Collection

* list
    - listOf(): 읽기전용
    - mutableListOf(): 읽고쓰기가능
    - elements의 데이터 타입이 달라도 된다
    ```
    var lst = listOf(1, "A", 10.0f, true)
    ```
    - 제러릭 사용 시 데이터 타입을 맞춰야한다
    ```
    var lst2 = listOf<Int>(1, 2, 3, 4, 5)
    ```

* Map
    - hashMapOf()
    ```
    var m = hashMapOf("A" to 1, "B" to 2)
    println(m["A"])
    ```
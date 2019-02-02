# 2019-02-02

## Kotlin의 DSL

* Domain-Specific Language
    - 특정 애플리케이션이나 Software에서 사용할 목적으로 만든 간이언어
    - 장점: 반복을 제거한다
    - 단점: 없는 문법을 만들었기 때문에 커뮤니케이션이 어렵다

    ```
    // 데이터클래스와 확장함수를 이용하여 DSL 사용하기

    fun MakePlayer(block: Player.() -> Unit): Player = Player().apply(block)
    fun Player.status(block: Status.()-> Unit) {
        status = Status().apply(block)
    }

    data class Player(var name: String? = null, var status: Status? = null)
    data class Status(var job: String? = null, var level: Int? = null)
    ```

    ```
    // DSL
    val p1 = MakePlayer {
        name = "Player 1 - " + Random().nextInt(200).toString()
        status {
            job = "Paladin"
            level = Random().nextInt(70)
        }
    }
    ```

    ```
    // 더 간단한 방법
    val p2 = Player("Player 2", Status("Archer", 23))
    ```
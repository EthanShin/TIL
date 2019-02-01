# 2019-02-01

## Kotlin의 Extensions

* 확장 함수
    - 이미 정의된 클래스에 멤버함수를 정의하는 것이다
    - 확장함수를 실행함과 동시에 객체정보를 공유할 수 있다

    ```
    fun MutableList<Int>.swap(index1: Int, index2: Int) {
        val tmp = this[index1]
        this[index1] = this[index2]
        this[index2] = tmp
    }

    val l = mutableListOf(1, 2, 3)
    l.swap(0, 2)
    ```
    
* 확장 함수 활용
    - 확장함수의 파라미터로 함수를 넘기면 객체설정 및 이벤트핸들러를 구현하기 쉽다
    ```
    fun ani(extFunc: Animal.() -> Unit): Animal {
        var ani = Animal()
        ani.extFunc()
        return ani
    }

    class Animal{
        open var nCount = 0
        fun crying() = println("$this>> 아흥")
        fun eat() = println("$this>> 우걱우걱")
        open fun setOnEvent(nCount: Int, message: String, extFunc: Animal.(Int) -> Unit): Animal {
        when (message) {
            "울어" -> { extFunc(nCount) }
            "먹어" -> { var n = if (nCount < 3) 3 else nCount; extFunc(n) }
            else -> { println("알수없는 메시지: ${message} 입니다.") }
        }
        return this
    }
    ```
    
    - main에서 위에 정의한 함수 실행
    ```
    var obj = ani {
        crying()
        eat()
        nCount++
    }

    println("증가된 숫자는 ${obj.nCount} 입니다.")
    obj.setOnEvent(3, "울어", {
        nCount ->
        println("${nCount}번 울겠습니다.")
        (1..nCount).map {crying()}
    })

    obj.setOnEvent(2, "먹어", {
        nCount ->
        println ("${nCount}번 먹겠습니다.")
        (1..nCount).map {eat()}
    })
    ```
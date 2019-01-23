# 2019-01-23

## Kotlin의 Object

* 3가지 형태의 사용법
    - static class 생성
    - class 내의 특정멤버 static으로 처리
    - 이름없는 객체(클래스에서 상속) 처리

* static class
    - 클래스를 정의 할 때, 클래스이름 앞에 object 키워드를 입력한다
    ```
    object SingleTon {
        var showMessage = {msg: String -> println(msg)}
    }
    ```

* static member
    - 멤버를 정의 할 때, 이름 앞에 companion object 키워드를 입력한다
    ```
    class StaticMember {
        companion object {
            var staticVar = "StaticMember.staticVar"
            fun staticFun() = println("StaticMember.staticFun")
        }
    }
    ```

* unnamed object
    - abstract class를 구현 할 때, 클래스 앞에 object 키워드를 입력한다
    ```
    fun main(args: Array<String>) {
        var obj = object: fakeClickHandler() {
            override fun onClick() {
                println ("Click")
            }
        }
        obj.onClick()
    }
 
    abstract class fakeClickHandler {
        abstract fun onClick()
    }
    ```
# 2019-01-11

## Kotlin의 특징

* 종결자를 사용하지 않아도 된다.
    - C언어나 JAVA에서 문장을 구분하는 식별자인 세미콜론(;)을 사용하지 않아도 된다.

* 타입을 선언하지 않아도 값을 대입하면 타입이 결정된다.
    - 콜론을 사용해 타입을 선언할 수도 있다.(타입을 선언하는 것을 권장)
    ```
    val myName: String = "ethan"
    ```

* 변수는 읽기전용과 읽고쓰기가능한 것이 있다.
    - val: 읽기전용
    - var: 읽고쓰기가능
    ```
    val myName: String = "ethan"
    var myAge: Int = 29
    
    myName = "Byeongki" //Val cannot be reassigned
    ```


* null의 사용을 엄격하게 제한한다.
    - null을 허용하는 변수를 '?'를 이용하여 따로 정의한다.
    ```
    var myName: String? = null

    var myAge: Int = null //Null cannot be a value of a non-null type String
    ```

* findViewByid 사용없이도 리소스에 접근가능하다.

## Intellij Tip
* psvm
    - public static void main(String args[])
    - intellij에서 pvsm을 입력하여 main메소드를 빠르게 만들 수 있다.
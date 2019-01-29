# 2019-01-29

## Kotlin의 Functional Programming

* 실행된 함수의 결과는 동일하다
    - 변수나 객체를 여기저기서 접근하지 않아야한다
    
* 고차함수
    - 파라미터로 함수를 입력받고 함수를 리턴하는 함수
    ```
    fun fun1(func: (Int, Int) -> Int) {
        println(func(10, 10))
    }
    ```

* lambda
    - 형식
    ```
    //{ 변수정의 -> 함수구현 }
    var pfunc = { a: Int, b: Int -> a + b}
    ```

* 고차함수에 람다식 넘기는 여러가지 방법
    ```
    example1(pfunc)
    example2{num, num2 -> num + num2}   // 함수만 넘길 때는 소괄호 생략가능
    example3({n, n2 -> n + n2}, 10, 20) // 다른 변수나 값과 같이 넘길 때는 소괄호 필수
    example4(::myFunction)              // 함수의 주소값 전달
    ```
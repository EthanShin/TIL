# 2019-01-15

## Kotlin의 Function

* Function 정의
    - fun 함수명(변수명: 데이터크기, ...): 리턴값 {return}
    ```
    fun funByReturn(s: String): String {return s} 
    ```

    - 한 줄로 표현할 때는 '=' 사용 가능
    ```
    fun funByInline(i: Int, j: Int) = i * j
    ```

    - Higher-Order Function
    ```
    fun higherFunc(f: () -> Unit) {
        f()
    }
    ```
    
* 함수형 변수
    - '::' 함수의 주소를 전달
    ```
    val funcVar = {s: String -> println(s)}
    var funcVarType: (String) -> Any? = ::funByReturn
    ```
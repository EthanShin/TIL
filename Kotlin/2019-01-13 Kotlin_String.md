# 2019-01-13

## Kotlin의 String

*  3개의 쌍따옴표로 멀티라인 문자열 지원
    ```
    var sLines = """
    1
    2
    3
    4
    5
    """
    ```

* 문자열 템플릿
    - $ 기호 사용
    ```
    var sName = "Ethan"
    var sFormatter = "$sName <-- sName의 값"
    ```

    - ${ }안에 함수호출이나 수식처리도 가능
    ```
    var sBash = "${"지금 시각은 " + Date()}"
    ```
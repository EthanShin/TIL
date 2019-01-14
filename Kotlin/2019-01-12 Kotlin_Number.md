# 2019-01-12

## Kotlin의 Number

* 숫자형 데이터 타입(크기순)
    ```
    var doubleV: Double = 100.1
    var floatV: Float = 100.0f
    var longV: Long = 100
    var intV: Int = 50
    var shortV: Short = 30
    var byteV: Byte = 10
    ```

* println(...)
    - 문자열을 출력하는 println 메소드에 숫자형 변수를 입력하면 .toString()을 입력하지 않아도 출력된다.
    ```
    println(doubleV.toString()) //100.1
    println(doubleV)            //100.1
    ```

* 캐스팅
    - to대입할크기()
    ```
    doubleV = intV.toDouble()   //50.0
    intV = floatV.toInt()       //100
    ```

    - as 키워드로 변환불가
    ```
    doubleV = intV as double    //ClassCastException
    ```

    - 문자열을 숫자로 변경할 때, to메소드를 이용하여 바로 사용가능
    ```
    val num = "100".toInt() + 50    //150
    ```
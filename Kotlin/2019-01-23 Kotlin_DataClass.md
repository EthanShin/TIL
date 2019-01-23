# 2019-01-23

## Kotlin의 DataClass

* 데이터를 처리에 특화된 클래스
    - data class로 정의하고 ( ) 속에 필드를 들을 정의한다
    - { } 속에 멤버필드나 메소드를 정의한다
    ```
    data class Student(var name: String, var age: Int) {
        var grade: String = ""
        operator fun plus(s: Student) {
            this.age + s.age
        }
    }
    ```

    - 객체 생성
    ```
    fun main(args: Array<String>) {
        var student1 = Student("ethan", 29)
        var student2 = Student(age = 10)
    }
    ```

* copy 메소드
    - 다른 객체로 부터 값을 복사한다
    ```
    var student3 = student1.copy()
    ```
    - 생성자에 특정 필드값을 입력하면 해당 필드값만 바뀌고 나머지값은 복사한다
    ```
    var student3 = student3.copy(name = "shin")
    ```

* destruction
    - 데이터클래스의 필드값을 분리하여 변수에 대입할 수 있다
    ```
    var (name1, age1) = student1
    var (name2) = student3
    ```
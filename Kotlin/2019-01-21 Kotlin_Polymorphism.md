# 2019-01-21

## Kotlin의 Polymorphism

* Overriding
    - 부모클래스에서 메소드와 필드를 open으로 정의한다
    - 자식클래스에서 override로 정의한다
    ```
    open class ParentClass {
        open var name = "parent"
        open fun example() = println(this.toString())
    }

    class ChildClass: ParentClass() {
        override var name = ""
        override fun example() = println(this.toString() + "재정의")
    }
    ```

* Overloading
    - 매개변수가 다르나 같은 이름을 쓰는 메소드를 지원한다
    ```
    fun example2() = println("example2")
    fun example2(name: String) = println("example2: $s")
    fun example2(name: String, age: Int) = println("example2: $s, $age")
    ```

    - 연산자 오버로딩을 지원한다
    ```
    class Student(s: String) {
        var name: String = s
        var nScore: Int = 0

        // Student + Student
        operator fun plus(student: Student): Int {
            return student.nScore + this.nScore
        }

        // Student++
        operator fun inc(): Student {
            this.nScore++
            return this
        }
    }
    ```
### Тема 2

Существует несколько интегрированных сред разработки (IDE), которые поддерживают разработку программ на Scala, такие как IntelliJ IDEA, Eclipse и Visual Studio Code (VS Code). ScalaIDE также является одним из вариантов IDE для разработки на Scala.

В Scala термин "object" обозначает класс, который считается цельным (singleton) классом.

Модули (modules) часто используются в Scala для создания и управления глобальными объектами и функциональностью.

Пример взаимодействия классов внутри модуля:

```scala
object MyModule {
  class MyClassA(val name: String) {
    def greet(): Unit = println(s"Hello from $name!")

    def callB(b: MyClassB): Unit = {
      println(s"$name is calling ${b.name}")
      b.greet()
    }
  }
}

class MyClassB(val name: String) {
  def greet(): Unit = println(s"Hello from $name!")

  def callA(a: MyClassA): Unit = {
    println(s"$name is calling ${a.name}!")
    a.greet()
  }
}

object Main {
  def main(args: Array[String]): Unit = {
    val a = new MyModule.MyClassA("Alice")
    val b = new MyModule.MyClassB("Bob")

    a.callB(b)
    b.callA(a)
  }
}
```

---

В Scala конструкторы (constructors) используются для создания экземпляров классов. Существуют два типа конструкторов:

1) Первичные конструкторы (primary constructors) определяются в самом определении класса и выполняются при создании экземпляра класса. Параметры первичного конструктора определены в определении класса (имя конструктора совпадает с именем класса).

Пример с первичным конструктором:

```scala
class MyClass(val name: String, val age: Int) {
  println("Creating instance of MyClass")

  def greet(): Unit = println(s"Hello, $name and $age years old")

  // .....
}
```

2) Вспомогательные конструкторы (auxiliary constructors) могут иметь другие списки параметров, чем первичный конструктор. Они определяются с использованием ключевого слова "this" и должны вызывать либо первичный конструктор, либо другой вспомогательный конструктор в качестве первого оператора.

Пример с вспомогательным конструктором:

```scala
class MyClass(val name: String, val age: Int) {
  def this(name: String) = this(name, 0)

  println("Creating instance of MyClass")

  def greet(): Unit = println(s"Hello, $name and $age years old")
}
```

В этом примере вспомогательный конструктор вызывает первичный конструктор с параметром "name" и значением по умолчанию (0).

Чтобы создать экземпляр класса с использованием вспомогательного конструктора, можно использовать ключевое слово "new", за которым следует имя класса и параметры вспомогательного конструктора.

Пример чтения файла и вывода его содержимого на консоль:

```scala
import java.io._

class MyClass {
  // Инициализация ресурсов
  val fileHandle = new File("data.txt") // Открывает файл для чтения
  val fis = new FileInputStream(fileHandle)
  val bis = new BufferedInputStream(fis) // Читает блок байтов в память
  val dis = new DataInputStream(bis) // Чтение данных

  try {
    while (dis.available() != 0) {
      val line = dis.readLine()
      println(line)
    }
  } catch {
    case e: IOException =>
      println("An error occurred while reading the file: " + e.getMessage)
  } finally {
    dis.close()
    println("Reading closed")
  }

  override def finalize(): Unit = {
    super.finalize()
  }
}

object Main {
  def main(args: Array[String]): Unit = {
    val myObject = new MyClass
    myObject.finalize() // Освобождение ресурсов

    // ...
  }
}
```

В этом примере используется класс `java.io.File`, чтобы открыть файл для чтения. Затем используются классы `FileInputStream`, `BufferedInputStream` и `DataInputStream` для чтения содержимого файла. В блоке `try` происходит чтение строк из файла и их вывод на консоль. Если возникает ошибка ввода-вывода (`IOException`), она обрабатывается в блоке `catch`. Затем в блоке `finally` происходит закрытие потоков чтения и выводится сообщение о завершении чтения. В методе `finalize` переопределен метод `finalize` для освобождения ресурсов.

Пример показывает общий подход к чтению файла и обработке ошибок в Scala.

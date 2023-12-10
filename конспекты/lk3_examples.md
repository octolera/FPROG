### zip: функция объединяет два списка в список пар ключ-значение.

```scala
val a = List(1, 2, 3)

object Main22 {
  def main(args: Array[String]): Unit = {
    val a = List(1, 2, 3)
    val b = List("one", "two", "three")
    val zipped = a.zip(b)
```
...

Функция zip соединяет элементы двух списков, создавая список кортежей ключ-значение. Затем можно применить фильтрацию к каждому элементу списка, и если условие выполняется (равно true), пара остается в списке.

Элементы можно вывести следующим образом:

```scala
zipped.foreach { case (a, b) => println(a + ": " + b) }
// 1: one
// 2: two
// 3: three
```

Примеры:

Сумма элементов в списке:
```scala
object Main22 {
  def sumList(lst: List[Int]): Int = {
    if (lst.isEmpty) 0
    else lst.head + sumList(lst.tail)
  }
  ...
}
```

При работе со списками практически всегда используется рекурсия. У нас есть несколько ветвей для работы со списками. Первая ветвь относится к базовым случаям, таким как пустые списки или списки с одним элементом (головой списка). Следующие ветви обрабатывают более общий случай и выполняют следующие действия: если список не соответствует базовому случаю, он должен быть уменьшен на один элемент, и рекурсия должна быть применена к укороченному списку, при этом сохраняется информация о том, что обработка предыдущего вызова функции еще не завершена.

Примеры:

Подсчет количества элементов в списке:
```scala
object Main22 {
  def sizeList(lst: List[Int]): Int = {
    ...
  }
  ...
}
```

Нахождение минимального элемента в списке:
```scala
import scala.io.StdIn

object Main28 {
  def minList(lst: List[Int], minValue: Int): Int = {
    if (lst.isEmpty) minValue
    else if (lst.head < minValue) minList(lst.tail, lst.head)
    else minList(lst.tail, minValue)
  }
  ...
}
```

Нахождение элемента по заданному индексу:
```scala
object Main22 {
  def posList(lst: List[Int], pos: Int): Int = {
    ...
  }
  ...
}
```

Строки

Операции со строками:

```scala
val s1 = "hello"
val s2 = "world"

// Конкатенация
val s3 = s1 + " " + s2 // "hello world"

// Длина строки
val len = s3.length // 11

// Подстрока
val sub = s3.substring(0, 5) // "hello"

// Замена
val replaced = s3.replace("hello", "hi") // "hi world"

// Разделение
val parts = s3.split(" ") // ["hello", "world"]
```

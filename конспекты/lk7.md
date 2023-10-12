## Списки
### filter() 
выв.эл-ты списка, удовл.условиям
### reverse() - 
### foldLeft(крит)() 
работает с разными видами коллекций
<pre><code>
// Список чисел
val numbers = List(1, 2, 3, 4, 5)
// Используем `foldLeft` для суммирования всех чисел
val sum = numbers.foldLeft(0)((acc, num) => acc + num)
println(s"Сумма чисел: $sum")
// Используем `foldLeft` для объединения всех строк
val strings = List("Hello", " ", "world", "!")
val combinedString = strings.foldLeft("")((acc, str) => acc + str)
println(s"Объединенная строка: $combinedString")
</code></pre>
### zip 
обьединяет два списка по примеру словаря(ключ-значение)
<pre><code>
// Два списка чисел
val numbers1 = List(1, 2, 3)
val numbers2 = List(10, 20, 30)
// Используем `zip` для объединения элементов двух списков
val result = numbers1.zip(numbers2)
// Выводим результат
println(result)
</code></pre>
минимальный элемент списка
<pre> <code>
import scala.io.Stdin

object Main228{
    def minList(lst:List[int], minval: Int): Int = {
        if(lst.isEmpty) minval
        else if(lst.head < minval) minList(lst.tail, lst.head)
        else minlist(lst.tail, minval)
    }
}
</code> </pre>

## Строки
Представлены классом String (immutable)

### Конкатенация строк:

val str1 = "Hello"
val str2 = "World"
val result = str1 + " " + str2
println(result) // Выводит "Hello World"

### Интерполяция строк:

val name = "Alice"
val age = 30
val result = s"My name is $name and I'm $age years old."
println(result) // Выводит "My name is Alice and I'm 30 years old."

### Получение длины строки:

val str = "Hello"
val length = str.length
println(length) // Выводит 5

### Извлечение подстроки:

val str = "Hello, World!"
val substring = str.substring(7, 12)
println(substring) // Выводит "World"

### Разделение строки на подстроки:

val str = "Hello, World!"
val substrings = str.split(",")
println(substrings.mkString(", ")) // Выводит "Hello,  World!"

### Замена подстроки:

val str = "Hello, World!"
val replaced = str.replace("World", "Scala")
println(replaced) // Выводит "Hello, Scala!"

### Преобразование строки в верхний/нижний регистр:

val str = "Hello"
val uppercase = str.toUpperCase
val lowercase = str.toLowerCase
println(uppercase) // Выводит "HELLO"
println(lowercase) // Выводит "hello"

### Проверка, начинается или заканчивается ли строка с определенной подстроки:

val str = "Hello, World!"
val startsWithHello = str.startsWith("Hello")
val endsWithWorld = str.endsWith("World")
println(startsWithHello) // Выводит true
println(endsWithWorld) // Выводит false

### Удаление начальных и конечных пробельных символов:

val str = "   Hello, World!   "
val trimmed = str.trim
println(trimmed) // Выводит "Hello, World!"

### Reverse

# Развитые типы функций. Операторы
## Абстрактные классы
Класс, содержащий один или несколько абстрактных методов должен быть объявлен как абстрактный.
```
// Абстрактный класс
abstract class Shape {
  def area(): Double // Абстрактный метод без реализации
  def perimeter(): Double // Абстрактный метод без реализации
}

// Подклассы, наследующие абстрактный класс и реализующие абстрактные методы
class Circle(radius: Double) extends Shape {
  def area(): Double = math.Pi * radius * radius
  def perimeter(): Double = 2 * math.Pi * radius
}

class Rectangle(length: Double, width: Double) extends Shape {
  def area(): Double = length * width
  def perimeter(): Double = 2 * (length + width)
}

// Использование абстрактных классов и методов
val circle = new Circle(5)
println("Площадь круга: " + circle.area())
println("Периметр круга: " + circle.perimeter())

val rectangle = new Rectangle(4, 6)
println("Площадь прямоугольника: " + rectangle.area())
println("Периметр прямоугольника: " + rectangle.perimeter())```
```
## Ленивые функции
```
// Ленивая функция
def lazyFunction(): Int = {
  println("Выполнение ленивой функции")
  42
}

// Использование ленивой функции
lazy val result = lazyFunction()
println("Программа продолжает выполнение")
println("Результат: " + result)

// Лямбда-выражение
val addNumbers = (x: Int, y: Int) => x + y
```

// Использование лямбда-выражения
val sum = addNumbers(5, 7)
println("Сумма чисел: " + sum)```

# Синтаксис и основные конструкции Scala:

1. Объявление классов и объектов:
   - Классы объявляются с использованием ключевого слова `class`.
   - Объекты объявляются с использованием ключевого слова `object`.

Пример:
```
class Person {
  // Код класса
}

object Main22 {
  // Код объекта
}
```

2. Определение методов:
   - Методы объявляются с использованием ключевого слова `def`.
   - Методы могут иметь параметры и тип возвращаемого значения.

Пример:
```
class Person {
  def hello(name: String): Unit = println(s"Hello, $name!")
}
```

3. Определение переменных и констант:
   - Переменные объявляются с использованием ключевого слова `var`.
   - Константы объявляются с использованием ключевого слова `val`.

Пример:
```
val pi: Double = 3.14159
var count: Int = 0
```

4. Интерполяция строк:
   - Интерполяция строк позволяет вставлять значения переменных в строки с помощью `$` или `${}`.

Пример:
```
val name = "Alice"
println(s"Hello, $name!")
```

5. Массивы:
   - Scala поддерживает массивы с использованием `Array`.

Пример:
```
val numbers = Array(1, 2, 3, 4, 5)
```

6. Условные выражения:
   - Условные выражения объявляются с использованием ключевых слов `if`, `else if` и `else`.

Пример:
```
val age = 25
if (age < 18) {
  println("Underage")
} else if (age < 65) {
  println("Adult")
} else {
  println("Senior")
}
```

7. Циклы:
   - Scala предоставляет циклы `for`, `while` и `do-while` для выполнения итераций.

Пример (цикл `for`):
```
for (i <- 1 to 5) {
  println(s"Number $i")
}
```

8. Сопоставление с образцом (pattern matching):
   - Scala предоставляет мощный механизм сопоставления с образцом для обработки различных случаев.

Пример:
```
val day = "Monday"
day match {
  case "Monday" => println("It's Monday!")
  case "Tuesday" => println("It's Tuesday!")
  case _ => println("It's another day.")
}
```

Это основные конструкции и синтаксис языка Scala. Ваш пример кода также демонстрирует некоторые из этих конструкций.


Классы и объекты в Scala являются основными строительными блоками объектно-ориентированного программирования и служат для создания абстракций, инкапсуляции данных и поведения. Классы определяют шаблоны для создания объектов, а объекты сами представляют конкретные экземпляры этих классов.

Пример создания класса в Scala:

```
class Person(name: String, age: Int) {
  def greet(): Unit = {
    println(s"Hello, my name is $name and I am $age years old.")
  }
}
```

В данном примере мы определили класс `Person`, который принимает два параметра: `name` и `age`. У класса `Person` есть метод `greet`, который выводит приветствие с использованием этих параметров.

Пример создания объекта на основе класса:

```
val person1 = new Person("Alice", 30)
val person2 = new Person("Bob", 25)

person1.greet() // Вывод: Hello, my name is Alice and I am 30 years old.
person2.greet() // Вывод: Hello, my name is BobВ Scala ключевое слово `def` используется для определения методов. Вот пример:

```scala
class Calculator {
  def add(a: Int, b: Int): Int = {
    a + b
  }
  
  def subtract(a: Int, b: Int): Int = {
    a - b
  }
}
```

В этом примере мы создали класс `Calculator` с двумя методами: `add` и `subtract`. Оба метода принимают два параметра типа `Int` и возвращают результат типа `Int`. Метод `add` складывает два числа, а метод `subtract` вычитает второе число из первого.

Чтобы использовать методы класса `Calculator`, мы можем создать экземпляр класса и вызвать методы на этом экземпляре:

```scala
val calculator = new Calculator()
val sum = calculator.add(5, 3) // sum будет равно 8
val difference = calculator.subtract(10, 4) // difference будет равно 6
```

В этом примере мы создаем экземпляр класса `Calculator` с помощью ключевого слова `new` и присваиваем его переменной `calculator`. Затем мы вызываем методы `add` и `subtract` на объекте `calculator` и сохраняем результаты в переменные `sum` и `difference` соответственно.

Таким образом, методы в Scala определяются с использованием ключевого слова `def`, и их результаты можно использовать в коде.
# классы
В Scala классы используются для определения шаблонов, описывающих состояние и поведение объектов. Классы объявляются с помощью ключевого слова class и могут содержать поля (состояние) и методы (поведение).
```
class Car(private val mark String, private val model String, private var year: Int) (
	def getMark() String = mark
	def getModel() String = model
	def getYear(): Int = year
	def setYear(newYear Int): Unit = (year = newYear)
}
object Main (
def main(args: Array[String]): Unit = { 
	val car = new Car("Toyota", "Corolla", 2015) 
	println(car.getMark()) 
	println(car.getYear())
	printin(car.getYear())
	printin(car.getModel())
	car setYear(2016)
}
}
```
### наследование
Наследование в Scala осуществляется с помощью ключевого слова extends. Подкласс наследует поля и методы суперкласса, что позволяет создавать иерархии классов и использовать полиморфизм.
(оффтоп про то, что в val хранятся ссылки) 
```
class Vehicle(val make: String, val model String, var year: Int) (
	def accelerate(): Unit = printin("Accelerating.") 
	def brake(): Unit = printin("Braking.")
class Car(make: String, model: String, year: Int, val numDoors: Int)
extends Vehicle(make, model, year) { 
	def openDoor(): Unit = printin("Opening door...")
	def closeDoor(): Unit = println("Closing door.")
```
## Полиморфизм 
в Scala позволяет использовать объекты производных классов так, как если бы они были объектами базового класса. Это упрощает код и позволяет создавать более гибкие приложения.

Пример полиморфизма:
```
def makeAnimalSpeak(animal: Animal): Unit = {
  animal.speak()
}

val myAnimal: Animal = new Dog("Buddy")
makeAnimalSpeak(myAnimal) // Вызывает метод speak для объекта типа Dog
```
### трейты
похожи на интерфейсы, могут иметь конкретные методы и поля, могут быть смешаны с классами
```
trait Greeting {
	def greet(): Unit = println("Hello, world!")
}
class MyClass extends Greeting (
	override def greet(): Unit = printin("Hello from MyClass!")
}
object Main (
	def main(args: Array[String]): Unit = ( obj.greet()//prints "Hello from MyClass!"
	val obj = new MyClass()
}}
```
# Модули в Scala 
Используются для упаковки функций, классов, трейтов
объявление - object (имя модуля)
Можно использовать содержимое модуля либо указав имя модуля + .(значение\функция) либо импортировать в текущую область. И за эти невероятные откровения я плачу 4к/год. Невероятно
классы могут объявляться как внутри, так и вне модуля
создание экземпляра класса из модуля = new Mymodule.MyClass()

# Модификаторы доступа

private: Члены класса, объявленные с модификатором private, видны только внутри самого класса. Они не доступны извне класса и его подклассов.
Пример:
```
class Person(private val name: String) {
  def printName(): Unit = {
    println(name)
  }
}

val person = new Person("Alice")
// person.name // Ошибка компиляции, так как name - приватное поле
person.printName() // Это работает, так как метод printName является публичным
```
protected: Члены класса, объявленные с модификатором protected, видны внутри самого класса, а также в его подклассах. Они не доступны извне класса и его подклассов.
Пример:
```
class Animal {
  protected val sound = "Some sound"
}

class Dog extends Animal {
  def speak(): Unit = {
    println(sound) // Здесь sound доступен, так как Dog является подклассом Animal
  }
}

val dog = new Dog()
// dog.sound // Ошибка компиляции, так как sound защищен и не виден вне класса Dog
```

public (по умолчанию): Члены класса, объявленные без модификатора доступа, считаются public. Они видны из любого места программы.

```
class Animal {
  protected val sound = "Some sound"
}

class Dog extends Animal {
  def speak(): Unit = {
    println(sound) // Здесь sound доступен, так как Dog является подклассом Animal
  }
}

val dog = new Dog()
// dog.sound // Ошибка компиляции, так как sound защищен и не виден вне класса Dog
```


Пример:

```
class Circle(radius: Double) {
  def calculateArea(): Double = {
    Math.PI * radius * radius
  }
}

val circle = new Circle(5.0)
val area = circle.calculateArea() // Метод calculateArea() является публичным и доступным извне
```

В Scala уровни доступа позволяют контролировать инкапсуляцию и безопасность кода, обеспечивая гибкость в организации классов и объектов в ваших приложениях.

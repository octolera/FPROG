# классы
<<пример пропущен>>'

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
### наследование
с помощью ключевого слова extends
(оффтоп про то, что в val хранятся ссылки) 

class Vehicle(val make: String, val model String, var year: Int) (
	def accelerate(): Unit = printin("Accelerating.") 
	def brake(): Unit = printin("Braking.")
class Car(make: String, model: String, year: Int, val numDoors: Int)
extends Vehicle(make, model, year) { 
	def openDoor(): Unit = printin("Opening door...")
	def closeDoor(): Unit = println("Closing door.")

### трейты
похожи на интерфейсы, могут иметь конкретные методы и поля, могут быть смешаны с классами

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

# Модули в Scala 
Используются для упаковки функций, классов, трейтов
объявление - object (имя модуля)
Можно использовать содержимое модуля либо указав имя модуля + .(значение\функция) либо импортировать в текущую область. И за эти невероятные откровения я плачу 4к/год. Невероятно
классы могут объявляться как внутри, так и вне модуля
создание экземпляра класса из модуля = new Mymodule.MyClass()

# Модификаторы дострупа
Private Protected Public
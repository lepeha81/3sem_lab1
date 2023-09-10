# 3sem_lab1
## Homework
### Задание 1
Выведите на консоль минимальные и максимальные значения для предопределенных типов данных CTS.

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace lesson
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Минимальное значение типа данных byte: " + Byte.MinValue);
            Console.WriteLine("Максимальное значение типа данных byte: " + Byte.MaxValue);
            Console.WriteLine("Минимальное значение типа данных sbyte: " + SByte.MinValue);
            Console.WriteLine("Максимальное значение типа данных sbyte: " + SByte.MaxValue);
            Console.WriteLine("Минимальное значение типа данных short: " + Int16.MinValue);
            Console.WriteLine("Максимальное значение типа данных short: " + Int16.MaxValue);
            Console.WriteLine("Минимальное значение типа данных ushort: " + UInt16.MinValue);
            Console.WriteLine("Максимальное значение типа данных ushort: " + UInt16.MaxValue);
            Console.WriteLine("Минимальное значение типа данных int: " + Int32.MinValue);
            Console.WriteLine("Максимальное значение типа данных int: " + Int32.MaxValue);
            Console.WriteLine("Минимальное значение типа данных uint: " + UInt32.MinValue);
            Console.WriteLine("Максимальное значение типа данных uint: " + UInt32.MaxValue);
            Console.WriteLine("Минимальное значение типа данных long: " + Int64.MinValue);
            Console.WriteLine("Максимальное значение типа данных long: " + Int64.MaxValue);
            Console.WriteLine("Минимальное значение типа данных ulong: " + UInt64.MinValue);
            Console.WriteLine("Максимальное значение типа данных ulong: " + UInt64.MaxValue);
            Console.WriteLine("Минимальное значение типа данных float: " + Single.MinValue);
            Console.WriteLine("Максимальное значение типа данных float: " + Single.MaxValue);
            Console.WriteLine("Минимальное значение типа данных double: " + Double.MinValue);
            Console.WriteLine("Максимальное значение типа данных double: " + Double.MaxValue);
            Console.WriteLine("Минимальное значение типа данных decimal: " +Decimal.MinValue);
            Console.WriteLine("Максимальное значение типа данных decimal: " + Decimal.MaxValue);
        }
    }
}


![image](https://github.com/lepeha81/2lab/blob/main/13.PNG)

### Задание 2
Создайте класс с именем Rectangle.
В теле класса создайте два поля, описывающие длины сторон double side1, side2.
Создайте пользовательский конструктор Rectangle(double sideA, double sideB), в теле которого поля sideA и sideB инициализируются значениями аргументов.
Создайте два private метода, вычисляющие площадь прямоугольника - double CalculateArea() и периметр прямоугольника - double CalculatePerimeter ().
Создайте два свойства double Area и double Perimeter с одним методом доступа get, вызывающим созданные ранее методы.
Напишите программу, которая принимает от пользователя длины двух сторон прямоугольника и выводит на экран периметр и площадь. Покройте тестами методы класса Rectangle.

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace lesson
{
    class Rectangle
    {
        private double side1, side2;
        public Rectangle(double sideA, double sideB)
        {
            this.side1 = sideA;
            this.side2 = sideB;
        }
        private double CalculateArea()
        {
            return (side1 * side2);
        }
        private double CalculatePerimeter()
        {
            return 2 * (side1 + side2);
        }
        public double Area
        {
            get
            {
                return CalculateArea();
            }
        }
        public double Perimeter
        {
            get
            {
                return CalculatePerimeter();

            }
        }
    }
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Введите длины двух сторон прямоугольника:");

            double sideA = Convert.ToDouble(Console.ReadLine());
            double sideB = Convert.ToDouble(Console.ReadLine());
            Rectangle rectangle = new Rectangle(sideA, sideB);
            Console.WriteLine("Периметр прямоугольника: " + rectangle.Perimeter);
            Console.WriteLine("Площадь прямоугольника: " + rectangle.Area);

        }
    }
}


# 3sem_lab1
## Homework
### Задание 1
Выведите на консоль минимальные и максимальные значения для предопределенных типов данных CTS.


```
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
```

![image]([https://github.com/lepeha81/2lab/blob/main/13.PNG](https://github.com/lepeha81/3sem_lab1/blob/main/1.PNG))

### Задание 2
Создайте класс с именем Rectangle.
В теле класса создайте два поля, описывающие длины сторон double side1, side2.
Создайте пользовательский конструктор Rectangle(double sideA, double sideB), в теле которого поля sideA и sideB инициализируются значениями аргументов.
Создайте два private метода, вычисляющие площадь прямоугольника - double CalculateArea() и периметр прямоугольника - double CalculatePerimeter ().
Создайте два свойства double Area и double Perimeter с одним методом доступа get, вызывающим созданные ранее методы.
Напишите программу, которая принимает от пользователя длины двух сторон прямоугольника и выводит на экран периметр и площадь. Покройте тестами методы класса Rectangle.
```
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
```
![image]([https://github.com/lepeha81/2lab/blob/main/13.PNG](https://github.com/lepeha81/3sem_lab1/blob/main/2.PNG))

Unit test
```
using Microsoft.VisualStudio.TestTools.UnitTesting;
using System;
using AD;
using System.Security.Policy;

namespace AD.Tests
{
    [TestClass]
    public class RectangleTests
    {
        [TestMethod]
        public void CalculateAreaTest()
        {
            int side1 = 3;
            int side2 = 4;
            Rectangle rectangle = new Rectangle(side1, side2);
            double area = rectangle.Area;

            Assert.AreEqual(12, area, 0.001);

        }

        [TestMethod]
        public void CalculatePerimetrTest()
        {
            int side1 = 3;
            int side2 = 4;
            Rectangle rectangle = new Rectangle(side1, side2);
            double perimetr = rectangle.Perimeter;

            Assert.AreEqual(14, perimetr, 0.001);

        }
    }
}
```
### Задание 3
Создайте классы Point и Figure.
Класс Point должен содержать два целочисленных поля с координатами точки.
Создайте два свойства с одним методом доступа get.
Создайте пользовательский конструктор, в теле которого проинициализируйте поля значениями аргументов.
Класс Figure должен содержать конструкторы, которые принимают от 3-х до 5-ти аргументов типа Point, а также строковое автосвойство для хранения названия фигуры.
Создайте два метода: double LengthSide(Point A, Point B), который рассчитывает длину стороны многоугольника; void PerimeterCalculator(), который рассчитывает периметр многоугольника.
Напишите программу, которая выводит на экран название и периметр многоугольника. Покройте тестами методы класса Figure.
```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

class Point
{
    private int x;
    private int y;

    public Point(int x, int y)
    {
        this.x = x;
        this.y = y;
    }

    public int X
    {
        get { return x; }
    }

    public int Y
    {
        get { return y; }
    }
}

class Figure
{
    private Point[] points;//массив координат точек
    private string name;

    public Figure(Point p1, Point p2, Point p3)
    {
        points = new Point[3];
        points[0] = p1;
        points[1] = p2;
        points[2] = p3;
    }

    public Figure(Point p1, Point p2, Point p3, Point p4)
    {
        points = new Point[4];
        points[0] = p1;
        points[1] = p2;
        points[2] = p3;
        points[3] = p4;
    }

    public Figure(Point p1, Point p2, Point p3, Point p4, Point p5)
    {
        points = new Point[5];
        points[0] = p1;
        points[1] = p2;
        points[2] = p3;
        points[3] = p4;
        points[4] = p5;
    }

    public string Name
    {
        get { return name; }
        set { name = value; }
    }

    public double LengthSide(Point A, Point B)
    {
        int xDiff = A.X - B.X;
        int yDiff = A.Y - B.Y;
        return Math.Sqrt(xDiff * xDiff + yDiff * yDiff);
    }

    public void PerimeterCalculator()
    {
        double perimeter = 0;
        for (int i = 0; i < points.Length - 1; i++)
        {
            perimeter += LengthSide(points[i], points[i + 1]);
        }
        perimeter += LengthSide(points[points.Length - 1], points[0]);
        Console.WriteLine("Название фигуры: {0}", name);
        Console.WriteLine("Периметр фигуры: {0}", perimeter);
    }
}

class Program
{
    static void Main()
    {
        Point p1 = new Point(0, 0);
        Point p2 = new Point(0, 2);
        Point p3 = new Point(2, 0);

        Figure triangle = new Figure(p1, p2, p3);
        triangle.Name = "Треугольник";
        triangle.PerimeterCalculator();
    }
}

```
![image]([https://github.com/lepeha81/2lab/blob/main/13.PNG](https://github.com/lepeha81/3sem_lab1/blob/main/3.PNG))

Unit test
```
using Microsoft.VisualStudio.TestTools.UnitTesting;
using System;
using Lesson;

namespace Lesson.Tests
{
    [TestClass]
    public class PointTests
    {
        [TestMethod]
        public void Point_Constructor_SetsXAndY()
        {
            int x = 3;
            int y = 4;

            Point point = new Point(x, y);

            Assert.AreEqual(x, point.X);/*Проверяет, равны ли указанные объекты, и создает исключение если 
два объекта не равны. Обрабатываются различные числовые типы как неравные, даже если логические значения равны.*/
            Assert.AreEqual(y, point.Y);
        }
    }
    [TestClass]
    public class FigureTests
    {
        [TestMethod]
        public void Figure_LengthSide_CalculatesCorrectLength()
        {
            Point A = new Point(0, 0);
            Point B = new Point(0, 3);
            Figure figure = new Figure(A, B);

            double length = figure.LengthSide(A, B);

            Assert.AreEqual(3.0, length, 0.001);//проверка с погрешностью
        }

        [TestMethod]
        public void Figure_PerimeterCalculator_CalculatesCorrectPerimeter()
        {
            Point p1 = new Point(0, 0);
            Point p2 = new Point(0, 1);
            Point p3 = new Point(1, 1);
            Point p4 = new Point(1, 0);

            Figure square = new Figure(p1, p2, p3, p4)
            {
                Name = "square",
            };
            //square.PerimeterCalculator();

            Assert.AreEqual(4.0, square.PerimeterCalculator(), 0.001);
        }

        [TestMethod]
        public void Figure_PerimeterCalculator_WithNullPoints()
        {
            Point p1 = new Point(0, 0);
            Point p2 = new Point(0, 2);
            Point p3 = new Point(2, 0);

            Figure triangle = new Figure(p1, p2, p3)
            {
                Name = "triangle",
            };
            //triangle.PerimeterCalculator();

            Assert.AreEqual(6.828, triangle.PerimeterCalculator(), 0.001);
        }
    }
}
```

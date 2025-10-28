using System;

namespace ExampleApp
{
    // Класс с методами
    public class MathOperations
    {
        // Публичный метод для сложения двух чисел
        public int Add(int a, int b)
        {
            return a + b;
        }

        // Приватный метод для умножения двух чисел
        private int Multiply(int a, int b)
        {
            return a * b;
        }

        // Публичный метод для вызова приватного метода умножения
        public int GetProduct(int a, int b)
        {
            return Multiply(a, b);
        }
    }

    // Класс Пользователь
    public class User
    {
        public int Id { get; set; }
        public string Name { get; set; }
        public string Email { get; set; }
        public DateTime RegistrationDate { get; set; }
        public string Role { get; set; } // например, "Пользователь", "Админ"
    }

    class Program
    {
        static void Main(string[] args)
        {
            // Создаем экземпляр класса MathOperations
            MathOperations math = new MathOperations();

            int num1 = 5;
            int num2 = 10;

            // Используем публичный метод Add
            int sum = math.Add(num1, num2);
            Console.WriteLine($"Сумма {num1} и {num2} равна {sum}");

            // Используем публичный метод для вызова приватного метода Multiply
            int product = math.GetProduct(num1, num2);
            Console.WriteLine($"Произведение {num1} и {num2} равно {product}");

            // Создаем экземпляр класса User
            User user = new User
            {
                Id = 1,
                Name = "Иван Иванов",
                Email = "ivanov@example.com",
                RegistrationDate = DateTime.Now,
                Role = "Пользователь"
            };

            // Вывод информации о пользователе
            Console.WriteLine("\nИнформация о пользователе:");
            Console.WriteLine($"ID: {user.Id}");
            Console.WriteLine($"Имя: {user.Name}");
            Console.WriteLine($"Email: {user.Email}");
            Console.WriteLine($"Дата регистрации: {user.RegistrationDate}");

{
    class Program
    {
        // 1. Создаем статические методы
        static void SayGoodMorning()
        {
            Console.WriteLine("Доброе утро!");
        }

        static void SayGoodEvening()
        {
            Console.WriteLine("Добрый вечер!");
        }

        // 2. Объявляем тип делегата
        delegate void GreetingDelegate();

        static void Main(string[] args)
        {
            // 3. Создаем экземпляр делегата и присваиваем ему метод
            GreetingDelegate greetingDelegate = SayGoodMorning;

            // 4. Вызываем метод через делегат
            greetingDelegate();

            // Меняем метод, который вызывается через делегат
            greetingDelegate = SayGoodEvening;
            greetingDelegate();

            Console.ReadLine();
        }
    }
}

{
    class Program
    {
        // 1. Создаем статические методы вычисления и вывода
        static void CalculateAndPrintSum(int a, int b)
        {
            Console.WriteLine($"Сумма чисел {a} и {b} = {a + b}");
        }

        static void CalculateAndPrintDifference(int a, int b)
        {
            Console.WriteLine($"Разность чисел {a} и {b} = {a - b}");
        }

        static void CalculateAndPrintProduct(int a, int b)
        {
            Console.WriteLine($"Произведение чисел {a} и {b} = {a * b}");
        }

        static void CalculateAndPrintDivision(int a, int b)
        {
            if (b != 0)
            {
                Console.WriteLine($"Деление числа {a} на {b} = {a / b}");
            }
            else
            {
                Console.WriteLine("Деление на ноль невозможно!");
            }
        }

        // 2. Объявляем тип делегата
        delegate void CalculateDelegate(int a, int b);

        static void Main(string[] args)
        {
            // 3. Создаем экземпляр делегата и присваиваем ему метод
            CalculateDelegate calculateDelegate = CalculateAndPrintSum;

            // 4. Применяем делегат для вызова методов
            calculateDelegate(10, 5);

            calculateDelegate = CalculateAndPrintDifference;
            calculateDelegate(10, 5);

            calculateDelegate = CalculateAndPrintProduct;
            calculateDelegate(10, 5);

            calculateDelega

{
    class Program
    {
        static double Average(int m, int n)
        {
            double sum = 0;
            double count = 0;

            for (int i = m; i <= n; i++)
            {
                sum += i;
                count++;
            }

            return sum / count;
        }

        delegate double AverageDelegate(int m, int n);

        static void Main(string[] args)
        {
            AverageDelegate averageDelegate = new AverageDelegate(Average);

            Console.WriteLine("Calculating average using delegate:");

            // Applying the delegate 3 times
            for (int i = 0; i < 3; i++)
            {
                int m = i * 10;
                int n = (i + 1) * 10;
                double result = averageDelegate(m, n);
                Console.WriteLine($"Average of numbers from {m} to {n} is: {result}");
            }
        }
    }
}

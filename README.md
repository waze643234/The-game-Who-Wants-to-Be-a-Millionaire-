```
using System;

class Program
{
    static void Main()
    {
        Console.OutputEncoding = System.Text.Encoding.UTF8;

        string[] questions = {
            "Питання 1, які кольори у прапору України?",
            "Питання 2, в якому місті знаходиться ДТЕУ?",
            "Питання 3, яка планета найближча до Сонця?",
            "Питання 4, скільки бітів в одному байті?",
            "Питання 5, який хімічний символ має золото?"
        };

        string[,] options = {
            { "1. жовтий і блакитний", "2. червоний і зелений", "3. чорний і жовтий", "4. зелений і фіолетовий" },
            { "1. Вінниця", "2. Київ", "3. Львів", "4. Одеса" },
            { "1. Венера", "2. Марс", "3. Меркурій", "4. Земля" },
            { "1. 4", "2. 16", "3. 32", "4. 8" },
            { "1. Ag", "2. Au", "3. Fe", "4. Pb" }
        };

        
        int[] correctAnswers = { 1, 2, 3, 4, 2 };

        int score = 0;

        for (int i = 0; i < questions.Length; i++)
        {
            Console.WriteLine($"Current User Score: {score}");
            Console.WriteLine(questions[i]);

            for (int j = 0; j < 4; j++)
            {
                Console.WriteLine("\t" + options[i, j]);
            }

            Console.Write("Ваша відповідь (1-4): ");
            bool isValid = int.TryParse(Console.ReadLine(), out int userAnswer);

            if (isValid && userAnswer == correctAnswers[i])
            {
                Console.WriteLine("Correct answer\n");
                score += 100;
            }
            else
            {
                Console.WriteLine("Wrong Answer");
                Console.WriteLine("кінець програми.");
                return; 
            }
        }

        Console.WriteLine($"Вітаємо! Ви виграли! Ваш фінальний рахунок: {score}");
    }
}

using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("=== BMI Calculator ===");

        Console.Write("Enter your weight in kg: ");
        if (!double.TryParse(Console.ReadLine(), out double weight) || weight <= 0)
        {
            Console.WriteLine("Invalid weight.");
            return;
        }

        Console.Write("Enter your height in meters: ");
        if (!double.TryParse(Console.ReadLine(), out double height) || height <= 0)
        {
            Console.WriteLine("Invalid height.");
            return;
        }

        double bmi = weight / (height * height);
        Console.WriteLine($"\nYour BMI is: {bmi:F2}");

        string category = bmi switch
        {
            < 18.5 => "Underweight",
            >= 18.5 and < 25 => "Normal weight",
            >= 25 and < 30 => "Overweight",
            _ => "Obese"
        };

        Console.WriteLine($"Category: {category}");
    }
}

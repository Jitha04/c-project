using System;

class IncomeTaxCalculator
{
    static void Main()
    {
        // Input: User's income
        Console.WriteLine("Enter your annual income:");
        double income = Convert.ToDouble(Console.ReadLine());

        // Tax slabs
        double tax = 0;

        // Apply tax slabs based on the income
        if (income <= 250000)
        {
            tax = 0;
        }
        else if (income > 250000 && income <= 500000)
        {
            tax = 0.05 * (income - 250000);  // 5% for income between 2.5L and 5L
        }
        else if (income > 500000 && income <= 1000000)
        {
            tax = (0.05 * 250000) + (0.1 * (income - 500000));  // 5% for first 2.5L and 10% for income above 5L
        }
        else if (income > 1000000)
        {
            tax = (0.05 * 250000) + (0.1 * 500000) + (0.2 * (income - 1000000));  // 5%, 10%, and 20% for above 10L
        }

        // Output: Display the calculated tax
        Console.WriteLine($"Your income tax is: {tax:C2}"); // Displays the tax in currency format
    }
}


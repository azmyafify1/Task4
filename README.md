using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        try
        {
            Console.WriteLine("Enter a list of integers separated by spaces:");
            string input = Console.ReadLine();
            string[] parts = input.Split(' ');
            HashSet<int> numbers = new HashSet<int>();

            for (int i = 0; i < parts.Length; i++)
            {
                int num = int.Parse(parts[i]);
                if (!numbers.Add(num))
                {
                    throw new Exception("Duplicate number found: " + num);
                }
            }

            Console.WriteLine("All numbers are unique!");
        }
        catch (Exception ex)
        {
            Console.WriteLine("Error: " + ex.Message);
        }
    }
}

# Sum-Of-Numbers
Using C# console application, input ten numbers and calculate the total sum.


namespace SumNum
{
    class Program
    {
        static void Main(string[] args)
        {
            //Variable Declarations
            double totalSum;
      
            Console.WriteLine("Enter ten values from 0 to 100.");
            //Assign and call method
            totalSum = sumValue();
            Console.WriteLine($"\nTotal Value: {totalSum}");
            Console.ReadLine();
        }




        //Add values 
        static double sumValue()
        {
            //Variables declaration and assignment for sumValue()
            double sum;
            double total = 0;

            //Repeat value entry 10 times
            for (int count = 0; count < 10; count ++)
            {
                //Label reference
                Start:

                Console.Write($"\nNumber {count + 1}: ");

                //Exception handler. Going to try the following block of code.
               try
               {
                 //Ask user for input and convert to double
                 sum = Convert.ToDouble(Console.ReadLine());
                 //Sum assignment with user input and sum arguements.
                 sum = repeatV(sum, count);
                 //total assignment with increasing input sum for every loop
                 total += sum;
                }
                //Catches error
               catch (Exception error)
               {
                    //sum assignment with count and error arguments
                    Console.WriteLine($"\n{error.Message.ToString()}");

                    //Goes to reference label
                    goto Start;
                }
            }
            //Return total
            return total;
        }

        //Looping negative and large numbers with two parameters for sum and count
        static double repeatV(double x, int y)
        {
            //Loop conditions
            while (x < 0 || x > 100)
            {
                Console.WriteLine("\nInvalid Value.");
                Console.Write($"\nNumber {y + 1}: ");
                x = Convert.ToDouble(Console.ReadLine());
            }
            
            //Return x
            return x;
        }
    }
}

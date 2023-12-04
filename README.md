char c=Convert.ToChar(Console.ReadLine());
int i=Convert.ToInt32(Console.ReadLine());


PrintBoard(c,i);



void PrintBoard(char column, int row)
{
    Console.Clear();
    Console.WriteLine($"{column}{row}");
    char[] ch = { 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H' };
    Console.Write("  ");
    foreach (char ch2 in ch)
        Console.Write(ch2 + " ");
    Console.Write("\n");
    for (int i = 0; i < 10; i++)
        Console.Write("--");

    Console.WriteLine();

    for (int i = 1; i < 9; i++)
    {
        Console.BackgroundColor = ConsoleColor.Black;
        Console.Write(i + "|");
        for (char j = 'A'; j <= 'H'; j++)
        {
            
            if ((i + (int)j) % 2 == 0)
            {
                Console.BackgroundColor = ConsoleColor.Black;
            }
            else
            {
                Console.BackgroundColor = ConsoleColor.White;
            }
            if (i == row && j == column)
            {
                Console.ForegroundColor = ConsoleColor.Red;
                Console.Write(" F");
            }
            else
            {
                Console.ForegroundColor = ConsoleColor.White;
                Console.Write("  ");
            }
                

        }

        Console.BackgroundColor = ConsoleColor.Black;
        Console.Write("|" + i);

        Console.WriteLine();
    }

    for (int i = 0; i < 10; i++)
        Console.Write("--");
    Console.WriteLine();
    Console.Write("  ");
    foreach (char ch2 in ch)
        Console.Write(ch2 + " ");
}



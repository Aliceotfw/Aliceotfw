using System.Data.Common;
using System.Runtime.InteropServices;

Console.Write("Enter coordinate1: ");
string coord1 = Console.ReadLine();
Console.Write("Enter coordinate2: ");
string coord2 = Console.ReadLine();





PrintBoard(coord1);
Console.WriteLine();
Console.WriteLine(CheckknightCoord(coord1, coord2)); 
if(CheckknightCoord(coord1, coord2))
    PrintBoard(coord2);





bool CheckknightCoord(string coord1, string coord2)
{
    char column1 = coord1[0];
    int row1 = int.Parse(coord1.Substring(1));
    char column2 = coord2[0];
    int row2 = int.Parse(coord2.Substring(1));

    int rowDifference = Math.Abs(row2 - row1);
    int columnDifference = Math.Abs(column2 - column1);

    return (rowDifference == 2 && columnDifference == 1) || (rowDifference == 1 && columnDifference == 2);
}


void PrintBoard(string coord1)
{
    char column = coord1[0];
    int row = int.Parse(coord1.Substring(1));
    char[] ch = { 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H' };
    Console.Write(" ");
    foreach (char ch2 in ch)
        Console.Write(" " + ch2 + " ");

    Console.WriteLine();

    for (int i = 1; i < 9; i++)
    {
        
        Console.Write(i);
        for (char j = 'A'; j <= 'H'; j++)
        {
            
            if ((i + (int)j) % 2 == 0)
            {
                Console.BackgroundColor = ConsoleColor.DarkGray;
            }
            else
            {
                Console.BackgroundColor = ConsoleColor.White;
            }
            if (i == row && j == column)
            {
                Console.ForegroundColor = ConsoleColor.Red;
                Console.Write(" N ");
            }
            else
            {
                Console.ForegroundColor = ConsoleColor.White;
                Console.Write("   ");
            }
                Console.ResetColor();

        }

        
        Console.Write(i);
        
        Console.WriteLine();
    }

    Console.Write(" ");
    foreach (char ch2 in ch)
        Console.Write(" " + ch2 + " ");
}  


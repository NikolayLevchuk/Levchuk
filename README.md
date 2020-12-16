# Levchuk

//lab 1 *** Variant_13

static void Main(string[] args)
{
string n,r; double P=0,a;
do { Console.Write("Введите количество сторон правильного n-угольника ");
n=Console.ReadLine(); 
} 
while (Convert.ToInt32(n)<2 || 360 % Convert.ToInt32(n)!=0); 
Console.Write("Введите радиус "); 
r = Console.ReadLine(); a = 2 * Convert.ToDouble(r) * Math.Tan(Math.PI / Convert.ToDouble(n)); Console.WriteLine("Сторона "+n+"-угольника = "+a); P = Convert.ToDouble(n) * Convert.ToDouble(a); Console.WriteLine("Периметр правильного "+n+"-уголника = " + P); }

//lab 2 *** var_13

static void Main(string[] args) {
double u = 0; double S = 0; 
int a = 0; 
double x; 
string b; 
Console.WriteLine("Введите значение ");

        do
        {
            b = Console.ReadLine();
            x = Convert.ToDouble(b);
            if (a > x)
            {
                Console.WriteLine("Введите другое значение ");
            }
        } while (a > x);

        for (int i = 0; i <= x; i++)
        {
            u += (Math.Pow(-1, i) * Math.Pow(i,2) + Math.Pow(-1, Math.Pow(i,2) - 1) *i) / (2*Math.Pow(i, 3) + 3);
            S *= u;
            Console.WriteLine("u" + i + "=" + u);
            u = 0;
        }
        Console.WriteLine("Добуток = " + S);
        Console.ReadKey();
    }
    
    //lab 3 *** var 13
    
    class Program
{
    static void Main(string[] args)
    {
        string str;
        int i;
        Console.WriteLine("Введите трехзначное число образующее строго возрастную последовательность");
        str = Console.ReadLine();
        if (str[0] < str[1] && str[1] < str[2] )
            Console.WriteLine("true");
        else
            Console.WriteLine("false");
    }
}

//lab 4 *** var 13

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApp9 { class Program { static void Main(string[] args) {

        string b;
        var mass = new List<int>();
        Console.WriteLine("Введите элемент массива");

        while (!string.IsNullOrWhiteSpace((b = Console.ReadLine())))
        {
            int c;
            if (int.TryParse(b, out c))
            {
                mass.Add(c);
                int count = mass.Count();
                if (count > 2 && mass[count - 1] < mass[count - 2] && mass[count - 2] > mass[count - 3])
                    Console.WriteLine("Локальный максимум {0}", mass[count - 2]);
                Console.WriteLine("выведите массив");
            }
            else
                Console.WriteLine("Некорректный ввод! Нужно исправить");
        }
        Console.WriteLine("----------------");
        Console.WriteLine("Получившийся массив");
        Console.WriteLine(string.Join("", mass));
        Console.WriteLine("----------------");
        Console.ReadKey();

    }
}

//lab 5 *** var 13

    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;

namespace ConsoleApp14 { class Program {

    static void Main(string[] args)
    {
        Console.WriteLine("Вкажiть розмiрнiсть квадратноi матриці");
        string str = Console.ReadLine();
        int N = Convert.ToInt32(str);
        int[,] matrix = new int[N, N];
        int sum1 = 0; int sum2 = 0;

        Random rnd = new Random();
        for (int i = 0; i < N; i++)
        {
            for (int t = 0; t < N; t++)
            {
                matrix[i, t] = rnd.Next(0, 10);
                Console.Write(matrix[i, t] + "\t");
            }
            Console.WriteLine();
        }

        for (int i = 0; i < N; i++)
        {
            sum1 += matrix[i, i];
            sum2 += matrix[i, N - i - 1];
        }

        Console.WriteLine();
        Console.WriteLine("Cума головноi матрицi - " + sum1);
        Console.WriteLine("Cума побічноi матрицi - " + sum2);
        Console.ReadKey();
    }
}

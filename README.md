# 1. SINTAXIS (Módulo CSharp)

1. Solicite el nombre de una persona, su edad y el nombre de una ciudad. Después de solicitar estos datos deberá mostrar por pantalla el siguiente mensaje: Te llamas y tienes <años> años. Bienvenido a

```csharp
namespace curso_csharp
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Introduzca su nombre: ");
            String nombre = Console.ReadLine();
            Console.WriteLine("Introduzca su edad: ");
            int edad = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("Introduzca el nombre de una ciudad: ");
            String ciudad = Console.ReadLine();

            Console.WriteLine($"Te llamas {nombre} y tienes {edad} años. Bienvenido a {ciudad}.");

            Console.ReadLine();
        }
    }
}
```

2. Solicite dos números y diga cual es el mayor.

```csharp
namespace curso_csharp
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Introduzca un numero: ");
            int num1 = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("Introduzca otro numero: ");
            int num2 = Convert.ToInt32(Console.ReadLine());

            if (num1 > num2)
            {
                Console.WriteLine($"{num1} es mayor que {num2}.");
            }
            else if (num2 == num1)
            {
                Console.WriteLine("Ambos numeros son el mismo.");
            }
            else
            {
                Console.WriteLine($"{num1} es menor que {num2}.");
            }

            Console.ReadLine();
        }
    }
}
```

3. Pedir el nombre de la semana al usuario y decirle si es fin de semana o no. En caso de error, indicarlo.

```csharp
namespace curso_csharp
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Introduzca un dia de la semana (sin tildes): ");
            String dia = Console.ReadLine().ToLower();

            switch (dia)
            {
                case "lunes":
                case "martes":
                case "miercoles":
                case "jueves":
                case "viernes":
                    Console.WriteLine("Este dia NO es fin de semana.");
                    break;
                case "sabado":
                case "domingo":
                    Console.WriteLine("Este dia SI es fin de semana.");
                    break;
                default:
                    Console.WriteLine("No has introducido un dia valido.");
                    break;
            }

            Console.ReadLine();
        }
    }
}
```

4. Recorre los números del 1 al 100. Muestra los números pares. Usar el tipo de bucle que quieras.

```csharp
namespace curso_csharp
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Numeros pares del 0 al 100:");

            for (int i = 0; i <= 100; i++) 
            {
                if (i % 2 == 0)
                {
                    Console.WriteLine(i);
                }
            }

            Console.ReadLine();
        }
    }
}
```
5. Solicitar un número al usuario y generar un Array con N números aleatorios. Por ejemplo, si el usuario introduce 4, el resultado por consola debería ser: 23, 34, 234, 11

```csharp
namespace curso_csharp
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Introduzca un numero para generar X numeros aleatorios (del 0 al 500): ");
            int num = Convert.ToInt32(Console.ReadLine());

            List<int> list = new List<int>();
            Random random = new Random();

            for (int i = 0; i < num; i++)
            {
                int aleatorio = random.Next(0, 500);
                list.Add(aleatorio);
            }

            foreach (int j in list)
            {
                Console.WriteLine(j);
            }

            Console.ReadLine();
        }
    }
}
```
6. Solicitar un número al usuario y un carácter. Crear una pirámide con N filas y el carácter solicitado. Por ejemplo, si el usuario introduce 5 y * el resultado por consola debería ser:

    ```
    *
    **
    * *
    *  *
    *****
    ```

```csharp
namespace curso_csharp
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Introduzca un numero para generar una piramide: ");
            int num = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("Introduzca un caracter para dibujar: ");
            char caracter = Convert.ToChar(Console.ReadLine());

            for (int i = 1; i < num; i++)
            {
                for (int j = 1; j <= i + 1; j++)
                {
                    if (j == 1 || j == i + 1 || i == num - 1)
                    {
                        Console.Write(caracter);
                    }
                    else
                    {
                        Console.Write(" ");
                    }
                    
                }
                Console.WriteLine();
            }

            Console.ReadLine();
        }
    }
}
```

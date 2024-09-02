Este programa en C# aborda cuatro ejercicios fundamentales de programación, cada uno diseñado para demostrar y aplicar conceptos básicos en C#. A continuación, se detalla cada uno de los ejercicios incluidos:

Comparación de Tres Números Enteros:
        Objetivo: El usuario ingresa tres números enteros. El programa determina cuál de estos números es el mayor y verifica si existe algún par de números iguales entre ellos.
        Función Principal: ObtenerMayorYComparar(int n1, int n2, int n3)
        Descripción: La función compara los tres números proporcionados y encuentra el mayor. Luego, construye un mensaje indicando el número mayor y si hay números que se repiten.

Determinación de Paridad:
        Objetivo: Solicita al usuario un número entero y determina si dicho número es par o impar.
        Función Principal: DeterminarParidad(int num)
        Descripción: Utiliza el operador módulo para evaluar la paridad del número ingresado. Retorna "par" si el número es divisible por 2 sin residuo, y "impar" en caso contrario.

Cálculo del Cuadrado de un Número Entero:
        Objetivo: Pide al usuario que ingrese un número entero y calcula su cuadrado.
        Función Principal: CalcularCuadrado(int num)
        Descripción: Calcula el cuadrado del número proporcionado y retorna el resultado. Este valor es mostrado al usuario como el cuadrado del número ingresado.

Verificación de Anagramas:
        Objetivo: Verifica si dos cadenas de texto ingresadas por el usuario son anagramas, es decir, si contienen los mismos caracteres con la misma frecuencia, aunque en diferente orden.
        Función Principal: SonAnagramasBasico(string str1, string str2)
        Descripción: Compara la frecuencia de cada carácter en ambas cadenas. Utiliza la función auxiliar ContarCaracteres para contar la aparición de cada carácter y determina si las cadenas son anagramas basándose en estas frecuencias.

Cómo Ejecutar el Programa

Ejercicio 1: El programa solicita tres números enteros. Luego, muestra cuál es el mayor y si hay números repetidos entre ellos.
Ejercicio 2: El usuario ingresa un número entero para determinar si es par o impar.
Ejercicio 3: Se pide al usuario un número entero y se calcula su cuadrado.
Ejercicio 4: Se ingresan dos cadenas de texto para verificar si son anagramas.

Cada ejercicio está implementado como una función separada para facilitar la comprensión y el mantenimiento del código. El programa está diseñado para ser interactivo y proporciona resultados claros y directos a los usuarios.
	using System;
	
	class Program
	{
	    static void Main()
	    {
	        // EJERCICIO #1: COMPARACION DE 3 NUMEROS ENTEROS
	        Console.WriteLine("Ejercicio 1: Comparación de tres números enteros.");
	        Console.WriteLine("Por favor, ingresa el primer número:");
	        int numero1 = int.Parse(Console.ReadLine());
	
	        Console.WriteLine("Ahora ingresa el segundo número:");
	        int numero2 = int.Parse(Console.ReadLine());
	
	        Console.WriteLine("Finalmente, ingresa el tercer número:");
	        int numero3 = int.Parse(Console.ReadLine());
	
	        string resultadoComparacion = ObtenerMayorYComparar(numero1, numero2, numero3);
	        Console.WriteLine(resultadoComparacion);
	        Console.WriteLine();  // Espacio para separar resultados
	
	        // EJERCICIO #2: FUNCION PAR O IMPAR
	        Console.WriteLine("Ejercicio 2: Determinar si un número es par o impar.");
	        Console.WriteLine("Por favor, ingresa un número entero:");
	        int numero = int.Parse(Console.ReadLine());
	
	        string resultadoParidad = DeterminarParidad(numero);
	        Console.WriteLine($"El número {numero} es {resultadoParidad}.");
	        Console.WriteLine();  // Espacio para separar resultados
	
	        // EJERCICIO #3: CALCULAR EL CUADRADO DE UN ENTERO
	        Console.WriteLine("Ejercicio 3: Calcular el cuadrado de un número entero.");
	        Console.WriteLine("Por favor, ingresa un número entero:");
	        int numeroCuadrado = int.Parse(Console.ReadLine());
	
	        int resultadoCuadrado = CalcularCuadrado(numeroCuadrado);
	        Console.WriteLine($"El cuadrado de {numeroCuadrado} es {resultadoCuadrado}.");
	        Console.WriteLine();  // Espacio para separar resultados
	
	        // EJERCICIO #4: DETERMINAR SI DOS CADENAS SON ANAGRAMAS
	        Console.WriteLine("Ejercicio 4: Verificar si dos cadenas son anagramas.");
	        Console.WriteLine("Ingresa la primera cadena:");
	        string cadena1 = Console.ReadLine();
	
	        Console.WriteLine("Ingresa la segunda cadena:");
	        string cadena2 = Console.ReadLine();
	
	        bool sonAnagramas = SonAnagramasBasico(cadena1, cadena2);
	        if (sonAnagramas)
	        {
	            Console.WriteLine("Las cadenas son anagramas.");
	        }
	        else
	        {
	            Console.WriteLine("Las cadenas no son anagramas.");
	        }
	    }
	
	    // FUNCION EJERCICIO #1
	    static string ObtenerMayorYComparar(int n1, int n2, int n3)
	    {
	        int mayor = n1;
	
	        if (n2 > mayor)
	        {
	            mayor = n2;
	        }
	        if (n3 > mayor)
	        {
	            mayor = n3;
	        }
	
	        string mensaje = $"El número más grande es: {mayor}";
	
	        if (n1 == n2 || n1 == n3 || n2 == n3)
	        {
	            mensaje += ". Además, hay números iguales entre sí.";
	        }
	        else
	        {
	            mensaje += ". Todos los números son diferentes.";
	        }
	
	        return mensaje;
	    }
	
	    // FUNCION EJERCICIO #2
	    static string DeterminarParidad(int num)
	    {
	        if (num % 2 == 0)
	        {
	            return "par";
	        }
	        else
	        {
	            return "impar";
	        }
	    }
	
	    // FUNCION EJERCICIO #3
	    static int CalcularCuadrado(int num)
	    {
	        return num * num;
	    }
	
	    // FUNCION EJERCICIO #4
	    static bool SonAnagramasBasico(string str1, string str2)
	    {
	        if (str1.Length != str2.Length)
	        {
	            return false;
	        }
	
	        str1 = str1.ToLower();
	        str2 = str2.ToLower();
	
	        foreach (char c in str1)
	        {
	            int countInStr1 = ContarCaracteres(str1, c);
	            int countInStr2 = ContarCaracteres(str2, c);
	
	            if (countInStr1 != countInStr2)
	            {
	                return false;
	            }
	        }
	
	        return true;
	    }
	
	    static int ContarCaracteres(string str, char c)
	    {
	        int count = 0;
	        foreach (char ch in str)
	        {
	            if (ch == c)
	            {
	                count++;
	            }
	        }
	        return count;
	    }
	}

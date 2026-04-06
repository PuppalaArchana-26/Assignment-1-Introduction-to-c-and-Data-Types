# Assignment-1-Introduction-to-c-and-Data-Types
# Assignment: Choosing Appropriate Data Types
## Question 1  What type would you choose for the following numbers?
## Answer
In a database, choosing the correct data type is important to store data properly and avoid errors. Below are the suitable data types with examples:
**Telephone Number** → VARCHAR  
  Example: 555-123-4567  
  Telephone numbers are stored as text because they may contain symbols like dashes and are not used for calculations.
**Height** → DECIMAL  
  Example: 5.9 or 175.5  
  Height can include decimal values, so a decimal type is suitable.
 **Age** → INT  
  Example: 27  
  Age is always a whole number.
 **Gender** → ENUM or VARCHAR  
  Example: Female  
  Gender has a limited set of values, so it can be stored as text.
**Salary** → DECIMAL  
  Example: 50000.75  
  Salary requires accuracy, especially for decimal values.
 **ISBN** → VARCHAR  
  Example: 978-3-16-148410-0  
  ISBN contains dashes and is not used in calculations.
**Book Price** → DECIMAL  
  Example: 19.99  
  Prices need exact precision for currency values.
 **Shipping Weight** → DECIMAL  
  Example: 1.25  
  Weight can have fractional values.
 **Country Population** → BIGINT  
  Example: 1400000000  
  Population numbers can be very large.
**Number of Stars in the Universe** → BIGINT  
  Example: 1000000000000000000  
  This represents extremely large values.
**Number of Employees (up to 50,000)** → INT  
  Example: 1250  
  This value is within the range of integer numbers.
## Question 2. What are the difference between value type and reference type variables? What is boxing and unboxing?
**#ANSWER**

In programming, variables can be either value types or reference types, and it’s important to know the difference.

**Value types** store the actual data. For example, if you have an integer or a float, the variable holds the number itself. Copying a value type creates a completely independent copy.

**Reference types** on the other hand, store a reference (like a pointer) to where the actual data is stored in memory. Objects, arrays, and strings are reference types. When you copy a reference type variable, both copies point to the same object, so changes in one affect the other.

**Example:**

**Value type:**
int a = 10;

int b = a; // b is a copy of a

b = 20;  // a is still 10

**Reference type:**

int[] arr1 = {1, 2, 3};

int[] arr2 = arr1; // arr2 points to the same array as arr1

arr2[0] = 10;     // arr1[0] is now 10 too

Boxing and Unboxing are ways to convert between value types and reference types.

**Boxing** happens when a value type is wrapped into an object so it can be treated as a reference type.

**Unboxing** happens when the value is taken back out of the object to its original type.

**Example:**

int num = 123;      // value type

object obj = num;   // boxing: value type -> reference type

int n = (int)obj;   // unboxing: reference type -> value type

## Question 3 What is meant by the terms managed resource and unmanaged resource in .NET?

**#ANSWER**

**Managed Resource**

**Definition:** Managed resources are handled automatically by the .NET runtime (CLR).
The Garbage Collector (GC) automatically allocates and frees memory for these objects.
You don’t need to manually clean them up.

**Examples:**

Objects created using new in C# (like String, List, StreamReader)
Arrays, classes, and other .NET objects

**Example:**

List<int> numbers = new List<int>(); // managed resource

numbers.Add(1);

numbers = null; // GC will clean it up automatically

**Unmanaged Resource**

**Definition:** Unmanaged resources are not handled by the .NET runtime.
You need to manually release or clean them when you’re done, otherwise they can cause memory leaks.

**Examples:**

File handles
Database connections
Network sockets
Windows handles, GDI objects, or external libraries

**Example:**

FileStream fs = new FileStream("file.txt", FileMode.Open); // unmanaged resource

fs.Close(); // manually release the resource

## Question 4 Whats the purpose of Garbage Collector in .NET?

**#ANSWER**

In .NET, the Garbage Collector (GC) is responsible for automatic memory management. Its main job is to clean up memory that is no longer being used by your program, so you don’t have to manually free it. This helps prevent memory leaks and improves the performance and reliability of your application.


**Playing with Console App**
**Practice number sizes and ranges**

## Question 1 .

Create a console application project named /02UnderstandingTypes/ that outputs the
number of bytes in memory that each of the following number types uses, and the
minimum and maximum values they can have: sbyte, byte, short, ushort, int, uint, long,
ulong, float, double, and decimal.
Composite Formatting to learn how to align text in a console application
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Number Type     Bytes     Min Value                 Max Value");
        Console.WriteLine("---------------------------------------------------------------");

        Console.WriteLine("{0,-15} {1,-8} {2,-25} {3}", "sbyte", sizeof(sbyte), sbyte.MinValue, sbyte.MaxValue);
        Console.WriteLine("{0,-15} {1,-8} {2,-25} {3}", "byte", sizeof(byte), byte.MinValue, byte.MaxValue);
        Console.WriteLine("{0,-15} {1,-8} {2,-25} {3}", "short", sizeof(short), short.MinValue, short.MaxValue);
        Console.WriteLine("{0,-15} {1,-8} {2,-25} {3}", "ushort", sizeof(ushort), ushort.MinValue, ushort.MaxValue);
        Console.WriteLine("{0,-15} {1,-8} {2,-25} {3}", "int", sizeof(int), int.MinValue, int.MaxValue);
        Console.WriteLine("{0,-15} {1,-8} {2,-25} {3}", "uint", sizeof(uint), uint.MinValue, uint.MaxValue);
        Console.WriteLine("{0,-15} {1,-8} {2,-25} {3}", "long", sizeof(long), long.MinValue, long.MaxValue);
        Console.WriteLine("{0,-15} {1,-8} {2,-25} {3}", "ulong", sizeof(ulong), ulong.MinValue, ulong.MaxValue);
        Console.WriteLine("{0,-15} {1,-8} {2,-25} {3}", "float", sizeof(float), float.MinValue, float.MaxValue);
        Console.WriteLine("{0,-15} {1,-8} {2,-25} {3}", "double", sizeof(double), double.MinValue, double.MaxValue);
        Console.WriteLine("{0,-15} {1,-8} {2,-25} {3}", "decimal", sizeof(decimal), decimal.MinValue, decimal.MaxValue);
    }
}

**EXPLANATION **

sizeof(type) → Returns the number of bytes used by the type.

type.MinValue and type.MaxValue → Shows the range of that numeric type.

Composite formatting ({0,-15} {1,-8} {2,-25} {3}) →

0 → first argument (Number Type)

-15 → left-align in 15-character width

Makes columns neatly aligned for readability


## Question 2

Write program to enter an integer number of centuries and convert it to years, days, hours,
minutes, seconds, milliseconds, microseconds, nanoseconds. Use an appropriate data
type for every data conversion. Beware of overflows!
Input: 1
Output: 1 centuries = 100 years = 36524 days = 876576 hours = 52594560 minutes
= 3155673600 seconds = 3155673600000 milliseconds = 3155673600000000
microseconds = 3155673600000000000 nanoseconds
Input: 5
Output: 5 centuries = 500 years = 182621 days = 4382904 hours = 262974240
minutes = 15778454400 seconds = 15778454400000 milliseconds = 15778454400000000
microseconds = 15778454400000000000 nanoseconds

**ANSWER**

using System;

class Program
{
    static void Main()
    {
        Console.Write("Enter number of centuries: ");
        long centuries = long.Parse(Console.ReadLine());

        // Step-by-step calculation using integers
        long years = centuries * 100;
        long days = years * 36524 / 100;      // 365.24 days per year
        long hours = days * 24;
        long minutes = hours * 60;
        long seconds = minutes * 60;
        decimal milliseconds = (decimal)seconds * 1000;
        decimal microseconds = milliseconds * 1000;
        decimal nanoseconds = microseconds * 1000;

        Console.WriteLine($"{centuries} centuries = {years} years = {days} days = {hours} hours = {minutes} minutes = {seconds} seconds = {milliseconds:N0} milliseconds = {microseconds:N0} microseconds = {nanoseconds:N0} nanoseconds");
    }
}
Explore following topics
C# Keywords
Main() and command-line arguments
Types (C# Programming Guide)
Statements, Expressions, and Operators
Strings (C# Programming Guide)
Nullable Types (C# Programming Guide)
Nullable reference types


**C# Keywords**

Definition: Reserved words in C# with special meaning; cannot be used as variable names.
Example:

int age = 21;  // 'int' is a keyword

**Main() and Command-Line Arguments**

Definition: Main() is the entry point of a C# program; it can take command-line arguments as input.
Example:

static void Main(string[] args)
{
    Console.WriteLine(args[0]); // prints first argument
}

**Types (C# Programming Guide)**

Definition: Data types define the type of data a variable can store.

Value types: store data directly (int, double)
Reference types: store reference to data (string, object)
Example:
int a = 10;       // value type
string name = "Archana"; // reference type

**Statements, Expressions, and Operators**

Definition:

Statement: A complete instruction (int a = 5;)
Expression: Produces a value (5 + 3)
Operator: Symbol to perform operations (+, -, *)
Example:
int sum = 5 + 3;  // expression with operator inside statement

**Strings (C# Programming Guide)**

Definition: A sequence of characters used to store text.
Example:

string name = "Archana";
Console.WriteLine("Hello " + name);

**Nullable Types (C# Programming Guide)**

Definition: Value types that can store null using ?.
Example:

int? age = null;
age = 25;
Console.WriteLine(age);  // 25

**Nullable Reference Types**

Definition: Reference types that explicitly allow null (introduced in C# 8.0) to prevent null reference exceptions.
Example:

string? name = null;  // nullable reference type
string city = "Cleveland"; // non-nullable


**Dividing an int by 0**

Throws a DivideByZeroException at runtime.

**Dividing a double by 0**

Results in Infinity or -Infinity; no exception is thrown.

 **Overflowing an int variable**

The value wraps around silently unless checked, in which case an OverflowException occurs.

**x = y++; vs x = ++y;**

y++ is post-increment (use value first, then increment)
++y is pre-increment (increment first, then use value)

**break, continue, and return in loops**

break → exits the entire loop
continue → skips current iteration and moves to next
return → exits the method entirely

**Three parts of a for statement**

Initialization, Condition, Iteration; condition is required, others are optional.
 
 **= vs == operators**
 
= → assignment
== → equality comparison

**for ( ; true; ) ; statement**

Compiles; represents an infinite loop.

**Underscore _ in a switch expression**

Represents the default case (matches anything not explicitly handled).

**Interface required for foreach**

The object must implement IEnumerable or IEnumerable<T>.

**FizzBuzz (Count to 100)**

using System;

class Exercise03
{
    static void Main()
    {
        for (int i = 1; i <= 100; i++)
        {
            if (i % 3 == 0 && i % 5 == 0)
                Console.WriteLine("fizzbuzz");
            else if (i % 3 == 0)
                Console.WriteLine("fizz");
            else if (i % 5 == 0)
                Console.WriteLine("buzz");
            else
                Console.WriteLine(i);
        }
    }
}

**Byte Overflow Example**

using System;

class ByteOverflow
{
    static void Main()
    {
        int max = 500;
        for (byte i = 0; i < max; i++)
        {
            Console.WriteLine(i);
        }
    }
} 

**Random Number Guessing Game (1–3)**

using System;

class RandomGuess
{
    static void Main()
    {
        int correctNumber = new Random().Next(3) + 1; // 1 to 3

        Console.Write("Guess a number between 1 and 3: ");
        int guessedNumber = int.Parse(Console.ReadLine());

        if (guessedNumber < 1 || guessedNumber > 3)
            Console.WriteLine("Invalid guess! Number must be 1, 2, or 3.");
        else if (guessedNumber < correctNumber)
            Console.WriteLine("Too low!");
        else if (guessedNumber > correctNumber)
            Console.WriteLine("Too high!");
        else
            Console.WriteLine("Correct! Well done!");
    }
}

using System;

class StarPyramid
{
    static void Main()
    {
        int totalLines = 5; // Number of lines in the pyramid

        for (int i = 1; i <= totalLines; i++)
        {
            // First inner loop: print spaces
            for (int j = i; j < totalLines; j++)
            {
                Console.Write(" ");
            }

            // Second inner loop: print stars
            for (int k = 1; k <= (2 * i - 1); k++)
            {
                Console.Write("*");
            }

            // Move to the next line
            Console.WriteLine();
        }
    }
}

**2. PRINT A PYRAMID**

using System;

class StarPyramid
{
    static void Main()
    {
        int totalLines = 5; // Number of lines in the pyramid

        for (int i = 1; i <= totalLines; i++)
        {
            // First inner loop: print spaces
            for (int j = i; j < totalLines; j++)
            {
                Console.Write(" ");
            }

            // Second inner loop: print stars
            for (int k = 1; k <= (2 * i - 1); k++)
            {
                Console.Write("*");
            }

            // Move to the next line
            Console.WriteLine();
        }
    }
}



**Write a program that generates a random number between 1 and 3 and asks the user to
guess what the number is. Tell the user if they guess low, high, or get the correct answer.
Also, tell the user if their answer is outside of the range of numbers that are valid guesses
(less than 1 or more than 3). You can convert the user's typed answer from a string to an
int using this code**



using System;

class RandomGuessGame
{
    static void Main()
    {
        // Generate a random number between 1 and 3
        int correctNumber = new Random().Next(3) + 1;

        // Ask the user to guess
        Console.Write("Guess a number between 1 and 3: ");
        int guessedNumber = int.Parse(Console.ReadLine()); // assume valid integer input

        // Check the guess
        if (guessedNumber < 1 || guessedNumber > 3)
        {
            Console.WriteLine("Invalid guess! Number must be 1, 2, or 3.");
        }
        else if (guessedNumber < correctNumber)
        {
            Console.WriteLine("Too low!");
        }
        else if (guessedNumber > correctNumber)
        {
            Console.WriteLine("Too high!");
        }
        else
        {
            Console.WriteLine("Correct! Well done!");
        }
    }
}

**Write a simple program that defines a variable representing a birth date and calculates
how many days old the person with that birth date is currently.
For extra credit, output the date of their next 10,000 day (about 27 years) anniversary.
Note: once you figure out their age in days, you can calculate the days until the next
anniversary using int daysToNextAnniversary = 10000 - (days % 10000);**

using System;

class AgeInDays
{
    static void Main()
    {
        // Define birth date (change to actual birth date)
        DateTime birthDate = new DateTime(1995, 5, 15);

        // Calculate age in days
        DateTime today = DateTime.Today;
        TimeSpan ageSpan = today - birthDate;
        int daysOld = ageSpan.Days;

        Console.WriteLine("You are " + daysOld + " days old.");

        // Calculate days until next 10,000-day anniversary
        int daysToNextAnniversary = 10000 - (daysOld % 10000);
        DateTime nextAnniversary = today.AddDays(daysToNextAnniversary);

        Console.WriteLine("Your next 10,000-day anniversary is in " + 
                           daysToNextAnniversary + " days, on " + 
                           nextAnniversary.ToString("MMMM dd, yyyy") + ".");
    }
}
How it works:
birthDate → set the person’s birth date.
ageSpan = today - birthDate → difference in TimeSpan.
daysOld = ageSpan.Days → total days.
daysToNextAnniversary = 10000 - (daysOld % 10000) → days until next 10,000-day milestone.
nextAnniversary = today.AddDays(daysToNextAnniversary) → date of next anniversary.


**QUESTION 5**

using System;

class TimeBasedGreeting
{
    static void Main()
    {
        // You can test with a specific time
        // DateTime currentTime = new DateTime(2026, 4, 6, 14, 30, 0); // 2:30 PM
        // Or use the current system time
        DateTime currentTime = DateTime.Now;

        int hour = currentTime.Hour; // 0-23

        if (hour >= 5 && hour < 12)
        {
            Console.WriteLine("Good Morning");
        }

        if (hour >= 12 && hour < 17)
        {
            Console.WriteLine("Good Afternoon");
        }

        if (hour >= 17 && hour < 21)
        {
            Console.WriteLine("Good Evening");
        }

        if ((hour >= 21 && hour <= 23) || (hour >= 0 && hour < 5))
        {
            Console.WriteLine("Good Night");
        }
    }
}

How it works:
currentTime.Hour gives the hour in 24-hour format (0–23).
if statements check which time range the current hour falls into:
5–11 → Morning
12–16 → Afternoon
17–20 → Evening
21–4 → Night
Only if is used, no else.

**Write a program that prints the result of counting up to 24 using four different increments.
First, count by 1s, then by 2s, by 3s, and finally by 4s.
Use nested for loops with your outer loop counting from 1 to 4. You inner loop should
count from 0 to 24, but increase the value of its /loop control variable/ by the value of the /
loop control variable/ from the outer loop. This means the incrementing in the /
afterthought/ expression will be based on a variable.
Your output should look something like this:**

using System;

class CountingByIncrements
{
    static void Main()
    {
        // Outer loop determines the increment (1,2,3,4)
        for (int outer = 1; outer <= 4; outer++)
        {
            // Inner loop counts from 0 to 24 by 'outer'
            for (int inner = 0; inner <= 24; inner += outer)
            {
                Console.Write(inner);

                if (inner + outer <= 24) // comma except after last number
                    Console.Write(",");
            }

            Console.WriteLine(); // move to next line for next increment
        }
    }
}


How it works:
Outer loop (outer) → determines the increment (1, 2, 3, 4).
Inner loop (inner) → counts from 0 to 24, incrementing by outer each time.
Console.Write(inner) prints the number, and commas are added except after the last number.
Console.WriteLine() moves to the next line for the next increment series.

**C# Operators**
Symbols that perform operations on variables or values, such as arithmetic, comparison, or logical operations.

 **Bitwise and Shift Operators**

Operators that work on the binary representation of numbers, including bitwise (&, |, ^, ~) and shift operators (<<, >>).

**Statement Keywords**

Keywords that control the flow of execution in a program, like return, break, and continue.

**Casting and Type Conversions**

Changing a variable from one data type to another, either implicitly (automatic) or explicitly (manual casting).

**Fundamentals of Garbage Collection**

Automatic memory management in .NET that frees memory of objects no longer in use.

**$ - String Interpolation**

A way to embed variables directly into strings using $ for cleaner, readable code.

**Formatting Types in .NET**

Customizing how values (numbers, dates, etc.) are displayed as strings.

**Iteration Statements**

Statements that repeat code multiple times, such as for, while, do-while, and foreach.

**Selection Statements**

Statements that choose a path based on a condition, such as if, if-else, or switch.



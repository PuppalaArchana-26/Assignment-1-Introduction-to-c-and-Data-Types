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

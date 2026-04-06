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
  

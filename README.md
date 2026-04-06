# Assignment-1-Introduction-to-c-and-Data-Types
# Assignment: Choosing Appropriate Data Types
## Question
What type would you choose for the following numbers?

## Answer

In a database, choosing the correct data type is important to store data properly and avoid errors. Below are the suitable data types with examples:

- **Telephone Number** → VARCHAR  
  Example: 555-123-4567  
  Telephone numbers are stored as text because they may contain symbols like dashes and are not used for calculations.

- **Height** → DECIMAL  
  Example: 5.9 or 175.5  
  Height can include decimal values, so a decimal type is suitable.

- **Age** → INT  
  Example: 27  
  Age is always a whole number.

- **Gender** → ENUM or VARCHAR  
  Example: Female  
  Gender has a limited set of values, so it can be stored as text.

- **Salary** → DECIMAL  
  Example: 50000.75  
  Salary requires accuracy, especially for decimal values.

- **ISBN** → VARCHAR  
  Example: 978-3-16-148410-0  
  ISBN contains dashes and is not used in calculations.

- **Book Price** → DECIMAL  
  Example: 19.99  
  Prices need exact precision for currency values.

- **Shipping Weight** → DECIMAL  
  Example: 1.25  
  Weight can have fractional values.

- **Country Population** → BIGINT  
  Example: 1400000000  
  Population numbers can be very large.

- **Number of Stars in the Universe** → BIGINT  
  Example: 1000000000000000000  
  This represents extremely large values.

- **Number of Employees (up to 50,000)** → INT  
  Example: 1250  
  This value is within the range of integer numbers.

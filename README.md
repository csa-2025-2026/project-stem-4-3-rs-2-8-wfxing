# unit-4-3-assignment

## Git Config
```
git config user.name "user"
git config user.email "email"
```

## Compiling and Running Java Programs
Note that since the shape classes are separate classes, you will need to compile ALL the files (at least one time).  You can do this by running
```
javac *.java
```
The star means to compile every file that is a Java file type.

Run your code by running
```
java Main.java
```

After you compile the shape classes, you only need to compile and run `Main.java` as usual.

# Instructions  

## Problem 1
Use a for loop to print the odd numbers between 1 and 25 inclusive.

## Problem 2
Use a for loop to print all of the numbers from 17 to 73 (inclusive) with 10 numbers on each line (the last line will have less than 10 numbers). Print one space between each number.

Hint - think about what values would be at the end of each line and what they have in common (think about modular division). You can then add an if block inside your loop which prints a new line when one of these numbers is encountered.

## Problem 3
Input an int between 0 and 50 and print the numbers between it and 50, including the number itself and the number 50. If the number is less than or equal to 0, or greater than or equal to 50, print "error". Print 5 numbers per line. The last line may or may not have 5 numbers.

Hint - use modular division to determine where you need to add a line break.

Sample Run 1:
```
Enter a number between 0 and 50:
23
23 24 25 26 27 
28 29 30 31 32 
33 34 35 36 37 
38 39 40 41 42 
43 44 45 46 47 
48 49 50
```
Sample Run 2:
```
Enter a number between 0 and 50:
-2
error
```

## Problem 4
Input an int greater than 0 and print every multiple of 3 between it and 0 inclusive in descending order. If the number is not greater than 0 print "error". Print all numbers on one line with single spaces in between.

Hint - use modular division to determine which numbers to print (you could check each number or just find the nearest multiple of 3 below/equal to the input and proceed from there).

Sample Run 1:
```
Enter a positive integer:
25
24 21 18 15 12 9 6 3 0 
```
Sample Run 2:
```
Enter a positive integer:
-2
error
```

## Sample Solutions
```java
// Problem 1
for (int i = 1; i <= 25; i+=2)
{
  System.out.println(i);
}

// Problem 2
for (int i = 17; i <= 73; i++)
{
  System.out.print(i + " ");

  if (i % 10 == 6)
  {
    System.out.println();
  }
}

// Problem 3
Scanner sc = new Scanner(System.in);
int n;

System.out.println("Enter a number between 0 and 50:");
n = sc.nextInt();

if (!(0 <= n && n <= 50))
{
  System.out.println("error");
}
else
{
  for (int i = n; i <= 50; i++)
  {
    System.out.print(i + " ");
    if (i % 5 == (n + 4) % 5)
    {
      System.out.println();
    }
  }
}

// Problem 4
Scanner sc = new Scanner(System.in);
int n;

System.out.println("Enter a positive integer:");
n = sc.nextInt();
if (n > 0)
{
  // Optional - decrease n to the nearest multiple of 3
  n -= (n % 3);	// Equivalent to n = n - (n % 3)

  for (int i = n; i >= 0; i -= 3)
  {
    System.out.print(i + " ");
  }
}
else
{
  System.out.println("error");
}
```

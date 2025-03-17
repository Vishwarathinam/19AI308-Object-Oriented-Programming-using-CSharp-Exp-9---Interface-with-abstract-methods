# 19AI308-Object-Oriented-Programming-using-CSharp-Exp-9---Interface-with-abstract-methods
## AIM:
To develop a small bank application by declaring deposit() and withdrawal() as abstract methods in the interface.

## ALGORITHM:
### Step 1:
Create an interface named bank

### Step 2:
Declare 2 functions deposit() and withdraw() as abstract methods in the interface.

### Step 3:
Create a class Operations as a Child class and inherit the bank

### Step 4:
Create another class Program and inside create the Main function

### Step 5:
Create an object for the operations class

### Step 6:
Get a Choice from the user for the operation to be performed. Using a switch implement the operations

### Step 7:
Using the Go-To statement you can rerun operations or close the session

### Step 8:
End of the Program

## PROGRAM:
```cs
using System;

namespace exp9
{
    public interface bank
    {
        public int deposit(int amt);
        public int withdraw(int amt);
    } 

    public class Operations : bank
    {
        public int amt, bal;
        
        public int deposit(int amt)
        {
            this.amt = amt;
            return this.bal + amt;
        }

        public int withdraw(int amt)
        {
            this.amt = amt;
            return this.bal - amt;
        }

        public void lines(int no)
        {
            for (int i = 0; i < no; i++)
            {
                Console.Write("-");
            }
            Console.WriteLine();
        }
    }

    public class Program
    {
        
        public static int Main(string[] args)
        {
            Operations op = new Operations();

            int choice,amt;
            
            Console.Write("Enter Intial Balance: ");
            op.bal = Convert.ToInt32(Console.ReadLine());
            op.lines(20);
            
            operations:
                Console.WriteLine("To Deposit Money - Enter 1");
                Console.WriteLine("To Withdraw Money - Enter 2");
                Console.WriteLine("To View Balance - Enter 3");
                op.lines(20);
                Console.Write("Enter a Number: ");
                choice = Convert.ToInt32(Console.ReadLine());
                op.lines(20);
                switch (choice)
                {
                    case 1:
                        Console.WriteLine("-----DEPOSIT-----");
                        Console.Write("Enter amount: ");
                        amt = Convert.ToInt32(Console.ReadLine());
                        op.bal = op.deposit(amt);
                        Console.WriteLine("New Balance: {0}", op.bal);
                        break;

                    case 2:
                        Console.WriteLine("-----WITHDRAW-----");
                        Console.Write("Enter amount: ");
                        amt = Convert.ToInt32(Console.ReadLine());
                        op.bal = op.withdraw(amt);
                        Console.WriteLine("New Balance: {0}", op.bal);
                        break;

                    case 3:
                        Console.WriteLine("-----BALANCE----");
                        Console.WriteLine("Balance: {0}", op.bal);
                        break;

                    default:
                        Console.WriteLine("Enter a Vaild Choice!!");
                        break;
                }
                op.lines(20);
                Console.WriteLine("Enter 1 to do more operation\nEnter 2 to close session");
                op.lines(20);
                Console.Write("Enter a Numer:");
                int more = Convert.ToInt32(Console.ReadLine());
                op.lines(20);
                if (more == 1)
                    goto operations;
                else
                {
                    Console.WriteLine("Thank You!!");
                    return 0;
                }
        }
    }
}
```

## OUTPUT:
![image](https://github.com/Ronick2005/19AI308-Object-Oriented-Programming-using-CSharp-Exp-9---Interface-with-abstract-methods/assets/83219341/0fd5d04e-5a08-4d7f-961d-4f3a50f7a1ca)

![image](https://github.com/Ronick2005/19AI308-Object-Oriented-Programming-using-CSharp-Exp-9---Interface-with-abstract-methods/assets/83219341/a1f90e34-5ecd-4f3f-b7f8-7209308a76b5)

## RESULT:
Thus, a C# program using the interface concept is written.

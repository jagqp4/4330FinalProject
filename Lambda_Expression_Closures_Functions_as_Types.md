# Java Lambda Expressions, Closures, or Functions as Types
* Lambda Expressions are a clearer way of representing a method interface using an expression.
* They also shorten the amount of code needed for declaring an anonymous inner class.
#### Key characteristics of a Lambda Expression:
* Optional Type Declaration
* Optional Parenthesis Encompassing Parameter
* Optional Curly-Braces
* Optional Return Keyword

#### Code Examples:
//with type declaration
MathOperation addition = (int a, int b) -> a + b;

//with out type declaration
MathOperation subtraction = (a, b) -> a - b;

//with return statement along with curly braces
MathOperation multiplication = (int a, int b) -> { return a * b; };


# C# Lambda Expressions, Closures, or Functions as Types
* A lambda expression is an anonymous function that you can use to create delegates or expression tree types.
* By using lambda expressions, you can write local functions that can be passed as arguments or returned as the value of function calls.
* To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator =>, and you put the expression or statement block on the other side.
* For example, the lambda expression x => x * x specifies a parameter that’s named x and returns the value of x squared.

#### Example Code:
delegate int del(int i);
static void Main(string[] args)
{
    del myDelegate = x => x * x;
    int j = myDelegate(5); //j = 25
}

* To create an Expression Tree Type:

#### Example Code:
using System.Linq.Expressions;
namespace ConsoleApplication1
{
    class Program
    {
        static void Main(string[] args)
        {
            Expression<del> myET = x => x * x;
        }
    }
}
* The => operator has the same precedence as assignment (=) and is right associative (see “Associativity” section of the Operators article).

#### Expression Lambdas:
* A lambda expression with an expression on the right side of the => operator is called an expression lambda. Expression lambdas are used extensively in the construction of Expression Trees. An expression lambda returns the result of the expression and takes the following basic form:
#### Code Example:
(input-parameters) => expression
              or
(int x, string s) => s.Length > x

#### Statement Lambdas:
* A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:
* (input-parameters) => { statement; }

#### Code Examples:
delegate void TestDelegate(string s);

                and

TestDelegate del = n => { string s = n + " World";
    Console.WriteLine(s); };

#### Async Lambdas:
* You can easily create lambda expressions and statements that incorporate asynchronous processing by using the async and await keywords.

#### Code Example:
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
    }

    private async void button1_Click(object sender, EventArgs e)
    {
        // ExampleMethodAsync returns a Task.
        await ExampleMethodAsync();
        textBox1.Text += "\r\nControl returned to Click event handler.\n";
    }

    async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}  

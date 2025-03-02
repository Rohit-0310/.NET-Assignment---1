### Practice Questions

## 1. OOPS Principles in C#

1. Define and provide an example of each OOPS principle in C#.

- `Encapsulation` => Encapsulation means hiding details inside a class there own class and only exposing necessary data.

```C#
class BankAccount
{
    private double balance = 500;
    public void Deposit(double amount)
    {
        if(amount > 0){
            balance += amount; ;
        }
    }
    public double GetBalance() { return balance; }
}
class Program
{
    static void Main()
    {
        BankAccount account  = new BankAccount();
        account.Deposit(400);
        Console.WriteLine(account.GetBalance());
    }
}
```

- `Inheritance` => Inheritance allows a class to inherit or use the property and method of another class.

```C#
class Animal
{
    public void makeSound()
    {
        Console.WriteLine("Animal is Makes Sound");
    }
}

class Dog : Animal
{
    public void Bark()
    {
        Console.WriteLine("Dog is Barking ");
    }
}

class Program
{
    static void Main()
    {
        Dog myDog = new Dog();
        myDog.makeSound();
        myDog.Bark();

    }
}
```

- `Polymorphism` => Polymorphism means one name, many forms. It allows methods to have different behaviors based on the object that is calling them.

```C#
class Animal
{
    public virtual void makeSound()
    {
        Console.WriteLine("Animal is Making Sound");
    }
}

class Dog : Animal
{
    public override void makeSound()
    {
        Console.WriteLine("Dog is Barking ");
    }
}

class Program
{
    static void Main()
    {
        Animal myAnimal = new Animal();
        myAnimal.makeSound();

        Dog myDog = new Dog();
        myDog.makeSound();

    }
}
```

- `Abstraction` => Hiding implementation details and exposing only necessary functionalities.

```C#
abstract class shape
{
    public abstract void Draw();
}
class Circle : shape
{
    public override void Draw()
    {
        Console.WriteLine("Circle Drawwww");
    }
}
class Program
{
    static void Main()
    {
        shape myShape = new Circle();
        myShape.Draw();
    }
}
```

2. Explain the difference between an abstract class and an interface.
   `abstract class hide implementation details, exposing only necessary parts while in inhwritance One class can inherit from another`

3. Implement method overriding and method overloading in C#.

**Method Overriding**
```C#
class Animal
{
    public virtual void makeSound()
    {
        Console.WriteLine("Animal is Making Sound");
    }
}

class Dog : Animal
{
    public override void makeSound()
    {
        Console.WriteLine("Dog is Barking ");
    }
}

class Program
{
    static void Main()
    {
        Animal myAnimal = new Animal();
        myAnimal.makeSound();

        Dog myDog = new Dog();
        myDog.makeSound();

    }
}
```
**Method Overloading**
```C#
class MathOperation
{
    public int Add(int x, int y)
    {
        return x + y;
    }
    public double Add(double x, double y)
    {
        return x + y;
    }
}
class Program
{
    static void Main()
    {
        MathOperation math = new MathOperation();
        Console.WriteLine(math.Add(2,5));
        Console.WriteLine(math.Add(4.3,6.5));
    }
}
```

4. Write a program to demonstrate multiple inheritance using interfaces.
```C#
interface Animal
{
    void MakeSound();
}
interface Pet
{
    void Play();
}
class Dog: Animal, Pet
{
    public void MakeSound()
    {
        Console.WriteLine("Making Sounddddd.......");
    }
    public void Play()
    {
        Console.WriteLine("Playingggggg......");
    }
}
class Program
{
    static void Main()
    {
        Dog myDog = new Dog();
        myDog.MakeSound();
        myDog.Play();
    }
}
```
5. Create a class hierarchy for a university system with students, faculty, and staff.



## 2. Collections in C#

1. Implement a program using a List to store employee details.
```C#
class Employee
{
    public int Id { get; set; }
    public string Name { get; set; }
    public int EmployeeAge { get; set; }

    public Employee( int id,string name, int age)
    {
        Id = id;
        Name = name;
        EmployeeAge = age;
    }
}
class Program
{
    static void Main()
    {
        List<Employee> employees = new List<Employee>
        {
            new Employee(1, "Alice", 34),
            new Employee(2, "Bob", 21),
        };

        employees.Add(new Employee(3, "Charlie", 43));
        employees.Add(new Employee(4, "Devid", 25));

        foreach (Employee emp in employees)
        {
            Console.WriteLine("Name - "+ emp.Name + " Age - "+ emp.EmployeeAge);
        }
        Console.WriteLine(employees);
    }
}
```
2. Demonstrate the use of Dictionary<TKey, TValue> with a real-world example.
```C#
class Program
{
    static void Main()
    {
        Dictionary<int, string> countryCode = new Dictionary<int, string> { };
        countryCode.Add(91, "India");
        countryCode.Add(1, "USA");
        countryCode.Add(54, "Argentina");
        countryCode.Add(977, "Nepal");

        foreach(KeyValuePair<int, string> code in countryCode)
        {
            Console.WriteLine("Country Code - " + "+" + code.Key + " Country Name - " + code.Value);

        }

    }
}
```
3. Implement a queue-based ticketing system.
4. Compare and contrast a Stack and a Queue.

### Stack `LIFO` => Last In, First Out
```C#
class Program
{
    static void Main()
    {
        Stack<int> stack = new Stack<int>();
        stack.Push(1);
        stack.Push(11);
        stack.Push(111);
        Console.WriteLine(stack.Pop());

    }
}
```

### Queue `FIFO` => First In, First Out
```C#
class Program
{
    static void Main()
    {
        Queue<int> stack = new Queue<int>();
        stack.Enqueue(1);
        stack.Enqueue(11);
        stack.Enqueue(111);
        Console.WriteLine(stack.Dequeue());

    }
}
```
5. Create a program to demonstrate LINQ operations on collections.
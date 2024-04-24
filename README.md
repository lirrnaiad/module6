# Module 6 Mastery Check

<details>
<summary><h2>Number 1</h2></summary>
  
## Question
Given this fragment,
```
class X {
   private int count;
}
```
<br>
Is the following fragment correct?
<br>

```
class Y {
  public static void main(String args[]) {
    X ob = new X();
    ob.count = 10;
  }
}
```
## Answer
No; a private member cannot be accessed outside of its class.
<br><br>

<strong>Extra Answer:</strong>
<br>
This fragment is incorrect because the instance variable "count" has an access specifier of private and cannot be accessed & modified outside of its own class.
<br>
<br>

</details>

<details>
<summary><h2>Number 2</h2></summary>
  
## Question
An access specifier must _______ a member's declaration.

## Answer
precede
<br>
</details>


<details>
<summary><h2>Number 3</h2></summary>
  
## Question
The complement of a queue is a stack. It uses first-in, last-out accessing and is often likened
to a stack of plates. The first plate put on the table is the last plate used. Create a stack class
called <strong>Stack</strong> that can hold characters. Call the methods that access the stack <strong>push()</strong> and
<strong>pop()</strong>. Allow the user to specify the size of the stack when it is created. Keep all other
members of the <strong>Stack</strong> class private. 
<br> <br>
(Hint: You can use the <strong>Queue</strong> class as a model; just
change the way that the data is accessed.)

## Answer
```
// Module Queue Class: https://gist.github.com/lirrnaiad/aaea654aef8139092a33217ab6d52cdb

public class Stack {
    private char stack[];
    private int top;

    // Constructor for stack with a given size
    public Stack(int size) {
        stack = new char[size];
        top = 0;
    }

    // Constructor for stack using an already existing stack
    public Stack(Stack toCopy) {
        top = toCopy.top;
        stack = new char[toCopy.stack.length];
        for (int i=0; i < top; i++) {
            stack[i] = toCopy.stack[i];
        }
    }

    // Constructor for stack using a char array
    public Stack(char[] a) {
        stack = new char[a.length];
        for (char c : a) {
            push(c);
        }
    }

    // Push char onto the stack
    public void push(char ch) {
        if(top == stack.length) {
            System.out.println("Stack is full.");
            return;
        }

        stack[top] = ch;
        top++;
    }

    // Pop char from the stack
    public char pop() {
        if(top == 0) {
            System.out.println("Stack is empty.");
            return (char) -1;
        }

        top--;
        return stack[top];
    }
}
```
<br>
Other answer (Generic Stack Implementation using Singly Linked List):
<br> https://gist.github.com/lirrnaiad/fdb577dd5d88b8b66cd5b91d149a55fb
</details>

<details>
<summary><h2>Number 4</h2></summary>
  
## Question
Given this class,
```
class Test {
  int a;
  Test(int i) { a = i; }
}
```
Write a method called <b>swap()</b> that exchanges the contents of the objects referred to by
two <b>Test</b> object references.
<br>

## Answer
```
void swap(Test obj1, Test obj2) {
  int temp;

  temp = obj1.a;
  obj1.a = obj2.a;
  obj2.a = temp;
}
```

</details>


<details>
<summary><h2>Number 5</h2></summary>
  
## Question
Is the following fragment correct?
```
class X {
  int meth(int a, int b) { ... }
  String meth(int a, int b) { ... }
}
```

## Answer
No. Overloaded methods can have different return types, but they do not play a role in overload
resolution. Overloaded methods must have different parameter lists.
</details>

<details>
<summary><h2>Number 6</h2></summary>
  
## Question
Write a recursive method that displays the contents of a string backwards.

## Answer
```
public class Backwards {
    private String str;

    public Backwards (String s) {
        str = s;
    }

    public void reverse(int index) {
        if (index != str.length() - 1) {
            reverse(index + 1);
        }

        System.out.println(str.charAt(index));
    }
}
```
</details>

<details>
<summary><h2>Number 7</h2></summary>
  
## Question
If all objects of a class need to share the same variable, how must you declare that variable?

## Answer
Shared variables are declared as <b>static</b>.
</details>


<details>
<summary><h2>Number 8</h2></summary>
  
## Question
Why might you need to use a static block?

## Answer
A <b>static</b> block is used to perform any initializations related to the class, before any objects are created.
</details>


<details>
<summary><h2>Number 9</h2></summary>
  
## Question
What is an inner class?

## Answer
An inner class is a nonstatic nested class.
</details>


<details>
<summary><h2>Number 10</h2></summary>
  
## Question
To make a member accessible by only other members of its class, what access specifier
must be used?

## Answer
<b>private</b>
</details>


<details>
<summary><h2>Number 11</h2></summary>
  
## Question
The name of a method plus its parameter list constitutes the method’s _________.

## Answer
signature
</details>


<details>
<summary><h2>Number 12</h2></summary>
  
## Question
An <b>int</b> argument is passed to a method by using call-by-__________.

## Answer
value
</details>


<details>
<summary><h2>Number 13</h2></summary>
  
## Question
Create a varargs method called <b>sum()</b> that sums the <b>int</b> values passed to it. Have it return
the result. Demonstrate its use.

## Answer
<b> Method </b>
```
public class SumIt {
    int sum(int ... n) {
        int sum = 0;
        for (int i = 0; i < n.length; i++) {
            sum += n[i];
        }

        return sum;
    }
}
```
<br>
<b> Demonstration </b>

```
public class Demo {
    public static void main(String[] args) {
        SumIt sumObj = new SumIt();

        int total = sumObj.sum(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);
        System.out.println("Sum: " + total);
    }
}
```
</details>


<details>
<summary><h2>Number 14</h2></summary>
  
## Question
Can a varargs method be overloaded?

## Answer
Yes.
</details>


<details>
<summary><h2>Number 15</h2></summary>
  
## Question
Show an example of an overloaded varargs method that is ambiguous.



## Answer
```
int varargsMethod (int ... v) {}

int varargsMethod (int d, int ... v) {}
```

If we try to call varargsMethod() with one argument, like this,
```
varArgsMethod(5);
```
the compiler can’t determine which version of the method to invoke.
</details>

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
<strong>Module Answer:</strong>
<br>
No; a private member cannot be accessed outside of its class.
<br>

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

<strong>Answer:</strong>
<br>
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

<strong>Module Answer:</strong>
<br>
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

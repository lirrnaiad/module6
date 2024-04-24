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
<strong>Answer:</strong>
<br>
This fragment is incorrect because the instance variable "count" has an access specifier of private and cannot be accessed & modified outside of its own class.
<br>
<br>
<strong>Module Answer:</strong>
<br>
No; a private member cannot be accessed outside of its class.
<br>

listing 1
// Demonstrate if-else-if statements.
class IfElse {
  public static void main(String args[]) {
    int month = 4; // April
    String season;

    if(month == 12 || month == 1 || month == 2) 
      season = "Winter";
    else if(month == 3 || month == 4 || month == 5)
      season = "Spring";
    else if(month == 6 || month == 7 || month == 8)
      season = "Summer";
    else if(month == 9 || month == 10 || month == 11)
      season = "Autumn";
    else 
      season = "Bogus Month";

    System.out.println("April is in the " + season + ".");
  }
}

listing 2
// A simple example of the switch.
class SampleSwitch {
  public static void main(String args[]) {
    for(int i=0; i<6; i++)
      switch(i) {
        case 0:
          System.out.println("i is zero.");
          break;
        case 1:
          System.out.println("i is one.");
          break;
        case 2:
          System.out.println("i is two.");
          break;
        case 3:
          System.out.println("i is three.");
          break;
        default:
          System.out.println("i is greater than 3.");
      }
  }
}

listing 3
// In a switch, break statements are optional.
class MissingBreak {
  public static void main(String args[]) {
    for(int i=0; i<12; i++)
      switch(i) {
        case 0:
        case 1:
        case 2:
        case 3:
        case 4:
          System.out.println("i is less than 5");
          break;
        case 5:
        case 6:
        case 7:
        case 8:
        case 9:
          System.out.println("i is less than 10");
          break;
        default:
          System.out.println("i is 10 or more.");
      }
  }
}

listing 4
// An improved version of the season program.
class Switch {
  public static void main(String args[]) {
    int month = 4;
    String season;

    switch (month) {
      case 12: 
      case 1: 
      case 2:
        season = "Winter";
        break;
      case 3: 
      case 4: 
      case 5:
        season = "Spring";
        break;
      case 6: 
      case 7: 
      case 8:
        season = "Summer";
        break;
      case 9: 
      case 10: 
      case 11:
        season = "Autumn";
        break;
      default:
        season = "Bogus Month";
    }
    System.out.println("April is in the " + season + ".");
  }
}

listing 5
// Use a string to control a switch statement.

class StringSwitch {
  public static void main(String args[]) {

    String str = "two";

    switch(str) {
      case "one":
        System.out.println("one");
        break;
      case "two": 
        System.out.println("two");
        break;
      case "three":
        System.out.println("three");
        break;
      default: 
        System.out.println("no match");
        break;
    }
  }
}


listing 6
// Demonstrate the while loop.
class While {
  public static void main(String args[]) {
    int n = 10;

    while(n > 0) {
      System.out.println("tick " + n);
      n--;
    }
  }
}

listing 7
// The target of a loop can be empty. 
class NoBody {
  public static void main(String args[]) {
    int i, j;

    i = 100;
    j = 200;

    // find midpoint between i and j
    while(++i < --j) ; // no body in this loop

    System.out.println("Midpoint is " + i);
  }
}

listing 8
// Demonstrate the do-while loop.
class DoWhile {
  public static void main(String args[]) {
    int n = 10;

    do {
      System.out.println("tick " + n);
      n--;
    } while(n > 0);
  }
}

listing 9
// Using a do-while to process a menu selection -- a simple help system.
class Menu {
  public static void main(String args[]) 
    throws java.io.IOException {
    char choice;

    do {
      System.out.println("Help on:");
      System.out.println("  1. if");
      System.out.println("  2. switch");
      System.out.println("  3. while");
      System.out.println("  4. do-while");
      System.out.println("  5. for\n");
      System.out.println("Choose one:");
      choice = (char) System.in.read();
    } while( choice < '1' || choice > '5');

    System.out.println("\n");
 
    switch(choice) {
      case '1':
        System.out.println("The if:\n");
        System.out.println("if(condition) statement;");
        System.out.println("else statement;");
        break;
      case '2':
        System.out.println("The switch:\n");
        System.out.println("switch(expression) {");
        System.out.println("  case constant:");
        System.out.println("    statement sequence");
        System.out.println("  break;");
        System.out.println("  // ...");
        System.out.println("}");
        break;
      case '3':
        System.out.println("The while:\n");
        System.out.println("while(condition) statement;");
        break;
      case '4':
        System.out.println("The do-while:\n");
        System.out.println("do {");
        System.out.println("  statement;");
        System.out.println("} while (condition);");
        break;
      case '5':
        System.out.println("The for:\n");
        System.out.print("for(init; condition; iteration)");
        System.out.println(" statement;");
        break;
    }
  }
}

listing 10
// Demonstrate the for loop.
class ForTick {
  public static void main(String args[]) {
    int n;

    for(n=10; n>0; n--)
      System.out.println("tick " + n);
  }
}

listing 11
// Declare a loop control variable inside the for.
class ForTick {
  public static void main(String args[]) {

    // here, n is declared inside of the for loop
    for(int n=10; n>0; n--)
      System.out.println("tick " + n);
  }
}

listing 12
// Test for primes.
class FindPrime {
  public static void main(String args[]) {
    int num;
    boolean isPrime;

    num = 14; 

    if(num < 2) isPrime = false;
    else isPrime = true;

    for(int i=2; i <= num/i; i++) {
      if((num % i) == 0) {
        isPrime = false;
        break;
      }
    }

    if(isPrime) System.out.println("Prime");
    else System.out.println("Not Prime");
  }
}

listing 13
class Sample {
  public static void main(String args[]) {
    int a, b;

    b = 4;
    for(a=1; a<b; a++) {
      System.out.println("a = " + a);
      System.out.println("b = " + b);
      b--;
    }
  }
}

listing 14
// Using the comma.
class Comma {
  public static void main(String args[]) {
    int a, b;

    for(a=1, b=4; a<b; a++, b--) {
      System.out.println("a = " + a);
      System.out.println("b = " + b);
    }
  }
}

listing 15
// Parts of the for loop can be empty.
class ForVar {
  public static void main(String args[]) {
    int i;
    boolean done = false;

    i = 0;
    for( ; !done; ) {
      System.out.println("i is " + i);
      if(i == 10) done = true;
      i++;
    }
  }
}

listing 16
// Use a for-each style for loop. 
class ForEach {  
  public static void main(String args[]) {  
    int nums[] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };  
    int sum = 0;  
 
    // use for-each style for to display and sum the values 
    for(int x : nums) {  
      System.out.println("Value is: " + x); 
      sum += x;  
    }  
 
    System.out.println("Summation: " + sum); 
  }  
}

listing 17
// Use break with a for-each style for.   
class ForEach2 {  
  public static void main(String args[]) {  
    int sum = 0;  
    int nums[] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };  
 
    // use for to display and sum the values  
    for(int x : nums) {  
      System.out.println("Value is: " + x);  
      sum += x;  
      if(x == 5) break; // stop the loop when 5 is obtained  
    }  
    System.out.println("Summation of first 5 elements: " + sum);  
  }  
} 

listing 18
// The for-each loop is essentially read-only. 
class NoChange {   
  public static void main(String args[]) {   
    int nums[] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };   
  
    for(int x : nums) {   
      System.out.print(x + " ");  
      x = x * 10; // no effect on nums 
    }   
    
    System.out.println(); 
 
    for(int x : nums)  
      System.out.print(x + " ");  
 
    System.out.println(); 
  }   
}

listing 19
// Use for-each style for on a two-dimensional array.  
class ForEach3 {  
  public static void main(String args[]) {  
    int sum = 0;  
    int nums[][] = new int[3][5];  
  
    // give nums some values  
    for(int i = 0; i < 3; i++)   
      for(int j=0; j < 5; j++)  
        nums[i][j] = (i+1)*(j+1);  
  
    // use for-each for to display and sum the values  
    for(int x[] : nums) {  
      for(int y : x) { 
        System.out.println("Value is: " + y);  
        sum += y;  
      } 
    }  
    System.out.println("Summation: " + sum);  
  }  
}

listing 20
// Search an array using for-each style for.  
class Search {  
  public static void main(String args[]) {  
    int nums[] = { 6, 8, 3, 7, 5, 6, 1, 4 }; 
    int val = 5;  
    boolean found = false;  
 
    // use for-each style for to search nums for val  
    for(int x : nums) {  
      if(x == val) {  
        found = true;  
        break;  
      }  
    }  
  
    if(found)   
      System.out.println("Value found!");  
  }  
}

listing 21
// Loops may be nested.
class Nested {
  public static void main(String args[]) {
    int i, j;

    for(i=0; i<10; i++) {
      for(j=i; j<10; j++)
        System.out.print(".");
      System.out.println();
    }
  }
}

listing 22
// Using break to exit a loop. 
class BreakLoop {
  public static void main(String args[]) {
    for(int i=0; i<100; i++) {
      if(i == 10) break; // terminate loop if i is 10
      System.out.println("i: " + i);
    }
    System.out.println("Loop complete.");
  }
}

listing 23
// Using break to exit a while loop. 
class BreakLoop2 {
  public static void main(String args[]) {
    int i = 0;
    
    while(i < 100) {
      if(i == 10) break; // terminate loop if i is 10
      System.out.println("i: " + i);
      i++;
    }
    System.out.println("Loop complete.");
  }
}

listing 24
// Using break with nested loops.
class BreakLoop3 {
  public static void main(String args[]) {
    for(int i=0; i<3; i++) {
      System.out.print("Pass " + i + ": ");
      for(int j=0; j<100; j++) {
        if(j == 10) break; // terminate loop if j is 10
        System.out.print(j + " ");
      }
      System.out.println();
    }
    System.out.println("Loops complete.");
  }
}

listing 25
// Using break as a civilized form of goto. 
class Break {
  public static void main(String args[]) {
    boolean t = true;

    first: {
      second: {
        third: {
          System.out.println("Before the break.");
          if(t) break second; // break out of second block
          System.out.println("This won't execute");
        }
        System.out.println("This won't execute");
      }
      System.out.println("This is after second block.");
    }
  }
}

listing 26
// Using break to exit from nested loops
class BreakLoop4 {
  public static void main(String args[]) {
    outer: for(int i=0; i<3; i++) {
      System.out.print("Pass " + i + ": ");
      for(int j=0; j<100; j++) {
        if(j == 10) break outer; // exit both loops
        System.out.print(j + " ");
      }
      System.out.println("This will not print");
    }
    System.out.println("Loops complete.");
  }
}

listing 27
// This program contains an error.
class BreakErr {
  public static void main(String args[]) {

    one: for(int i=0; i<3; i++) {
      System.out.print("Pass " + i + ": ");
    }

    for(int j=0; j<100; j++) {
      if(j == 10) break one; // WRONG
      System.out.print(j + " ");
    }
  }
}

listing 28
// Demonstrate continue.
class Continue {
  public static void main(String args[]) {
    for(int i=0; i<10; i++) {
      System.out.print(i + " ");
      if (i%2 == 0) continue;
      System.out.println("");
    }
  }
}

listing 29
// Using continue with a label.
class ContinueLabel {
  public static void main(String args[]) {
outer: for (int i=0; i<10; i++) {
         for(int j=0; j<10; j++) {
           if(j > i) {
             System.out.println();
             continue outer;
           }
           System.out.print(" " + (i * j));
         }
       }
       System.out.println();
  }
}

listing 30
// Demonstrate return.
class Return {
  public static void main(String args[]) {
    boolean t = true;

    System.out.println("Before the return.");

    if(t) return; // return to caller

    System.out.println("This won't execute.");
  }
}


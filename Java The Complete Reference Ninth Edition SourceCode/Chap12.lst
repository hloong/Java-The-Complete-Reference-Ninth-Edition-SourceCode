listing 1
// An enumeration of apple varieties. 
enum Apple {  
  Jonathan, GoldenDel, RedDel, Winesap, Cortland 
} 
 
class EnumDemo { 
  public static void main(String args[])  
  { 
    Apple ap; 
 
    ap = Apple.RedDel; 
 
    // Output an enum value. 
    System.out.println("Value of ap: " + ap); 
    System.out.println(); 
 
    ap = Apple.GoldenDel; 
 
    // Compare two enum values. 
    if(ap == Apple.GoldenDel)  
      System.out.println("ap contains GoldenDel.\n"); 
 
    // Use an enum to control a switch statement. 
    switch(ap) { 
      case Jonathan: 
        System.out.println("Jonathan is red."); 
        break; 
      case GoldenDel: 
        System.out.println("Golden Delicious is yellow."); 
        break; 
      case RedDel:  
        System.out.println("Red Delicious is red."); 
        break; 
      case Winesap: 
        System.out.println("Winesap is red."); 
        break; 
      case Cortland: 
        System.out.println("Cortland is red."); 
        break; 
    } 
  } 
}

listing 2
// Use the built-in enumeration methods. 
 
// An enumeration of apple varieties. 
enum Apple {  
  Jonathan, GoldenDel, RedDel, Winesap, Cortland 
} 
 
class EnumDemo2 { 
  public static void main(String args[])  
  { 
    Apple ap; 
 
    System.out.println("Here are all Apple constants"); 
 
    // use values() 
    Apple allapples[] = Apple.values(); 
    for(Apple a : allapples) 
      System.out.println(a); 
 
    System.out.println(); 
    
    // use valueOf() 
    ap = Apple.valueOf("Winesap"); 
    System.out.println("ap contains " + ap); 
 
  } 
}

listing 3
// Use an enum constructor, instance variable, and method. 
enum Apple { 
  Jonathan(10), GoldenDel(9), RedDel(12), Winesap(15), Cortland(8); 
 
  private int price; // price of each apple 
 
  // Constructor 
  Apple(int p) { price = p; } 
 
  int getPrice() { return price; } 
} 
 
class EnumDemo3 { 
  public static void main(String args[])  
  { 
    Apple ap; 
 
    // Display price of Winesap. 
    System.out.println("Winesap costs " + 
                       Apple.Winesap.getPrice() + 
                       " cents.\n"); 
 
    // Display all apples and prices. 
    System.out.println("All apple prices:"); 
    for(Apple a : Apple.values()) 
      System.out.println(a + " costs " + a.getPrice() + 
                         " cents."); 
  } 
}


listing 4
// Use an enum constructor. 
enum Apple { 
  Jonathan(10), GoldenDel(9), RedDel, Winesap(15), Cortland(8); 
 
  private int price; // price of each apple 
 
  // Constructor 
  Apple(int p) { price = p; } 
 
  // Overloaded constructor 
  Apple() { price = -1; } 
 
  int getPrice() { return price; } 
}

listing 5
// Demonstrate ordinal(), compareTo(), and equals(). 
 
// An enumeration of apple varieties. 
enum Apple {  
  Jonathan, GoldenDel, RedDel, Winesap, Cortland 
} 
 
class EnumDemo4 { 
  public static void main(String args[])  
  { 
    Apple ap, ap2, ap3; 
 
    // Obtain all ordinal values using ordinal(). 
    System.out.println("Here are all apple constants" + 
                       " and their ordinal values: "); 
    for(Apple a : Apple.values()) 
      System.out.println(a + " " + a.ordinal()); 
 
    ap =  Apple.RedDel; 
    ap2 = Apple.GoldenDel; 
    ap3 = Apple.RedDel; 
 
    System.out.println(); 
 
    // Demonstrate compareTo() and equals() 
    if(ap.compareTo(ap2) < 0) 
      System.out.println(ap + " comes before " + ap2); 
 
    if(ap.compareTo(ap2) > 0) 
      System.out.println(ap2 + " comes before " + ap); 
 
    if(ap.compareTo(ap3) == 0) 
      System.out.println(ap + " equals " + ap3); 
   
    System.out.println(); 
 
    if(ap.equals(ap2)) 
      System.out.println("Error!"); 
 
    if(ap.equals(ap3)) 
      System.out.println(ap + " equals " + ap3); 
 
    if(ap == ap3) 
      System.out.println(ap + " == " + ap3); 
 
  } 
}

listing 6
// An improved version of the "Descision Maker" 
// program from Chapter 9. This version uses an 
// enum, rather than interface variables, to  
// represent the answers. 
 
import java.util.Random; 
 
// An enumeration of the possible answers. 
enum Answers { 
  NO, YES, MAYBE, LATER, SOON, NEVER 
} 
 
class Question { 
  Random rand = new Random(); 
  Answers ask() { 
    int prob = (int) (100 * rand.nextDouble()); 
 
    if (prob < 15) 
      return Answers.MAYBE; // 15% 
    else if (prob < 30) 
      return Answers.NO;    // 15% 
    else if (prob < 60) 
      return Answers.YES;   // 30% 
    else if (prob < 75) 
      return Answers.LATER; // 15% 
    else if (prob < 98) 
      return Answers.SOON;  // 13% 
    else 
      return Answers.NEVER; // 2% 
  } 
} 
 
class AskMe { 
  static void answer(Answers result) { 
    switch(result) { 
      case NO: 
        System.out.println("No"); 
        break; 
      case YES: 
        System.out.println("Yes"); 
        break; 
      case MAYBE: 
        System.out.println("Maybe"); 
        break; 
      case LATER: 
        System.out.println("Later"); 
        break; 
      case SOON: 
        System.out.println("Soon"); 
        break; 
      case NEVER: 
        System.out.println("Never"); 
        break; 
    } 
  } 
 
  public static void main(String args[]) { 
    Question q = new Question(); 
    answer(q.ask()); 
    answer(q.ask()); 
    answer(q.ask()); 
    answer(q.ask()); 
  } 
}

listing 7
// Demonstrate a type wrapper. 
class Wrap { 
  public static void main(String args[]) { 
     
    Integer iOb = new Integer(100);  
 
    int i = iOb.intValue(); 
 
    System.out.println(i + " " + iOb); // displays 100 100 
  } 
}

listing 8
// Demonstrate a autoboxing/unboxing. 
class AutoBox { 
  public static void main(String args[]) { 
     
    Integer iOb = 100; // autobox an int 
 
    int i = iOb; // auto-unbox 
 
    System.out.println(i + " " + iOb);  // displays 100 100 
  } 
}

listing 9
// Autoboxing/unboxing takes place with 
// method parameters and return values. 
 
class AutoBox2 { 
  // Take an Integer parameter and return 
  // an int value; 
  static int m(Integer v) { 
    return v ; // auto-unbox to int 
  }  
 
  public static void main(String args[]) {     
    // Pass an int to m() and assign the return value 
    // to an Integer.  Here, the argument 100 is autoboxed 
    // into an Integer.  The return value is also autoboxed 
    // into an Integer. 
    Integer iOb = m(100);  
 
    System.out.println(iOb); 
  } 
}


listing 10
// Autoboxing/unboxing occurs inside expressions. 
 
class AutoBox3 { 
  public static void main(String args[]) { 
     
    Integer iOb, iOb2; 
    int i; 
 
    iOb = 100; 
    System.out.println("Original value of iOb: " + iOb); 
 
    // The following automatically unboxes iOb, 
    // performs the increment, and then reboxes 
    // the result back into iOb. 
    ++iOb; 
    System.out.println("After ++iOb: " + iOb); 
 
    // Here, iOb is unboxed, the expression is  
    // evaluated, and the result is reboxed and 
    // assigned to iOb2. 
    iOb2 = iOb + (iOb / 3); 
    System.out.println("iOb2 after expression: " + iOb2); 
 
    // The same expression is evaluated, but the 
    // result is not reboxed. 
    i = iOb + (iOb / 3); 
    System.out.println("i after expression: " + i); 
 
  } 
}

listing 11
class AutoBox4 { 
  public static void main(String args[]) { 
     
    Integer iOb = 100;; 
    Double dOb = 98.6; 
 
 
    dOb = dOb + iOb; 
    System.out.println("dOb after expression: " + dOb); 
  } 
}

listing 12
// Autoboxing/unboxing a Boolean and Character. 
 
class AutoBox5 { 
  public static void main(String args[]) { 
    
    // Autobox/unbox a boolean. 
    Boolean b = true; 
 
    // Below, b is auto-unboxed when used in  
    // a conditional expression, such as an if. 
    if(b) System.out.println("b is true"); 
 
    // Autobox/unbox a char. 
    Character ch = 'x'; // box a char 
    char ch2 = ch; // unbox a char 
 
    System.out.println("ch2 is " + ch2); 
  } 
}

listing 13
// An error produced by manual unboxing. 
class UnboxingError {  
  public static void main(String args[]) {  
      
    Integer iOb = 1000; // autobox the value 1000 
  
    int i = iOb.byteValue(); // manually unbox as byte !!! 
  
    System.out.println(i);  // does not display 1000 ! 
  }  
}

listing 14
import java.lang.annotation.*; 
import java.lang.reflect.*; 
 
// An annotation type declaration. 
@Retention(RetentionPolicy.RUNTIME)  
@interface MyAnno { 
  String str(); 
  int val(); 
} 
 
class Meta { 
 
  // Annotate a method. 
  @MyAnno(str = "Annotation Example", val = 100) 
  public static void myMeth() { 
    Meta ob = new Meta(); 
 
    // Obtain the annotation for this method 
    // and display the values of the members. 
    try { 
      // First, get a Class object that represents 
      // this class. 
      Class<?> c = ob.getClass(); 
 
      // Now, get a Method object that represents 
      // this method. 
      Method m = c.getMethod("myMeth"); 
 
      // Next, get the annotation for this class. 
      MyAnno anno = m.getAnnotation(MyAnno.class); 
  
      // Finally, display the values. 
      System.out.println(anno.str() + " " + anno.val()); 
    } catch (NoSuchMethodException exc) { 
       System.out.println("Method Not Found."); 
    } 
  } 
 
  public static void main(String args[]) { 
    myMeth(); 
  } 
}

listing 15
import java.lang.annotation.*; 
import java.lang.reflect.*; 
 
@Retention(RetentionPolicy.RUNTIME)  
@interface MyAnno { 
  String str(); 
  int val(); 
} 
 
class Meta { 
 
  // myMeth now has two arguments. 
  @MyAnno(str = "Two Parameters", val = 19) 
  public static void myMeth(String str, int i)  
  { 
    Meta ob = new Meta(); 
 
    try { 
      Class<?> c = ob.getClass(); 
 
      // Here, the parameter types are specified. 
      Method m = c.getMethod("myMeth", String.class, int.class); 
 
      MyAnno anno = m.getAnnotation(MyAnno.class); 
  
      System.out.println(anno.str() + " " + anno.val()); 
    } catch (NoSuchMethodException exc) { 
       System.out.println("Method Not Found."); 
    } 
  } 
 
  public static void main(String args[]) { 
    myMeth("test", 10); 
  } 
}

listing 16
// Show all annotations for a class and a method. 
import java.lang.annotation.*; 
import java.lang.reflect.*; 
 
@Retention(RetentionPolicy.RUNTIME)  
@interface MyAnno { 
  String str(); 
  int val(); 
} 
 
@Retention(RetentionPolicy.RUNTIME)  
@interface What { 
  String description(); 
} 
 
@What(description = "An annotation test class") 
@MyAnno(str = "Meta2", val = 99) 
class Meta2 { 
 
  @What(description = "An annotation test method") 
  @MyAnno(str = "Testing", val = 100) 
  public static void myMeth() { 
    Meta2 ob = new Meta2(); 
 
    try { 
      Annotation annos[] = ob.getClass().getAnnotations(); 
 
      // Display all annotations for Meta2. 
      System.out.println("All annotations for Meta2:"); 
      for(Annotation a : annos) 
        System.out.println(a); 
 
      System.out.println(); 
 
      // Display all annotations for myMeth. 
      Method m = ob.getClass( ).getMethod("myMeth"); 
      annos = m.getAnnotations();  
 
      System.out.println("All annotations for myMeth:"); 
      for(Annotation a : annos) 
        System.out.println(a); 
 
    } catch (NoSuchMethodException exc) { 
       System.out.println("Method Not Found."); 
    } 
  } 
 
  public static void main(String args[]) { 
    myMeth(); 
  } 
}

listing 17
import java.lang.annotation.*; 
import java.lang.reflect.*; 
 
// An annotation type declaration that includes defaults. 
@Retention(RetentionPolicy.RUNTIME)  
@interface MyAnno { 
  String str() default "Testing"; 
  int val() default 9000; 
} 
 
class Meta3 { 
 
  // Annotate a method using the default values. 
  @MyAnno() 
  public static void myMeth() { 
    Meta3 ob = new Meta3(); 
 
    // Obtain the annotation for this method 
    // and display the values of the members. 
    try { 
      Class<?> c = ob.getClass(); 
 
      Method m = c.getMethod("myMeth"); 
 
      MyAnno anno = m.getAnnotation(MyAnno.class); 
  
      System.out.println(anno.str() + " " + anno.val()); 
    } catch (NoSuchMethodException exc) { 
       System.out.println("Method Not Found."); 
    } 
  } 
 
  public static void main(String args[]) { 
    myMeth(); 
  } 
}

listing 18
import java.lang.annotation.*; 
import java.lang.reflect.*; 
 
// A marker annotation. 
@Retention(RetentionPolicy.RUNTIME)  
@interface MyMarker { } 
 
class Marker { 
 
  // Annotate a method using a marker. 
  // Notice that no ( ) is needed. 
  @MyMarker 
  public static void myMeth() { 
    Marker ob = new Marker(); 
 
    try { 
      Method m = ob.getClass().getMethod("myMeth"); 
 
      // Determine if the annotation is present. 
      if(m.isAnnotationPresent(MyMarker.class)) 
        System.out.println("MyMarker is present.");  
 
    } catch (NoSuchMethodException exc) { 
       System.out.println("Method Not Found."); 
    } 
  } 
 
  public static void main(String args[]) { 
    myMeth(); 
  } 
}

listing 19
import java.lang.annotation.*; 
import java.lang.reflect.*; 
 
// A single-member annotation. 
@Retention(RetentionPolicy.RUNTIME)  
@interface MySingle { 
  int value(); // this variable name must be value 
} 
 
class Single { 
 
  // Annotate a method using a marker. 
  @MySingle(100) 
  public static void myMeth() { 
    Single ob = new Single(); 
 
    try { 
      Method m = ob.getClass().getMethod("myMeth"); 
 
      MySingle anno = m.getAnnotation(MySingle.class); 
 
      System.out.println(anno.value()); // displays 100 
 
    } catch (NoSuchMethodException exc) { 
       System.out.println("Method Not Found."); 
    } 
  } 
 
  public static void main(String args[]) { 
    myMeth(); 
  } 
}

listing 20
// Demonstrate several type annotations. 
import java.lang.annotation.*;  
import java.lang.reflect.*;  
 
// A marker annotation that can be applied to a type. 
@Target(ElementType.TYPE_USE) 
@interface TypeAnno { } 
 
// Another marker annotation that can be applied to a type.  
@Target(ElementType.TYPE_USE) 
@interface NotZeroLen {  
}  
 
// Still another marker annotation that can be applied to a type. 
@Target( ElementType.TYPE_USE ) 
@interface Unique { } 
 
// A parameterized annotation that can be applied to a type. 
@Target(ElementType.TYPE_USE) 
@interface MaxLen {  
  int value(); 
}  
 
// An annotation that can be applied to a type parameter. 
@Target(ElementType.TYPE_PARAMETER) 
@interface What {  
  String description();  
}  
 
// An annotation that can be applied to a field declaration. 
@Target(ElementType.FIELD) 
@interface EmptyOK { } 
 
// An annotation that can be applied to a method declaration. 
@Target(ElementType.METHOD) 
@interface Recommended { } 
 
 
// Use an annotation on a type parameter.  
class TypeAnnoDemo<@What(description = "Generic data type") T> {  
 
  // Use a type annotation on a constructor. 
  public @Unique TypeAnnoDemo() {}  
  
  // Annotate the type (in this case String), not the field. 
  @TypeAnno String str; 
 
  // This annotates the field test. 
  @EmptyOK String test; 
 
  // Use a type annotation to annotate this (the receiver). 
  public int f(@TypeAnno TypeAnnoDemo<T> this, int x) { 
    return 10; 
  }   
 
  // Annotate the return type. 
  public @TypeAnno Integer f2(int j, int k) { 
    return j+k; 
  } 
 
  // Annotate the method declaration. 
  public @Recommended Integer f3(String str) { 
    return str.length() / 2; 
  } 
 
  // Use a type annotation with a throws clause. 
  public void f4() throws @TypeAnno NullPointerException { 
    // ... 
  } 
 
  // Annotate array levels. 
  String @MaxLen(10) [] @NotZeroLen [] w; 
 
  // Annotate the array element type. 
  @TypeAnno Integer[] vec; 
 
  public static void myMeth(int i) {  
 
    // Use a type annotation on a type argument. 
    TypeAnnoDemo<@TypeAnno Integer> ob = 
                             new TypeAnnoDemo<@TypeAnno Integer>();  
 
    // Use a type annotation with new. 
    @Unique TypeAnnoDemo<Integer> ob2 = new @Unique TypeAnnoDemo<Integer>(); 
 
    Object x = new Integer(10); 
    Integer y; 
 
    // Use a type annotation on a cast. 
    y = (@TypeAnno Integer) x; 
  } 
  
  public static void main(String args[]) {  
    myMeth(10);  
  }  
 
  // Use type annotation with inheritance clause. 
  class SomeClass extends @TypeAnno TypeAnnoDemo<Boolean> {} 
}

listing 21
// Demonstrate a repeated annotation.

import java.lang.annotation.*; 
import java.lang.reflect.*; 

// Make MyAnno repeatable
@Retention(RetentionPolicy.RUNTIME)  
@Repeatable(MyRepeatedAnnos.class)
@interface MyAnno { 
  String str() default "Testing"; 
  int val() default 9000; 
} 

// This is the container annotation.
@Retention(RetentionPolicy.RUNTIME)  
@interface MyRepeatedAnnos { 
  MyAnno[] value(); 
} 
 
class RepeatAnno { 
 
  // Repeat MyAnno on myMeth().
  @MyAnno(str = "First annotation", val = -1) 
  @MyAnno(str = "Second annotation", val = 100) 
  public static void myMeth(String str, int i)  
  { 
    RepeatAnno ob = new RepeatAnno(); 
 
    try { 
      Class<?> c = ob.getClass(); 
 
      // Obtain the annotations for myMeth(). 
      Method m = c.getMethod("myMeth", String.class, int.class); 
 
      // Display the repeated MyAnno annotations. 
      Annotation anno = m.getAnnotation(MyRepeatedAnnos.class);  
      System.out.println(anno); 

    } catch (NoSuchMethodException exc) { 
       System.out.println("Method Not Found."); 
    } 
  } 
 
  public static void main(String args[]) { 
    myMeth("test", 10); 
  } 
}

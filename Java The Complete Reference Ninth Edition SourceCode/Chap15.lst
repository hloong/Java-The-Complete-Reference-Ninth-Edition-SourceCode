listing 1
// Demonstrate a simple lambda expression. 
 
// A functional interface. 
interface MyNumber { 
  double getValue();  
} 
 
class LambdaDemo { 
  public static void main(String args[]) 
  { 
    MyNumber myNum;  // declare an interface reference 
 
    // Here, the lambda expression is simply a constant expression. 
    // When it is assigned to myNum, a class instance is 
    // constructed in which the lambda expression provides an override 
    // of the getValue() method in MyNumber. 
    myNum = () -> 123.45; 
 
    // Call getValue(), which is overridden by the previously assigned 
    // lambda expression. 
    System.out.println("A fixed value: " + myNum.getValue()); 
 
    // Here, a more complex expression is used. 
    myNum = () -> Math.random() * 100; 
 
    // These call the lambda expression in the previous line. 
    System.out.println("A random value: " + myNum.getValue()); 
    System.out.println("Another random value: " + myNum.getValue()); 
 
    // A lambda expression must be compatible with the method 
    // defined by the functional interface. Therefore, this won't work: 
//  myNum = () -> "123.03"; // Error! 
  } 
}

listing 2
// Demonstrate a lambda expression that takes a parameter. 
 
// Another functional interface. 
interface NumericTest { 
 boolean test(int n);  
} 
 
class LambdaDemo2 { 
  public static void main(String args[]) 
  { 
    // A lambda expression that tests if a number is even. 
    NumericTest isEven = (n) -> (n % 2)==0; 
 
    if(isEven.test(10)) System.out.println("10 is even"); 
    if(!isEven.test(9)) System.out.println("9 is not even"); 
 
    // Now, use a lambda expression that tests if a number 
    // is non-negative. 
    NumericTest isNonNeg = (n) -> n >= 0; 
 
    if(isNonNeg.test(1)) System.out.println("1 is non-negative"); 
    if(!isNonNeg.test(-1)) System.out.println("-1 is negative"); 
  } 
}

listing 3
// Demonstrate a lambda expression that takes two parameters. 
 
interface NumericTest2 { 
  boolean test(int n, int d); 
} 
 
class LambdaDemo3 { 
  public static void main(String args[]) 
  { 
    // This lambda expression determines if one number is  
    // a factor of another. 
    NumericTest2 isFactor = (n, d) -> (n % d) == 0; 
 
    if(isFactor.test(10, 2)) 
      System.out.println("2 is a factor of 10"); 
 
    if(!isFactor.test(10, 3)) 
      System.out.println("3 is not a factor of 10");   
  } 
}

listing 4
// A block lambda that computes the factorial of an int value. 
 
interface NumericFunc { 
  int func(int n); 
} 
 
class BlockLambdaDemo { 
  public static void main(String args[]) 
  { 
 
    // This block lambda computes the factorial of an int value. 
    NumericFunc factorial = (n) ->  { 
      int result = 1; 
 
      for(int i=1; i <= n; i++) 
        result = i * result; 
 
      return result; 
    }; 
 
    System.out.println("The factoral of 3 is " + factorial.func(3)); 
    System.out.println("The factoral of 5 is " + factorial.func(5)); 
  } 
}

listing 5
// A block lambda that reverses the characters in a string. 
 
interface StringFunc { 
  String func(String n); 
} 
 
class BlockLambdaDemo2 { 
  public static void main(String args[]) 
  { 
 
    // This block lambda that reverses the charactrers in a string. 
    StringFunc reverse = (str) ->  { 
      String result = ""; 
      int i; 
 
      for(i = str.length()-1; i >= 0; i--) 
        result += str.charAt(i); 
 
      return result; 
    }; 
 
    System.out.println("Lambda reversed is " + 
                         reverse.func("Lambda")); 
    System.out.println("Expression reversed is " + 
                         reverse.func("Expression")); 
  } 
}

listing 6
// Use a generic functional interface with lambda expressions. 
 
// A generic functional interface. 
interface SomeFunc<T> { 
  T func(T t); 
} 
 
class GenericFunctionalInterfaceDemo { 
  public static void main(String args[]) 
  { 
 
    // Use a String-based version of SomeFunc. 
    SomeFunc<String> reverse = (str) ->  { 
      String result = ""; 
      int i; 
 
      for(i = str.length()-1; i >= 0; i--) 
        result += str.charAt(i); 
 
      return result; 
    }; 
 
    System.out.println("Lambda reversed is " + 
                       reverse.func("Lambda")); 
    System.out.println("Expression reversed is " + 
                       reverse.func("Expression")); 
 
    // Now, use an Integer-based version of SomeFunc. 
    SomeFunc<Integer> factorial = (n) ->  { 
      int result = 1; 
 
      for(int i=1; i <= n; i++) 
        result = i * result; 
 
      return result; 
    }; 
 
    System.out.println("The factoral of 3 is " + factorial.func(3)); 
    System.out.println("The factoral of 5 is " + factorial.func(5)); 
  } 
}

listing 7
// Use lambda expressions as an argument to a method. 
 
interface StringFunc { 
  String func(String n); 
} 
 
class LambdasAsArgumentsDemo { 
 
  // This method has a functional interface as the type of 
  // its first parameter. Thus, it can be passed a reference to 
  // any instance of that interface, including the instance created 
  // by a lambda expression. 
  // The second parameter specifies the string to operate on. 
  static String stringOp(StringFunc sf, String s) { 
    return sf.func(s); 
  } 
 
  public static void main(String args[]) 
  { 
    String inStr = "Lambdas add power to Java"; 
    String outStr; 
 
    System.out.println("Here is input string: " + inStr); 
 
    // Here, a simple expression lambda that uppercases a string 
    // is passed to stringOp( ). 
    outStr = stringOp((str) -> str.toUpperCase(), inStr); 
    System.out.println("The string in uppercase: " + outStr); 
 
    // This passes a block lambda that removes spaces. 
    outStr = stringOp((str) ->  { 
                       String result = ""; 
                       int i; 
 
                       for(i = 0; i < str.length(); i++) 
                       if(str.charAt(i) != ' ') 
                         result += str.charAt(i); 
 
                       return result; 
                     }, inStr); 
 
    System.out.println("The string with spaces removed: " + outStr); 
 
 
    // Of course, it is also possible to pass a StringFunc instance 
    // created by an earlier lambda expression. For example,  
    // after this declaration executes, reverse refers to a 
    // synthetic instance of StringFunc. 
    StringFunc reverse = (str) ->  { 
      String result = ""; 
      int i; 
 
      for(i = str.length()-1; i >= 0; i--) 
        result += str.charAt(i); 
 
      return result; 
    }; 
 
    // Now, reverse can be passed as the first parameter to stringOp() 
    // since it refers to a StringFunc object. 
    System.out.println("The string reversed: " + 
                       stringOp(reverse, inStr)); 
  } 
}

listing 8
// Throw an exception from a lambda expression. 
 
interface DoubleNumericArrayFunc { 
  double func(double[] n) throws EmptyArrayException; 
} 
 
class EmptyArrayException extends Exception { 
  EmptyArrayException() { 
    super("Array Empty"); 
  } 
} 
 
class LambdaExceptionDemo { 
 
  public static void main(String args[]) throws EmptyArrayException 
  { 
    double[] values  = { 1.0, 2.0, 3.0, 4.0 }; 
 
    // This block lambda computes the average of an array of doubles. 
    DoubleNumericArrayFunc average = (n) ->  { 
      double sum = 0; 
 
      if(n.length == 0) 
        throw new EmptyArrayException(); 
 
      for(int i=0; i < n.length; i++) 
        sum += n[i]; 
 
      return sum / n.length; 
    }; 
 
    System.out.println("The average is " + average.func(values)); 
 
    // This causes an exception to be thrown. 
    System.out.println("The average is " + average.func(new double[0])); 
  } 
}

listing 9
// An example of capturing a local variable from the enclosing scope. 
 
interface MyFunc { 
  int func(int n); 
} 
 
class VarCapture { 
  public static void main(String args[]) 
  { 
    // A local variable that can be captured. 
    int num = 10; 
 
    MyFunc myLambda = (n) ->  { 
      // This use of num is OK. It does not modify num. 
      int v = num + n; 
 
      // However, the following is illegal because it attempts  
      // to modify the value of num. 
//    num++; 
 
      return v; 
    }; 
 
    // The following line would also cause an error, because 
    // it would remove the effectively final status from num. 
//  num = 9; 
  } 
}

listing 10
// Demonstrate a method reference for a static method. 
 
// A functional interface for string operations. 
interface StringFunc { 
  String func(String n); 
} 
 
// This class defines a static method called strReverse(). 
class MyStringOps { 
  // A static method that reverses a string. 
  static String strReverse(String str) { 
      String result = ""; 
      int i; 
 
      for(i = str.length()-1; i >= 0; i--) 
        result += str.charAt(i); 
 
      return result; 
  } 
}     
 
class MethodRefDemo { 
 
  // This method has a functional interface as the type of 
  // its first parameter. Thus, it can be passed any instance 
  // of that interface, including a method reference. 
  static String stringOp(StringFunc sf, String s) { 
    return sf.func(s); 
  } 
 
  public static void main(String args[]) 
  { 
    String inStr = "Lambdas add power to Java"; 
    String outStr; 
 
    // Here, a method reference to strReverse is passed to stringOp(). 
    outStr = stringOp(MyStringOps::strReverse, inStr); 
 
    System.out.println("Original string: " + inStr); 
    System.out.println("String reversed: " + outStr); 
  } 
}

listing 11
// Demonstrate a method reference to an instance method 
 
// A functional interface for string operations. 
interface StringFunc { 
  String func(String n); 
} 
 
// Now, this class defines an instance method called strReverse(). 
class MyStringOps { 
  String strReverse(String str) { 
      String result = ""; 
      int i; 
 
      for(i = str.length()-1; i >= 0; i--) 
        result += str.charAt(i); 
 
      return result; 
  } 
}     
 
class MethodRefDemo2 { 
 
  // This method has a functional interface as the type of 
  // its first parameter. Thus, it can be passed any instance 
  // of that interface, including method references. 
  static String stringOp(StringFunc sf, String s) { 
    return sf.func(s); 
  } 
 
  public static void main(String args[]) 
  { 
    String inStr = "Lambdas add power to Java"; 
    String outStr; 
 
    // Create a MyStringOps object. 
    MyStringOps strOps = new MyStringOps( ); 
 
    // Now, a method reference to the instance method strReverse 
    // is passed to stringOp(). 
    outStr = stringOp(strOps::strReverse, inStr); 
 
    System.out.println("Original string: " + inStr); 
    System.out.println("String reversed: " + outStr); 
  } 
}

listing 12
// Use an instance method reference with different objects. 
 
// A functional interface that takes two reference arguments 
// and returns a boolean result. 
interface MyFunc<T> { 
  boolean func(T v1, T v2); 
} 
 
// A class that stores the temperature high for a day. 
class HighTemp { 
  private int hTemp; 
 
  HighTemp(int ht) { hTemp = ht; } 
 
  // Return true if the invoking HighTemp object has the same 
  // temperature as ht2. 
  boolean sameTemp(HighTemp ht2) { 
    return hTemp == ht2.hTemp; 
  } 
 
  // Return true if the invoking HighTemp object has a temperature 
  // that is less than ht2. 
  boolean lessThanTemp(HighTemp ht2) { 
    return hTemp < ht2.hTemp; 
  } 
} 
 
class InstanceMethWithObjectRefDemo { 
 
  // A method that returns the number of occurences 
  // of an object for which some criteria, as specified by 
  // the MyFunc parameter, is true. 
  static <T> int counter(T[] vals, MyFunc<T> f, T v) { 
    int count = 0; 
 
    for(int i=0; i < vals.length; i++) 
      if(f.func(vals[i], v)) count++; 
 
    return count;   
  } 
 
  public static void main(String args[]) 
  { 
    int count; 
 
    // Create an array of HighTemp objects. 
    HighTemp[] weekDayHighs = { new HighTemp(89), new HighTemp(82), 
                                new HighTemp(90), new HighTemp(89), 
                                new HighTemp(89), new HighTemp(91), 
                                new HighTemp(84), new HighTemp(83) }; 
 
    // Use counter() with arrays of the class HighTemp. 
    // Notice that a reference to the instance method 
    // sameTemp() is passed as the second argument. 
    count = counter(weekDayHighs, HighTemp::sameTemp, 
                  new HighTemp(89)); 
    System.out.println(count + " days had a high of 89"); 
 
    // Now, create and use another array of HighTemp objects. 
    HighTemp[] weekDayHighs2 = { new HighTemp(32), new HighTemp(12), 
                                new HighTemp(24), new HighTemp(19), 
                                new HighTemp(18), new HighTemp(12), 
                                new HighTemp(-1), new HighTemp(13) }; 
 
    count = counter(weekDayHighs2, HighTemp::sameTemp, 
                    new HighTemp(12)); 
    System.out.println(count + " days had a high of 12"); 
 
 
    // Now, use lessThanTemp() to find days when temperature was less 
    // that a specified value. 
    count = counter(weekDayHighs, HighTemp::lessThanTemp, 
                    new HighTemp(89)); 
    System.out.println(count + " days had a high less than 89"); 
 
    count = counter(weekDayHighs2, HighTemp::lessThanTemp, 
                    new HighTemp(19)); 
    System.out.println(count + " days had a high of less than 19"); 
  } 
}

listing 13
// Demonstrate a method reference to a generic method 
// declared inside a non-generic class. 
 
// A functional interface that operates on an array 
// and a value, and returns an int result. 
interface MyFunc<T> { 
  int func(T[] vals, T v); 
} 
 
// This class defines a method called countMatching() that 
// returns the number of items in an array that are equal  
// to a specified value. Notice that countMatching() 
// is generic, but MyArrayOps is not. 
class MyArrayOps { 
  static <T> int countMatching(T[] vals, T v) { 
    int count = 0; 
 
    for(int i=0; i < vals.length; i++) 
      if(vals[i] == v) count++; 
 
      return count; 
  } 
}     
 
class GenericMethodRefDemo { 
 
  // This method has the MyFunc functional interface as the 
  // type of its first parameter. The other two parameters 
  // receive an array and a value, both of type T. 
  static <T> int myOp(MyFunc<T> f, T[] vals, T v) { 
    return f.func(vals, v); 
  } 
 
  public static void main(String args[]) 
  { 
    Integer[] vals = { 1, 2, 3, 4, 2 ,3, 4, 4, 5 }; 
    String[] strs = { "One", "Two", "Three", "Two" }; 
    int count; 
 
    count = myOp(MyArrayOps::<Integer>countMatching, vals, 4); 
    System.out.println("vals contains " + count + " 4s"); 
 
    count = myOp(MyArrayOps::<String>countMatching, strs, "Two"); 
    System.out.println("strs contains " + count + " Twos"); 
  } 
}

listing 14
// Use a method reference to help find the maximum value in a collection. 
import java.util.*; 
 
class MyClass { 
  private int val; 
 
  MyClass(int v) { val = v; } 
 
  int getVal() { return val; } 
} 
 
class UseMethodRef { 
  // A compare() method compatible with the one defined by Comparator<T>. 
  static int compareMC(MyClass a, MyClass b) { 
    return a.getVal() - b.getVal(); 
  } 
 
  public static void main(String args[]) 
  { 
    ArrayList<MyClass> al = new ArrayList<MyClass>(); 
 
    al.add(new MyClass(1)); 
    al.add(new MyClass(4)); 
    al.add(new MyClass(2)); 
    al.add(new MyClass(9)); 
    al.add(new MyClass(3)); 
    al.add(new MyClass(7)); 
 
    // Find the maximum value in al using the compareMC() method. 
    MyClass maxValObj = Collections.max(al, UseMethodRef::compareMC); 
 
    System.out.println("Maximum value is: " + maxValObj.getVal()); 
  } 
}

listing 15
// Demonstrate a Constructor reference. 
 
// MyFunc is a functional interface whose method returns 
// a MyClass reference. 
interface MyFunc { 
   MyClass func(int n); 
} 
 
class MyClass { 
  private int val; 
 
  // This constructor takes an argument. 
  MyClass(int v) { val = v; } 
 
  // This is the default constructor. 
  MyClass() { val = 0; } 
 
  // ... 
 
  int getVal() { return val; };   
}     
 
class ConstructorRefDemo { 
  public static void main(String args[]) 
  { 
    // Create a reference to the MyClass constructor. 
    // Because func() in MyFunc takes an argument, new 
    // refers to the parameterized constructor in MyClass, 
    // not the default constructor. 
    MyFunc myClassCons = MyClass::new; 
 
    // Create an instance of MyClass via that constructor reference. 
    MyClass mc = myClassCons.func(100); 
 
    // Use the instance of MyClass just created. 
    System.out.println("val in mc is " + mc.getVal( )); 
  } 
}

listing 16
// Demonstrate a constructor reference with a generic class. 
 
// MyFunc is now a generic functional interface. 
interface MyFunc<T> { 
   MyClass<T> func(T n); 
} 
 
class MyClass<T> { 
  private T val; 
 
  // A constructor that takes an argument. 
  MyClass(T v) { val = v; } 
 
  // This is the default constructor. 
  MyClass( ) { val = null;  } 
 
  // ... 
 
  T getVal() { return val; };   
}     
 
class ConstructorRefDemo2 { 
 
  public static void main(String args[]) 
  { 
    // Create a reference to the MyClass<T> constructor. 
    MyFunc<Integer> myClassCons = MyClass<Integer>::new; 
 
    // Create an instance of MyClass<T> via that constructor reference. 
    MyClass<Integer> mc = myClassCons.func(100); 
 
    // Use the instance of MyClass<T> just created. 
    System.out.println("val in mc is " + mc.getVal( )); 
  } 
}

listing 17
// Implement a simple class factory using a constructor reference. 
 
interface MyFunc<R, T> { 
   R func(T n); 
} 
 
// A simple generic class. 
class MyClass<T> { 
  private T val; 
 
  // A constructor that takes an argument. 
  MyClass(T v) { val = v; } 
 
  // The default constructor. This constructor 
  // is NOT used by this program. 
  MyClass() { val = null; } 
  // ... 
 
  T getVal() { return val; };   
}     
 
// A simple, non-generic class. 
class MyClass2 { 
  String  str; 
 
  // A constructor that takes an argument. 
  MyClass2(String s) { str = s; } 
 
  // The default constructor. This 
  // constructor is NOT used by this program. 
  MyClass2() { str = ""; } 
 
  // ... 
 
  String getVal() { return str; };   
}     
 
class ConstructorRefDemo3 { 
 
  // A factory method for class objects. The class must 
  // have a constructor that takes one parameter of type T. 
  // R specifies the type of object being created. 
  static <R,T> R myClassFactory(MyFunc<R, T> cons, T v) { 
    return cons.func(v); 
  } 
  
  public static void main(String args[]) 
  { 
    // Create a reference to a MyClass constructor. 
    // In this case, new refers to the constructor that 
    // takes an argument. 
    MyFunc<MyClass<Double>, Double> myClassCons = MyClass<Double>::new; 
 
    // Create an instance of MyClass by use of the factory method. 
    MyClass<Double> mc = myClassFactory(myClassCons, 100.1); 
 
    // Use the instance of MyClass just created. 
    System.out.println("val in mc is " + mc.getVal( )); 
 
    // Now, create a different class by use of myClassFactory(). 
    MyFunc<MyClass2, String> myClassCons2 = MyClass2::new; 
 
    // Create an instance of MyClass2 by use of the factory method. 
    MyClass2 mc2 = myClassFactory(myClassCons2, "Lambda"); 
 
    // Use the instance of MyClass just created. 
    System.out.println("str in mc2 is " + mc2.getVal( )); 
  } 
}

listing 18
// Use the Function built-in functional interface. 
 
// Import the Function interface. 
import java.util.function.Function; 
 
class UseFunctionInterfaceDemo { 
  public static void main(String args[]) 
  { 
 
    // This block lambda computes the factorial of an int value. 
    // This time, Function is the functional interface. 
    Function<Integer, Integer> factorial = (n) ->  { 
      int result = 1; 
      for(int i=1; i <= n; i++) 
        result = i * result; 
      return result; 
    }; 
 
    System.out.println("The factoral of 3 is " + factorial.apply(3)); 
    System.out.println("The factoral of 5 is " + factorial.apply(5)); 
  } 
}


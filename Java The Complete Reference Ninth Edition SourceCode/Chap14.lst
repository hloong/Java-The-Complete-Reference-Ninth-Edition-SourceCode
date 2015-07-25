listing 1
// A simple generic class.  
// Here, T is a type parameter that 
// will be replaced by a real type 
// when an object of type Gen is created. 
class Gen<T> { 
  T ob; // declare an object of type T 
   
  // Pass the constructor a reference to  
  // an object of type T. 
  Gen(T o) { 
    ob = o; 
  } 
 
  // Return ob. 
  T getob() { 
    return ob; 
  } 
 
  // Show type of T. 
  void showType() { 
    System.out.println("Type of T is " + 
                       ob.getClass().getName()); 
  } 
} 
 
// Demonstrate the generic class. 
class GenDemo { 
  public static void main(String args[]) { 
    // Create a Gen reference for Integers.  
    Gen<Integer> iOb;  
 
    // Create a Gen<Integer> object and assign its 
    // reference to iOb.  Notice the use of autoboxing  
    // to encapsulate the value 88 within an Integer object. 
    iOb = new Gen<Integer>(88); 
 
    // Show the type of data used by iOb. 
    iOb.showType(); 
 
    // Get the value in iOb. Notice that 
    // no cast is needed. 
    int v = iOb.getob(); 
    System.out.println("value: " + v); 
 
    System.out.println(); 
 
    // Create a Gen object for Strings. 
    Gen<String> strOb = new Gen<String>("Generics Test"); 
 
    // Show the type of data used by strOb. 
    strOb.showType(); 
 
    // Get the value of strOb. Again, notice 
    // that no cast is needed. 
    String str = strOb.getob(); 
    System.out.println("value: " + str); 
  } 
}

listing 2
// NonGen is functionally equivalent to Gen 
// but does not use generics.  
class NonGen {  
  Object ob; // ob is now of type Object 
    
  // Pass the constructor a reference to   
  // an object of type Object 
  NonGen(Object o) {  
    ob = o;  
  }  
  
  // Return type Object. 
  Object getob() {  
    return ob;  
  }  
 
  // Show type of ob.  
  void showType() {  
    System.out.println("Type of ob is " +  
                       ob.getClass().getName());  
  }  
}  
  
// Demonstrate the non-generic class.  
class NonGenDemo {  
  public static void main(String args[]) {  
    NonGen iOb;   
  
    // Create NonGen Object and store 
    // an Integer in it. Autoboxing still occurs. 
    iOb = new NonGen(88);  
  
    // Show the type of data used by iOb. 
    iOb.showType(); 
 
    // Get the value of iOb. 
    // This time, a cast is necessary. 
    int v = (Integer) iOb.getob();  
    System.out.println("value: " + v);  
  
    System.out.println();  
  
    // Create another NonGen object and  
    // store a String in it. 
    NonGen strOb = new NonGen("Non-Generics Test");  
  
    // Show the type of data used by strOb. 
    strOb.showType(); 
 
    // Get the value of strOb. 
    // Again, notice that a cast is necessary.  
    String str = (String) strOb.getob();  
    System.out.println("value: " + str);  
 
    // This compiles, but is conceptually wrong! 
    iOb = strOb; 
    v = (Integer) iOb.getob(); // run-time error! 
  }  
}

listing 3
// A simple generic class with two type 
// parameters: T and V. 
class TwoGen<T, V> { 
  T ob1; 
  V ob2; 
   
  // Pass the constructor a reference to  
  // an object of type T. 
  TwoGen(T o1, V o2) { 
    ob1 = o1; 
    ob2 = o2; 
  } 
 
  // Show types of T and V. 
  void showTypes() { 
    System.out.println("Type of T is " + 
                       ob1.getClass().getName()); 
 
    System.out.println("Type of V is " + 
                       ob2.getClass().getName()); 
  } 
 
  T getob1() { 
    return ob1; 
  } 
 
  V getob2() { 
    return ob2; 
  } 
} 
 
// Demonstrate TwoGen. 
class SimpGen { 
  public static void main(String args[]) { 
 
    TwoGen<Integer, String> tgObj = 
      new TwoGen<Integer, String>(88, "Generics"); 
 
    // Show the types. 
    tgObj.showTypes(); 
 
    // Obtain and show values. 
    int v = tgObj.getob1(); 
    System.out.println("value: " + v); 
 
    String str = tgObj.getob2(); 
    System.out.println("value: " + str); 
  } 
}

listing 4
// Stats attempts (unsuccessfully) to  
// create a generic class that can compute 
// the average of an array of numbers of 
// any given type. 
// 
// The class contains an error! 
class Stats<T> {  
  T[] nums; // nums is an array of type T 
    
  // Pass the constructor a reference to   
  // an array of type T. 
  Stats(T[] o) {  
    nums = o;  
  }  
  
  // Return type double in all cases. 
  double average() {  
    double sum = 0.0; 
 
    for(int i=0; i < nums.length; i++)  
      sum += nums[i].doubleValue(); // Error!!! 
 
    return sum / nums.length; 
  }  
}

listing 5
// In this version of Stats, the type argument for 
// T must be either Number, or a class derived 
// from Number. 
class Stats<T extends Number> {  
  T[] nums; // array of Number or subclass 
    
  // Pass the constructor a reference to   
  // an array of type Number or subclass. 
  Stats(T[] o) {  
    nums = o;  
  }  
  
  // Return type double in all cases. 
  double average() {  
    double sum = 0.0; 
 
    for(int i=0; i < nums.length; i++)  
      sum += nums[i].doubleValue(); 
 
    return sum / nums.length; 
  }  
}  
  
// Demonstrate Stats.  
class BoundsDemo {  
  public static void main(String args[]) {  
 
    Integer inums[] = { 1, 2, 3, 4, 5 }; 
    Stats<Integer> iob = new Stats<Integer>(inums);   
    double v = iob.average(); 
    System.out.println("iob average is " + v); 
 
    Double dnums[] = { 1.1, 2.2, 3.3, 4.4, 5.5 }; 
    Stats<Double> dob = new Stats<Double>(dnums);   
    double w = dob.average(); 
    System.out.println("dob average is " + w); 
 
    // This won't compile because String is not a 
    // subclass of Number. 
//    String strs[] = { "1", "2", "3", "4", "5" }; 
//    Stats<String> strob = new Stats<String>(strs);   
  
//    double x = strob.average(); 
//    System.out.println("strob average is " + v); 
 
  }  
}

listing 6
// Use a wildcard.  
class Stats<T extends Number> {   
  T[] nums; // array of Number or subclass  
     
  // Pass the constructor a reference to    
  // an array of type Number or subclass.  
  Stats(T[] o) {   
    nums = o;   
  }   
   
  // Return type double in all cases.  
  double average() {   
    double sum = 0.0;  
  
    for(int i=0; i < nums.length; i++)   
      sum += nums[i].doubleValue();  
  
    return sum / nums.length;  
  } 
 
  // Determine if two averages are the same. 
  // Notice the use of the wildcard. 
  boolean sameAvg(Stats<?> ob) { 
    if(average() == ob.average())  
      return true; 
 
    return false; 
  } 
}   
   
// Demonstrate wildcard. 
class WildcardDemo {   
  public static void main(String args[]) {   
    Integer inums[] = { 1, 2, 3, 4, 5 };  
    Stats<Integer> iob = new Stats<Integer>(inums);    
    double v = iob.average();  
    System.out.println("iob average is " + v);  
  
    Double dnums[] = { 1.1, 2.2, 3.3, 4.4, 5.5 };  
    Stats<Double> dob = new Stats<Double>(dnums);    
    double w = dob.average();  
    System.out.println("dob average is " + w);  
  
    Float fnums[] = { 1.0F, 2.0F, 3.0F, 4.0F, 5.0F };  
    Stats<Float> fob = new Stats<Float>(fnums);    
    double x = fob.average();  
    System.out.println("fob average is " + x);  
  
    // See which arrays have same average. 
    System.out.print("Averages of iob and dob "); 
    if(iob.sameAvg(dob)) 
      System.out.println("are the same.");  
    else 
      System.out.println("differ.");  
 
    System.out.print("Averages of iob and fob "); 
    if(iob.sameAvg(fob)) 
      System.out.println("are the same.");  
    else 
      System.out.println("differ.");  
  }   
}

listing 7
// Bounded Wildcard arguments. 
 
// Two-dimensional coordinates. 
class TwoD { 
  int x, y; 
 
  TwoD(int a, int b) { 
    x = a; 
    y = b; 
  } 
} 
 
// Three-dimensional coordinates. 
class ThreeD extends TwoD { 
  int z; 
   
  ThreeD(int a, int b, int c) { 
    super(a, b); 
    z = c; 
  } 
} 
 
// Four-dimensional coordinates. 
class FourD extends ThreeD { 
  int t; 
 
  FourD(int a, int b, int c, int d) { 
    super(a, b, c); 
    t = d;  
  } 
} 
 
// This class holds an array of coordinate objects. 
class Coords<T extends TwoD> { 
  T[] coords; 
 
  Coords(T[] o) { coords = o; } 
} 
 
// Demonstrate a bounded wildcard. 
class BoundedWildcard { 
  static void showXY(Coords<?> c) { 
    System.out.println("X Y Coordinates:"); 
    for(int i=0; i < c.coords.length; i++) 
      System.out.println(c.coords[i].x + " " + 
                         c.coords[i].y); 
    System.out.println(); 
  } 
 
  static void showXYZ(Coords<? extends ThreeD> c) { 
    System.out.println("X Y Z Coordinates:"); 
    for(int i=0; i < c.coords.length; i++) 
      System.out.println(c.coords[i].x + " " + 
                         c.coords[i].y + " " + 
                         c.coords[i].z); 
    System.out.println(); 
  } 
 
  static void showAll(Coords<? extends FourD> c) { 
    System.out.println("X Y Z T Coordinates:"); 
    for(int i=0; i < c.coords.length; i++) 
      System.out.println(c.coords[i].x + " " + 
                         c.coords[i].y + " " + 
                         c.coords[i].z + " " + 
                         c.coords[i].t); 
    System.out.println(); 
  } 
 
  public static void main(String args[]) { 
    TwoD td[] = { 
      new TwoD(0, 0), 
      new TwoD(7, 9), 
      new TwoD(18, 4), 
      new TwoD(-1, -23) 
    }; 
 
    Coords<TwoD> tdlocs = new Coords<TwoD>(td);     
 
    System.out.println("Contents of tdlocs."); 
    showXY(tdlocs); // OK, is a TwoD 
//  showXYZ(tdlocs); // Error, not a ThreeD 
//  showAll(tdlocs); // Error, not a FourD 
 
    // Now, create some FourD objects. 
    FourD fd[] = { 
      new FourD(1, 2, 3, 4), 
      new FourD(6, 8, 14, 8), 
      new FourD(22, 9, 4, 9), 
      new FourD(3, -2, -23, 17) 
    }; 
 
    Coords<FourD> fdlocs = new Coords<FourD>(fd);     
 
    System.out.println("Contents of fdlocs."); 
    // These are all OK. 
    showXY(fdlocs);  
    showXYZ(fdlocs); 
    showAll(fdlocs); 
  } 
}

listing 8
// Demonstrate a simple generic method. 
class GenMethDemo {  
 
  // Determine if an object is in an array. 
  static <T extends Comparable<T>, V extends T> boolean isIn(T x, V[] y) { 
 
    for(int i=0; i < y.length; i++) 
      if(x.equals(y[i])) return true; 
 
    return false; 
  } 
 
  public static void main(String args[]) {  
 
    // Use isIn() on Integers. 
    Integer nums[] = { 1, 2, 3, 4, 5 }; 
 
    if(isIn(2, nums)) 
      System.out.println("2 is in nums"); 
 
    if(!isIn(7, nums)) 
      System.out.println("7 is not in nums"); 
 
    System.out.println(); 
 
    // Use isIn() on Strings. 
    String strs[] = { "one", "two", "three", 
                      "four", "five" }; 
 
    if(isIn("two", strs)) 
      System.out.println("two is in strs"); 
 
    if(!isIn("seven", strs)) 
      System.out.println("seven is not in strs"); 
 
    // Opps! Won't compile! Types must be compatible. 
//    if(isIn("two", nums)) 
//      System.out.println("two is in strs"); 
  }  
}

listing 9
// Use a generic constructor. 
class GenCons { 
  private double val; 
 
  <T extends Number> GenCons(T arg) { 
    val = arg.doubleValue(); 
  } 
 
  void showval() { 
    System.out.println("val: " + val); 
  } 
} 
 
class GenConsDemo { 
  public static void main(String args[]) { 
 
    GenCons test = new GenCons(100); 
    GenCons test2 = new GenCons(123.5F); 
 
    test.showval(); 
    test2.showval(); 
  } 
}

listing 10
// A generic interface example. 
 
// A Min/Max interface. 
interface MinMax<T extends Comparable<T>> { 
  T min(); 
  T max(); 
} 
 
// Now, implement MinMax 
class MyClass<T extends Comparable<T>> implements MinMax<T> { 
  T[] vals; 
 
  MyClass(T[] o) { vals = o; } 
 
  // Return the minimum value in vals. 
  public T min() { 
    T v = vals[0]; 
 
    for(int i=1; i < vals.length; i++) 
      if(vals[i].compareTo(v) < 0) v = vals[i]; 
 
    return v; 
  } 
 
  // Return the maximum value in vals. 
  public T max() { 
    T v = vals[0]; 
 
    for(int i=1; i < vals.length; i++) 
      if(vals[i].compareTo(v) > 0) v = vals[i]; 
 
    return v; 
  } 
} 
 
class GenIFDemo { 
  public static void main(String args[]) { 
    Integer inums[] = {3, 6, 2, 8, 6 }; 
    Character chs[] = {'b', 'r', 'p', 'w' }; 
 
    MyClass<Integer> iob = new MyClass<Integer>(inums); 
    MyClass<Character> cob = new MyClass<Character>(chs); 
 
    System.out.println("Max value in inums: " + iob.max()); 
    System.out.println("Min value in inums: " + iob.min()); 
 
    System.out.println("Max value in chs: " + cob.max()); 
    System.out.println("Min value in chs: " + cob.min()); 
  } 
}

listing 11
// Demonstrate a raw type. 
class Gen<T> {  
  T ob; // declare an object of type T  
    
  // Pass the constructor a reference to   
  // an object of type T.  
  Gen(T o) {  
    ob = o;  
  }  
  
  // Return ob.  
  T getob() {  
    return ob;  
  }  
}  
  
// Demonstrate raw type. 
class RawDemo {  
  public static void main(String args[]) {  
 
    // Create a Gen object for Integers. 
    Gen<Integer> iOb = new Gen<Integer>(88);  
   
    // Create a Gen object for Strings. 
    Gen<String> strOb = new Gen<String>("Generics Test");  
  
    // Create a raw-type Gen object and give it 
    // a Double value. 
    Gen raw = new Gen(new Double(98.6)); 
 
    // Cast here is necessary because type is unknown. 
    double d = (Double) raw.getob(); 
    System.out.println("value: " + d); 
 
    // The use of a raw type can lead to run-time. 
    // exceptions.  Here are some examples. 
 
    // The following cast causes a run-time error! 
//    int i = (Integer) raw.getob(); // run-time error 
 
    // This assigment overrides type safety. 
    strOb = raw; // OK, but potentially wrong 
//    String str = strOb.getob(); // run-time error  
     
    // This assingment also overrides type safety. 
    raw = iOb; // OK, but potentially wrong 
//    d = (Double) raw.getob(); // run-time error 
  }  
}

listing 12
// A simple generic class hierarchy. 
class Gen<T> {  
  T ob; 
    
  Gen(T o) {  
    ob = o;  
  }  
  
  // Return ob.  
  T getob() {  
    return ob;  
  }  
}  
 
// A subclass of Gen. 
class Gen2<T> extends Gen<T> { 
  Gen2(T o) { 
    super(o); 
  } 
}

listing 13
// A subclass can add its own type parameters. 
class Gen<T> {  
  T ob; // declare an object of type T  
    
  // Pass the constructor a reference to   
  // an object of type T.  
  Gen(T o) {  
    ob = o;  
  }  
  
  // Return ob.  
  T getob() {  
    return ob;  
  }  
}  
 
// A subclass of Gen that defines a second 
// type parameter, called V. 
class Gen2<T, V> extends Gen<T> { 
  V ob2; 
 
  Gen2(T o, V o2) { 
    super(o); 
    ob2 = o2; 
  } 
 
  V getob2() { 
    return ob2; 
  } 
} 
  
// Create an object of type Gen2. 
class HierDemo {  
  public static void main(String args[]) {  
    
    // Create a Gen2 object for String and Integer. 
    Gen2<String, Integer> x = 
      new Gen2<String, Integer>("Value is: ", 99);  
 
    System.out.print(x.getob()); 
    System.out.println(x.getob2()); 
  }  
}

listing 14
// A nongeneric class can be the superclass 
// of a generic subclass. 
 
// A nongeneric class. 
class NonGen { 
  int num; 
 
  NonGen(int i) { 
    num = i; 
  } 
 
  int getnum() { 
    return num; 
  } 
} 
 
// A generic subclass. 
class Gen<T> extends NonGen {  
  T ob; // declare an object of type T  
    
  // Pass the constructor a reference to   
  // an object of type T.  
  Gen(T o, int i) {  
    super(i); 
    ob = o;  
  }  
  
  // Return ob.  
  T getob() {  
    return ob;  
  }  
}  
  
// Create a Gen object. 
class HierDemo2 {  
  public static void main(String args[]) {  
    
    // Create a Gen object for String. 
    Gen<String> w = new Gen<String>("Hello", 47); 
    
    System.out.print(w.getob() + " "); 
    System.out.println(w.getnum()); 
  }  
}

listing 15
// Use the instanceof operator with a generic class hierarchy.  
class Gen<T> {   
  T ob;  
     
  Gen(T o) {   
    ob = o;   
  }   
   
  // Return ob.   
  T getob() {   
    return ob;   
  }   
}   
  
// A subclass of Gen.  
class Gen2<T> extends Gen<T> {  
  Gen2(T o) {  
    super(o);  
  }  
}  
  
// Demonstrate run-time type ID implications of generic 
// class hierarchy. 
class HierDemo3 {   
  public static void main(String args[]) {   
     
    // Create a Gen object for Integers.  
    Gen<Integer> iOb = new Gen<Integer>(88);  
  
    // Create a Gen2 object for Integers.  
    Gen2<Integer> iOb2 = new Gen2<Integer>(99);   
    
    // Create a Gen2 object for Strings.  
    Gen2<String> strOb2 = new Gen2<String>("Generics Test");   
  
    // See if iOb2 is some form of Gen2. 
    if(iOb2 instanceof Gen2<?>)   
      System.out.println("iOb2 is instance of Gen2");  
 
    // See if iOb2 is some form of Gen. 
    if(iOb2 instanceof Gen<?>)   
      System.out.println("iOb2 is instance of Gen");  
  
    System.out.println();  
  
    // See if strOb2 is a Gen2. 
    if(strOb2 instanceof Gen2<?>)   
      System.out.println("strOb is instance of Gen2");  
  
    // See if strOb2 is a Gen. 
    if(strOb2 instanceof Gen<?>)   
      System.out.println("strOb is instance of Gen");  
 
    System.out.println();  
  
    // See if iOb is an instance of Gen2, which it is not. 
    if(iOb instanceof Gen2<?>)   
      System.out.println("iOb is instance of Gen2");  
  
    // See if iOb is an instance of Gen, which it is. 
    if(iOb instanceof Gen<?>)   
      System.out.println("iOb is instance of Gen");  
  
    // The following can't be compiled because  
    // generic type info does not exist at run-time. 
//    if(iOb2 instanceof Gen2<Integer>)   
//      System.out.println("iOb2 is instance of Gen2<Integer>");  
  }   
}

listing 16
// Overriding a generic method in a generic class. 
class Gen<T> {  
  T ob; // declare an object of type T  
    
  // Pass the constructor a reference to   
  // an object of type T.  
  Gen(T o) {  
    ob = o;  
  }  
  
  // Return ob.  
  T getob() {  
    System.out.print("Gen's getob(): " ); 
    return ob;  
  }  
}  
 
// A subclass of Gen that overrides getob(). 
class Gen2<T> extends Gen<T> { 
 
  Gen2(T o) { 
    super(o); 
  } 
   
  // Override getob(). 
  T getob() {  
    System.out.print("Gen2's getob(): "); 
    return ob;  
  }  
} 
  
// Demonstrate generic method override. 
class OverrideDemo {  
  public static void main(String args[]) {  
    
    // Create a Gen object for Integers. 
    Gen<Integer> iOb = new Gen<Integer>(88); 
 
    // Create a Gen2 object for Integers. 
    Gen2<Integer> iOb2 = new Gen2<Integer>(99);  
   
    // Create a Gen2 object for Strings. 
    Gen2<String> strOb2 = new Gen2<String>("Generics Test");  
 
    System.out.println(iOb.getob()); 
    System.out.println(iOb2.getob()); 
    System.out.println(strOb2.getob()); 
  }  
}

listing 17
// A situation that creates a bridge method. 
class Gen<T> {  
  T ob; // declare an object of type T  
    
  // Pass the constructor a reference to   
  // an object of type T.  
  Gen(T o) {  
    ob = o;  
  }  
  
  // Return ob.  
  T getob() {  
    return ob;  
  }  
}  
 
// A subclass of Gen. 
class Gen2 extends Gen<String> { 
 
  Gen2(String o) { 
    super(o); 
  } 
 
  // A String-specific override of getob(). 
  String getob() { 
    System.out.print("You called String getob(): "); 
    return ob; 
  } 
} 
  
// Demonstrate a situation that requires a bridge method. 
class BridgeDemo {  
  public static void main(String args[]) {  
 
    // Create a Gen2 object for Strings. 
    Gen2 strOb2 = new Gen2("Generics Test");  
 
    System.out.println(strOb2.getob()); 
  }  
}

listing 18
// Ambiguity caused by erasure on  
// overloaded methods. 
class MyGenClass<T, V> {  
  T ob1;  
  V ob2;  
 
  // ... 
 
  // These two overloaded methods are ambiguous 
  // and will not compile. 
  void set(T o) { 
    ob1 = o; 
  } 
 
  void set(V o) { 
    ob2 = o; 
  } 
}

listing 19
// Can't create an instance of T. 
class Gen<T> {  
  T ob;  
  Gen() {  
    ob = new T(); // Illegal!!! 
  }  
} 

listing 20
class Wrong<T> {  
  // Wrong, no static variables of type T. 
  static T ob; 
    
  // Wrong, no static method can use T. 
  static T getob() { 
    return ob; 
  } 
}

listing 21
// Generics and arrays. 
class Gen<T extends Number> {  
  T ob;  
 
  T vals[]; // OK 
 
  Gen(T o, T[] nums) {  
    ob = o; 
 
    // This statement is illegal. 
    // vals = new T[10]; // can't create an array of T 
 
    // But, this statement is OK. 
    vals = nums; // OK to assign reference to existent array 
  }  
}  
  
class GenArrays {  
  public static void main(String args[]) {  
    Integer n[] = { 1, 2, 3, 4, 5 };   
 
    Gen<Integer> iOb = new Gen<Integer>(50, n); 
 
    // Can't create an array of type-specific generic references. 
    // Gen<Integer> gens[] = new Gen<Integer>[10]; // Wrong! 
 
    // This is OK. 
    Gen<?> gens[] = new Gen<?>[10]; // OK
  } 
}


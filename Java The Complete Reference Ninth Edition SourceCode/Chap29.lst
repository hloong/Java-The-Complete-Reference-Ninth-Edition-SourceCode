listing 1
// Demonstrate several Stream operations. 
 
import java.util.*; 
import java.util.stream.*; 
 
class StreamDemo { 
 
  public static void main(String[] args) { 
 
    // Create a list of Integer values. 
    ArrayList<Integer> myList = new ArrayList<>( ); 
    myList.add(7); 
    myList.add(18); 
    myList.add(10); 
    myList.add(24); 
    myList.add(17); 
    myList.add(5); 
 
    System.out.println("Original list: " + myList); 
 
    // Obtain a Stream to the array list. 
    Stream<Integer> myStream = myList.stream(); 
 
    // Obtain the minimum and maximum value by uses of min(), 
    // max(), isPresent(), and get(). 
    Optional<Integer> minVal = myStream.min(Integer::compare); 
    if(minVal.isPresent()) System.out.println("Minimum value: " + 
                                               minVal.get()); 
 
    // Must obtain a new stream because previous call to min() 
    // is a terminal operation that consumed the stream. 
    myStream = myList.stream(); 
    Optional<Integer> maxVal = myStream.max(Integer::compare); 
    if(maxVal.isPresent()) System.out.println("Maximum value: " + 
                                               maxVal.get()); 
 
    // Sort the stream by use of sorted(). 
    Stream<Integer> sortedStream = myList.stream().sorted(); 
 
    // Display the sorted stream by use of forEach(). 
    System.out.print("Sorted stream: "); 
    sortedStream.forEach((n) -> System.out.print(n + " ")); 
    System.out.println(); 
 
    // Display only the odd values by use of filter(). 
    Stream<Integer> oddVals =  
           myList.stream().sorted().filter((n) -> (n % 2) == 1); 
    System.out.print("Odd values: "); 
    oddVals.forEach((n) -> System.out.print(n + " ")); 
    System.out.println(); 
 
    // Display only the odd values that are greater than 5. Notice that 
    // two filter operations are pipelined. 
    oddVals = myList.stream().filter( (n) -> (n % 2) == 1) 
                             .filter((n) -> n > 5); 
    System.out.print("Odd values greater than 5: "); 
    oddVals.forEach((n) -> System.out.print(n + " ") ); 
    System.out.println(); 
  } 
}

listing 2
// Demonstrate the reduce() method. 
 
import java.util.*; 
import java.util.stream.*; 
 
class StreamDemo2 { 
 
  public static void main(String[] args) { 
 
    // Create a list of Integer values. 
    ArrayList<Integer> myList = new ArrayList<>( ); 
 
    myList.add(7); 
    myList.add(18); 
    myList.add(10); 
    myList.add(24); 
    myList.add(17); 
    myList.add(5); 
 
    // Two ways to obtain the integer product of the elements 
    // in myList by use of reduce(). 
    Optional<Integer> productObj = myList.stream().reduce((a,b) -> a*b); 
    if(productObj.isPresent()) 
      System.out.println("Product as Optional: " + productObj.get()); 
 
    int product = myList.stream().reduce(1, (a,b) -> a*b); 
    System.out.println("Product as int: " + product); 
  } 
}

listing 3
// Demonstrate the use of a combiner with reduce() 
 
import java.util.*; 
import java.util.stream.*; 
 
class StreamDemo3 { 
 
  public static void main(String[] args) { 
 
    // This is now a list of double values. 
    ArrayList<Double> myList = new ArrayList<>( ); 
 
    myList.add(7.0); 
    myList.add(18.0); 
    myList.add(10.0); 
    myList.add(24.0); 
    myList.add(17.0); 
    myList.add(5.0); 
 
    double productOfSqrRoots = myList.parallelStream().reduce( 
                                     1.0, 
                                     (a,b) -> a * Math.sqrt(b),                                      
                                     (a,b) -> a * b 
                                ); 
 
    System.out.println("Product of square roots: " + productOfSqrRoots); 
  } 
}

listing 4
// Map one stream to another. 
 
import java.util.*; 
import java.util.stream.*; 
 
class StreamDemo4 { 
 
  public static void main(String[] args) { 
 
    // A list of double values. 
    ArrayList<Double> myList = new ArrayList<>( ); 
 
    myList.add(7.0); 
    myList.add(18.0); 
    myList.add(10.0); 
    myList.add(24.0); 
    myList.add(17.0); 
    myList.add(5.0); 
 
    // Map the square root of the elements in myList to a new stream. 
    Stream<Double> sqrtRootStrm = myList.stream().map((a) -> Math.sqrt(a)); 
 
    // Find the product to the square roots. 
    double productOfSqrRoots = sqrtRootStrm.reduce(1.0, (a,b) -> a*b); 
 
    System.out.println("Product of square roots is " + productOfSqrRoots); 
  } 
}

listing 5
// Use map() to create a new stream that contains only 
// selected aspects of the original stream. 
 
import java.util.*; 
import java.util.stream.*; 
 
class NamePhoneEmail { 
  String name;   
  String phonenum; 
  String email; 
 
  NamePhoneEmail(String n, String p, String e) { 
    name = n; 
    phonenum = p; 
    email = e; 
  } 
} 
 
class NamePhone { 
  String name; 
  String phonenum; 
 
  NamePhone(String n, String p) { 
    name = n; 
    phonenum = p; 
  } 
} 
 
class StreamDemo5 { 
 
  public static void main(String[] args) { 
 
    // A list of names, phone numbers, and e-mail addresses. 
    ArrayList<NamePhoneEmail> myList = new ArrayList<>( ); 
 
    myList.add(new NamePhoneEmail("Larry", "555-5555", 
                                  "Larry@HerbSchildt.com")); 
    myList.add(new NamePhoneEmail("James", "555-4444", 
                                  "James@HerbSchildt.com")); 
    myList.add(new NamePhoneEmail("Mary", "555-3333", 
                                  "Mary@HerbSchildt.com")); 
 
    System.out.println("Original values in myList: "); 
    myList.stream().forEach( (a) -> { 
      System.out.println(a.name + " " + a.phonenum + " " + a.email); 
    }); 
    System.out.println(); 
 
    // Map just the names and phone numbers to a new stream. 
    Stream<NamePhone> nameAndPhone = myList.stream().map( 
                                     (a) -> new NamePhone(a.name,a.phonenum) 
                                   ); 
 
    System.out.println("List of names and phone numbers: "); 
    nameAndPhone.forEach( (a) -> { 
      System.out.println(a.name + " " + a.phonenum); 
    }); 
  } 
}

listing 6
// Map a Stream to an intStream. 
 
import java.util.*; 
import java.util.stream.*; 
 
class StreamDemo6 { 
 
  public static void main(String[] args) { 
 
    // A list of double values. 
    ArrayList<Double> myList = new ArrayList<>( ); 
 
    myList.add(1.1); 
    myList.add(3.6); 
    myList.add(9.2); 
    myList.add(4.7); 
    myList.add(12.1); 
    myList.add(5.0); 
 
    System.out.print("Original values in myList: "); 
    myList.stream().forEach( (a) -> { 
      System.out.print(a + " "); 
    }); 
    System.out.println(); 
 
    // Map the ceiling of the elements in myList to an InStream. 
    IntStream cStrm = myList.stream().mapToInt((a) -> (int) Math.ceil(a)); 
 
    System.out.print("The ceilings of the values in myList: "); 
    cStrm.forEach( (a) -> { 
      System.out.print(a + " "); 
    }); 
 
  } 
}

listing 7
// Use collect() to create a List and a Set from a stream. 
 
import java.util.*; 
import java.util.stream.*; 
 
class NamePhoneEmail { 
  String name;   
  String phonenum; 
  String email; 
 
  NamePhoneEmail(String n, String p, String e) { 
    name = n; 
    phonenum = p; 
    email = e; 
  } 
} 
 
class NamePhone { 
  String name; 
  String phonenum; 
 
  NamePhone(String n, String p) { 
    name = n; 
    phonenum = p; 
  } 
} 
 
class StreamDemo7 { 
 
  public static void main(String[] args) { 
 
    // A list of names, phone numbers, and e-mail addresses. 
    ArrayList<NamePhoneEmail> myList = new ArrayList<>( ); 
 
    myList.add(new NamePhoneEmail("Larry", "555-5555", 
                                  "Larry@HerbSchildt.com")); 
    myList.add(new NamePhoneEmail("James", "555-4444", 
                                  "James@HerbSchildt.com")); 
    myList.add(new NamePhoneEmail("Mary", "555-3333", 
                                  "Mary@HerbSchildt.com")); 
 
    // Map just the names and phone numbers to a new stream. 
    Stream<NamePhone> nameAndPhone = myList.stream().map( 
                                     (a) -> new NamePhone(a.name,a.phonenum) 
                                   ); 
 
    // Use collect to create a List of the names and phone numbers. 
    List<NamePhone> npList = nameAndPhone.collect(Collectors.toList()); 
 
    System.out.println("Names and phone numbers in a List:"); 
    for(NamePhone e : npList)  
      System.out.println(e.name + ": " + e.phonenum); 
 
    // Obtain another mapping of the names and phone numbers. 
    nameAndPhone = myList.stream().map( 
                                     (a) -> new NamePhone(a.name,a.phonenum) 
                                    ); 
 
    // Now, create a Set by use of collect(). 
    Set<NamePhone> npSet = nameAndPhone.collect(Collectors.toSet()); 
 
    System.out.println("\nNames and phone numbers in a Set:"); 
    for(NamePhone e : npSet)  
      System.out.println(e.name + ": " + e.phonenum); 
  } 
}

listing 8
// Use an iterator with a stream. 
 
import java.util.*; 
import java.util.stream.*; 
 
class StreamDemo8 { 
 
  public static void main(String[] args) { 
 
    // Create a list of Strings. 
    ArrayList<String> myList = new ArrayList<>( ); 
    myList.add("Alpha"); 
    myList.add("Beta"); 
    myList.add("Gamma"); 
    myList.add("Delta"); 
    myList.add("Phi"); 
    myList.add("Omega"); 
 
    // Obtain a Stream to the array list. 
    Stream<String> myStream = myList.stream(); 
 
    // Obtain an iterator to the stream. 
    Iterator<String> itr = myStream.iterator(); 
 
    // Iterate the elements in the stream. 
    while(itr.hasNext())  
      System.out.println(itr.next()); 
  } 
}

listing 9
// Use a Spliterator. 
 
import java.util.*; 
import java.util.stream.*; 
 
class StreamDemo9 { 
 
  public static void main(String[] args) { 
 
    // Create a list of Strings. 
    ArrayList<String> myList = new ArrayList<>( ); 
    myList.add("Alpha"); 
    myList.add("Beta"); 
    myList.add("Gamma"); 
    myList.add("Delta"); 
    myList.add("Phi"); 
    myList.add("Omega"); 
 
    // Obtain a Stream to the array list. 
    Stream<String> myStream = myList.stream(); 
 
    // Obtain a Spliterator. 
    Spliterator<String> splitItr = myStream.spliterator(); 
 
    // Iterate the elements of the stream. 
    while(splitItr.tryAdvance((n) -> System.out.println(n))); 
  } 
}

listing 10
// Demonstrate trySplit(). 
 
import java.util.*; 
import java.util.stream.*; 
 
class StreamDemo10 { 
 
  public static void main(String[] args) { 
 
    // Create a list of Strings. 
    ArrayList<String> myList = new ArrayList<>( ); 
    myList.add("Alpha"); 
    myList.add("Beta"); 
    myList.add("Gamma"); 
    myList.add("Delta"); 
    myList.add("Phi"); 
    myList.add("Omega"); 
 
    // Obtain a Stream to the array list. 
    Stream<String> myStream = myList.stream(); 
 
    // Obtain a Spliterator. 
    Spliterator<String> splitItr = myStream.spliterator(); 
 
    // Now, split the first iterator. 
    Spliterator<String> splitItr2 = splitItr.trySplit(); 
 
     // If splitItr could be split, use splitItr2 first. 
    if(splitItr2 != null) { 
      System.out.println("Output from splitItr2: "); 
      splitItr2.forEachRemaining((n) -> System.out.println(n)); 
    } 
     
    // Now, use the splitItr. 
    System.out.println("\nOutput from splitItr: "); 
    splitItr.forEachRemaining((n) -> System.out.println(n)); 
  } 
}


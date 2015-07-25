listing 1
// Demonstrate ArrayList. 
import java.util.*; 
 
class ArrayListDemo { 
  public static void main(String args[]) { 
    // Create an array list. 
    ArrayList<String> al = new ArrayList<String>(); 
     
    System.out.println("Initial size of al: " + 
                       al.size()); 
 
    // Add elements to the array list. 
    al.add("C"); 
    al.add("A"); 
    al.add("E"); 
    al.add("B"); 
    al.add("D"); 
    al.add("F"); 
    al.add(1, "A2"); 
 
    System.out.println("Size of al after additions: " + 
                       al.size()); 
 
    // Display the array list. 
    System.out.println("Contents of al: " + al); 
 
    // Remove elements from the array list. 
    al.remove("F"); 
    al.remove(2); 
 
    System.out.println("Size of al after deletions: " + 
                       al.size()); 
    System.out.println("Contents of al: " + al); 
  } 
}

listing 2
// Convert an ArrayList into an array.  
import java.util.*;  
  
class ArrayListToArray {  
  public static void main(String args[]) {  
    // Create an array list. 
    ArrayList<Integer> al = new ArrayList<Integer>();  
      
    // Add elements to the array list. 
    al.add(1);  
    al.add(2);  
    al.add(3);  
    al.add(4);  
  
    System.out.println("Contents of al: " + al);  
  
    // Get the array. 
    Integer ia[] = new Integer[al.size()];  
    ia = al.toArray(ia);  
  
    int sum = 0;  
  
    // Sum the array. 
    for(int i : ia) sum += i;  
  
    System.out.println("Sum is: " + sum);  
  }  
}

listing 3
// Demonstrate LinkedList. 
import java.util.*; 
 
class LinkedListDemo { 
  public static void main(String args[]) { 
    // Create a linked list. 
    LinkedList<String> ll = new LinkedList<String>(); 
     
    // Add elements to the linked list. 
    ll.add("F"); 
    ll.add("B"); 
    ll.add("D"); 
    ll.add("E"); 
    ll.add("C"); 
    ll.addLast("Z"); 
    ll.addFirst("A"); 
 
    ll.add(1, "A2"); 
 
    System.out.println("Original contents of ll: " + ll); 
 
    // Remove elements from the linked list. 
    ll.remove("F"); 
    ll.remove(2); 
 
    System.out.println("Contents of ll after deletion: " 
                       + ll); 
 
    // Remove first and last elements. 
    ll.removeFirst(); 
    ll.removeLast(); 
 
    System.out.println("ll after deleting first and last: " 
                       + ll); 
 
    // Get and set a value. 
    String val = ll.get(2); 
    ll.set(2, val + " Changed"); 
 
    System.out.println("ll after change: " + ll); 
  } 
}

listing 4
// Demonstrate HashSet. 
import java.util.*; 
 
class HashSetDemo { 
  public static void main(String args[]) { 
    // Create a hash set. 
    HashSet<String> hs = new HashSet<String>(); 
     
    // Add elements to the hash set. 
    hs.add("Beta"); 
    hs.add("Alpha"); 
    hs.add("Eta"); 
    hs.add("Gamma"); 
    hs.add("Epsilon");
    hs.add("Omega");   

    System.out.println(hs); 
  } 
}

listing 5
// Demonstrate TreeSet. 
import java.util.*; 
 
class TreeSetDemo { 
  public static void main(String args[]) { 
    // Create a tree set. 
    TreeSet<String> ts = new TreeSet<String>(); 
     
    // Add elements to the tree set. 
    ts.add("C"); 
    ts.add("A"); 
    ts.add("B"); 
    ts.add("E"); 
    ts.add("F"); 
    ts.add("D"); 
 
    System.out.println(ts); 
  } 
}

listing 6
// Demonstrate ArrayDeque.
import java.util.*; 
 
class ArrayDequeDemo { 
  public static void main(String args[]) { 
    // Create a tree set. 
    ArrayDeque<String> adq = new ArrayDeque<String>(); 
     
    // Use an ArrayDeque like a stack.
    adq.push("A"); 
    adq.push("B");  
    adq.push("D"); 
    adq.push("E"); 
    adq.push("F"); 
 
    System.out.print("Popping the stack: ");

    while(adq.peek() != null) 
      System.out.print(adq.pop() + " ");

    System.out.println();
  } 
}

listing 7
// Demonstrate iterators. 
import java.util.*; 
 
class IteratorDemo { 
  public static void main(String args[]) { 
    // Create an array list. 
    ArrayList<String> al = new ArrayList<String>(); 
     
    // Add elements to the array list. 
    al.add("C"); 
    al.add("A"); 
    al.add("E"); 
    al.add("B"); 
    al.add("D"); 
    al.add("F"); 
 
    // Use iterator to display contents of al. 
    System.out.print("Original contents of al: "); 
    Iterator<String> itr = al.iterator(); 
    while(itr.hasNext()) { 
      String element = itr.next(); 
      System.out.print(element + " "); 
    } 
    System.out.println(); 
 
    // Modify objects being iterated. 
    ListIterator<String> litr = al.listIterator();  
    while(litr.hasNext()) { 
      String element = litr.next(); 
      litr.set(element + "+"); 
    } 
 
    System.out.print("Modified contents of al: "); 
    itr = al.iterator();  
    while(itr.hasNext()) { 
      String element = itr.next(); 
      System.out.print(element + " "); 
    } 
    System.out.println(); 
 
    // Now, display the list backwards. 
    System.out.print("Modified list backwards: "); 
    while(litr.hasPrevious()) { 
      String element = litr.previous(); 
      System.out.print(element + " "); 
    } 
    System.out.println(); 
  } 
}

listing 8
// Use the for-each for loop to cycle through a collection. 
import java.util.*; 
 
class ForEachDemo { 
  public static void main(String args[]) { 
    // Create an array list for integers. 
    ArrayList<Integer> vals = new ArrayList<Integer>(); 
     
    // Add values to the array list. 
    vals.add(1); 
    vals.add(2); 
    vals.add(3); 
    vals.add(4); 
    vals.add(5); 
 
    // Use for loop to display the values. 
    System.out.print("Original contents of vals: "); 
    for(int v : vals)  
      System.out.print(v + " "); 
    System.out.println(); 
 
    // Now, sum the values by using a for loop. 
    int sum = 0; 
    for(int v : vals)  
      sum += v; 
 
    System.out.println("Sum of values: " + sum); 
  } 
}

listing 9
// A simple Spliterator demonstration. 
import java.util.*; 
 
class SpliteratorDemo { 

  public static void main(String args[]) { 
    // Create an array list for doubles. 
    ArrayList<Double> vals = new ArrayList<>(); 
     
    // Add values to the array list. 
    vals.add(1.0); 
    vals.add(2.0); 
    vals.add(3.0); 
    vals.add(4.0); 
    vals.add(5.0); 
 
    // Use tryAdvance() to display contents of vals. 
    System.out.print("Contents of vals:\n"); 
    Spliterator<Double> spltitr = vals.spliterator(); 
    while(spltitr.tryAdvance((n) -> System.out.println(n)));
    System.out.println();  

    // Create new list that contains square roots. 
    spltitr = vals.spliterator(); 
    ArrayList<Double> sqrs = new ArrayList<>();
    while(spltitr.tryAdvance((n) -> sqrs.add(Math.sqrt(n))));

    // Use forEachRemaining to display contents of sqrs. 
    System.out.print("Contents of sqrs:\n"); 
    spltitr = sqrs.spliterator(); 
    spltitr.forEachRemaining((n) -> System.out.println(n));
    System.out.println();  
  }
}


listing 10
// A simple mailing list example.  
import java.util.*;  
  
class Address {  
  private String name;  
  private String street;  
  private String city;  
  private String state;  
  private String code;  
  
  Address(String n, String s, String c,   
          String st, String cd) {  
    name = n;  
    street = s;  
    city = c;  
    state = st;  
    code = cd;  
  }  
  
  public String toString() {  
    return name + "\n" + street + "\n" +  
           city + " " + state + " " + code;  
  }  
}  
  
class MailList {  
  public static void main(String args[]) {  
    LinkedList<Address> ml = new LinkedList<Address>();  
      
    // Add elements to the linked list. 
    ml.add(new Address("J.W. West", "11 Oak Ave",  
                       "Urbana", "IL", "61801"));  
    ml.add(new Address("Ralph Baker", "1142 Maple Lane",  
                       "Mahome", "IL", "61853"));  
    ml.add(new Address("Tom Carlton", "867 Elm St",  
                       "Champaign", "IL", "61820"));  
 
    // Display the mailing list. 
    for(Address element : ml) 
      System.out.println(element + "\n");  
 
    System.out.println();  
  }  
}

listing 11
import java.util.*;  
  
class HashMapDemo {  
  public static void main(String args[]) {  
  
    // Create a hash map. 
    HashMap<String, Double> hm = new HashMap<String, Double>();  
      
    // Put elements to the map  
    hm.put("John Doe", new Double(3434.34));  
    hm.put("Tom Smith", new Double(123.22));  
    hm.put("Jane Baker", new Double(1378.00));  
    hm.put("Tod Hall", new Double(99.22));  
    hm.put("Ralph Smith", new Double(-19.08));  
  
    // Get a set of the entries. 
    Set<Map.Entry<String, Double>> set = hm.entrySet();  
 
    // Display the set. 
    for(Map.Entry<String, Double> me : set) { 
      System.out.print(me.getKey() + ": ");  
      System.out.println(me.getValue());  
    }  
 
    System.out.println();  
  
    // Deposit 1000 into John Doe's account. 
    double balance = hm.get("John Doe");  
    hm.put("John Doe", balance + 1000);  
 
    System.out.println("John Doe's new balance: " +  
      hm.get("John Doe"));  
  }  
}

listing 12
import java.util.*;  
  
class TreeMapDemo {  
  public static void main(String args[]) {  
  
    // Create a tree map. 
    TreeMap<String, Double> tm = new TreeMap<String, Double>();  
      
    // Put elements to the map. 
    tm.put("John Doe", new Double(3434.34));  
    tm.put("Tom Smith", new Double(123.22));  
    tm.put("Jane Baker", new Double(1378.00));  
    tm.put("Tod Hall", new Double(99.22));  
    tm.put("Ralph Smith", new Double(-19.08));  
  
    // Get a set of the entries. 
    Set<Map.Entry<String, Double>> set = tm.entrySet(); 
  
    // Display the elements. 
    for(Map.Entry<String, Double> me : set) { 
      System.out.print(me.getKey() + ": ");  
      System.out.println(me.getValue());  
    }  
    System.out.println();  
 
    // Deposit 1000 into John Doe's account. 
    double balance = tm.get("John Doe");  
    tm.put("John Doe", balance + 1000);  
 
    System.out.println("John Doe's new balance: " +  
      tm.get("John Doe"));  
  }  
}

listing 13
// Use a custom comparator.  
import java.util.*;  
  
// A reverse comparator for strings.  
class MyComp implements Comparator<String> {  
  public int compare(String aStr, String bStr) {  
  
    // Reverse the comparison. 
    return bStr.compareTo(aStr);  
  }  
  
  // No need to override equals or the default methods.  
}  
  
class CompDemo {  
  public static void main(String args[]) {  
    // Create a tree set. 
    TreeSet<String> ts = new TreeSet<String>(new MyComp());  
      
    // Add elements to the tree set. 
    ts.add("C");  
    ts.add("A");  
    ts.add("B");  
    ts.add("E");  
    ts.add("F");  
    ts.add("D");  
  
    // Display the elements. 
    for(String element : ts) 
      System.out.print(element + " ");  
 
    System.out.println();  
  }  
}

listing 14
// Use a lambda expression to create a reverse comparator. 
import java.util.*;  
  
class CompDemo2 {  
  public static void main(String args[]) {  

    // Pass a reversed comparator to TreeSet() via a
    // lambda expression.
    TreeSet<String> ts = new TreeSet<String>(
                               (aStr, bStr) -> bStr.compareTo(aStr));  

    // Add elements to the tree set. 
    ts.add("C");  
    ts.add("A");  
    ts.add("B");  
    ts.add("E");  
    ts.add("F");  
    ts.add("D");  
  
    // Display the elements. 
    for(String element : ts) 
      System.out.print(element + " ");  
 
    System.out.println();  
  }  
}

listing 15
// Use a comparator to sort accounts by last name.  
import java.util.*;  
  
// Compare last whole words in two strings.  
class TComp implements Comparator<String> {  
  public int compare(String aStr, String bStr) {  
    int i, j, k;  
  
    // Find index of beginning of last name. 
    i = aStr.lastIndexOf(' ');  
    j = bStr.lastIndexOf(' ');  
  
    k = aStr.substring(i).compareToIgnoreCase(bStr.substring(j));  
    if(k==0) // last names match, check entire name  
      return aStr.compareToIgnoreCase(bStr);  
    else  
      return k;  
  }  
  
  // No need to override equals.  
}  
  
class TreeMapDemo2 {  
  public static void main(String args[]) {  
    // Create a tree map. 
    TreeMap<String, Double> tm = new TreeMap<String, Double>(new TComp());  
      
    // Put elements to the map. 
    tm.put("John Doe", new Double(3434.34));  
    tm.put("Tom Smith", new Double(123.22));  
    tm.put("Jane Baker", new Double(1378.00));  
    tm.put("Tod Hall", new Double(99.22));  
    tm.put("Ralph Smith", new Double(-19.08));  
  
    // Get a set of the entries.  
    Set<Map.Entry<String, Double>> set = tm.entrySet();  
  
    // Display the elements. 
    for(Map.Entry<String, Double> me : set) { 
      System.out.print(me.getKey() + ": ");  
      System.out.println(me.getValue());  
    }  
    System.out.println();  
  
    // Deposit 1000 into John Doe's account. 
    double balance =  tm.get("John Doe");  
    tm.put("John Doe", balance + 1000);  
 
    System.out.println("John Doe's new balance: " +  
      tm.get("John Doe"));  
  }  
}

listing 16
// Use thenComparing() to sort by last, then first name.  
import java.util.*;  
  
// A comparator that compares last names.  
class CompLastNames implements Comparator<String> {  
  public int compare(String aStr, String bStr) {  
    int i, j;  
  
    // Find index of beginning of last name. 
    i = aStr.lastIndexOf(' ');  
    j = bStr.lastIndexOf(' ');  
  
    return aStr.substring(i).compareToIgnoreCase(bStr.substring(j));  
  }  
}  

// Sort by entire name when last names are equal.
class CompThenByFirstName implements Comparator<String> {
  public int compare(String aStr, String bStr) {
    int i, j;  

    return aStr.compareToIgnoreCase(bStr);  
  }  
}
  
class TreeMapDemo2A {  
  public static void main(String args[]) {  
    // Use thenComparing() to create a comparator that compares
    // last names, then compares entire name when last names match.
    CompLastNames compLN = new CompLastNames();
    Comparator<String> compLastThenFirst =
                         compLN.thenComparing(new CompThenByFirstName());

    // Create a tree map. 
    TreeMap<String, Double> tm =
                         new TreeMap<String, Double>(compLastThenFirst);  
      
    // Put elements to the map. 
    tm.put("John Doe", new Double(3434.34));  
    tm.put("Tom Smith", new Double(123.22));  
    tm.put("Jane Baker", new Double(1378.00));  
    tm.put("Tod Hall", new Double(99.22));  
    tm.put("Ralph Smith", new Double(-19.08));  

    // Get a set of the entries.  
    Set<Map.Entry<String, Double>> set = tm.entrySet();  
  
    // Display the elements. 
    for(Map.Entry<String, Double> me : set) { 
      System.out.print(me.getKey() + ": ");  
      System.out.println(me.getValue());  
    }  
    System.out.println();  
  
    // Deposit 1000 into John Doe's account. 
    double balance =  tm.get("John Doe");  
    tm.put("John Doe", balance + 1000);  
 
    System.out.println("John Doe's new balance: " +  
      tm.get("John Doe"));  
  }  
}

listing 17
// Demonstrate various algorithms.  
import java.util.*;  
  
class AlgorithmsDemo {  
  public static void main(String args[]) {  
  
    // Create and initialize linked list. 
    LinkedList<Integer> ll = new LinkedList<Integer>();  
    ll.add(-8);  
    ll.add(20);  
    ll.add(-20);  
    ll.add(8);  
      
    // Create a reverse order comparator. 
    Comparator<Integer> r = Collections.reverseOrder();  
  
    // Sort list by using the comparator. 
    Collections.sort(ll, r);  
  
    System.out.print("List sorted in reverse: ");      
    for(int i : ll) 
      System.out.print(i+ " ");  
 
    System.out.println();  
  
    // Shuffle list. 
    Collections.shuffle(ll);  
  
    // Display randomized list. 
    System.out.print("List shuffled: ");      
    for(int i : ll) 
      System.out.print(i + " ");  
 
    System.out.println();  
  
    System.out.println("Minimum: " + Collections.min(ll));      
    System.out.println("Maximum: " + Collections.max(ll));          
  }  
}


listing 18
// Demonstrate Arrays  
import java.util.*;  
  
class ArraysDemo {  
  public static void main(String args[]) {  
  
    // Allocate and initialize array. 
    int array[] = new int[10];  
    for(int i = 0; i < 10; i++)  
      array[i] = -3 * i;  
  
    // Display, sort, and display the array. 
    System.out.print("Original contents: ");  
    display(array);  
    Arrays.sort(array);  
    System.out.print("Sorted: ");  
    display(array);  
  
    // Fill and display the array. 
    Arrays.fill(array, 2, 6, -1);  
    System.out.print("After fill(): ");  
    display(array);  
  
    // Sort and display the array. 
    Arrays.sort(array);  
    System.out.print("After sorting again: ");  
    display(array);  
  
    // Binary search for -9. 
    System.out.print("The value -9 is at location ");  
    int index =   
      Arrays.binarySearch(array, -9);  
 
    System.out.println(index);  
  }  
  
  static void display(int array[]) {  
    for(int i: array) 
      System.out.print(i + " ");  
 
    System.out.println();  
  }  
}

listing 19
// Demonstrate various Vector operations. 
import java.util.*; 
 
class VectorDemo { 
  public static void main(String args[]) { 
 
    // initial size is 3, increment is 2 
    Vector<Integer> v = new Vector<Integer>(3, 2); 
 
    System.out.println("Initial size: " + v.size()); 
    System.out.println("Initial capacity: " + 
                       v.capacity()); 
 
    v.addElement(1); 
    v.addElement(2); 
    v.addElement(3); 
    v.addElement(4); 
 
    System.out.println("Capacity after four additions: " + 
                       v.capacity()); 
    v.addElement(5); 
    System.out.println("Current capacity: " + 
                       v.capacity()); 
    v.addElement(6); 
    v.addElement(7); 
 
    System.out.println("Current capacity: " + 
                       v.capacity()); 
    v.addElement(9); 
    v.addElement(10); 
 
    System.out.println("Current capacity: " + 
                       v.capacity()); 
    v.addElement(11); 
    v.addElement(12); 
 
 
    System.out.println("First element: " + v.firstElement()); 
    System.out.println("Last element: " + v.lastElement()); 
 
    if(v.contains(3)) 
      System.out.println("Vector contains 3."); 
 
    // Enumerate the elements in the vector. 
    Enumeration<Integer> vEnum = v.elements(); 
 
    System.out.println("\nElements in vector:"); 
    while(vEnum.hasMoreElements()) 
      System.out.print(vEnum.nextElement() + " "); 
    System.out.println(); 
  } 
}

listing 20
// Use an iterator to display contents. 
Iterator<Integer> vItr = v.iterator(); 
 
System.out.println("\nElements in vector:"); 
while(vItr.hasNext())  
  System.out.print(vItr.next() + " "); 
System.out.println();

listing 21
// Use an enhanced for loop to display contents.   
System.out.println("\nElements in vector:");  
for(int i : v) 
  System.out.print(i + " ");  
 
System.out.println();

listing 22
// Demonstrate the Stack class. 
import java.util.*; 
  
class StackDemo { 
  static void showpush(Stack<Integer> st, int a) { 
    st.push(a); 
    System.out.println("push(" + a + ")"); 
    System.out.println("stack: " + st); 
  } 
 
  static void showpop(Stack<Integer> st) { 
    System.out.print("pop -> "); 
    Integer a = st.pop(); 
    System.out.println(a); 
    System.out.println("stack: " + st); 
  } 
 
  public static void main(String args[]) { 
    Stack<Integer> st = new Stack<Integer>(); 
 
    System.out.println("stack: " + st); 
    showpush(st, 42); 
    showpush(st, 66); 
    showpush(st, 99); 
    showpop(st); 
    showpop(st); 
    showpop(st); 
 
    try { 
      showpop(st); 
    } catch (EmptyStackException e) { 
      System.out.println("empty stack"); 
    } 
  } 
}

listing 23
// Demonstrate a Hashtable. 
import java.util.*; 
  
class HTDemo { 
  public static void main(String args[]) { 
    Hashtable<String, Double> balance = 
      new Hashtable<String, Double>(); 
 
    Enumeration<String> names; 
    String str; 
    double bal; 
 
    balance.put("John Doe", 3434.34); 
    balance.put("Tom Smith", 123.22); 
    balance.put("Jane Baker", 1378.00); 
    balance.put("Tod Hall", 99.22); 
    balance.put("Ralph Smith", -19.08); 
 
    // Show all balances in hashtable. 
    names = balance.keys(); 
    while(names.hasMoreElements()) { 
      str = names.nextElement(); 
      System.out.println(str + ": " + 
                         balance.get(str)); 
    } 
 
    System.out.println(); 
 
    // Deposit 1,000 into John Doe's account. 
    bal = balance.get("John Doe"); 
    balance.put("John Doe", bal+1000); 
    System.out.println("John Doe's new balance: " + 
                       balance.get("John Doe")); 
  } 
}

listing 24
// Use iterators with a Hashtable. 
import java.util.*; 
 
class HTDemo2 { 
  public static void main(String args[]) { 
    Hashtable<String, Double> balance = 
      new Hashtable<String, Double>(); 
 
    String str; 
    double bal; 
 
    balance.put("John Doe", 3434.34); 
    balance.put("Tom Smith", 123.22); 
    balance.put("Jane Baker", 1378.00); 
    balance.put("Tod Hall", 99.22); 
    balance.put("Ralph Smith", -19.08); 
 
    // Show all balances in hashtable. 
    // First, get a set view of the keys. 
    Set<String> set = balance.keySet(); 
 
    // Get an iterator. 
    Iterator<String> itr = set.iterator(); 
    while(itr.hasNext()) { 
      str = itr.next(); 
      System.out.println(str + ": " + 
                         balance.get(str)); 
    } 
 
    System.out.println(); 
 
    // Deposit 1,000 into John Doe's account. 
    bal = balance.get("John Doe"); 
    balance.put("John Doe", bal+1000); 
    System.out.println("John Doe's new balance: " + 
                       balance.get("John Doe")); 
  } 
}

listing 25
// Demonstrate a Property list.  
import java.util.*;  
   
class PropDemo {  
  public static void main(String args[]) {  
    Properties capitals = new Properties();  
  
    capitals.put("Illinois", "Springfield");  
    capitals.put("Missouri", "Jefferson City");  
    capitals.put("Washington", "Olympia");  
    capitals.put("California", "Sacramento");  
    capitals.put("Indiana", "Indianapolis");  
  
    // Get a set-view of the keys. 
    Set<?> states = capitals.keySet(); 
  
    // Show all of the states and capitals. 
    for(Object name : states)  
      System.out.println("The capital of " +  
                         name + " is " +  
                         capitals.getProperty((String)name)  
                         + ".");  
  
    System.out.println();  
  
    // Look for state not in list -- specify default. 
    String str = capitals.getProperty("Florida", "Not Found");  
    System.out.println("The capital of Florida is "  
                       + str + ".");  
  }  
}

listing 26
// Use a default property list.  
import java.util.*;  
   
class PropDemoDef {  
  public static void main(String args[]) {  
    Properties defList = new Properties();  
    defList.put("Florida", "Tallahassee");  
    defList.put("Wisconsin", "Madison");  
  
    Properties capitals = new Properties(defList);  
  
    capitals.put("Illinois", "Springfield");  
    capitals.put("Missouri", "Jefferson City");  
    capitals.put("Washington", "Olympia");  
    capitals.put("California", "Sacramento");  
    capitals.put("Indiana", "Indianapolis");  
  
    // Get a set-view of the keys. 
    Set<?> states = capitals.keySet(); 
  
    // Show all of the states and capitals. 
    for(Object name : states)  
      System.out.println("The capital of " +  
                         name + " is " +  
                         capitals.getProperty((String)name)  
                         + ".");  
  
    System.out.println();  
  
    // Florida will now be found in the default list.  
    String str = capitals.getProperty("Florida");  
    System.out.println("The capital of Florida is "  
                       + str + ".");  
  }  
}

listing 27
/* A simple telephone number database that uses 
   a property list. */ 
import java.io.*; 
import java.util.*; 
 
class Phonebook { 
  public static void main(String args[])  
    throws IOException 
  { 
    Properties ht = new Properties(); 
    BufferedReader br = 
      new BufferedReader(new InputStreamReader(System.in)); 
    String name, number; 
    FileInputStream fin = null; 
    boolean changed = false; 
 
    // Try to open phonebook.dat file. 
    try { 
      fin = new FileInputStream("phonebook.dat"); 
    } catch(FileNotFoundException e) { 
      // ignore missing file 
    } 
 
    /* If phonebook file already exists,  
       load existing telephone numbers. */ 
    try { 
      if(fin != null) { 
        ht.load(fin); 
        fin.close(); 
      } 
    } catch(IOException e) { 
      System.out.println("Error reading file."); 
    } 
 
    // Let user enter new names and numbers. 
    do { 
      System.out.println("Enter new name" +  
                         " ('quit' to stop): "); 
      name = br.readLine(); 
      if(name.equals("quit")) continue; 
 
      System.out.println("Enter number: "); 
      number = br.readLine(); 
 
      ht.put(name, number); 
      changed = true; 
    } while(!name.equals("quit")); 
 
    // If phone book data has changed, save it. 
    if(changed) { 
      FileOutputStream fout = new FileOutputStream("phonebook.dat"); 
 
      ht.store(fout, "Telephone Book"); 
      fout.close(); 
    } 
 
    // Look up numbers given a name. 
    do { 
      System.out.println("Enter name to find" + 
                         " ('quit' to quit): "); 
      name = br.readLine(); 
      if(name.equals("quit")) continue; 
 
      number = (String) ht.get(name); 
      System.out.println(number); 
    } while(!name.equals("quit")); 
  } 
}

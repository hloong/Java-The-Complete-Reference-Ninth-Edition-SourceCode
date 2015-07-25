listing 1
// A simple pattern matching demo. 
import java.util.regex.*; 
 
class RegExpr { 
  public static void main(String args[]) { 
    Pattern pat; 
    Matcher mat; 
    boolean found; 
 
    pat = Pattern.compile("Java"); 
    mat = pat.matcher("Java"); 
 
    found = mat.matches(); // check for a match 
 
    System.out.println("Testing Java against Java."); 
    if(found) System.out.println("Matches"); 
    else System.out.println("No Match"); 
 
    System.out.println(); 
 
    System.out.println("Testing Java against Java 8."); 
    mat = pat.matcher("Java 8"); // create a new matcher 
 
    found = mat.matches(); // check for a match 
 
    if(found) System.out.println("Matches"); 
    else System.out.println("No Match"); 
  } 
}

listing 2
// Use find() to find a subsequence. 
import java.util.regex.*; 
 
class RegExpr2 { 
  public static void main(String args[]) { 
    Pattern pat = Pattern.compile("Java"); 
    Matcher mat = pat.matcher("Java 8"); 
 
    System.out.println("Looking for Java in Java 8."); 
 
    if(mat.find()) System.out.println("subsequence found"); 
    else System.out.println("No Match"); 
  } 
}

listing 3
// Use find() to find multiple subsequences. 
import java.util.regex.*; 
 
class RegExpr3 { 
  public static void main(String args[]) { 
    Pattern pat = Pattern.compile("test"); 
    Matcher mat = pat.matcher("test 1 2 3 test"); 
 
    while(mat.find()) { 
      System.out.println("test found at index " + 
                         mat.start()); 
    } 
  } 
}

listing 4
// Use a quantifier. 
import java.util.regex.*; 
 
class RegExpr4 { 
  public static void main(String args[]) { 
    Pattern pat = Pattern.compile("W+"); 
    Matcher mat = pat.matcher("W WW WWW"); 
 
    while(mat.find()) 
      System.out.println("Match: " + mat.group());  
  } 
}

listing 5
// Use wildcard and quantifier. 
import java.util.regex.*; 
 
class RegExpr5 { 
  public static void main(String args[]) { 
    Pattern pat = Pattern.compile("e.+d"); 
    Matcher mat = pat.matcher("extend cup end table"); 
 
    while(mat.find()) 
      System.out.println("Match: " + mat.group());  
  } 
}

listing 6
// Use the ? quantifier. 
import java.util.regex.*; 
 
class RegExpr6 { 
  public static void main(String args[]) { 
    // Use reluctant matching behavoir. 
    Pattern pat = Pattern.compile("e.+?d"); 
    Matcher mat = pat.matcher("extend cup end table"); 
 
    while(mat.find()) 
      System.out.println("Match: " + mat.group());  
  } 
}

listing 7
// Use a character class. 
import java.util.regex.*; 
 
class RegExpr7 { 
  public static void main(String args[]) { 
    // Match lowercase words. 
    Pattern pat = Pattern.compile("[a-z]+"); 
    Matcher mat = pat.matcher("this is a test."); 
 
    while(mat.find()) 
      System.out.println("Match: " + mat.group());  
  } 
}

listing 8
// Use replaceAll(). 
import java.util.regex.*; 
 
class RegExpr8 { 
  public static void main(String args[]) { 
    String str = "Jon Jonathan Frank Ken Todd"; 
 
    Pattern pat = Pattern.compile("Jon.*? "); 
    Matcher mat = pat.matcher(str); 
 
    System.out.println("Original sequence: " + str); 
 
    str = mat.replaceAll("Eric "); 
 
    System.out.println("Modified sequence: " + str); 
 
  } 
}

listing 9
// Use split(). 
import java.util.regex.*; 
 
class RegExpr9 { 
  public static void main(String args[]) { 
 
    // Match lowercase words. 
    Pattern pat = Pattern.compile("[ ,.!]"); 
 
    String strs[] = pat.split("one two,alpha9 12!done."); 
 
    for(int i=0; i < strs.length; i++) 
      System.out.println("Next token: " + strs[i]); 
 
  } 
}

listing 10
// Demonstrate reflection.
import java.lang.reflect.*;
public class ReflectionDemo1 {
  public static void main(String args[]) {
    try {
      Class<?> c = Class.forName("java.awt.Dimension");
      System.out.println("Constructors:");
      Constructor<?> constructors[] = c.getConstructors();
      for(int i = 0; i < constructors.length; i++) {
        System.out.println(" " + constructors[i]);
      }

      System.out.println("Fields:");
      Field fields[] = c.getFields();
      for(int i = 0; i < fields.length; i++) {
        System.out.println(" " + fields[i]);
      }

      System.out.println("Methods:");
      Method methods[] = c.getMethods();
      for(int i = 0; i < methods.length; i++) {
        System.out.println(" " + methods[i]);
      }
    }
    catch(Exception e) {
      System.out.println("Exception: " + e);
    }
  }
}

listing 11
// Show public methods.
import java.lang.reflect.*;
public class ReflectionDemo2 {
  public static void main(String args[]) {
    try {
      A a = new A();
      Class<?> c = a.getClass();
      System.out.println("Public Methods:");
      Method methods[] = c.getDeclaredMethods();
      for(int i = 0; i < methods.length; i++) {
        int modifiers = methods[i].getModifiers();
        if(Modifier.isPublic(modifiers)) {
          System.out.println(" " + methods[i].getName());
        }
      }
    }
    catch(Exception e) {
      System.out.println("Exception: " + e);
    }
  }
}

class A {
  public void a1() {
  }
  public void a2() {
  }
  protected void a3() {
  }
  private void a4() {
  }
}

listing 12
import java.rmi.*;
public interface AddServerIntf extends Remote {
  double add(double d1, double d2) throws RemoteException;
}

listing 13
import java.rmi.*;
import java.rmi.server.*;
public class AddServerImpl extends UnicastRemoteObject
  implements AddServerIntf {

  public AddServerImpl() throws RemoteException {
  }
  public double add(double d1, double d2) throws RemoteException {
    return d1 + d2;
  }
}

listing 14
import java.net.*;
import java.rmi.*;
public class AddServer {
  public static void main(String args[]) {
    try {
      AddServerImpl addServerImpl = new AddServerImpl();
      Naming.rebind("AddServer", addServerImpl);
    }
    catch(Exception e) {
      System.out.println("Exception: " + e);
    }
  }
}

listing 15
import java.rmi.*;
public class AddClient {
  public static void main(String args[]) {
    try {
      String addServerURL = "rmi://" + args[0] + "/AddServer";
      AddServerIntf addServerIntf =
                    (AddServerIntf)Naming.lookup(addServerURL);
      System.out.println("The first number is: " + args[1]);
      double d1 = Double.valueOf(args[1]).doubleValue();
      System.out.println("The second number is: " + args[2]);

      double d2 = Double.valueOf(args[2]).doubleValue();
      System.out.println("The sum is: " + addServerIntf.add(d1, d2));
    }
    catch(Exception e) {
      System.out.println("Exception: " + e);
    }
  }
}

listing 16
// Demonstrate date formats.
import java.text.*;
import java.util.*;

public class DateFormatDemo {
  public static void main(String args[]) {
    Date date = new Date();
    DateFormat df;

    df = DateFormat.getDateInstance(DateFormat.SHORT, Locale.JAPAN);
    System.out.println("Japan: " + df.format(date));

    df = DateFormat.getDateInstance(DateFormat.MEDIUM, Locale.KOREA);
    System.out.println("Korea: " + df.format(date));

    df = DateFormat.getDateInstance(DateFormat.LONG, Locale.UK);
    System.out.println("United Kingdom: " + df.format(date));

    df = DateFormat.getDateInstance(DateFormat.FULL, Locale.US);
    System.out.println("United States: " + df.format(date));
  }
}

listing 17
// Demonstrate time formats.
import java.text.*;
import java.util.*;
public class TimeFormatDemo {
  public static void main(String args[]) {
    Date date = new Date();
    DateFormat df;

    df = DateFormat.getTimeInstance(DateFormat.SHORT, Locale.JAPAN);
    System.out.println("Japan: " + df.format(date));

    df = DateFormat.getTimeInstance(DateFormat.LONG, Locale.UK);
    System.out.println("United Kingdom: " + df.format(date));

    df = DateFormat.getTimeInstance(DateFormat.FULL, Locale.CANADA);
    System.out.println("Canada: " + df.format(date));
  }
}

listing 18
// Demonstrate SimpleDateFormat.
import java.text.*;
import java.util.*;

public class SimpleDateFormatDemo {
  public static void main(String args[]) {
    Date date = new Date();
    SimpleDateFormat sdf;
    sdf = new SimpleDateFormat("hh:mm:ss");
    System.out.println(sdf.format(date));
    sdf = new SimpleDateFormat("dd MMM yyyy hh:mm:ss zzz");
    System.out.println(sdf.format(date));
    sdf = new SimpleDateFormat("E MMM dd yyyy");
    System.out.println(sdf.format(date));
  }
}

listing 19
// A Simple example of LocalDate and LocalTime. 
import java.time.*; 
 
class DateTimeDemo { 
  public static void main(String args[]) { 
 
    LocalDate curDate = LocalDate.now(); 
    System.out.println(curDate); 
 
    LocalTime curTime = LocalTime.now(); 
    System.out.println(curTime); 
  } 
}

listing 20
// Demonstrate DateTimeFormatter. 
import java.time.*; 
import java.time.format.*; 
 
class DateTimeDemo2 { 
  public static void main(String args[]) { 
 
    LocalDate curDate = LocalDate.now(); 
    System.out.println(curDate.format( 
           DateTimeFormatter.ofLocalizedDate(FormatStyle.FULL))); 
 
    LocalTime curTime = LocalTime.now(); 
    System.out.println(curTime.format( 
           DateTimeFormatter.ofLocalizedTime(FormatStyle.SHORT))); 
  } 
}

listing 21
// Create a custom date and time format. 
import java.time.*; 
import java.time.format.*; 
 
class DateTimeDemo3 { 
  public static void main(String args[]) { 
 
    LocalDateTime curDateTime = LocalDateTime.now(); 
    System.out.println(curDateTime.format( 
               DateTimeFormatter.ofPattern("MMMM d',' yyyy h':'mm a"))); 
  } 
}

listing 22
// Parse a date and time. 
import java.time.*; 
import java.time.format.*; 
 
class DateTimeDemo4 { 
  public static void main(String args[]) { 
 
    // Obtain a LocalDateTime object by parsing a date and time string. 
    LocalDateTime curDateTime = 
         LocalDateTime.parse("June 21, 2014 12:01 AM", 
                  DateTimeFormatter.ofPattern("MMMM d',' yyyy hh':'mm a")); 
 
     // Now, display the parsed date and time. 
    System.out.println(curDateTime.format( 
               DateTimeFormatter.ofPattern("MMMM d',' yyyy h':'mm a"))); 
  } 
}


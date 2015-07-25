listing 1
// Demonstrate StringTokenizer.
import java.util.StringTokenizer;

class STDemo {
  static String in = "title=Java: The Complete Reference;" +
    "author=Schildt;" +
    "publisher=McGraw-Hill;" +
    "copyright=2014";

  public static void main(String args[]) {
    StringTokenizer st = new StringTokenizer(in, "=;");

    while(st.hasMoreTokens()) {
      String key = st.nextToken();
      String val = st.nextToken();
      System.out.println(key + "\t" + val);
    }
  }
}

listing 2
// BitSet Demonstration.
import java.util.BitSet;

class BitSetDemo {
  public static void main(String args[]) {
    BitSet bits1 = new BitSet(16);
    BitSet bits2 = new BitSet(16);

    // set some bits
    for(int i=0; i<16; i++) {
      if((i%2) == 0) bits1.set(i);
      if((i%5) != 0) bits2.set(i);
    }

    System.out.println("Initial pattern in bits1: ");
    System.out.println(bits1);
    System.out.println("\nInitial pattern in bits2: ");
    System.out.println(bits2);

    // AND bits
    bits2.and(bits1);
    System.out.println("\nbits2 AND bits1: ");
    System.out.println(bits2);

    // OR bits
    bits2.or(bits1);
    System.out.println("\nbits2 OR bits1: ");
    System.out.println(bits2);

    // XOR bits
    bits2.xor(bits1);
    System.out.println("\nbits2 XOR bits1: ");
    System.out.println(bits2);
  }
}

listing 3
// Demonstrate Optional<T>.

import java.util.*;

class OptionalDemo {
  public static void main(String args[]) {

    Optional<String> noVal = Optional.empty();

    Optional<String> hasVal = Optional.of("ABCDEFG");    

    if(noVal.isPresent()) System.out.println("This won't be displayed");
    else System.out.println("noVal has no value");

    if(hasVal.isPresent()) System.out.println("The string in hasVal is: " +
                                               hasVal.get());

    String defStr = noVal.orElse("Default String");
    System.out.println(defStr);
  }
}

listing 4
// Show date and time using only Date methods.
import java.util.Date;

class DateDemo {
  public static void main(String args[]) {
    // Instantiate a Date object
    Date date = new Date();
    
    // display time and date using toString()
    System.out.println(date);

    // Display number of milliseconds since midnight, January 1, 1970 GMT
    long msec = date.getTime();
    System.out.println("Milliseconds since Jan. 1, 1970 GMT = " + msec);
  }
}

listing 5
// Demonstrate Calendar
import java.util.Calendar;

class CalendarDemo {
  public static void main(String args[]) {
    String months[] = {
             "Jan", "Feb", "Mar", "Apr", 
             "May", "Jun", "Jul", "Aug",
             "Sep", "Oct", "Nov", "Dec"};

    // Create a calendar initialized with the
    // current date and time in the default
    // locale and timezone.
    Calendar calendar = Calendar.getInstance();

    // Display current time and date information.
    System.out.print("Date: ");
    System.out.print(months[calendar.get(Calendar.MONTH)]);
    System.out.print(" " + calendar.get(Calendar.DATE) + " ");
    System.out.println(calendar.get(Calendar.YEAR));

    System.out.print("Time: ");
    System.out.print(calendar.get(Calendar.HOUR) + ":");
    System.out.print(calendar.get(Calendar.MINUTE) + ":");
    System.out.println(calendar.get(Calendar.SECOND));

    // Set the time and date information and display it.
    calendar.set(Calendar.HOUR, 10);
    calendar.set(Calendar.MINUTE, 29);
    calendar.set(Calendar.SECOND, 22);

    System.out.print("Updated time: ");
    System.out.print(calendar.get(Calendar.HOUR) + ":");
    System.out.print(calendar.get(Calendar.MINUTE) + ":");
    System.out.println(calendar.get(Calendar.SECOND));
  }
}

listing 6
// Demonstrate GregorianCalendar
import java.util.*;

class GregorianCalendarDemo {
  public static void main(String args[]) {
    String months[] = {
             "Jan", "Feb", "Mar", "Apr", 
             "May", "Jun", "Jul", "Aug",
             "Sep", "Oct", "Nov", "Dec"};
    int year;

    // Create a Gregorian calendar initialized 
    // with the current date and time in the
    // default locale and timezone.
    GregorianCalendar gcalendar = new GregorianCalendar();

    // Display current time and date information.
    System.out.print("Date: ");
    System.out.print(months[gcalendar.get(Calendar.MONTH)]);
    System.out.print(" " + gcalendar.get(Calendar.DATE) + " ");
    System.out.println(year = gcalendar.get(Calendar.YEAR));

    System.out.print("Time: ");
    System.out.print(gcalendar.get(Calendar.HOUR) + ":");
    System.out.print(gcalendar.get(Calendar.MINUTE) + ":");
    System.out.println(gcalendar.get(Calendar.SECOND));

    // Test if the current year is a leap year
    if(gcalendar.isLeapYear(year)) {
      System.out.println("The current year is a leap year");
    }
    else {
      System.out.println("The current year is not a leap year");
    }
  }
}

listing 7
// Demonstrate random Gaussian values.
import java.util.Random;

class RandDemo {
  public static void main(String args[]) {
    Random r = new Random();
    double val;
    double sum = 0;
    int bell[] = new int[10];

    for(int i=0; i<100; i++) {
      val = r.nextGaussian();
      sum += val;
      double t = -2;
      for(int x=0; x<10; x++, t += 0.5)
        if(val < t) {
          bell[x]++;
          break;
        }
    }
    System.out.println("Average of values: " +
                        (sum/100));

    // display bell curve, sideways
    for(int i=0; i<10; i++) {
      for(int x=bell[i]; x>0; x--)
        System.out.print("*");
      System.out.println();
    }
  }
}

listing 8
/* Demonstrate the Observable class and the
   Observer interface.
*/

import java.util.*;

// This is the observing class.
class Watcher implements Observer {
  public void update(Observable obj, Object arg) {
    System.out.println("update() called, count is " +
                       ((Integer)arg).intValue());
  }
}

// This is the class being observed.
class BeingWatched extends Observable {
  void counter(int period) {
    for( ; period >=0; period--) {
      setChanged();
      notifyObservers(new Integer(period));
      try {
        Thread.sleep(100);
      } catch(InterruptedException e) {
        System.out.println("Sleep interrupted");
      }
    }
  }

}

class ObserverDemo {
  public static void main(String args[]) {
    BeingWatched observed = new BeingWatched();
    Watcher observing = new Watcher();

    /* Add the observing to the list of observers for
       observed object.  */
    observed.addObserver(observing);

    observed.counter(10);
  }
}

listing 9
/* An object may be observed by two or more
   observers.
*/

import java.util.*;

// This is the first observing class.
class Watcher1 implements Observer {
  public void update(Observable obj, Object arg) {
    System.out.println("update() called, count is " +
                       ((Integer)arg).intValue());
  }
}

// This is the second observing class.
class Watcher2 implements Observer {
  public void update(Observable obj, Object arg) {
    // Ring bell when done
    if(((Integer)arg).intValue() == 0)
      System.out.println("Done" + '\7');
  }
}

// This is the class being observed.
class BeingWatched extends Observable {
  void counter(int period) {
    for( ; period >=0; period--) {
      setChanged();
      notifyObservers(new Integer(period));
      try {
        Thread.sleep(100);
      } catch(InterruptedException e) {
        System.out.println("Sleep interrupted");
      }
    }
  }
}

class TwoObservers {
  public static void main(String args[]) {
    BeingWatched observed = new BeingWatched();
    Watcher1 observing1 = new Watcher1();
    Watcher2 observing2 = new Watcher2();

    // add both observers
    observed.addObserver(observing1);
    observed.addObserver(observing2);

    observed.counter(10);
  }
}

listing 10
// Demonstrate Timer and TimerTask.

import java.util.*;

class MyTimerTask extends TimerTask {
  public void run() {
    System.out.println("Timer task executed.");
  }
}

class TTest {
  public static void main(String args[]) {
    MyTimerTask myTask = new MyTimerTask();
    Timer myTimer = new Timer();

    /* Set an initial delay of 1 second,
       then repeat every half second.
    */
    myTimer.schedule(myTask, 1000, 500);
    
    try {
      Thread.sleep(5000);
    } catch (InterruptedException exc) {}

    myTimer.cancel();
  }
}

listing 11
// Demonstrate Currency.
import java.util.*;

class CurDemo {
  public static void main(String args[]) {
    Currency c;

    c = Currency.getInstance(Locale.US);

    System.out.println("Symbol: " + c.getSymbol());
    System.out.println("Default fractional digits: " +
                       c.getDefaultFractionDigits());
  }
}

listing 12
// A very simple example that uses Formatter. 
import java.util.*; 
 
class FormatDemo { 
  public static void main(String args[]) { 
    Formatter fmt = new Formatter(); 
 
    fmt.format("Formatting %s is easy %d %f", "with Java", 10, 98.6); 
 
    System.out.println(fmt); 

    fmt.close();
  } 
}

listing 13
// Demonstrate the %f and %e format specifiers. 
import java.util.*; 
 
class FormatDemo2 { 
  public static void main(String args[]) { 
    Formatter fmt = new Formatter(); 
 
    for(double i=1.23; i < 1.0e+6; i *= 100) { 
      fmt.format("%f %e", i, i); 
      System.out.println(fmt); 
    } 
    fmt.close(); 
  } 
}

listing 14
// Formatting time and date. 
import java.util.*; 
 
class TimeDateFormat { 
  public static void main(String args[]) { 
    Formatter fmt = new Formatter(); 
    Calendar cal = Calendar.getInstance(); 
 
    // Display standard 12-hour time format. 
    fmt.format("%tr", cal); 
    System.out.println(fmt); 
    fmt.close();
 
    // Display complete time and date information. 
    fmt = new Formatter(); 
    fmt.format("%tc", cal); 
    System.out.println(fmt); 
    fmt.close();
 
    // Display just hour and minute. 
    fmt = new Formatter(); 
    fmt.format("%tl:%tM", cal, cal); 
    System.out.println(fmt); 
    fmt.close();
 
    // Display month by name and number. 
    fmt = new Formatter(); 
    fmt.format("%tB %tb %tm", cal, cal, cal); 
    System.out.println(fmt); 
    fmt.close();
  } 
}

listing 15
// Demonstrate the %n and %% format specifiers. 
import java.util.*; 
 
class FormatDemo3 { 
  public static void main(String args[]) { 
    Formatter fmt = new Formatter(); 
 
    fmt.format("Copying file%nTransfer is %d%% complete", 88); 
    System.out.println(fmt); 
    fmt.close();
  } 
}

listing 16
// Demonstrate a field-width specifier. 
import java.util.*; 
 
class FormatDemo4 { 
  public static void main(String args[]) { 
    Formatter fmt = new Formatter(); 
 
    fmt.format("|%f|%n|%12f|%n|%012f|", 
               10.12345, 10.12345, 10.12345); 
 
    System.out.println(fmt); 

    fmt.close(); 
  } 
}

listing 17
// Create a table of squares and cubes. 
import java.util.*; 
 
class FieldWidthDemo { 
  public static void main(String args[]) { 
    Formatter fmt; 
  
    for(int i=1; i <= 10; i++) { 
      fmt = new Formatter(); 
 
      fmt.format("%4d %4d %4d", i, i*i, i*i*i); 
      System.out.println(fmt); 
      fmt.close(); 
    } 
  } 
}

listing 18
// Demonstrate the precision modifier. 
import java.util.*; 
 
class PrecisionDemo { 
  public static void main(String args[]) { 
    Formatter fmt = new Formatter(); 
 
    // Format 4 decimal places. 
    fmt.format("%.4f", 123.1234567); 
    System.out.println(fmt); 
    fmt.close();
 
    // Format to 2 decimal places in a 16 character field. 
    fmt = new Formatter(); 
    fmt.format("%16.2e", 123.1234567); 
    System.out.println(fmt); 
    fmt.close();
 
    // Display at most 15 characters in a string. 
    fmt = new Formatter(); 
    fmt.format("%.15s", "Formatting with Java is now easy."); 
    System.out.println(fmt); 
    fmt.close();
  } 
}

listing 19
// Demonstrate left justification. 
import java.util.*; 
 
class LeftJustify { 
  public static void main(String args[]) { 
    Formatter fmt = new Formatter(); 
 
    // Right justify by default 
    fmt.format("|%10.2f|", 123.123); 
    System.out.println(fmt); 
    fmt.close();
 
    // Now, left justify. 
    fmt = new Formatter(); 
    fmt.format("|%-10.2f|", 123.123); 
    System.out.println(fmt); 
    fmt.close();
  } 
}

listing 20
// Demonstrate the space format specifiers. 
import java.util.*; 
 
class FormatDemo5 { 
  public static void main(String args[]) { 
    Formatter fmt = new Formatter(); 
 
    fmt.format("% d", -100); 
    System.out.println(fmt); 
    fmt.close();
 
    fmt = new Formatter(); 
    fmt.format("% d", 100); 
    System.out.println(fmt); 
    fmt.close();
 
    fmt = new Formatter(); 
    fmt.format("% d", -200); 
    System.out.println(fmt); 
    fmt.close();
 
    fmt = new Formatter(); 
    fmt.format("% d", 200); 
    System.out.println(fmt); 
    fmt.close();
  } 
}

listing 21
// Use arguments indexes to simplify the 
// creation of a custom time and date format. 
import java.util.*; 
 
class FormatDemo6 { 
  public static void main(String args[]) { 
    Formatter fmt = new Formatter(); 
    Calendar cal = Calendar.getInstance(); 
 
    fmt.format("Today is day %te of %<tB, %<tY", cal); 
    System.out.println(fmt); 
    fmt.close();
  } 
}

listing 22
// Use automatic resource management with Formatter.
import java.util.*; 
 
class FormatDemo { 
  public static void main(String args[]) { 

    try (Formatter fmt = new Formatter())
    {
      fmt.format("Formatting %s is easy %d %f", "with Java", 10, 98.6); 
      System.out.println(fmt); 
    }
  } 
}

listing 23
// Use Scanner to compute an average of the values. 
import java.util.*; 
 
class AvgNums { 
  public static void main(String args[]) { 
    Scanner conin = new Scanner(System.in); 
 
    int count = 0; 
    double sum = 0.0; 
 
    System.out.println("Enter numbers to average."); 
 
    // Read and sum numbers. 
    while(conin.hasNext()) { 
      if(conin.hasNextDouble()) { 
        sum += conin.nextDouble(); 
        count++; 
      } 
      else { 
        String str = conin.next();  
        if(str.equals("done")) break; 
        else { 
          System.out.println("Data format error."); 
          return; 
        } 
      } 
    } 
    conin.close(); 
    System.out.println("Average is " + sum / count); 
  } 
}

listing 24
// Use Scanner to compute an average of the values in a file. 
import java.util.*; 
import java.io.*; 
 
class AvgFile { 
  public static void main(String args[]) 
    throws IOException { 
 
    int count = 0; 
    double sum = 0.0; 
 
    // Write output to a file. 
    FileWriter fout = new FileWriter("test.txt"); 
    fout.write("2 3.4 5 6 7.4 9.1 10.5 done"); 
    fout.close(); 
 
    FileReader fin = new FileReader("Test.txt"); 
 
    Scanner src = new Scanner(fin); 
 
    // Read and sum numbers. 
    while(src.hasNext()) { 
      if(src.hasNextDouble()) { 
        sum += src.nextDouble(); 
        count++; 
      } 
      else { 
        String str = src.next();  
        if(str.equals("done")) break; 
        else { 
          System.out.println("File format error."); 
          return; 
        } 
      } 
    } 
 
    src.close(); 
    System.out.println("Average is " + sum / count); 
  } 
}

listing 25
// Use Scanner to read various types of data from a file. 
import java.util.*; 
import java.io.*; 
 
class ScanMixed { 
  public static void main(String args[]) 
    throws IOException { 
 
    int i; 
    double d; 
    boolean b; 
    String str; 
 
    // Write output to a file. 
    FileWriter fout = new FileWriter("test.txt"); 
    fout.write("Testing Scanner 10 12.2 one true two false"); 
    fout.close(); 
 
    FileReader fin = new FileReader("Test.txt"); 
 
    Scanner src = new Scanner(fin); 
 
 
    // Read to end. 
    while(src.hasNext()) { 
      if(src.hasNextInt()) { 
        i = src.nextInt(); 
        System.out.println("int: " + i); 
      } 
      else if(src.hasNextDouble()) { 
        d = src.nextDouble(); 
        System.out.println("double: " + d); 
      } 
      else if(src.hasNextBoolean()) { 
        b = src.nextBoolean(); 
        System.out.println("boolean: " + b); 
      } 
      else { 
        str = src.next(); 
        System.out.println("String: " + str); 
      } 
    } 
 
    src.close(); 
  } 
}

listing 26
// Use Scanner to compute an average a list of 
// comma-separated values.  
import java.util.*; 
import java.io.*; 
 
class SetDelimiters { 
  public static void main(String args[]) 
    throws IOException { 
 
    int count = 0; 
    double sum = 0.0; 
 
    // Write output to a file. 
    FileWriter fout = new FileWriter("test.txt"); 
 
    // Now, store values in comma-separated list. 
    fout.write("2, 3.4,    5,6, 7.4, 9.1, 10.5, done"); 
    fout.close(); 
 
    FileReader fin = new FileReader("Test.txt"); 
 
    Scanner src = new Scanner(fin); 
 
    // Set delimiters to space and comma. 
    src.useDelimiter(", *"); 
 
    // Read and sum numbers. 
    while(src.hasNext()) { 
      if(src.hasNextDouble()) { 
        sum += src.nextDouble(); 
        count++; 
      } 
      else { 
        String str = src.next();  
        if(str.equals("done")) break; 
        else { 
          System.out.println("File format error."); 
          return; 
        } 
      } 
    } 
 
    src.close(); 
    System.out.println("Average is " + sum / count); 
  } 
}

listing 27
// Demonstrate findInLine(). 
import java.util.*; 
 
class FindInLineDemo { 
  public static void main(String args[]) { 
    String instr = "Name: Tom Age: 28 ID: 77"; 
 
    Scanner conin = new Scanner(instr); 
 
    // Find and display age. 
    conin.findInLine("Age:"); // find Age 
 
    if(conin.hasNext()) 
      System.out.println(conin.next()); 
    else 
      System.out.println("Error!"); 

    conin.close();
  } 
}

listing 28
import java.util.*;

// Default version (English).
public class SampleRB extends ListResourceBundle {
  protected Object[][] getContents() {
    Object[][] resources = new Object[3][2];

    resources[0][0] = "title";
    resources[0][1] = "My Program";

    resources[1][0] = "StopText";
    resources[1][1] = "Stop";

    resources[2][0] = "StartText";
    resources[2][1] = "Start";
  
    return resources;
  }
}

listing 29
import java.util.*;

// German version.
public class SampleRB_de extends ListResourceBundle {
  protected Object[][] getContents() {
    Object[][] resources = new Object[3][2];

    resources[0][0] = "title";
    resources[0][1] = "Mein Programm";

    resources[1][0] = "StopText";
    resources[1][1] = "Anschlag";

    resources[2][0] = "StartText";
    resources[2][1] = "Anfang";
  
    return resources;
  }
}

listing 30
// Demonstrate a resource bundle.
import java.util.*; 

class LRBDemo { 
  public static void main(String args[]) { 
    ResourceBundle rd = ResourceBundle.getBundle("SampleRB");

    System.out.println("English version: ");
    System.out.println("String for Title key : " +
                       rd.getString("title"));

    System.out.println("String for StopText key: " +
                       rd.getString("StopText"));

    System.out.println("String for StartText key: " +
                       rd.getString("StartText"));

    rd = ResourceBundle.getBundle("SampleRB", Locale.GERMAN);

    System.out.println("\nGerman version: ");
    System.out.println("String for Title key : " +
                       rd.getString("title"));

    System.out.println("String for StopText key: " +
                       rd.getString("StopText"));

    System.out.println("String for StartText key: " +
                       rd.getString("StartText"));
  } 
}
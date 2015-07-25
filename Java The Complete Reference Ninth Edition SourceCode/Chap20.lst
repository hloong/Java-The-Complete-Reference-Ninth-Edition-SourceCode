listing 1
// Demonstrate File. 
import java.io.File; 
 
class FileDemo { 
  static void p(String s) { 
    System.out.println(s); 
  } 
 
  public static void main(String args[]) { 
    File f1 = new File("/java/COPYRIGHT"); 
 
    p("File Name: " + f1.getName()); 
    p("Path: " + f1.getPath()); 
    p("Abs Path: " + f1.getAbsolutePath()); 
    p("Parent: " + f1.getParent()); 
    p(f1.exists() ? "exists" : "does not exist"); 
    p(f1.canWrite() ? "is writeable" : "is not writeable"); 
    p(f1.canRead() ? "is readable" : "is not readable"); 
    p("is " + (f1.isDirectory() ? "" : "not" + " a directory")); 
    p(f1.isFile() ? "is normal file" : "might be a named pipe"); 
    p(f1.isAbsolute() ? "is absolute" : "is not absolute"); 
    p("File last modified: " + f1.lastModified()); 
    p("File size: " + f1.length() + " Bytes"); 
  } 
}

listing 2
// Using directories. 
import java.io.File; 
 
class DirList { 
  public static void main(String args[]) { 
    String dirname = "/java"; 
    File f1 = new File(dirname); 
 
    if (f1.isDirectory()) { 
      System.out.println("Directory of " + dirname); 
      String s[] = f1.list(); 
 
      for (int i=0; i < s.length; i++) { 
        File f = new File(dirname + "/" + s[i]); 
        if (f.isDirectory()) { 
          System.out.println(s[i] + " is a directory"); 
        } else { 
          System.out.println(s[i] + " is a file"); 
        } 
      } 
    } else { 
      System.out.println(dirname + " is not a directory"); 
    } 
  } 
}

listing 3
import java.io.*; 
 
public class OnlyExt implements FilenameFilter { 
  String ext; 
 
  public OnlyExt(String ext) { 
    this.ext = "." + ext; 
  } 
 
  public boolean accept(File dir, String name) { 
    return name.endsWith(ext); 
  } 
}

listing 4
// Directory of .HTML files. 
import java.io.*;
class DirListOnly { 
  public static void main(String args[]) { 
    String dirname = "/java"; 
    File f1 = new File(dirname); 
    FilenameFilter only = new OnlyExt("html"); 
    String s[] = f1.list(only);
    for (int i=0; i < s.length; i++) { 
      System.out.println(s[i]); 
    } 
  } 
}

listing 5
// Demonstrate FileInputStream. 
// This program uses try-with-resources. It requires JDK 7 or later. 
 
import java.io.*;  
  
class FileInputStreamDemo {  
  public static void main(String args[]) {  
    int size;  
  
    // Use try-with-resources to close the stream. 
    try ( FileInputStream f = 
           new FileInputStream("FileInputStreamDemo.java") ) { 
  
      System.out.println("Total Available Bytes: " +  
                         (size = f.available()));  
  
      int n = size/40;  
      System.out.println("First " + n +  
                         " bytes of the file one read() at a time");  
      for (int i=0; i < n; i++) {  
        System.out.print((char) f.read());  
      }  
  
      System.out.println("\nStill Available: " + f.available());  
  
      System.out.println("Reading the next " + n +  
                         " with one read(b[])");  
      byte b[] = new byte[n];  
      if (f.read(b) != n) {  
        System.err.println("couldn't read " + n + " bytes.");  
      }  
  
      System.out.println(new String(b, 0, n));  
      System.out.println("\nStill Available: " + (size = f.available()));  
      System.out.println("Skipping half of remaining bytes with skip()");  
      f.skip(size/2);  
      System.out.println("Still Available: " + f.available());  
  
      System.out.println("Reading " + n/2 + " into the end of array");  
      if (f.read(b, n/2, n/2) != n/2) {  
        System.err.println("couldn't read " + n/2 + " bytes.");  
      }  
  
      System.out.println(new String(b, 0, b.length));  
      System.out.println("\nStill Available: " + f.available());  
    } catch(IOException e) {  
      System.out.println("I/O Error: " + e);  
    }  
  }  
}

listing 6
// Demonstrate FileOutputStream. 
// This program uses the traditional approach to closing a file. 
 
import java.io.*; 
 
class FileOutputStreamDemo { 
  public static void main(String args[]) { 
    String source = "Now is the time for all good men\n" 
      + " to come to the aid of their country\n" 
      + " and pay their due taxes."; 
    byte buf[] = source.getBytes(); 
    FileOutputStream f0 = null; 
    FileOutputStream f1 = null; 
    FileOutputStream f2 = null; 
 
    try { 
      f0 = new FileOutputStream("file1.txt"); 
      f1 = new FileOutputStream("file2.txt"); 
      f2 = new FileOutputStream("file3.txt"); 
 
      // write to first file 
      for (int i=0; i < buf.length; i += 2) f0.write(buf[i]);      
 
      // write to second file 
      f1.write(buf); 
 
      // write to third file 
      f2.write(buf, buf.length-buf.length/4, buf.length/4); 
    } catch(IOException e) { 
      System.out.println("An I/O Error Occured"); 
    } finally { 
      try { 
        if(f0 != null) f0.close(); 
      } catch(IOException e) { 
        System.out.println("Error Closing file1.txt"); 
      } 
      try { 
        if(f1 != null) f1.close(); 
      } catch(IOException e) { 
        System.out.println("Error Closing file2.txt"); 
      } 
      try { 
        if(f2 != null) f2.close(); 
      } catch(IOException e) { 
        System.out.println("Error Closing file3.txt"); 
      } 
    } 
  } 
}


listing 7
// Demonstrate FileOutputStream. 
// This version uses try-with-resources. It requires JDK 7 or later. 
 
import java.io.*; 
 
class FileOutputStreamDemo { 
  public static void main(String args[]) { 
    String source = "Now is the time for all good men\n" 
      + " to come to the aid of their country\n" 
      + " and pay their due taxes."; 
    byte buf[] = source.getBytes(); 
 
    // Use try-with-resources to close the files. 
    try (FileOutputStream f0 = new FileOutputStream("file1.txt"); 
         FileOutputStream f1 = new FileOutputStream("file2.txt"); 
         FileOutputStream f2 = new FileOutputStream("file3.txt") ) 
    { 
 
      // write to first file 
      for (int i=0; i < buf.length; i += 2) f0.write(buf[i]);      
 
      // write to second file 
      f1.write(buf); 
 
      // write to third file 
      f2.write(buf, buf.length-buf.length/4, buf.length/4); 
    } catch(IOException e) { 
      System.out.println("An I/O Error Occured"); 
    } 
  } 
}

listing 8
// Demonstrate ByteArrayInputStream. 
import java.io.*; 
 
class ByteArrayInputStreamDemo { 
  public static void main(String args[]) { 
    String tmp = "abcdefghijklmnopqrstuvwxyz"; 
    byte b[] = tmp.getBytes(); 
 
    ByteArrayInputStream input1 = new ByteArrayInputStream(b); 
    ByteArrayInputStream input2 = new ByteArrayInputStream(b,0,3); 
  } 
}

listing 9
import java.io.*; 
 
class ByteArrayInputStreamReset { 
  public static void main(String args[]) { 
    String tmp = "abc"; 
    byte b[] = tmp.getBytes(); 
    ByteArrayInputStream in = new ByteArrayInputStream(b); 
 
    for (int i=0; i<2; i++) { 
      int c; 
      while ((c = in.read()) != -1) { 
        if (i == 0) { 
          System.out.print((char) c); 
        } else { 
          System.out.print(Character.toUpperCase((char) c)); 
        } 
      } 
      System.out.println(); 
      in.reset(); 
    } 
  } 
}

listing 10
// Demonstrate ByteArrayOutputStream. 
// This program uses try-with-resources. It requires JDK 7 or later. 
 
import java.io.*; 
 
class ByteArrayOutputStreamDemo { 
  public static void main(String args[]) { 
    ByteArrayOutputStream f = new ByteArrayOutputStream(); 
    String s = "This should end up in the array"; 
    byte buf[] = s.getBytes(); 
 
    try { 
      f.write(buf); 
    } catch(IOException e) { 
      System.out.println("Error Writing to Buffer"); 
      return; 
    } 
 
    System.out.println("Buffer as a string"); 
    System.out.println(f.toString()); 
    System.out.println("Into array"); 
    byte b[] = f.toByteArray(); 
    for (int i=0; i<b.length; i++) System.out.print((char) b[i]); 
 
    System.out.println("\nTo an OutputStream()"); 
 
    // Use try-with-resources to manage the file stream. 
    try ( FileOutputStream f2 = new FileOutputStream("test.txt") ) 
    { 
      f.writeTo(f2); 
    } catch(IOException e) { 
      System.out.println("I/O Error: " + e); 
      return; 
    } 
 
    System.out.println("Doing a reset"); 
    f.reset(); 
 
    for (int i=0; i<3; i++) f.write('X'); 
 
    System.out.println(f.toString()); 
  } 
}

listing 11
// Use buffered input. 
// This program uses try-with-resources. It requires JDK 7 or later. 
 
import java.io.*; 
 
class BufferedInputStreamDemo { 
  public static void main(String args[]) { 
    String s = "This is a &copy; copyright symbol " + 
      "but this is &copy not.\n"; 
    byte buf[] = s.getBytes(); 
 
    ByteArrayInputStream in = new ByteArrayInputStream(buf); 
    int c; 
    boolean marked = false; 
 
    // Use try-with-resources to manage the file. 
    try ( BufferedInputStream f = new BufferedInputStream(in) ) 
    { 
      while ((c = f.read()) != -1) { 
        switch(c) { 
        case '&': 
          if (!marked) { 
            f.mark(32); 
            marked = true; 
          } else { 
            marked = false; 
          } 
          break; 
        case ';': 
          if (marked) { 
            marked = false; 
            System.out.print("(c)"); 
          } else 
            System.out.print((char) c); 
          break; 
        case ' ': 
          if (marked) { 
            marked = false; 
            f.reset(); 
            System.out.print("&"); 
          } else 
            System.out.print((char) c); 
          break; 
        default: 
          if (!marked) 
            System.out.print((char) c); 
          break; 
        } 
      } 
    } catch(IOException e) { 
      System.out.println("I/O Error: " + e); 
    } 
  } 
}

listing 12
// Demonstrate unread(). 
// This program uses try-with-resources. It requires JDK 7 or later. 
 
import java.io.*; 
 
class PushbackInputStreamDemo { 
  public static void main(String args[]) { 
    String s = "if (a == 4) a = 0;\n"; 
    byte buf[] = s.getBytes(); 
    ByteArrayInputStream in = new ByteArrayInputStream(buf); 
    int c; 
 
    try ( PushbackInputStream f = new PushbackInputStream(in) ) 
    { 
      while ((c = f.read()) != -1) { 
        switch(c) { 
        case '=': 
          if ((c = f.read()) == '=') 
            System.out.print(".eq."); 
          else { 
            System.out.print("<-"); 
            f.unread(c); 
          } 
          break; 
        default: 
          System.out.print((char) c); 
          break; 
        } 
      } 
    } catch(IOException e) { 
      System.out.println("I/O Error: " + e); 
    } 
  } 
}

listing 13
// Demonstrate sequenced input. 
// This program uses the traditional approach to closing a file. 
 
import java.io.*; 
import java.util.*; 
 
class InputStreamEnumerator implements Enumeration<FileInputStream> { 
  private Enumeration<String> files; 
 
  public InputStreamEnumerator(Vector<String> files) { 
    this.files = files.elements(); 
  } 
 
  public boolean hasMoreElements() { 
    return files.hasMoreElements(); 
  } 
 
  public FileInputStream nextElement() { 
    try { 
      return new FileInputStream(files.nextElement().toString()); 
    } catch (IOException e) { 
      return null; 
    } 
  } 
} 
 
class SequenceInputStreamDemo { 
  public static void main(String args[]) { 
    int c; 
    Vector<String> files = new Vector<String>(); 
 
    files.addElement("file1.txt"); 
    files.addElement("file2.txt"); 
    files.addElement("file3.txt"); 
    InputStreamEnumerator ise = new InputStreamEnumerator(files); 
    InputStream input = new SequenceInputStream(ise); 
 
    try { 
      while ((c = input.read()) != -1) 
        System.out.print((char) c); 
    } catch(NullPointerException e) { 
      System.out.println("Error Opening File."); 
    } catch(IOException e) { 
      System.out.println("I/O Error: " + e); 
    } finally { 
      try { 
        input.close(); 
      } catch(IOException e) { 
        System.out.println("Error Closing SequenceInputStream"); 
      } 
    } 
  } 
}

listing 14
// Demonstrate printf(). 
 
class PrintfDemo { 
  public static void main(String args[]) { 
    System.out.println("Here are some numeric values " + 
                      "in different formats.\n"); 
 
    System.out.printf("Various integer formats: "); 
    System.out.printf("%d %(d %+d %05d\n", 3, -3, 3, 3); 
 
    System.out.println(); 
    System.out.printf("Default floating-point format: %f\n", 
                      1234567.123); 
    System.out.printf("Floating-point with commas: %,f\n", 
                      1234567.123); 
    System.out.printf("Negative floating-point default: %,f\n", 
                      -1234567.123); 
    System.out.printf("Negative floating-point option: %,(f\n", 
                      -1234567.123); 
 
    System.out.println(); 
 
    System.out.printf("Line up positive and negative values:\n"); 
    System.out.printf("% ,.2f\n% ,.2f\n", 
                      1234567.123, -1234567.123); 
  } 
}

listing 15
// Demonstrate DataInputStream and DataOutputStream. 
// This program uses try-with-resources. It requires JDK 7 or later. 
 
import java.io.*; 
 
class DataIODemo { 
  public static void main(String args[]) throws IOException { 
 
    // First, write the data.  
    try ( DataOutputStream dout = 
            new DataOutputStream(new FileOutputStream("Test.dat")) ) 
    { 
      dout.writeDouble(98.6); 
      dout.writeInt(1000); 
      dout.writeBoolean(true); 
 
    } catch(FileNotFoundException e) { 
      System.out.println("Cannot Open Output File"); 
      return; 
    } catch(IOException e) { 
      System.out.println("I/O Error: " + e); 
    }  
 
    // Now, read the data back. 
    try ( DataInputStream din =  
            new DataInputStream(new FileInputStream("Test.dat")) ) 
    { 
 
      double d = din.readDouble(); 
      int i = din.readInt(); 
      boolean b = din.readBoolean(); 
 
      System.out.println("Here are the values: " + 
                          d + " " + i + " " + b); 
    } catch(FileNotFoundException e) { 
      System.out.println("Cannot Open Input File"); 
      return; 
    } catch(IOException e) { 
      System.out.println("I/O Error: " + e); 
    } 
  } 
}

listing 16
// Demonstrate FileReader. 
// This program uses try-with-resources. It requires JDK 7 or later. 
 
import java.io.*; 
 
class FileReaderDemo { 
  public static void main(String args[]) { 
 
    try ( FileReader fr = new FileReader("FileReaderDemo.java") ) 
    { 
      int c; 
 
      // Read and display the file. 
      while((c = fr.read()) != -1) System.out.print((char) c); 
 
    } catch(IOException e) { 
      System.out.println("I/O Error: " + e); 
    } 
  } 
} 

listing 17
// Demonstrate FileWriter. 
// This program uses try-with-resources. It requires JDK 7 or later. 
 
import java.io.*; 
 
class FileWriterDemo { 
  public static void main(String args[]) throws IOException { 
    String source = "Now is the time for all good men\n" 
      + " to come to the aid of their country\n" 
      + " and pay their due taxes."; 
    char buffer[] = new char[source.length()]; 
    source.getChars(0, source.length(), buffer, 0); 
 
    try ( FileWriter f0 = new FileWriter("file1.txt"); 
          FileWriter f1 = new FileWriter("file2.txt"); 
          FileWriter f2 = new FileWriter("file3.txt") ) 
    { 
      // write to first file 
      for (int i=0; i < buffer.length; i += 2) { 
        f0.write(buffer[i]); 
      } 
 
      // write to second file 
      f1.write(buffer); 
 
      // write to third file 
      f2.write(buffer,buffer.length-buffer.length/4,buffer.length/4); 
 
    } catch(IOException e) { 
      System.out.println("An I/O Error Occured"); 
    } 
  } 
}

listing 18
// Demonstrate CharArrayReader. 
// This program uses try-with-resources. It requires JDK 7 or later. 
 
import java.io.*; 
 
public class CharArrayReaderDemo { 
  public static void main(String args[]) { 
    String tmp = "abcdefghijklmnopqrstuvwxyz"; 
    int length = tmp.length(); 
    char c[] = new char[length]; 
 
    tmp.getChars(0, length, c, 0); 
    int i; 
 
    try (CharArrayReader input1 = new CharArrayReader(c) ) 
    { 
      System.out.println("input1 is:"); 
      while((i = input1.read()) != -1) { 
        System.out.print((char)i); 
      } 
      System.out.println(); 
    } catch(IOException e) { 
      System.out.println("I/O Error: " + e); 
    } 
 
    try ( CharArrayReader input2 = new CharArrayReader(c, 0, 5) ) 
    { 
      System.out.println("input2 is:"); 
      while((i = input2.read()) != -1) { 
        System.out.print((char)i); 
      } 
      System.out.println(); 
    } catch(IOException e) { 
      System.out.println("I/O Error: " + e); 
    } 
  } 
}

listing 19
// Demonstrate CharArrayWriter. 
// This program uses try-with-resources. It requires JDK 7 or later. 
 
import java.io.*; 
 
class CharArrayWriterDemo { 
  public static void main(String args[]) throws IOException { 
    CharArrayWriter f = new CharArrayWriter(); 
    String s = "This should end up in the array"; 
    char buf[] = new char[s.length()]; 
 
    s.getChars(0, s.length(), buf, 0); 
 
    try { 
      f.write(buf); 
    } catch(IOException e) { 
      System.out.println("Error Writing to Buffer"); 
      return; 
    } 
 
    System.out.println("Buffer as a string"); 
    System.out.println(f.toString()); 
    System.out.println("Into array"); 
 
    char c[] = f.toCharArray(); 
    for (int i=0; i<c.length; i++) { 
      System.out.print(c[i]); 
    } 
 
    System.out.println("\nTo a FileWriter()"); 
 
    // Use try-with-resources to manage the file stream. 
    try ( FileWriter f2 = new FileWriter("test.txt") ) 
    { 
      f.writeTo(f2); 
    } catch(IOException e) { 
      System.out.println("I/O Error: " + e); 
    } 
 
    System.out.println("Doing a reset"); 
    f.reset(); 
 
    for (int i=0; i<3; i++) f.write('X'); 
 
    System.out.println(f.toString()); 
  } 
}

listing 20
// Use buffered input. 
// This program uses try-with-resources. It requires JDK 7 or later. 
 
import java.io.*; 
 
class BufferedReaderDemo { 
  public static void main(String args[]) throws IOException { 
    String s = "This is a &copy; copyright symbol " + 
      "but this is &copy not.\n"; 
    char buf[] = new char[s.length()]; 
    s.getChars(0, s.length(), buf, 0); 
 
    CharArrayReader in = new CharArrayReader(buf); 
    int c; 
    boolean marked = false; 
 
    try ( BufferedReader f = new BufferedReader(in) ) 
    { 
 
      while ((c = f.read()) != -1) { 
        switch(c) { 
        case '&': 
          if (!marked) { 
            f.mark(32); 
            marked = true; 
          } else { 
            marked = false; 
          } 
          break; 
        case ';': 
          if (marked) { 
            marked = false; 
            System.out.print("(c)"); 
          } else 
            System.out.print((char) c); 
          break; 
        case ' ': 
          if (marked) { 
            marked = false; 
            f.reset(); 
            System.out.print("&"); 
          } else 
            System.out.print((char) c); 
          break; 
        default: 
          if (!marked) 
            System.out.print((char) c); 
          break; 
        } 
      } 
    } catch(IOException e) { 
      System.out.println("I/O Error: " + e); 
    } 
  } 
}

listing 21
// Demonstrate unread(). 
// This program uses try-with-resources. It requires JDK 7 or later. 
 
import java.io.*; 
 
class PushbackReaderDemo { 
  public static void main(String args[]) { 
    String s = "if (a == 4) a = 0;\n"; 
    char buf[] = new char[s.length()]; 
    s.getChars(0, s.length(), buf, 0); 
    CharArrayReader in = new CharArrayReader(buf); 
 
    int c; 
 
    try ( PushbackReader f = new PushbackReader(in) ) 
    { 
      while ((c = f.read()) != -1) { 
        switch(c) { 
        case '=': 
          if ((c = f.read()) == '=') 
            System.out.print(".eq."); 
          else { 
            System.out.print("<-"); 
            f.unread(c); 
          } 
          break; 
        default: 
          System.out.print((char) c); 
          break; 
        } 
      } 
    } catch(IOException e) { 
      System.out.println("I/O Error: " + e); 
    } 
  } 
}

listing 22
// Demonstrate Console. 
import java.io.*; 
 
class ConsoleDemo { 
  public static void main(String args[]) { 
    String str; 
    Console con; 
 
    // Obtain a reference to the console. 
    con = System.console(); 
    // If no console available, exit. 
    if(con == null) return; 
 
    // Read a string and then display it. 
    str = con.readLine("Enter a string: "); 
    con.printf("Here is your string: %s\n", str); 
  } 
}

listing 23
// A serialization demo. 
// This program uses try-with-resources. It requires JDK 7 or later. 
 
import java.io.*; 
 
public class SerializationDemo { 
  public static void main(String args[]) { 
 
    // Object serialization 
 
    try ( ObjectOutputStream objOStrm = 
            new ObjectOutputStream(new FileOutputStream("serial")) ) 
    { 
      MyClass object1 = new MyClass("Hello", -7, 2.7e10); 
      System.out.println("object1: " + object1); 
 
      objOStrm.writeObject(object1); 
    } 
    catch(IOException e) { 
      System.out.println("Exception during serialization: " + e); 
    } 
 
    // Object deserialization 
 
    try ( ObjectInputStream objIStrm = 
            new ObjectInputStream(new FileInputStream("serial")) ) 
    { 
      MyClass object2 = (MyClass)objIStrm.readObject(); 
      System.out.println("object2: " + object2); 
    } 
    catch(Exception e) { 
      System.out.println("Exception during deserialization: " + e); 
    } 
  } 
} 
 
class MyClass implements Serializable { 
  String s; 
  int i; 
  double d; 
 
  public MyClass(String s, int i, double d) { 
    this.s = s; 
    this.i = i; 
    this.d = d; 
  } 
 
  public String toString() { 
    return "s=" + s + "; i=" + i + "; d=" + d; 
  } 
}


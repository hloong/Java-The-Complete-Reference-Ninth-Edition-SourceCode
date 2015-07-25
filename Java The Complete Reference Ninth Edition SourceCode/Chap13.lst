listing 1
// Use a BufferedReader to read characters from the console. 
import java.io.*; 
 
class BRRead { 
  public static void main(String args[]) throws IOException 
  { 
    char c; 
    BufferedReader br = new 
            BufferedReader(new InputStreamReader(System.in)); 
    System.out.println("Enter characters, 'q' to quit.");
    // read characters 
    do { 
      c = (char) br.read(); 
      System.out.println(c); 
    } while(c != 'q'); 
  } 
}

listing 2
// Read a string from console using a BufferedReader. 
import java.io.*; 
 
class BRReadLines { 
  public static void main(String args[]) throws IOException 
  { 
    // create a BufferedReader using System.in 
    BufferedReader br = new BufferedReader(new 
                            InputStreamReader(System.in)); 
    String str;
    System.out.println("Enter lines of text."); 
    System.out.println("Enter 'stop' to quit."); 
    do { 
      str = br.readLine(); 
      System.out.println(str); 
    } while(!str.equals("stop")); 
  } 
}

listing 3
// A tiny editor. 
import java.io.*; 
 
class TinyEdit { 
  public static void main(String args[]) throws IOException 
  { 
    // create a BufferedReader using System.in 
    BufferedReader br = new BufferedReader(new 
                            InputStreamReader(System.in)); 
    String str[] = new String[100];
    System.out.println("Enter lines of text."); 
    System.out.println("Enter 'stop' to quit."); 
    for(int i=0; i<100; i++) { 
      str[i] = br.readLine(); 
      if(str[i].equals("stop")) break; 
    }
    System.out.println("\nHere is your file:");
    // display the lines 
    for(int i=0; i<100; i++) { 
      if(str[i].equals("stop")) break; 
      System.out.println(str[i]); 
    } 
  } 
}

listing 4
// Demonstrate System.out.write(). 
class WriteDemo { 
  public static void main(String args[]) { 
    int b; 
 
    b = 'A'; 
    System.out.write(b); 
    System.out.write('\n'); 
  } 
}

listing 5
// Demonstrate PrintWriter 
import java.io.*; 
 
public class PrintWriterDemo { 
  public static void main(String args[]) { 
    PrintWriter pw = new PrintWriter(System.out, true); 
 
    pw.println("This is a string"); 
    int i = -7; 
    pw.println(i); 
    double d = 4.5e-7; 
    pw.println(d); 
  } 
}

listing 6
/* Display a text file. 
   To use this program, specify the name 
   of the file that you want to see. 
   For example, to see a file called TEST.TXT, 
   use the following command line. 
 
   java ShowFile TEST.TXT 
*/ 
 
import java.io.*; 
 
class ShowFile { 
  public static void main(String args[]) 
  { 
    int i; 
    FileInputStream fin; 
 
    // First, confirm that a file name has been specified. 
    if(args.length != 1) { 
      System.out.println("Usage: ShowFile filename"); 
      return; 
    } 
 
    // Attempt to open the file. 
    try { 
      fin = new FileInputStream(args[0]); 
    } catch(FileNotFoundException e) { 
      System.out.println("Cannot Open File"); 
      return; 
    } 
 
    // At this point, the file is open and can be read. 
    // The following reads characters until EOF is encountered. 
    try { 
      do { 
        i = fin.read(); 
        if(i != -1) System.out.print((char) i); 
      } while(i != -1); 
    } catch(IOException e) { 
      System.out.println("Error Reading File"); 
   } 
 
    // Close the file. 
    try { 
      fin.close(); 
    } catch(IOException e) { 
        System.out.println("Error Closing File"); 
    } 
  } 
}

listing 7
/* Display a text file. 
   To use this program, specify the name 
   of the file that you want to see. 
   For example, to see a file called TEST.TXT, 
   use the following command line. 
 
   java ShowFile TEST.TXT 
 
   This variation wraps the code that opens and 
   accesses the file within a single try block. 
   The file is closed by the finally block. 
*/ 
 
import java.io.*; 
 
class ShowFile { 
  public static void main(String args[]) 
  { 
    int i; 
    FileInputStream fin = null; 
 
    // First, confirm that a file name has been specified. 
    if(args.length != 1) { 
      System.out.println("Usage: ShowFile filename"); 
      return; 
    } 
 
    // The following code opens a file, reads characters until EOF 
    // is encountered, and then closes the file via a finally block. 
    try { 
      fin = new FileInputStream(args[0]); 
 
      do { 
        i = fin.read(); 
        if(i != -1) System.out.print((char) i); 
      } while(i != -1); 
 
    } catch(FileNotFoundException e) { 
      System.out.println("File Not Found."); 
    } catch(IOException e) { 
      System.out.println("An I/O Error Occurred"); 
    } finally { 
      // Close file in all cases. 
      try { 
        if(fin != null) fin.close(); 
      } catch(IOException e) { 
        System.out.println("Error Closing File"); 
      } 
    } 
  } 
}

listing 8
/* Copy a text file. 
   To use this program, specify the name 
   of the source file and the destination file. 
   For example, to copy a file called FIRST.TXT 
   to a file called SECOND.TXT, use the following 
   command line. 
 
   java CopyFile FIRST.TXT SECOND.TXT 
*/ 
 
import java.io.*; 
 
class CopyFile { 
  public static void main(String args[]) throws IOException  
  { 
    int i; 
    FileInputStream fin = null; 
    FileOutputStream fout = null; 
 
    // First, confirm that both files has been specified. 
    if(args.length != 2) { 
      System.out.println("Usage: CopyFile from to"); 
      return; 
    } 
 
    // Copy a File. 
    try { 
      // Attempt to open the files. 
      fin = new FileInputStream(args[0]); 
      fout = new FileOutputStream(args[1]); 
 
      do { 
        i = fin.read(); 
        if(i != -1) fout.write(i); 
      } while(i != -1); 
 
    } catch(IOException e) { 
      System.out.println("I/O Error: " + e); 
    } finally { 
      try { 
        if(fin != null) fin.close(); 
      } catch(IOException e2) { 
        System.out.println("Error Closing Input File"); 
      } 
      try { 
        if(fout != null) fout.close(); 
      } catch(IOException e2) { 
        System.out.println("Error Closing Output File"); 
      } 
    } 
  } 
}

listing 9
/* This version of the ShowFile program uses a try-with-resources 
   statement to automatically close a file after it is no longer needed. 
 
   Note: This code requires JDK 7 or later. 
*/ 
 
import java.io.*; 
 
class ShowFile { 
  public static void main(String args[]) 
  { 
    int i; 
 
    // First, confirm that a file name has been specified. 
    if(args.length != 1) { 
      System.out.println("Usage: ShowFile filename"); 
      return; 
    } 
 
    // The following code uses a try-with-resources statement to open 
    // a file and then automatically close it when the try block is left. 
    try(FileInputStream fin = new FileInputStream(args[0])) {  
 
      do { 
        i = fin.read(); 
        if(i != -1) System.out.print((char) i); 
      } while(i != -1); 
 
    } catch(FileNotFoundException e) { 
      System.out.println("File Not Found."); 
    } catch(IOException e) { 
      System.out.println("An I/O Error Occurred"); 
    }  
 
  } 
}

listing 10
/* A version of CopyFile that uses try-with-resources. 
   It demonstrates two resources (in this case files) being 
   managed by a single try statement. 
*/ 
 
import java.io.*; 
 
class CopyFile { 
  public static void main(String args[]) throws IOException  
  { 
    int i; 
 
    // First, confirm that both files has been specified. 
    if(args.length != 2) { 
      System.out.println("Usage: CopyFile from to"); 
      return; 
    } 
 
    // Open and manage two files via the try statement. 
    try (FileInputStream fin = new FileInputStream(args[0]); 
         FileOutputStream fout = new FileOutputStream(args[1])) 
    { 
 
      do { 
        i = fin.read(); 
        if(i != -1) fout.write(i); 
      } while(i != -1); 
 
    } catch(IOException e) { 
      System.out.println("I/O Error: " + e); 
    } 
  } 
}

listing 11
import java.awt.*; 
import java.applet.*; 
 
public class SimpleApplet extends Applet { 
  public void paint(Graphics g) { 
    g.drawString("A Simple Applet", 20, 20); 
  } 
}

listing 12
import java.awt.*; 
import java.applet.*; 
/* 
<applet code="SimpleApplet" width=200 height=60> 
</applet> 
*/ 
 
public class SimpleApplet extends Applet { 
  public void paint(Graphics g) { 
    g.drawString("A Simple Applet", 20, 20); 
  } 
}

listing 13
// Demonstrate instanceof operator. 
class A { 
  int i, j; 
}
class B { 
  int i, j; 
}
class C extends A { 
  int k; 
}
class D extends A { 
  int k; 
}
class InstanceOf { 
  public static void main(String args[]) { 
    A a = new A(); 
    B b = new B(); 
    C c = new C(); 
    D d = new D(); 
    if(a instanceof A) 
      System.out.println("a is instance of A"); 
    if(b instanceof B) 
      System.out.println("b is instance of B"); 
    if(c instanceof C) 
      System.out.println("c is instance of C");  
    if(c instanceof A) 
      System.out.println("c can be cast to A");
    if(a instanceof C) 
      System.out.println("a can be cast to C");
    System.out.println();
    // compare types of derived types 
    A ob;
    ob = d; // A reference to d 
    System.out.println("ob now refers to d"); 
    if(ob instanceof D) 
      System.out.println("ob is instance of D");
    System.out.println();
    ob = c; // A reference to c 
    System.out.println("ob now refers to c");
    if(ob instanceof D) 
      System.out.println("ob can be cast to D"); 
    else 
      System.out.println("ob cannot be cast to D");
    if(ob instanceof A) 
      System.out.println("ob can be cast to A");
    System.out.println();
    // all objects can be cast to Object 
    if(a instanceof Object) 
      System.out.println("a may be cast to Object"); 
    if(b instanceof Object) 
      System.out.println("b may be cast to Object"); 
    if(c instanceof Object) 
      System.out.println("c may be cast to Object"); 
    if(d instanceof Object) 
      System.out.println("d may be cast to Object"); 
  } 
}

listing 14
// A simple example that uses a native method. 
public class NativeDemo { 
  int i; 
  public static void main(String args[]) { 
    NativeDemo ob = new NativeDemo();
    ob.i = 10; 
    System.out.println("This is ob.i before the native method:" + 
                       ob.i); 
    ob.test(); // call a native method 
    System.out.println("This is ob.i after the native method:" + 
                       ob.i); 
  } 
  // declare native method 
  public native void test() ;
  // load DLL that contains static method 
  static { 
    System.loadLibrary("NativeDemo"); 
  } 
}

listing 15
/* DO NOT EDIT THIS FILE - it is machine generated */ 
#include <jni.h> 
/* Header for class NativeDemo */ 
 
#ifndef _Included_NativeDemo 
#define _Included_NativeDemo 
#ifdef _ _cplusplus 
extern "C" { 
#endif 
/* 
 * Class:     NativeDemo 
 * Method:    test 
 * Signature: ()V 
 */ 
JNIEXPORT void JNICALL Java_NativeDemo_test 
   (JNIEnv *, jobject); 
 
#ifdef _ _cplusplus 
} 
#endif 
#endif

listing 16
/* This file contains the C version of the 
   test() method. 
*/ 
 
#include <jni.h> 
#include "NativeDemo.h" 
#include <stdio.h> 
 
JNIEXPORT void JNICALL Java_NativeDemo_test(JNIEnv *env, jobject obj) 
{ 
  jclass cls; 
  jfieldID fid; 
  jint i; 
 
  printf("Starting the native method.\n"); 
  cls = (*env)->GetObjectClass(env, obj); 
  fid = (*env)->GetFieldID(env, cls, "i", "I"); 
 
  if(fid == 0) { 
    printf("Could not get field id.\n"); 
    return; 
  } 
 
  i = (*env)->GetIntField(env, obj, fid); 
  printf("i = %d\n", i); 
  (*env)->SetIntField(env, obj, fid, 2*i); 
  printf("Ending the native method.\n"); 
}

listing 17
// Demonstrate assert. 
class AssertDemo { 
  static int val = 3; 
 
  // Return an integer. 
  static int getnum() { 
    return val--; 
  } 
 
  public static void main(String args[]) 
  { 
    int n; 
 
    for(int i=0; i < 10; i++) { 
      n = getnum(); 
 
      assert n > 0; // will fail when n is 0 
 
      System.out.println("n is " + n); 
    } 
  } 
}

listing 18
// A poor way to use assert!!! 
class AssertDemo { 
  // get a random number generator 
  static int val = 3; 
 
  // Return an integer. 
  static int getnum() { 
    return val--; 
  } 
 
  public static void main(String args[]) 
  { 
    int n = 0; 
 
    for(int i=0; i < 10; i++) { 
 
      assert (n = getnum()) > 0; // This is not a good idea! 
 
      System.out.println("n is " + n); 
    } 
  } 
}

listing 19
// Compute the hypotenuse of a right triangle. 
class Hypot { 
  public static void main(String args[]) { 
    double side1, side2; 
    double hypot; 
    side1 = 3.0; 
    side2 = 4.0; 
 
    // Notice how sqrt() and pow() must be qualified by 
    // their class name, which is Math. 
    hypot = Math.sqrt(Math.pow(side1, 2) + 
                      Math.pow(side2, 2)); 
 
    System.out.println("Given sides of lengths " + 
                       side1 + " and " + side2 + 
                       " the hypotenuse is " + 
                       hypot); 
  } 
}

listing 20
// Use static import to bring sqrt() and pow() into view. 
import static java.lang.Math.sqrt; 
import static java.lang.Math.pow; 
 
// Compute the hypotenuse of a right triangle. 
class Hypot { 
  public static void main(String args[]) { 
    double side1, side2; 
    double hypot; 
 
    side1 = 3.0; 
    side2 = 4.0; 
 
    // Here, sqrt() and pow() can be called by themselves, 
    // without their class name. 
    hypot = sqrt(pow(side1, 2) + pow(side2, 2)); 
 
    System.out.println("Given sides of lengths " + 
                       side1 + " and " + side2 + 
                       " the hypotenuse is " + 
                       hypot); 
  } 
}

listing 21
class MyClass { 
  int a; 
  int b; 
 
  // initialize a and b individually 
  MyClass(int i, int j) { 
    a = i; 
    b = j; 
  } 
 
  // initialize a and b to the same value 
  MyClass(int i) { 
    a = i; 
    b = i; 
  } 
 
  // give a and b default values of 0 
  MyClass( ) { 
    a = 0; 
    b = 0; 
  } 
}

listing 22
class MyClass { 
  int a; 
  int b; 
 
  // initialize a and b individually 
  MyClass(int i, int j) { 
    a = i; 
    b = j; 
  } 
 
  // initialize a and b to the same value 
  MyClass(int i) { 
    this(i, i); // invokes MyClass(i, i) 
  } 
 
  // give a and b default values of 0 
  MyClass( ) { 
    this(0); // invokes MyClass(0) 
  } 
}


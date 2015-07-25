listing 1
// Use Channel I/O to read a file. Requires JDK 7 or later. 
 
import java.io.*; 
import java.nio.*; 
import java.nio.channels.*; 
import java.nio.file.*; 
 
public class ExplicitChannelRead { 
  public static void main(String args[]) { 
    int count; 
    Path filepath = null; 
 
    // First, obtain a path to the file. 
    try { 
      filepath = Paths.get("test.txt"); 
    } catch(InvalidPathException e) { 
      System.out.println("Path Error " + e); 
      return; 
    } 
 
    // Next, obtain a channel to that file within a try-with-resources block. 
    try ( SeekableByteChannel fChan = Files.newByteChannel(filepath) ) 
    { 
 
      // Allocate a buffer. 
      ByteBuffer mBuf = ByteBuffer.allocate(128); 
 
      do { 
        // Read a buffer. 
        count = fChan.read(mBuf); 
 
        // Stop when end of file is reached. 
        if(count != -1) { 
         
          // Rewind the buffer so that it can be read. 
          mBuf.rewind(); 
 
          // Read bytes from the buffer and show 
          // them on the screen as characters. 
          for(int i=0; i < count; i++) 
            System.out.print((char)mBuf.get()); 
        } 
      } while(count != -1); 
 
      System.out.println(); 
    } catch (IOException e) { 
      System.out.println("I/O Error " + e); 
    } 
  } 
}

listing 2
// A more compact way to open a channel. Requires JDK 7 or later. 
 
import java.io.*; 
import java.nio.*; 
import java.nio.channels.*; 
import java.nio.file.*; 
 
public class ExplicitChannelRead { 
  public static void main(String args[]) { 
    int count; 
 
    // Here, the channel is opened on the Path returned by Paths.get(). 
    // There is no need for the filepath variable. 
    try ( SeekableByteChannel fChan = 
            Files.newByteChannel(Paths.get("test.txt")) ) 
    { 
      // Allocate a buffer. 
      ByteBuffer mBuf = ByteBuffer.allocate(128); 
 
      do { 
        // Read a buffer. 
        count = fChan.read(mBuf); 
  
        // Stop when end of file is reached. 
        if(count != -1) { 
         
          // Rewind the buffer so that it can be read. 
          mBuf.rewind(); 
 
          // Read bytes from the buffer and show 
          // them on the screen as characters. 
          for(int i=0; i < count; i++) 
            System.out.print((char)mBuf.get()); 
        } 
      } while(count != -1); 
 
      System.out.println(); 
    } catch(InvalidPathException e) { 
      System.out.println("Path Error " + e); 
    } catch (IOException e) { 
      System.out.println("I/O Error " + e); 
    } 
  } 
}

listing 3
// Use a mapped file to read a file. Requires JDK 7 or later. 
 
import java.io.*; 
import java.nio.*; 
import java.nio.channels.*; 
import java.nio.file.*; 
 
public class MappedChannelRead { 
  public static void main(String args[]) { 
 
    // Obtain a channel to a file within a try-with-resources block. 
    try ( FileChannel fChan = 
         (FileChannel) Files.newByteChannel(Paths.get("test.txt")) ) 
    { 
 
      // Get the size of the file. 
      long fSize = fChan.size(); 
 
      // Now, map the file into a buffer. 
      MappedByteBuffer mBuf = fChan.map(FileChannel.MapMode.READ_ONLY, 0, fSize); 
 
      // Read and display bytes from buffer. 
      for(int i=0; i < fSize; i++) 
        System.out.print((char)mBuf.get()); 
 
      System.out.println(); 
 
    } catch(InvalidPathException e) { 
      System.out.println("Path Error " + e); 
    } catch (IOException e) { 
      System.out.println("I/O Error " + e); 
    } 
  } 
}

listing 4
// Write to a file using NIO. Requires JDK 7 or later.  
  
import java.io.*;  
import java.nio.*;  
import java.nio.channels.*;  
import java.nio.file.*;  
  
public class ExplicitChannelWrite {  
  public static void main(String args[]) {  
  
    // Obtain a channel to a file within a try-with-resources block.  
    try ( FileChannel fChan = (FileChannel)  
            Files.newByteChannel(Paths.get("test.txt"),  
                                 StandardOpenOption.WRITE,  
                                 StandardOpenOption.CREATE) ) 
    {  
      // Create a buffer.  
      ByteBuffer mBuf = ByteBuffer.allocate(26);  
  
      // Write some bytes to the buffer.  
      for(int i=0; i<26; i++)  
        mBuf.put((byte)('A' + i));  
  
      // Reset the buffer so that it can be written.  
      mBuf.rewind();  
  
      // Write the buffer to the output file.  
      fChan.write(mBuf);  
  
    } catch(InvalidPathException e) {  
      System.out.println("Path Error " + e);  
    } catch (IOException e) {  
      System.out.println("I/O Error: " + e);  
      System.exit(1);  
    }  
  }  
}

listing 5
for(int h=0; h < 3; h++) { 
  // Write some bytes to the buffer. 
  for(int i=0; i<26; i++) 
    mBuf.put((byte)('A' + i)); 
 
  // Rewind the buffer so that it can be written. 
  mBuf.rewind(); 
 
  // Write the buffer to the output file. 
  fChan.write(mBuf); 
 
  // Rewind the buffer so that it can be written to again. 
  mBuf.rewind(); 
}

listing 6
// Write to a mapped file. Requires JDK 7 or later. 
 
import java.io.*; 
import java.nio.*; 
import java.nio.channels.*; 
import java.nio.file.*; 
 
public class MappedChannelWrite { 
  public static void main(String args[]) { 
 
    // Obtain a channel to a file within a try-with-resources block. 
    try ( FileChannel fChan = (FileChannel) 
          Files.newByteChannel(Paths.get("test.txt"), 
                   StandardOpenOption.WRITE, 
                   StandardOpenOption.READ, 
                   StandardOpenOption.CREATE) ) 
    { 
 
      // Then, map the file into a buffer. 
      MappedByteBuffer mBuf = fChan.map(FileChannel.MapMode.READ_WRITE, 0, 26); 
 
      // Write some bytes to the buffer. 
      for(int i=0; i<26; i++) 
        mBuf.put((byte)('A' + i)); 
 
    } catch(InvalidPathException e) { 
      System.out.println("Path Error " + e); 
    } catch (IOException e) { 
      System.out.println("I/O Error " + e); 
    } 
  } 
}

listing 7
// Copy a file using NIO. Requires JDK 7 or later. 
import java.io.*; 
import java.nio.*; 
import java.nio.channels.*; 
import java.nio.file.*; 
 
public class NIOCopy { 
 
  public static void main(String args[]) { 
 
    if(args.length != 2) { 
      System.out.println("Usage: Copy from to"); 
      return; 
    } 
 
    try { 
      Path source = Paths.get(args[0]); 
      Path target = Paths.get(args[1]); 
 
      // Copy the file. 
      Files.copy(source, target, StandardCopyOption.REPLACE_EXISTING); 
 
    } catch(InvalidPathException e) { 
      System.out.println("Path Error " + e); 
    } catch (IOException e) { 
      System.out.println("I/O Error " + e); 
    } 
  } 
}

listing 8
/* Display a text file using stream-based, NIO code. 
   Requires JDK 7 or later. 
 
   To use this program, specify the name 
   of the file that you want to see. 
   For example, to see a file called TEST.TXT, 
   use the following command line. 
 
   java ShowFile TEST.TXT 
*/ 
 
import java.io.*; 
import java.nio.file.*; 
 
class ShowFile { 
  public static void main(String args[]) 
  { 
    int i; 
 
    // First, confirm that a file name has been specified. 
    if(args.length != 1) { 
      System.out.println("Usage: ShowFile filename"); 
      return; 
    } 
 
    // Open the file and obtain a stream linked to it. 
    try ( InputStream fin = Files.newInputStream(Paths.get(args[0])) )  
    { 
      do { 
        i = fin.read(); 
        if(i != -1) System.out.print((char) i); 
      } while(i != -1); 
 
    } catch(InvalidPathException e) { 
      System.out.println("Path Error " + e); 
    } catch(IOException e) { 
      System.out.println("I/O Error "  + e); 
    } 
  } 
}

listing 9
// Demonstrate NIO-based, stream output. Requires JDK 7 or later. 
 
import java.io.*; 
import java.nio.file.*; 
 
class NIOStreamWrite { 
  public static void main(String args[]) 
  { 
    // Open the file and obtain a stream linked to it. 
    try ( OutputStream fout = 
          new BufferedOutputStream( 
                Files.newOutputStream(Paths.get("test.txt"))) ) 
    { 
      // Write some bytes to the stream. 
      for(int i=0; i < 26; i++) 
        fout.write((byte)('A' + i)); 
 
    } catch(InvalidPathException e) { 
      System.out.println("Path Error " + e); 
    } catch(IOException e) { 
      System.out.println("I/O Error: " + e); 
    } 
  } 
}

listing 10
// Obtain information about a path and a file. 
// Requires JDK 7 or later.  
  
import java.io.*;  
import java.nio.file.*;  
import java.nio.file.attribute.*;  
  
class PathDemo {  
  public static void main(String args[]) {  
    Path filepath = Paths.get("examples\\test.txt");  
  
    System.out.println("File Name: " + filepath.getName(1));  
    System.out.println("Path: " + filepath);  
    System.out.println("Absolute Path: " + filepath.toAbsolutePath());  
    System.out.println("Parent: " + filepath.getParent());  
  
    if(Files.exists(filepath))  
      System.out.println("File exists");  
    else  
      System.out.println("File does not exist");  
  
    try {  
      if(Files.isHidden(filepath))  
        System.out.println("File is hidden");  
      else  
        System.out.println("File is not hidden");  
    } catch(IOException e) {  
        System.out.println("I/O Error: " + e);  
    }  
  
    Files.isWritable(filepath);  
    System.out.println("File is writeable");  
  
 
    Files.isReadable(filepath);  
    System.out.println("File is readable");  
  
    try {  
      BasicFileAttributes attribs =  
        Files.readAttributes(filepath, BasicFileAttributes.class);  
  
      if(attribs.isDirectory())  
        System.out.println("The file is a directory");  
      else  
        System.out.println("The file is not a directory");  
  
      if(attribs.isRegularFile())  
        System.out.println("The file is a normal file");  
      else  
        System.out.println("The file is not a normal file");  
  
      if(attribs.isSymbolicLink())  
        System.out.println("The file is a symbolic link");  
      else  
        System.out.println("The file is not a symbolic link");  
  
      System.out.println("File last modified: " + attribs.lastModifiedTime());  
      System.out.println("File size: " + attribs.size() + " Bytes");  
    } catch(IOException e) {  
      System.out.println("Error reading attributes: " + e);  
    }  
  }  
}

listing 11
// Display a directory. Requires JDK 7 or later. 
 
import java.io.*; 
import java.nio.file.*; 
import java.nio.file.attribute.*; 
 
class DirList { 
  public static void main(String args[]) { 
    String dirname = "\\MyDir"; 
 
    // Obtain and manage a directory stream within an ARM Block. 
    try ( DirectoryStream<Path> dirstrm = 
            Files.newDirectoryStream(Paths.get(dirname)) ) 
    { 
      System.out.println("Directory of " + dirname); 
  
      // Because DirectoryStream implements Iterable, we 
      // can use a "foreach" loop to display the directory. 
      for(Path entry : dirstrm) { 
        BasicFileAttributes attribs = 
             Files.readAttributes(entry, BasicFileAttributes.class); 
 
        if(attribs.isDirectory()) 
          System.out.print("<DIR> "); 
        else 
          System.out.print("      "); 
 
        System.out.println(entry.getName(1)); 
      } 
    } catch(InvalidPathException e) { 
      System.out.println("Path Error " + e); 
    } catch(NotDirectoryException e) { 
      System.out.println(dirname + " is not a directory."); 
    } catch (IOException e) { 
      System.out.println("I/O Error: " + e); 
    } 
  } 
}

listing 12 
// Display a directory of only those files that are writable.  
  
import java.io.*;  
import java.nio.file.*;  
import java.nio.file.attribute.*;  
  
class DirList {  
  public static void main(String args[]) {  
    String dirname = "\\MyDir";  
  
    // Create a filter that returns true only for writable files.  
    DirectoryStream.Filter<Path> how = new DirectoryStream.Filter<Path>() {  
      public boolean accept(Path filename) throws IOException {  
        if(Files.isWritable(filename)) return true;  
        return false;  
      }  
    };  
  
    // Obtain and manage a directory stream of writable files.  
    try (DirectoryStream<Path> dirstrm =   
           Files.newDirectoryStream(Paths.get(dirname), how) )  
    {  
      System.out.println("Directory of " + dirname);  
   
      for(Path entry : dirstrm) {  
        BasicFileAttributes attribs =  
          Files.readAttributes(entry, BasicFileAttributes.class);  
  
        if(attribs.isDirectory())  
          System.out.print("<DIR> ");  
        else  
          System.out.print("      ");  
  
        System.out.println(entry.getName(1)); 
      }  
    } catch(InvalidPathException e) {  
      System.out.println("Path Error " + e);  
    } catch(NotDirectoryException e) {  
      System.out.println(dirname + " is not a directory.");  
    } catch (IOException e) {  
      System.out.println("I/O Error: " + e);  
    }  
  }  
}

listing 13
// A simple example that uses walkFileTree( ) to display a directory tree. 
// Requires JDK 7 or later.  
  
import java.io.*;  
import java.nio.file.*;  
import java.nio.file.attribute.*;  
 
// Create a custom version of SimpleFileVisitor that overrides 
// the visitFile( ) method. 
class MyFileVisitor extends SimpleFileVisitor<Path> { 
  public FileVisitResult visitFile(Path path, BasicFileAttributes attribs) 
    throws IOException 
  { 
    System.out.println(path); 
    return FileVisitResult.CONTINUE; 
  } 
} 
  
class DirTreeList {  
  public static void main(String args[]) {  
    String dirname = "\\MyDir";  
 
    System.out.println("Directory tree starting with " + dirname + ":\n"); 
 
    try { 
      Files.walkFileTree(Paths.get(dirname), new MyFileVisitor()); 
    } catch (IOException exc) { 
      System.out.println("I/O Error"); 
    } 
  } 
}

listing 14
// Use Channels to read a file. Pre-JDK 7 version. 
import java.io.*; 
import java.nio.*; 
import java.nio.channels.*; 
 
public class ExplicitChannelRead { 
  public static void main(String args[]) { 
    FileInputStream fIn = null; 
    FileChannel fChan = null; 
    ByteBuffer mBuf; 
    int count; 
 
    try { 
      // First, open a file for input. 
      fIn = new FileInputStream("test.txt"); 
 
      // Next, obtain a channel to that file. 
      fChan = fIn.getChannel(); 
 
      // Allocate a buffer.  
      mBuf = ByteBuffer.allocate(128);  
 
      do { 
        // Read a buffer. 
        count = fChan.read(mBuf); 
 
        // Stop when end of file is reached. 
        if(count != -1) { 
         
          // Rewind the buffer so that it can be read. 
          mBuf.rewind(); 
 
          // Read bytes from the buffer and show 
          // them on the screen. 
          for(int i=0; i < count; i++) 
            System.out.print((char)mBuf.get()); 
        } 
      } while(count != -1); 
 
      System.out.println(); 
 
    } catch (IOException e) { 
      System.out.println("I/O Error " + e); 
    } finally { 
      try { 
        if(fChan != null) fChan.close(); // close channel 
      } catch(IOException e) { 
        System.out.println("Error Closing Channel."); 
      } 
      try { 
        if(fIn != null) fIn.close(); // close file 
      } catch(IOException e) { 
        System.out.println("Error Closing File."); 
      } 
    } 
  } 
}

listing 15
// Use a mapped file to read a file. Pre-JDK 7 version. 
 
import java.io.*; 
import java.nio.*; 
import java.nio.channels.*; 
 
public class MappedChannelRead { 
  public static void main(String args[]) { 
    FileInputStream fIn = null; 
    FileChannel fChan = null; 
    long fSize; 
    MappedByteBuffer mBuf; 
 
    try { 
      // First, open a file for input. 
      fIn = new FileInputStream("test.txt"); 
 
      // Next, obtain a channel to that file. 
      fChan = fIn.getChannel(); 
 
      // Get the size of the file. 
      fSize = fChan.size(); 
 
      // Now, map the file into a buffer. 
      mBuf = fChan.map(FileChannel.MapMode.READ_ONLY, 0, fSize); 
 
      // Read and display bytes from buffer. 
      for(int i=0; i < fSize; i++) 
        System.out.print((char)mBuf.get()); 
 
    } catch (IOException e) { 
      System.out.println("I/O Error " + e); 
    } finally { 
      try { 
        if(fChan != null) fChan.close(); // close channel 
      } catch(IOException e) { 
        System.out.println("Error Closing Channel."); 
      } 
      try { 
        if(fIn != null) fIn.close(); // close file 
      } catch(IOException e) { 
        System.out.println("Error Closing File."); 
      } 
    } 
  } 
}

listing 16
// Write to a file using NIO. Pre-JDK 7 Version. 
import java.io.*; 
import java.nio.*; 
import java.nio.channels.*; 
 
public class ExplicitChannelWrite { 
  public static void main(String args[]) { 
    FileOutputStream fOut = null; 
    FileChannel fChan = null; 
    ByteBuffer mBuf; 
 
    try { 
      // First, open the output file. 
      fOut = new FileOutputStream("test.txt"); 
 
      // Next, get a channel to the output file. 
      fChan = fOut.getChannel(); 
 
      // Create a buffer. 
      mBuf = ByteBuffer.allocate(26); 
 
      // Write some bytes to the buffer. 
      for(int i=0; i<26; i++) 
        mBuf.put((byte)('A' + i)); 
 
      // Rewind the buffer so that it can be written. 
      mBuf.rewind(); 
 
      // Write the buffer to the output file. 
      fChan.write(mBuf); 
    } catch (IOException e) { 
      System.out.println("I/O Error " + e); 
    } finally { 
      try { 
        if(fChan != null) fChan.close(); // close channel 
      } catch(IOException e) { 
        System.out.println("Error Closing Channel."); 
      } 
      try { 
        if(fOut != null) fOut.close(); // close file 
      } catch(IOException e) { 
        System.out.println("Error Closing File."); 
      } 
    } 
  } 
}

listing 17
// Write to a mapped file. Pre JDK 7 version. 
import java.io.*; 
import java.nio.*; 
import java.nio.channels.*; 
 
public class MappedChannelWrite { 
  public static void main(String args[]) { 
    RandomAccessFile fOut = null; 
    FileChannel fChan = null; 
    ByteBuffer mBuf; 
 
    try { 
      fOut = new RandomAccessFile("test.txt", "rw"); 
 
      // Next, obtain a channel to that file. 
      fChan = fOut.getChannel(); 
 
      // Then, map the file into a buffer. 
      mBuf = fChan.map(FileChannel.MapMode.READ_WRITE, 0, 26); 
 
      // Write some bytes to the buffer. 
      for(int i=0; i<26; i++) 
        mBuf.put((byte)('A' + i)); 
 
    } catch (IOException e) { 
      System.out.println("I/O Error " + e); 
    } finally { 
      try { 
        if(fChan != null) fChan.close(); // close channel 
      } catch(IOException e) { 
        System.out.println("Error Closing Channel."); 
      } 
      try { 
        if(fOut != null) fOut.close(); // close file 
      } catch(IOException e) { 
        System.out.println("Error Closing File."); 
      } 
    } 
  } 
}


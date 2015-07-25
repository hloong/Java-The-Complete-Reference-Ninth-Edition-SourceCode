listing 1
// Demonstrate InetAddress. 
import java.net.*; 
 
class InetAddressTest  
{ 
  public static void main(String args[]) throws UnknownHostException { 
    InetAddress Address = InetAddress.getLocalHost(); 
    System.out.println(Address); 
    Address = InetAddress.getByName("www.HerbSchildt.com"); 
    System.out.println(Address); 
    InetAddress SW[] = InetAddress.getAllByName("www.nba.com"); 
    for (int i=0; i<SW.length; i++) 
      System.out.println(SW[i]); 
  } 
}

listing 2
// Demonstrate Sockets. 
import java.net.*; 
import java.io.*; 
 
class Whois { 
  public static void main(String args[]) throws Exception { 
    int c; 
 
    // Create a socket connected to internic.net, port 43. 
    Socket s = new Socket("whois.internic.net", 43); 
 
    // Obtain input and output streams. 
    InputStream in = s.getInputStream(); 
    OutputStream out = s.getOutputStream(); 
 
    // Construct a request string. 
    String str = (args.length == 0 ? "MHProfessional.com" : args[0]) + "\n"; 
    // Convert to bytes. 
    byte buf[] = str.getBytes(); 
 
    // Send request. 
    out.write(buf); 
 
    // Read and display response. 
    while ((c = in.read()) != -1) { 
      System.out.print((char) c); 
    } 
    s.close(); 
  } 
}

listing 3
// Demonstrate URL. 
import java.net.*; 
class URLDemo { 
  public static void main(String args[]) throws MalformedURLException { 
    URL hp = new URL("http://www.HerbSchildt.com/WhatsNew"); 
 
    System.out.println("Protocol: " + hp.getProtocol()); 
    System.out.println("Port: " + hp.getPort()); 
    System.out.println("Host: " + hp.getHost()); 
    System.out.println("File: " + hp.getFile()); 
    System.out.println("Ext:" + hp.toExternalForm()); 
  } 
}

listing 4
// Demonstrate URLConnection. 
import java.net.*; 
import java.io.*; 
import java.util.Date; 
 
class UCDemo 
{ 
  public static void main(String args[]) throws Exception { 
    int c; 
    URL hp = new URL("http://www.internic.net"); 
    URLConnection hpCon = hp.openConnection(); 
 
    // get date 
    long d = hpCon.getDate();  
    if(d==0) 
      System.out.println("No date information."); 
    else 
      System.out.println("Date: " + new Date(d)); 
 
    // get content type 
    System.out.println("Content-Type: " + hpCon.getContentType()); 
 
    // get expiration date 
    d = hpCon.getExpiration(); 
    if(d==0) 
      System.out.println("No expiration information."); 
    else 
      System.out.println("Expires: " + new Date(d)); 
 
    // get last-modified date 
    d = hpCon.getLastModified(); 
    if(d==0) 
      System.out.println("No last-modified information."); 
    else 
      System.out.println("Last-Modified: " + new Date(d)); 
 
    // get content length 
    long len = hpCon.getContentLengthLong(); 
    if(len == -1) 
      System.out.println("Content length unavailable."); 
    else 
      System.out.println("Content-Length: " + len); 
 
    if(len != 0) { 
      System.out.println("=== Content ==="); 
      InputStream input = hpCon.getInputStream(); 

      while (((c = input.read()) != -1)) { 
        System.out.print((char) c); 
      } 
      input.close(); 
 
    } else { 
      System.out.println("No content available."); 
    } 
 
  } 
}

listing 5
// Demonstrate HttpURLConnection. 
import java.net.*; 
import java.io.*; 
import java.util.*; 
 
class HttpURLDemo  
{ 
  public static void main(String args[]) throws Exception { 
    URL hp = new URL("http://www.google.com"); 
 
    HttpURLConnection hpCon = (HttpURLConnection) hp.openConnection(); 
 
    // Display request method. 
    System.out.println("Request method is " + 
                       hpCon.getRequestMethod()); 
 
    // Display response code. 
    System.out.println("Response code is " + 
                       hpCon.getResponseCode()); 
 
    // Display response message. 
    System.out.println("Response Message is " + 
                       hpCon.getResponseMessage()); 
 
    // Get a list of the header fields and a set 
    // of the header keys. 
    Map<String, List<String>> hdrMap = hpCon.getHeaderFields(); 
    Set<String> hdrField = hdrMap.keySet(); 
 
    System.out.println("\nHere is the header:"); 
 
    // Display all header keys and values.. 
    for(String k : hdrField) { 
      System.out.println("Key: " + k + 
                         "  Value: " + hdrMap.get(k)); 
    } 
  } 
}

listing 6
// Demonstrate Datagrams. 
import java.net.*; 
 
class WriteServer { 
  public static int serverPort = 998; 
  public static int clientPort = 999; 
  public static int buffer_size = 1024; 
  public static DatagramSocket ds; 
  public static byte buffer[] = new byte[buffer_size]; 
 
  public static void TheServer() throws Exception { 
    int pos=0; 
    while (true) { 
      int c = System.in.read(); 
      switch (c) { 
        case -1:  
          System.out.println("Server Quits."); 
          ds.close();
          return; 
        case '\r':  
          break; 
        case '\n': 
          ds.send(new DatagramPacket(buffer,pos, 
             InetAddress.getLocalHost(),clientPort)); 
          pos=0; 
          break; 
        default: 
          buffer[pos++] = (byte) c; 
      } 
    } 
  } 
 
  public static void TheClient() throws Exception { 
    while(true) { 
      DatagramPacket p = new DatagramPacket(buffer, buffer.length); 
      ds.receive(p); 
      System.out.println(new String(p.getData(), 0, p.getLength())); 
    } 
  } 
 
  public static void main(String args[]) throws Exception { 
    if(args.length == 1) { 
      ds = new DatagramSocket(serverPort); 
      TheServer(); 
    } else { 
      ds = new DatagramSocket(clientPort); 
      TheClient(); 
    } 
  } 
}


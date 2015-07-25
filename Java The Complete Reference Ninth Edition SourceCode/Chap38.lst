listing 1
import java.io.*; 
import javax.servlet.*; 
 
public class HelloServlet extends GenericServlet { 
 
  public void service(ServletRequest request,  
    ServletResponse response)  
  throws ServletException, IOException { 
    response.setContentType("text/html"); 
    PrintWriter pw = response.getWriter(); 
    pw.println("<B>Hello!"); 
    pw.close(); 
  } 
}

listing 2
<html> 
<body> 
<center> 
<form name="Form1" 
  method="post" 
  action="http://localhost:8080/examples/servlets/servlet/PostParametersServlet"> 
<table> 
<tr> 
  <td><B>Employee</td> 
  <td><input type=textbox name="e" size="25" value=""></td> 
</tr> 
<tr> 
  <td><B>Phone</td> 
  <td><input type=textbox name="p" size="25" value=""></td> 
</tr> 
</table> 
<input type=submit value="Submit"> 
</body> 
</html>

listing 3
import java.io.*; 
import java.util.*; 
import javax.servlet.*; 
 
public class PostParametersServlet  
extends GenericServlet { 
 
  public void service(ServletRequest request,  
    ServletResponse response)  
  throws ServletException, IOException { 
 
    // Get print writer. 
    PrintWriter pw = response.getWriter(); 
 
    // Get enumeration of parameter names. 
    Enumeration e = request.getParameterNames(); 
 
    // Display parameter names and values. 
    while(e.hasMoreElements()) { 
      String pname = (String)e.nextElement(); 
      pw.print(pname + " = "); 
      String pvalue = request.getParameter(pname); 
      pw.println(pvalue); 
    } 
    pw.close(); 
  } 
}

listing 4
<html> 
<body> 
<center> 
<form name="Form1"  
  action="http://localhost:8080/examples/servlets/servlet/ColorGetServlet"> 
<B>Color:</B> 
<select name="color" size="1"> 
<option value="Red">Red</option> 
<option value="Green">Green</option> 
<option value="Blue">Blue</option> 
</select> 
<br><br> 
<input type=submit value="Submit"> 
</form> 
</body> 
</html>

listing 5
import java.io.*; 
import javax.servlet.*; 
import javax.servlet.http.*; 
 
public class ColorGetServlet extends HttpServlet { 
 
  public void doGet(HttpServletRequest request,  
    HttpServletResponse response)  
  throws ServletException, IOException { 
 
    String color = request.getParameter("color"); 
    response.setContentType("text/html"); 
    PrintWriter pw = response.getWriter(); 
    pw.println("<B>The selected color is:  "); 
    pw.println(color); 
    pw.close(); 
  } 
}

listing 6
<html> 
<body> 
<center> 
<form name="Form1"  
  method="post" 
  action="http://localhost:8080/examples/servlets/servlet/ColorPostServlet"> 
<B>Color:</B> 
<select name="color" size="1"> 
<option value="Red">Red</option> 
<option value="Green">Green</option> 
<option value="Blue">Blue</option> 
</select> 
<br><br> 
<input type=submit value="Submit"> 
</form> 
</body> 
</html>

listing 7
import java.io.*; 
import javax.servlet.*; 
import javax.servlet.http.*; 
 
public class ColorPostServlet extends HttpServlet { 
 
  public void doPost(HttpServletRequest request,  
    HttpServletResponse response)  
  throws ServletException, IOException { 
 
    String color = request.getParameter("color"); 
    response.setContentType("text/html"); 
    PrintWriter pw = response.getWriter(); 
    pw.println("<B>The selected color is:  "); 
    pw.println(color); 
    pw.close(); 
  } 
}

listing 8
<html> 
<body> 
<center> 
<form name="Form1"  
  method="post" 
  action="http://localhost:8080/examples/servlets/servlet/AddCookieServlet"> 
<B>Enter a value for MyCookie:</B> 
<input type=textbox name="data" size=25 value=""> 
<input type=submit value="Submit"> 
</form> 
</body> 
</html>

listing 9
import java.io.*; 
import javax.servlet.*; 
import javax.servlet.http.*; 
 
public class AddCookieServlet extends HttpServlet { 
 
  public void doPost(HttpServletRequest request,  
    HttpServletResponse response)  
  throws ServletException, IOException { 
 
    // Get parameter from HTTP request. 
    String data = request.getParameter("data"); 
 
    // Create cookie. 
    Cookie cookie = new Cookie("MyCookie", data); 
 
    // Add cookie to HTTP response. 
    response.addCookie(cookie); 
 
    // Write output to browser. 
    response.setContentType("text/html"); 
    PrintWriter pw = response.getWriter(); 
    pw.println("<B>MyCookie has been set to"); 
    pw.println(data); 
    pw.close(); 
  } 
}

listing 10
import java.io.*; 
import javax.servlet.*; 
import javax.servlet.http.*; 
 
public class GetCookiesServlet extends HttpServlet { 
 
  public void doGet(HttpServletRequest request,  
    HttpServletResponse response)  
  throws ServletException, IOException { 
 
    // Get cookies from header of HTTP request. 
    Cookie[] cookies = request.getCookies(); 
 
    // Display these cookies. 
    response.setContentType("text/html"); 
    PrintWriter pw = response.getWriter(); 
    pw.println("<B>"); 
    for(int i = 0; i < cookies.length; i++) { 
      String name = cookies[i].getName(); 
      String value = cookies[i].getValue(); 
      pw.println("name = " + name +  
        "; value = " + value); 
    } 
    pw.close(); 
  } 
}

listing 11
import java.io.*; 
import java.util.*; 
import javax.servlet.*; 
import javax.servlet.http.*; 
 
public class DateServlet extends HttpServlet { 
 
  public void doGet(HttpServletRequest request,  
    HttpServletResponse response)  
  throws ServletException, IOException { 
 
    // Get the HttpSession object. 
    HttpSession hs = request.getSession(true); 
 
    // Get writer. 
    response.setContentType("text/html"); 
    PrintWriter pw = response.getWriter(); 
    pw.print("<B>"); 
 
    // Display date/time of last access. 
    Date date = (Date)hs.getAttribute("date"); 
    if(date != null) { 
      pw.print("Last access: " + date + "<br>"); 
    } 
 
    // Display current date/time. 
    date = new Date(); 
    hs.setAttribute("date", date); 
    pw.println("Current date: " + date); 
  } 
}


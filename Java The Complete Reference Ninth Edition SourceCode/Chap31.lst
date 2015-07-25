listing 1
// A simple Swing application. 
 
import javax.swing.*; 
  
class SwingDemo { 
 
  SwingDemo() { 
 
    // Create a new JFrame container. 
    JFrame jfrm = new JFrame("A Simple Swing Application"); 
 
    // Give the frame an initial size. 
    jfrm.setSize(275, 100); 
 
    // Terminate the program when the user closes the application. 
    jfrm.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); 
 
    // Create a text-based label. 
    JLabel jlab = new JLabel(" Swing means powerful GUIs."); 
 
    // Add the label to the content pane. 
    jfrm.add(jlab); 
 
    // Display the frame. 
    jfrm.setVisible(true); 
  } 
 
  public static void main(String args[]) { 
    // Create the frame on the event dispatching thread. 
    SwingUtilities.invokeLater(new Runnable() { 
      public void run() { 
        new SwingDemo(); 
      } 
    }); 
  } 
}

listing 2
// Handle an event in a Swing program. 
 
import java.awt.*; 
import java.awt.event.*; 
import javax.swing.*; 
  
class EventDemo { 
 
  JLabel jlab; 
 
  EventDemo() { 
 
    // Create a new JFrame container. 
    JFrame jfrm = new JFrame("An Event Example"); 
 
    // Specify FlowLayout for the layout manager. 
    jfrm.setLayout(new FlowLayout()); 
 
    // Give the frame an initial size. 
    jfrm.setSize(220, 90); 
 
    // Terminate the program when the user closes the application. 
    jfrm.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); 
 
    // Make two buttons. 
    JButton jbtnAlpha = new JButton("Alpha"); 
    JButton jbtnBeta = new JButton("Beta"); 
 
    // Add action listener for Alpha. 
    jbtnAlpha.addActionListener(new ActionListener() { 
      public void actionPerformed(ActionEvent ae) { 
        jlab.setText("Alpha was pressed."); 
      } 
    }); 
 
    // Add action listener for Beta. 
    jbtnBeta.addActionListener(new ActionListener() { 
      public void actionPerformed(ActionEvent ae) { 
        jlab.setText("Beta was pressed."); 
      } 
    }); 
 
    // Add the buttons to the content pane. 
    jfrm.add(jbtnAlpha);  
    jfrm.add(jbtnBeta);  
 
    // Create a text-based label. 
    jlab = new JLabel("Press a button."); 
 
    // Add the label to the content pane. 
    jfrm.add(jlab); 
 
    // Display the frame. 
    jfrm.setVisible(true); 
  } 
 
  public static void main(String args[]) { 
    // Create the frame on the event dispatching thread. 
    SwingUtilities.invokeLater(new Runnable() { 
      public void run() { 
        new EventDemo(); 
      } 
    }); 
  } 
}

listing 3
// A simple Swing-based applet 
 
import javax.swing.*; 
import java.awt.*; 
import java.awt.event.*; 
 
/* 
This HTML can be used to launch the applet: 
 
<applet code="MySwingApplet" width=220 height=90> 
</applet> 
*/ 
 
public class MySwingApplet extends JApplet { 
  JButton jbtnAlpha; 
  JButton jbtnBeta; 
 
  JLabel jlab; 
 
  // Initialize the applet. 
  public void init() { 
    try { 
      SwingUtilities.invokeAndWait(new Runnable () { 
        public void run() { 
          makeGUI(); // initialize the GUI 
        } 
      }); 
    } catch(Exception exc) { 
      System.out.println("Can't create because of "+ exc); 
    } 
  } 
 
  // This applet does not need to override start(), stop(), 
  // or destroy().  
 
  // Setup and initialize the GUI.  
  private void makeGUI() { 
    // Set the applet to use flow layout. 
    setLayout(new FlowLayout()); 
 
    // Make two buttons. 
    jbtnAlpha = new JButton("Alpha"); 
    jbtnBeta = new JButton("Beta"); 
 
    // Add action listener for Alpha. 
    jbtnAlpha.addActionListener(new ActionListener() {      
      public void actionPerformed(ActionEvent le) {  
        jlab.setText("Alpha was pressed.");  
      } 
    }); 
 
    // Add action listener for Beta. 
    jbtnBeta.addActionListener(new ActionListener() {      
      public void actionPerformed(ActionEvent le) {  
        jlab.setText("Beta was pressed.");  
      }      
    });      
 
    // Add the buttons to the content pane. 
    add(jbtnAlpha); 
    add(jbtnBeta); 
 
    // Create a text-based label. 
    jlab = new JLabel("Press a button."); 
 
    // Add the label to the content pane. 
    add(jlab);     
  } 
}

listing 3
// Paint lines to a panel. 
   
import java.awt.*;   
import java.awt.event.*;   
import javax.swing.*;   
import java.util.*; 
   
// This class extends JPanel. It overrides 
// the paintComponent() method so that random 
// lines are plotted in the panel. 
class PaintPanel extends JPanel {   
  Insets ins; // holds the panel's insets 
 
  Random rand; // used to generate random numbers 
 
  // Construct a panel. 
  PaintPanel() {   
     
    // Put a border around the panel. 
    setBorder( 
      BorderFactory.createLineBorder(Color.RED, 5)); 
 
    rand = new Random(); 
  } 
 
  // Override the paintComponent() method. 
  protected void paintComponent(Graphics g) { 
    // Always call the superclass method first. 
    super.paintComponent(g); 
 
    int x, y, x2, y2; 
 
    // Get the height and width of the component. 
    int height = getHeight(); 
    int width = getWidth(); 
 
    // Get the insets. 
    ins = getInsets(); 
 
    // Draw ten lines whose endpoints are randomly generated. 
    for(int i=0; i < 10; i++) { 
      // Obtain random coordinates that define 
      // the endpoints of each line. 
      x = rand.nextInt(width-ins.left); 
      y = rand.nextInt(height-ins.bottom); 
      x2 = rand.nextInt(width-ins.left); 
      y2 = rand.nextInt(height-ins.bottom); 
 
      // Draw the line. 
      g.drawLine(x, y, x2, y2); 
    } 
  } 
} 
 
// Demonstrate painting directly onto a panel. 
class PaintDemo { 
 
  JLabel jlab; 
  PaintPanel pp; 
 
  PaintDemo() { 
 
    // Create a new JFrame container. 
    JFrame jfrm = new JFrame("Paint Demo"); 
   
    // Give the frame an initial size.   
    jfrm.setSize(200, 150);   
   
    // Terminate the program when the user closes the application. 
    jfrm.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); 
   
    // Create the panel that will be painted. 
    pp = new PaintPanel(); 
 
    // Add the panel to the content pane.  Because the default 
    // border layout is used, the panel will automatically be 
    // sized to fit the center region. 
    jfrm.add(pp);    
 
    // Display the frame.   
    jfrm.setVisible(true);   
  }   
    
  public static void main(String args[]) {   
    // Create the frame on the event dispatching thread.   
    SwingUtilities.invokeLater(new Runnable() {   
      public void run() {   
        new PaintDemo();   
      }   
    });   
  }   
}


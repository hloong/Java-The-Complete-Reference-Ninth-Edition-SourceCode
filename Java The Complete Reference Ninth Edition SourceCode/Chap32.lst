listing 1
// Demonstrate JLabel and ImageIcon. 
import java.awt.*; 
import javax.swing.*; 
/* 
  <applet code="JLabelDemo" width=250 height=200> 
  </applet> 
*/ 
 
public class JLabelDemo extends JApplet { 
 
  public void init() { 
    try { 
      SwingUtilities.invokeAndWait( 
        new Runnable() { 
          public void run() { 
            makeGUI(); 
          } 
        } 
      ); 
    } catch (Exception exc) { 
      System.out.println("Can't create because of " + exc); 
    } 
  } 
 
  private void makeGUI() { 
 
    // Create an icon. 
    ImageIcon ii = new ImageIcon("hourglass.png"); 
 
    // Create a label. 
    JLabel jl = new JLabel("Hourglass", ii, JLabel.CENTER); 
 
    // Add the label to the content pane. 
    add(jl); 
  } 
}

listing 2
// Demonstrate JTextField. 
import java.awt.*; 
import java.awt.event.*; 
import javax.swing.*; 
/* 
  <applet code="JTextFieldDemo" width=300 height=50> 
  </applet> 
*/ 
   
public class JTextFieldDemo extends JApplet { 
  JTextField jtf; 
 
  public void init() { 
    try { 
      SwingUtilities.invokeAndWait( 
        new Runnable() { 
          public void run() { 
            makeGUI(); 
          } 
        } 
      ); 
    } catch (Exception exc) { 
      System.out.println("Can't create because of " + exc); 
    } 
  }     
 
  private void makeGUI() { 
 
    // Change to flow layout. 
    setLayout(new FlowLayout()); 
 
    // Add text field to content pane. 
    jtf = new JTextField(15); 
    add(jtf); 
    jtf.addActionListener(new ActionListener() { 
      public void actionPerformed(ActionEvent ae) { 
        // Show text when user presses ENTER. 
        showStatus(jtf.getText()); 
      } 
    }); 
  } 
}

listing 3
// Demonstrate an icon-based JButton. 
import java.awt.*; 
import java.awt.event.*; 
import javax.swing.*; 
/* 
  <applet code="JButtonDemo" width=250 height=750> 
  </applet> 
*/ 
   
public class JButtonDemo extends JApplet  
implements ActionListener { 
  JLabel jlab; 
 
  public void init() { 
    try { 
      SwingUtilities.invokeAndWait( 
        new Runnable() { 
          public void run() { 
            makeGUI(); 
          } 
        } 
      ); 
    } catch (Exception exc) { 
      System.out.println("Can't create because of " + exc); 
    } 
  }     
 
  private void makeGUI() { 
 
    // Change to flow layout. 
    setLayout(new FlowLayout()); 
 
    // Add buttons to content pane. 
    ImageIcon hourglass = new ImageIcon("hourglass.png"); 
    JButton jb = new JButton(hourglass); 
    jb.setActionCommand("Hourglass"); 
    jb.addActionListener(this); 
    add(jb); 
 
    ImageIcon analog = new ImageIcon("analog.png"); 
    jb = new JButton(analog); 
    jb.setActionCommand("Analog Clock"); 
    jb.addActionListener(this); 
    add(jb); 
 
    ImageIcon digital = new ImageIcon("digital.png"); 
    jb = new JButton(digital); 
    jb.setActionCommand("Digital Clock"); 
    jb.addActionListener(this); 
    add(jb); 
 
    ImageIcon stopwatch = new ImageIcon("stopwatch.png"); 
    jb = new JButton(stopwatch); 
    jb.setActionCommand("Stopwatch"); 
    jb.addActionListener(this); 
    add(jb); 
 
    // Create and add the label to content pane. 
    jlab = new JLabel("Choose a Timepiece"); 
    add(jlab); 
  } 
 
  // Handle button events. 
  public void actionPerformed(ActionEvent ae) { 
    jlab.setText("You selected " + ae.getActionCommand()); 
  } 
}

listing 4
// Demonstrate JToggleButton. 
import java.awt.*; 
import java.awt.event.*; 
import javax.swing.*; 
/* 
  <applet code="JToggleButtonDemo" width=200 height=80> 
  </applet> 
*/ 
 
public class JToggleButtonDemo extends JApplet { 
 
  JLabel jlab; 
  JToggleButton jtbn; 
 
  public void init() { 
    try { 
      SwingUtilities.invokeAndWait( 
        new Runnable() { 
          public void run() { 
            makeGUI(); 
          } 
        } 
      ); 
    } catch (Exception exc) { 
      System.out.println("Can't create because of " + exc); 
    } 
  } 
 
  private void makeGUI() { 
 
    // Change to flow layout. 
    setLayout(new FlowLayout()); 
  
    // Create a label. 
    jlab = new JLabel("Button is off.");  
 
    // Make a toggle button. 
    jtbn =  new JToggleButton("On/Off"); 
 
    // Add an item listener for the toggle button. 
    jtbn.addItemListener(new ItemListener() { 
      public void itemStateChanged(ItemEvent ie) { 
        if(jtbn.isSelected()) 
          jlab.setText("Button is on."); 
        else 
          jlab.setText("Button is off."); 
      } 
 
    }); 
  
    // Add the toggle button and label to the content pane.  
    add(jtbn);   
    add(jlab);  
  } 
}


listing 5
// Demonstrate JCheckbox. 
import java.awt.*; 
import java.awt.event.*; 
import javax.swing.*; 
/* 
  <applet code="JCheckBoxDemo" width=270 height=50> 
  </applet> 
*/ 
   
public class JCheckBoxDemo extends JApplet  
implements ItemListener { 
  JLabel jlab; 
 
  public void init() { 
    try { 
      SwingUtilities.invokeAndWait( 
        new Runnable() { 
          public void run() { 
            makeGUI(); 
          } 
        } 
      ); 
    } catch (Exception exc) { 
      System.out.println("Can't create because of " + exc); 
    } 
  }     
 
  private void makeGUI() { 
 
    // Change to flow layout. 
    setLayout(new FlowLayout()); 
 
    // Add check boxes to the content pane. 
    JCheckBox cb = new JCheckBox("C");  
    cb.addItemListener(this); 
    add(cb); 
 
    cb = new JCheckBox("C++"); 
    cb.addItemListener(this); 
    add(cb); 
 
    cb = new JCheckBox("Java"); 
    cb.addItemListener(this); 
    add(cb); 
 
    cb = new JCheckBox("Perl"); 
    cb.addItemListener(this); 
    add(cb); 
 
    // Create the label and add it to the content pane. 
    jlab = new JLabel("Select languages"); 
    add(jlab); 
  } 
 
  // Handle item events for the check boxes. 
  public void itemStateChanged(ItemEvent ie) { 
    JCheckBox cb = (JCheckBox)ie.getItem(); 
 
    if(cb.isSelected()) 
      jlab.setText(cb.getText() + " is selected"); 
    else 
      jlab.setText(cb.getText() + " is cleared"); 
  } 
}

listing 6
// Demonstrate JRadioButton 
import java.awt.*; 
import java.awt.event.*; 
import javax.swing.*; 
/* 
  <applet code="JRadioButtonDemo" width=300 height=50> 
  </applet> 
*/ 
   
public class JRadioButtonDemo extends JApplet  
implements ActionListener { 
  JLabel jlab; 
 
  public void init() { 
    try { 
      SwingUtilities.invokeAndWait( 
        new Runnable() { 
          public void run() { 
            makeGUI(); 
          } 
        } 
      ); 
    } catch (Exception exc) { 
      System.out.println("Can't create because of " + exc); 
    } 
  }     
 
  private void makeGUI() { 
 
    // Change to flow layout. 
    setLayout(new FlowLayout()); 
 
    // Create radio buttons and add them to content pane. 
    JRadioButton b1 = new JRadioButton("A"); 
    b1.addActionListener(this); 
    add(b1); 
 
    JRadioButton b2 = new JRadioButton("B"); 
    b2.addActionListener(this); 
    add(b2); 
 
    JRadioButton b3 = new JRadioButton("C"); 
    b3.addActionListener(this); 
    add(b3); 
       
    // Define a button group. 
    ButtonGroup bg = new ButtonGroup(); 
    bg.add(b1); 
    bg.add(b2); 
    bg.add(b3); 
 
    // Create a label and add it to the content pane. 
    jlab = new JLabel("Select One"); 
    add(jlab); 
  } 
 
  // Handle button selection. 
  public void actionPerformed(ActionEvent ae) { 
    jlab.setText("You selected " + ae.getActionCommand()); 
  } 
}

listing 7
// Demonstrate JTabbedPane. 
import javax.swing.*; 
/* 
  <applet code="JTabbedPaneDemo" width=400 height=100> 
  </applet> 
*/ 
 
public class JTabbedPaneDemo extends JApplet { 
 
  public void init() { 
    try { 
      SwingUtilities.invokeAndWait( 
        new Runnable() { 
          public void run() { 
            makeGUI(); 
          } 
        } 
      ); 
    } catch (Exception exc) { 
      System.out.println("Can't create because of " + exc); 
    } 
  }     
 
  private void makeGUI() { 
 
    JTabbedPane jtp = new JTabbedPane(); 
    jtp.addTab("Cities", new CitiesPanel()); 
    jtp.addTab("Colors", new ColorsPanel()); 
    jtp.addTab("Flavors", new FlavorsPanel()); 
    add(jtp); 
  } 
} 
 
// Make the panels that will be added to the tabbed pane. 
class CitiesPanel extends JPanel { 
 
  public CitiesPanel() { 
    JButton b1 = new JButton("New York"); 
    add(b1); 
    JButton b2 = new JButton("London"); 
    add(b2); 
    JButton b3 = new JButton("Hong Kong"); 
    add(b3); 
    JButton b4 = new JButton("Tokyo"); 
    add(b4); 
  } 
} 
 
class ColorsPanel extends JPanel { 
 
  public ColorsPanel() { 
    JCheckBox cb1 = new JCheckBox("Red"); 
    add(cb1); 
    JCheckBox cb2 = new JCheckBox("Green"); 
    add(cb2); 
    JCheckBox cb3 = new JCheckBox("Blue"); 
    add(cb3); 
  } 
} 
 
class FlavorsPanel extends JPanel { 
 
  public FlavorsPanel() { 
    JComboBox<String> jcb = new JComboBox<String>(); 
    jcb.addItem("Vanilla"); 
    jcb.addItem("Chocolate"); 
    jcb.addItem("Strawberry"); 
    add(jcb); 
  } 
}

listing 8
// Demonstrate JScrollPane. 
import java.awt.*; 
import javax.swing.*; 
/* 
  <applet code="JScrollPaneDemo" width=300 height=250> 
  </applet> 
*/ 
   
public class JScrollPaneDemo extends JApplet { 
 
  public void init() { 
    try { 
      SwingUtilities.invokeAndWait( 
        new Runnable() { 
          public void run() { 
            makeGUI(); 
          } 
        } 
      ); 
    } catch (Exception exc) { 
      System.out.println("Can't create because of " + exc); 
    } 
  }     
 
  private void makeGUI() { 
 
    // Add 400 buttons to a panel. 
    JPanel jp = new JPanel(); 
    jp.setLayout(new GridLayout(20, 20)); 
    int b = 0; 
    for(int i = 0; i < 20; i++) { 
      for(int j = 0; j < 20; j++) { 
        jp.add(new JButton("Button " + b)); 
        ++b; 
      } 
    } 
 
    // Create the scroll pane. 
    JScrollPane jsp = new JScrollPane(jp); 
 
    // Add the scroll pane to the content pane. 
    // Because the default border layout is used, 
    // the scroll pane will be added to the center. 
    add(jsp, BorderLayout.CENTER); 
  } 
}

listing 9
// Demonstrate JList. 
import javax.swing.*;  
import javax.swing.event.*; 
import java.awt.*; 
import java.awt.event.*; 
   
/* 
  <applet code="JListDemo" width=200 height=120> 
  </applet> 
*/ 
   
public class JListDemo extends JApplet { 
  JList<String> jlst; 
  JLabel jlab; 
  JScrollPane jscrlp; 
 
  // Create an array of cities. 
  String Cities[] = { "New York", "Chicago", "Houston", 
                      "Denver", "Los Angeles", "Seattle", 
                      "London", "Paris", "New Delhi", 
                      "Hong Kong", "Tokyo", "Sydney" }; 
 
  public void init() { 
    try { 
      SwingUtilities.invokeAndWait( 
        new Runnable() { 
          public void run() { 
            makeGUI(); 
          } 
        } 
      ); 
    } catch (Exception exc) { 
      System.out.println("Can't create because of " + exc); 
    } 
  }     
 
  private void makeGUI() { 
 
    // Change to flow layout. 
    setLayout(new FlowLayout()); 
 
    // Create a JList. 
    jlst = new JList<String>(Cities); 
 
    // Set the list selection mode to single-selection. 
    jlst.setSelectionMode(ListSelectionModel.SINGLE_SELECTION); 
 
    // Add the list to a scroll pane. 
    jscrlp = new JScrollPane(jlst); 
 
    // Set the preferred size of the scroll pane. 
    jscrlp.setPreferredSize(new Dimension(120, 90)); 
 
    // Make a label that displays the selection. 
    jlab = new JLabel("Choose a City"); 
 
    // Add selection listener for the list. 
    jlst.addListSelectionListener(new ListSelectionListener() {  
      public void valueChanged(ListSelectionEvent le) {  
        // Get the index of the changed item. 
        int idx = jlst.getSelectedIndex(); 
 
        // Display selection, if item was selected. 
        if(idx != -1) 
          jlab.setText("Current selection: " + Cities[idx]); 
        else // Othewise, reprompt. 
          jlab.setText("Choose a City"); 
 
      }  
    });  
 
    // Add the list and label to the content pane. 
    add(jscrlp); 
    add(jlab); 
  } 
}

listing 10
// Demonstrate JComboBox. 
import java.awt.*; 
import java.awt.event.*; 
import javax.swing.*; 
/* 
  <applet code="JComboBoxDemo" width=300 height=200> 
  </applet> 
*/ 
   
public class JComboBoxDemo extends JApplet { 
  JLabel jlab; 
  ImageIcon hourglass, analog, digital, stopwatch; 
  JComboBox<String> jcb; 
 
  String timepieces[] = { "Hourglass", "Analog", "Digital", "Stopwatch" }; 
 
  public void init() { 
    try { 
      SwingUtilities.invokeAndWait( 
        new Runnable() { 
          public void run() { 
            makeGUI(); 
          } 
        } 
      ); 
    } catch (Exception exc) { 
      System.out.println("Can't create because of " + exc); 
    } 
  }     
 
  private void makeGUI() { 
 
    // Change to flow layout. 
    setLayout(new FlowLayout()); 
 
    // Instantiate a combo box and add it to the content pane. 
    jcb = new JComboBox<String>(timepieces); 
    add(jcb); 
 
    // Handle selections. 
    jcb.addActionListener(new ActionListener() { 
      public void actionPerformed(ActionEvent ae) { 
        String s = (String) jcb.getSelectedItem(); 
        jlab.setIcon(new ImageIcon(s + ".png")); 
      } 
    }); 
 
 
    // Create a label and add it to the content pane. 
    jlab = new JLabel(new ImageIcon("hourglass.png")); 
    add(jlab); 
  } 
 
}

listing 11
// Demonstrate JTree. 
import java.awt.*; 
import javax.swing.event.*; 
import javax.swing.*; 
import javax.swing.tree.*; 
/* 
  <applet code="JTreeDemo" width=400 height=200> 
  </applet> 
*/ 
   
 
public class JTreeDemo extends JApplet { 
  JTree tree; 
  JLabel jlab; 
 
  public void init() { 
    try { 
      SwingUtilities.invokeAndWait( 
        new Runnable() { 
          public void run() { 
            makeGUI(); 
          } 
        } 
      ); 
    } catch (Exception exc) { 
      System.out.println("Can't create because of " + exc); 
    } 
  } 
 
  private void makeGUI() { 
 
    // Create top node of tree. 
    DefaultMutableTreeNode top = new DefaultMutableTreeNode("Options"); 
 
    // Create subtree of "A". 
    DefaultMutableTreeNode a = new DefaultMutableTreeNode("A"); 
    top.add(a); 
    DefaultMutableTreeNode a1 = new DefaultMutableTreeNode("A1"); 
    a.add(a1); 
    DefaultMutableTreeNode a2 = new DefaultMutableTreeNode("A2"); 
    a.add(a2); 
 
    // Create subtree of "B". 
    DefaultMutableTreeNode b = new DefaultMutableTreeNode("B"); 
    top.add(b); 
    DefaultMutableTreeNode b1 = new DefaultMutableTreeNode("B1"); 
    b.add(b1); 
    DefaultMutableTreeNode b2 = new DefaultMutableTreeNode("B2"); 
    b.add(b2); 
    DefaultMutableTreeNode b3 = new DefaultMutableTreeNode("B3"); 
    b.add(b3); 
 
    // Create the tree. 
    tree = new JTree(top); 
 
    // Add the tree to a scroll pane. 
    JScrollPane jsp = new JScrollPane(tree); 
 
    // Add the scroll pane to the content pane. 
    add(jsp); 
 
    // Add the label to the content pane. 
    jlab = new JLabel(); 
    add(jlab, BorderLayout.SOUTH); 
 
    // Handle tree selection events. 
    tree.addTreeSelectionListener(new TreeSelectionListener() { 
      public void valueChanged(TreeSelectionEvent tse) { 
        jlab.setText("Selection is " + tse.getPath()); 
      } 
    }); 
  } 
}

listing 12
// Demonstrate JTable. 
import java.awt.*; 
import javax.swing.*; 
/* 
  <applet code="JTableDemo" width=400 height=200> 
  </applet> 
*/ 
 
public class JTableDemo extends JApplet { 
 
  public void init() { 
    try { 
      SwingUtilities.invokeAndWait( 
        new Runnable() { 
          public void run() { 
            makeGUI(); 
          } 
        } 
      ); 
    } catch (Exception exc) { 
      System.out.println("Can't create because of " + exc); 
    } 
  } 
 
  private void makeGUI() { 
 
    // Initialize column headings. 
    String[] colHeads = { "Name", "Extension", "ID#" }; 
 
    // Initialize data. 
    Object[][] data = { 
      { "Gail", "4567", "865" }, 
      { "Ken", "7566", "555" }, 
      { "Viviane", "5634", "587" }, 
      { "Melanie", "7345", "922" }, 
      { "Anne", "1237", "333" }, 
      { "John", "5656", "314" }, 
      { "Matt", "5672", "217" }, 
      { "Claire", "6741", "444" }, 
      { "Erwin", "9023", "519" }, 
      { "Ellen", "1134", "532" }, 
      { "Jennifer", "5689", "112" }, 
      { "Ed", "9030", "133" }, 
      { "Helen", "6751", "145" } 
    }; 
 
    // Create the table. 
    JTable table = new JTable(data, colHeads); 
 
    // Add the table to a scroll pane. 
    JScrollPane jsp = new JScrollPane(table); 
 
    // Add the scroll pane to the content pane. 
    add(jsp); 
  } 
}


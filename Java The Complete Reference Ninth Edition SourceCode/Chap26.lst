listing 1
// Demonstrate Labels 
import java.awt.*; 
import java.applet.*; 
/* 
<applet code="LabelDemo" width=300 height=200> 
</applet> 
*/ 
 
public class LabelDemo extends Applet { 
  public void init() { 
    Label one = new Label("One"); 
    Label two = new Label("Two"); 
    Label three = new Label("Three"); 
 
    // add labels to applet window 
    add(one); 
    add(two); 
    add(three); 
  } 
}

listing 2
// Demonstrate Buttons 
import java.awt.*; 
import java.awt.event.*; 
import java.applet.*; 
/* 
  <applet code="ButtonDemo" width=250 height=150> 
  </applet> 
*/ 
 
public class ButtonDemo extends Applet implements ActionListener { 
  String msg = ""; 
  Button yes, no, maybe; 
 
  public void init() { 
    yes = new Button("Yes"); 
    no = new Button("No"); 
    maybe = new Button("Undecided"); 
 
    add(yes); 
    add(no); 
    add(maybe); 
 
    yes.addActionListener(this); 
    no.addActionListener(this); 
    maybe.addActionListener(this); 
  } 
 
  public void actionPerformed(ActionEvent ae) { 
    String str = ae.getActionCommand(); 
    if(str.equals("Yes")) { 
      msg = "You pressed Yes."; 
    } 
    else if(str.equals("No")) { 
      msg = "You pressed No."; 
    } 
    else { 
      msg = "You pressed Undecided."; 
    } 
 
    repaint(); 
  } 
 
  public void paint(Graphics g) { 
     g.drawString(msg, 6, 100); 
  } 
}

listing 3
// Recognize Button objects. 
import java.awt.*; 
import java.awt.event.*; 
import java.applet.*; 
/* 
  <applet code="ButtonList" width=250 height=150> 
  </applet> 
*/ 
 
public class ButtonList extends Applet implements ActionListener { 
  String msg = ""; 
  Button bList[] = new Button[3]; 
 
  public void init() { 
    Button yes = new Button("Yes"); 
    Button no = new Button("No"); 
    Button maybe = new Button("Undecided"); 
 
    // store references to buttons as added 
    bList[0] = (Button) add(yes); 
    bList[1] = (Button) add(no); 
    bList[2] = (Button) add(maybe); 
 
    // register to receive action events 
    for(int i = 0; i < 3; i++) { 
      bList[i].addActionListener(this); 
    } 
  } 
 
  public void actionPerformed(ActionEvent ae) { 
    for(int i = 0; i < 3; i++) { 
      if(ae.getSource() == bList[i]) { 
        msg = "You pressed " + bList[i].getLabel(); 
      } 
    } 
    repaint(); 
  } 
 
  public void paint(Graphics g) { 
     g.drawString(msg, 6, 100); 
  } 
}

listing 4
// Demonstrate check boxes.  
import java.awt.*; 
import java.awt.event.*; 
import java.applet.*; 
/* 
  <applet code="CheckboxDemo" width=240 height=200> 
  </applet> 
*/ 
 
public class CheckboxDemo extends Applet implements ItemListener { 
  String msg = ""; 
  Checkbox windows, android, solaris, mac; 
 
  public void init() { 
    windows = new Checkbox("Windows", null, true); 
    android = new Checkbox("Android"); 
    solaris = new Checkbox("Solaris"); 
    mac = new Checkbox("Mac OS"); 
 
    add(windows); 
    add(android); 
    add(solaris); 
    add(mac); 
 
    windows.addItemListener(this); 
    android.addItemListener(this); 
    solaris.addItemListener(this); 
    mac.addItemListener(this); 
  } 
 
  public void itemStateChanged(ItemEvent ie) { 
    repaint(); 
  } 
 
  // Display current state of the check boxes. 
  public void paint(Graphics g) { 
    msg = "Current state: "; 
    g.drawString(msg, 6, 80); 
    msg = "  Windows: " + windows.getState(); 
    g.drawString(msg, 6, 100); 
    msg = "  Android: " + android.getState(); 
    g.drawString(msg, 6, 120); 
    msg = "  Solaris: " + solaris.getState(); 
    g.drawString(msg, 6, 140); 
    msg = "  Mac OS: " + mac.getState(); 
    g.drawString(msg, 6, 160); 
  } 
}

listing 5
// Demonstrate check box group.  
import java.awt.*; 
import java.awt.event.*; 
import java.applet.*; 
/* 
  <applet code="CBGroup" width=240 height=200> 
  </applet> 
*/ 
 
public class CBGroup extends Applet implements ItemListener { 
  String msg = ""; 
  Checkbox windows, android, solaris, mac; 
  CheckboxGroup cbg; 
 
  public void init() { 
    cbg = new CheckboxGroup(); 
    windows = new Checkbox("Windows", cbg, true); 
    android = new Checkbox("Android", cbg, false); 
    solaris = new Checkbox("Solaris", cbg, false); 
    mac = new Checkbox("Mac OS", cbg, false); 
 
    add(windows); 
    add(android); 
    add(solaris); 
    add(mac); 
 
    windows.addItemListener(this); 
    android.addItemListener(this); 
    solaris.addItemListener(this); 
    mac.addItemListener(this); 
  } 
 
  public void itemStateChanged(ItemEvent ie) { 
    repaint(); 
  } 
 
  // Display current state of the check boxes. 
  public void paint(Graphics g) { 
    msg = "Current selection: "; 
    msg += cbg.getSelectedCheckbox().getLabel(); 
    g.drawString(msg, 6, 100); 
  } 
}


listing 6
// Demonstrate Choice lists.  
import java.awt.*; 
import java.awt.event.*; 
import java.applet.*; 
/* 
  <applet code="ChoiceDemo" width=300 height=180> 
  </applet> 
*/ 
 
public class ChoiceDemo extends Applet implements ItemListener { 
  Choice os, browser; 
  String msg = ""; 
 
  public void init() { 
    os = new Choice(); 
    browser = new Choice(); 
 
    // add items to os list 
    os.add("Windows"); 
    os.add("Android"); 
    os.add("Solaris"); 
    os.add("Mac OS"); 
 
    // add items to browser list 
    browser.add("Internet Explorer"); 
    browser.add("Firefox"); 
    browser.add("Chrome"); 
 
    // add choice lists to window 
    add(os); 
    add(browser); 
 
    // register to receive item events 
    os.addItemListener(this); 
    browser.addItemListener(this); 
  } 
 
  public void itemStateChanged(ItemEvent ie) { 
    repaint(); 
  } 
 
  // Display current selections. 
  public void paint(Graphics g) { 
    msg = "Current OS: "; 
    msg += os.getSelectedItem(); 
    g.drawString(msg, 6, 120); 
    msg = "Current Browser: "; 
    msg += browser.getSelectedItem(); 
    g.drawString(msg, 6, 140); 
  } 
}

listing 7
// Demonstrate Lists.  
import java.awt.*; 
import java.awt.event.*; 
import java.applet.*; 
/* 
  <applet code="ListDemo" width=300 height=180> 
  </applet> 
*/ 
 
public class ListDemo extends Applet implements ActionListener { 
  List os, browser; 
  String msg = ""; 
 
  public void init() { 
    os = new List(4, true); 
    browser = new List(4, false); 
 
    // add items to os list 
    os.add("Windows"); 
    os.add("Android"); 
    os.add("Solaris"); 
    os.add("Mac OS"); 
 
    // add items to browser list 
    browser.add("Internet Explorer"); 
    browser.add("Firefox"); 
    browser.add("Chrome"); 
 
    browser.select(1); 
 
    // add lists to window 
    add(os); 
    add(browser); 
 
    // register to receive action events 
    os.addActionListener(this); 
    browser.addActionListener(this); 
  } 
 
  public void actionPerformed(ActionEvent ae) { 
    repaint(); 
  } 
 
  // Display current selections. 
  public void paint(Graphics g) { 
    int idx[]; 
 
    msg = "Current OS: "; 
    idx = os.getSelectedIndexes(); 
    for(int i=0; i<idx.length; i++) 
      msg += os.getItem(idx[i]) + "  "; 
    g.drawString(msg, 6, 120); 
    msg = "Current Browser: "; 
    msg += browser.getSelectedItem(); 
    g.drawString(msg, 6, 140); 
  } 
}


listing 8
// Demonstrate scroll bars.  
import java.awt.*; 
import java.awt.event.*; 
import java.applet.*; 
/* 
  <applet code="SBDemo" width=300 height=200> 
  </applet> 
*/ 
 
public class SBDemo extends Applet 
  implements AdjustmentListener, MouseMotionListener { 
  String msg = ""; 
  Scrollbar vertSB, horzSB; 
 
  public void init() { 
    int width = Integer.parseInt(getParameter("width")); 
    int height = Integer.parseInt(getParameter("height")); 
 
    vertSB = new Scrollbar(Scrollbar.VERTICAL, 
                          0, 1, 0, height); 
    vertSB.setPreferredSize(new Dimension(20, 100));

    horzSB = new Scrollbar(Scrollbar.HORIZONTAL, 
                           0, 1, 0, width); 
    horzSB.setPreferredSize(new Dimension(100, 20));

    add(vertSB); 
    add(horzSB); 
 
    // register to receive adjustment events 
    vertSB.addAdjustmentListener(this); 
    horzSB.addAdjustmentListener(this); 
 
    addMouseMotionListener(this); 
  } 
 
  public void adjustmentValueChanged(AdjustmentEvent ae) { 
    repaint(); 
  } 
 
  // Update scroll bars to reflect mouse dragging. 
  public void mouseDragged(MouseEvent me) { 
    int x = me.getX(); 
    int y = me.getY(); 
    vertSB.setValue(y); 
    horzSB.setValue(x); 
    repaint(); 
  } 
 
  // Necessary for MouseMotionListener 
  public void mouseMoved(MouseEvent me) { 
  } 
 
  // Display current value of scroll bars. 
  public void paint(Graphics g) { 
     msg = "Vertical: " + vertSB.getValue(); 
     msg += ",  Horizontal: " + horzSB.getValue(); 
     g.drawString(msg, 6, 160); 
 
     // show current mouse drag position 
     g.drawString("*", horzSB.getValue(), 
                  vertSB.getValue()); 
  } 
}

listing 9
// Demonstrate text field.  
import java.awt.*; 
import java.awt.event.*; 
import java.applet.*; 
/* 
 
  <applet code="TextFieldDemo" width=380 height=150> 
  </applet> 
*/ 
 
public class TextFieldDemo extends Applet 
  implements ActionListener { 
 
  TextField name, pass; 
 
  public void init() { 
    Label namep = new Label("Name: ", Label.RIGHT); 
    Label passp = new Label("Password: ", Label.RIGHT); 
    name = new TextField(12); 
    pass = new TextField(8); 
    pass.setEchoChar('?'); 
 
    add(namep); 
    add(name); 
    add(passp); 
    add(pass); 
 
    // register to receive action events 
    name.addActionListener(this); 
    pass.addActionListener(this); 
  } 
 
  // User pressed Enter. 
  public void actionPerformed(ActionEvent ae) { 
    repaint(); 
  } 
 
  public void paint(Graphics g) { 
     g.drawString("Name: " + name.getText(), 6, 60); 
     g.drawString("Selected text in name: " 
                  + name.getSelectedText(), 6, 80); 
     g.drawString("Password: " + pass.getText(), 6, 100); 
  } 
}

listing 10
// Demonstrate TextArea. 
import java.awt.*; 
import java.applet.*; 
/* 
<applet code="TextAreaDemo" width=300 height=250> 
</applet> 
*/ 
 
public class TextAreaDemo extends Applet { 
  public void init() { 
    String val =  
      "Java 8 is the latest version of the most\n" + 
      "widely-used computer language for Internet programming,\n" + 
      "Building on a rich heritage, Java has advanced both\n" + 
      "the art and science of computer language design.\n\n" + 
      "One of the reasons for Java's ongoing success is its\n" + 
      "constant, steady rate of evolution. Java has never stood\n" + 
      "still. Instead, Java has consistently adapted to the\n" + 
      "rapidly changing landscape of the networked world.\n" + 
      "Moreover, Java has often led the way, charting the\n" + 
      "course for others to follow."; 
 
    TextArea text = new TextArea(val, 10, 30); 
    add(text); 
  } 
}

listing 11
// Use left-aligned flow layout.  
import java.awt.*; 
import java.awt.event.*; 
import java.applet.*; 
/* 
  <applet code="FlowLayoutDemo" width=240 height=200> 
  </applet> 
*/ 
 
public class FlowLayoutDemo extends Applet 
  implements ItemListener { 
 
  String msg = ""; 
  Checkbox windows, android, solaris, mac; 
 
  public void init() { 
    // set left-aligned flow layout 
    setLayout(new FlowLayout(FlowLayout.LEFT)); 
 
    windows = new Checkbox("Windows", null, true); 
    android = new Checkbox("Android"); 
    solaris = new Checkbox("Solaris"); 
    mac = new Checkbox("Mac OS"); 
 
    add(windows); 
    add(android); 
    add(solaris); 
    add(mac); 
 
    // register to receive item events 
    windows.addItemListener(this); 
    android.addItemListener(this); 
    solaris.addItemListener(this); 
    mac.addItemListener(this); 
  } 
 
  // Repaint when status of a check box changes. 
  public void itemStateChanged(ItemEvent ie) { 
    repaint(); 
  } 
 
  // Display current state of the check boxes. 
  public void paint(Graphics g) { 
 
    msg = "Current state: "; 
    g.drawString(msg, 6, 80); 
    msg = "  Windows: " + windows.getState(); 
    g.drawString(msg, 6, 100); 
    msg = "  Android: " + android.getState(); 
    g.drawString(msg, 6, 120); 
    msg = "  Solaris: " + solaris.getState(); 
    g.drawString(msg, 6, 140); 
    msg = "  Mac: " + mac.getState(); 
    g.drawString(msg, 6, 160); 
  } 
}


listing 12
// Demonstrate BorderLayout. 
import java.awt.*; 
import java.applet.*; 
import java.util.*; 
/* 
<applet code="BorderLayoutDemo" width=400 height=200> 
</applet> 
*/ 
 
public class BorderLayoutDemo extends Applet { 
  public void init() { 
    setLayout(new BorderLayout()); 
 
    add(new Button("This is across the top."), 
        BorderLayout.NORTH); 
    add(new Label("The footer message might go here."), 
        BorderLayout.SOUTH); 
    add(new Button("Right"), BorderLayout.EAST); 
    add(new Button("Left"), BorderLayout.WEST); 
 
    String msg = "The reasonable man adapts " + 
      "himself to the world;\n" + 
      "the unreasonable one persists in " + 
      "trying to adapt the world to himself.\n" + 
      "Therefore all progress depends " + 
      "on the unreasonable man.\n\n" + 
      "        - George Bernard Shaw\n\n"; 
 
    add(new TextArea(msg), BorderLayout.CENTER); 
  } 
}

listing 13
// Demonstrate BorderLayout with insets.  
import java.awt.*; 
import java.applet.*; 
import java.util.*; 
/* 
<applet code="InsetsDemo" width=400 height=200> 
</applet> 
*/ 
 
public class InsetsDemo extends Applet { 
  public void init() { 
    // set background color so insets can be easily seen 
    setBackground(Color.cyan); 
 
    setLayout(new BorderLayout()); 
 
    add(new Button("This is across the top."), 
        BorderLayout.NORTH); 
    add(new Label("The footer message might go here."), 
        BorderLayout.SOUTH); 
    add(new Button("Right"), BorderLayout.EAST); 
    add(new Button("Left"), BorderLayout.WEST); 
 
    String msg = "The reasonable man adapts " + 
      "himself to the world;\n" + 
      "the unreasonable one persists in " + 
      "trying to adapt the world to himself.\n" + 
      "Therefore all progress depends " + 
      "on the unreasonable man.\n\n" + 
      "        - George Bernard Shaw\n\n"; 
 
    add(new TextArea(msg), BorderLayout.CENTER); 
  } 
  // add insets 
  public Insets getInsets() { 
    return new Insets(10, 10, 10, 10); 
  } 
}

listing 14
// Demonstrate GridLayout 
import java.awt.*; 
import java.applet.*; 
/* 
<applet code="GridLayoutDemo" width=300 height=200> 
</applet> 
*/ 
 
public class GridLayoutDemo extends Applet { 
  static final int n = 4; 
  public void init() { 
    setLayout(new GridLayout(n, n)); 
 
    setFont(new Font("SansSerif", Font.BOLD, 24)); 
 
    for(int i = 0; i < n; i++) { 
      for(int j = 0; j < n; j++) { 
        int k = i * n + j; 
        if(k > 0) 
          add(new Button("" + k)); 
      } 
    } 
  } 
}

listing 15
// Demonstrate CardLayout.  
import java.awt.*; 
import java.awt.event.*; 
import java.applet.*; 
/* 
  <applet code="CardLayoutDemo" width=300 height=100> 
  </applet> 
*/ 
 
public class CardLayoutDemo extends Applet 
  implements ActionListener, MouseListener { 
 
  Checkbox windowsXP, windows7, windows8, android, solaris, mac; 
  Panel osCards; 
  CardLayout cardLO; 
  Button Win, Other; 
 
  public void init() { 
    Win = new Button("Windows"); 
    Other = new Button("Other"); 
    add(Win); 
    add(Other); 
 
    cardLO = new CardLayout(); 
    osCards = new Panel(); 
    osCards.setLayout(cardLO); // set panel layout to card layout 
 
    windowsXP = new Checkbox("Windows XP", null, true); 
    windows7 = new Checkbox("Windows 7", null, false); 
    windows8 = new Checkbox("Windows 8", null, false); 
    android = new Checkbox("Android"); 
    solaris = new Checkbox("Solaris"); 
    mac = new Checkbox("Mac OS"); 
 
    // add Windows check boxes to a panel 
    Panel winPan = new Panel(); 
    winPan.add(windowsXP); 
    winPan.add(windows7); 
    winPan.add(windows8); 
 
    // Add other OS check boxes to a panel 
    Panel otherPan = new Panel(); 
    otherPan.add(android); 
    otherPan.add(solaris); 
    otherPan.add(mac); 
 
    // add panels to card deck panel 
    osCards.add(winPan, "Windows"); 
    osCards.add(otherPan, "Other"); 
 
    // add cards to main applet panel 
    add(osCards); 
 
    // register to receive action events 
    Win.addActionListener(this); 
    Other.addActionListener(this); 
 
    // register mouse events 
    addMouseListener(this); 
  } 
 
  // Cycle through panels. 
  public void mousePressed(MouseEvent me) { 
    cardLO.next(osCards); 
  } 
 
  // Provide empty implementations for the other MouseListener methods. 
  public void mouseClicked(MouseEvent me) { 
  } 
  public void mouseEntered(MouseEvent me) { 
  } 
  public void mouseExited(MouseEvent me) { 
  } 
  public void mouseReleased(MouseEvent me) { 
  } 
 
  public void actionPerformed(ActionEvent ae) { 
    if(ae.getSource() == Win) { 
 
      cardLO.show(osCards, "Windows"); 
    } 
    else { 
      cardLO.show(osCards, "Other"); 
    } 
  } 
}


listing 16
// Use GridBagLayout. 
import java.awt.*; 
import java.awt.event.*; 
import java.applet.*; 
/* 
  <applet code="GridBagDemo" width=250 height=200> 
  </applet> 
*/ 
 
public class GridBagDemo extends Applet 
  implements ItemListener { 
 
  String msg = ""; 
  Checkbox windows, android, solaris, mac; 
 
  public void init() { 
    GridBagLayout gbag = new GridBagLayout(); 
    GridBagConstraints gbc = new GridBagConstraints(); 
    setLayout(gbag); 
 
    // Define check boxes. 
    windows = new Checkbox("Windows ", null, true); 
    android = new Checkbox("Android"); 
    solaris = new Checkbox("Solaris"); 
    mac = new Checkbox("Mac OS"); 
 
    // Define the grid bag. 
 
    // Use default row weight of 0 for first row. 
    gbc.weightx = 1.0; // use a column weight of 1 
    gbc.ipadx = 200; // pad by 200 units 
    gbc.insets = new Insets(4, 4, 0, 0); // inset slightly from top left 
 
    gbc.anchor = GridBagConstraints.NORTHEAST; 
 
    gbc.gridwidth = GridBagConstraints.RELATIVE; 
    gbag.setConstraints(windows, gbc); 
 
    gbc.gridwidth = GridBagConstraints.REMAINDER; 
    gbag.setConstraints(android, gbc); 
 
    // Give second row a weight of 1. 
    gbc.weighty = 1.0; 
 
    gbc.gridwidth = GridBagConstraints.RELATIVE; 
    gbag.setConstraints(solaris, gbc); 
 
    gbc.gridwidth = GridBagConstraints.REMAINDER; 
    gbag.setConstraints(mac, gbc); 
 
    // Add the components. 
    add(windows); 
    add(android); 
    add(solaris); 
    add(mac); 
 
    // Register to receive item events. 
    windows.addItemListener(this); 
    android.addItemListener(this); 
    solaris.addItemListener(this); 
    mac.addItemListener(this); 
  } 
 
  // Repaint when status of a check box changes. 
  public void itemStateChanged(ItemEvent ie) { 
    repaint(); 
  } 
 
  // Display current state of the check boxes. 
  public void paint(Graphics g) { 
    msg = "Current state: "; 
    g.drawString(msg, 6, 80); 
    msg = "  Windows: " + windows.getState(); 
    g.drawString(msg, 6, 100); 
    msg = "  Android: " + android.getState(); 
    g.drawString(msg, 6, 120); 
    msg = "  Solaris: " + solaris.getState(); 
    g.drawString(msg, 6, 140); 
    msg = "  Mac: " + mac.getState(); 
    g.drawString(msg, 6, 160); 
  } 
}

listing 17
// Illustrate menus.  
import java.awt.*; 
import java.awt.event.*; 
import java.applet.*; 
/* 
  <applet code="MenuDemo" width=250 height=250> 
  </applet> 
*/ 
 
// Create a subclass of Frame 
class MenuFrame extends Frame { 
  String msg = ""; 
  CheckboxMenuItem debug, test; 
 
  MenuFrame(String title) { 
    super(title); 
 
    // create menu bar and add it to frame 
    MenuBar mbar = new MenuBar(); 
    setMenuBar(mbar); 
 
    // create the menu items 
    Menu file = new Menu("File"); 
    MenuItem item1, item2, item3, item4, item5; 
    file.add(item1 = new MenuItem("New...")); 
    file.add(item2 = new MenuItem("Open...")); 
    file.add(item3 = new MenuItem("Close")); 
    file.add(item4 = new MenuItem("-")); 
    file.add(item5 = new MenuItem("Quit...")); 
    mbar.add(file); 
 
    Menu edit = new Menu("Edit"); 
    MenuItem item6, item7, item8, item9; 
    edit.add(item6 = new MenuItem("Cut")); 
    edit.add(item7 = new MenuItem("Copy")); 
    edit.add(item8 = new MenuItem("Paste")); 
    edit.add(item9 = new MenuItem("-")); 
 
    Menu sub = new Menu("Special"); 
    MenuItem item10, item11, item12; 
    sub.add(item10 = new MenuItem("First")); 
    sub.add(item11 = new MenuItem("Second")); 
    sub.add(item12 = new MenuItem("Third")); 
    edit.add(sub); 
 
    // these are checkable menu items 
    debug = new CheckboxMenuItem("Debug"); 
    edit.add(debug); 
    test = new CheckboxMenuItem("Testing"); 
    edit.add(test); 
 
    mbar.add(edit); 
 
    // create an object to handle action and item events 
    MyMenuHandler handler = new MyMenuHandler(this); 
    // register it to receive those events 
    item1.addActionListener(handler); 
    item2.addActionListener(handler); 
    item3.addActionListener(handler); 
    item4.addActionListener(handler); 
    item5.addActionListener(handler); 
    item6.addActionListener(handler); 
    item7.addActionListener(handler); 
    item8.addActionListener(handler); 
    item9.addActionListener(handler); 
    item10.addActionListener(handler); 
    item11.addActionListener(handler); 
    item12.addActionListener(handler); 
    debug.addItemListener(handler); 
    test.addItemListener(handler); 
 
    // create an object to handle window events 
    MyWindowAdapter adapter = new MyWindowAdapter(this); 
     // register it to receive those events 
    addWindowListener(adapter); 
  } 
 
  public void paint(Graphics g) { 
    g.drawString(msg, 10, 200); 
 
   if(debug.getState()) 
      g.drawString("Debug is on.", 10, 220); 
    else 
      g.drawString("Debug is off.", 10, 220); 
 
    if(test.getState()) 
      g.drawString("Testing is on.", 10, 240); 
    else 
      g.drawString("Testing is off.", 10, 240); 
  } 
} 
 
class MyWindowAdapter extends WindowAdapter { 
  MenuFrame menuFrame; 
  public MyWindowAdapter(MenuFrame menuFrame) { 
    this.menuFrame = menuFrame; 
  } 
  public void windowClosing(WindowEvent we) { 
    menuFrame.setVisible(false); 
  } 
} 
 
class MyMenuHandler implements ActionListener, ItemListener { 
  MenuFrame menuFrame; 
  public MyMenuHandler(MenuFrame menuFrame) { 
    this.menuFrame = menuFrame; 
  } 
  // Handle action events 
  public void actionPerformed(ActionEvent ae) { 
      String msg = "You selected "; 
      String arg = ae.getActionCommand(); 
      if(arg.equals("New...")) 
        msg += "New."; 
      else if(arg.equals("Open...")) 
        msg += "Open."; 
      else if(arg.equals("Close")) 
        msg += "Close."; 
      else if(arg.equals("Quit...")) 
        msg += "Quit."; 
      else if(arg.equals("Edit")) 
        msg += "Edit."; 
      else if(arg.equals("Cut")) 
        msg += "Cut."; 
      else if(arg.equals("Copy")) 
        msg += "Copy."; 
      else if(arg.equals("Paste")) 
        msg += "Paste."; 
      else if(arg.equals("First")) 
        msg += "First."; 
      else if(arg.equals("Second")) 
        msg += "Second."; 
      else if(arg.equals("Third")) 
        msg += "Third."; 
      else if(arg.equals("Debug")) 
        msg += "Debug."; 
      else if(arg.equals("Testing")) 
        msg += "Testing."; 
      menuFrame.msg = msg; 
      menuFrame.repaint(); 
  } 
  // Handle item events 
  public void itemStateChanged(ItemEvent ie) { 
    menuFrame.repaint(); 
  } 
} 
 
// Create frame window. 
public class MenuDemo extends Applet { 
  Frame f; 
 
  public void init() { 
    f = new MenuFrame("Menu Demo"); 
    int width = Integer.parseInt(getParameter("width")); 
    int height = Integer.parseInt(getParameter("height")); 
 
    setSize(new Dimension(width, height)); 
 
    f.setSize(width, height); 
    f.setVisible(true); 
  } 
 
  public void start() { 
    f.setVisible(true); 
  } 
 
  public void stop() { 
    f.setVisible(false); 
  } 
}

listing 18
// Demonstrate Dialog box.  
import java.awt.*; 
import java.awt.event.*; 
import java.applet.*; 
/* 
  <applet code="DialogDemo" width=250 height=250> 
  </applet> 
*/ 
 
// Create a subclass of Dialog. 
class SampleDialog extends Dialog implements ActionListener { 
  SampleDialog(Frame parent, String title) { 
    super(parent, title, false); 
    setLayout(new FlowLayout()); 
    setSize(300, 200); 
 
    add(new Label("Press this button:")); 
    Button b; 
    add(b = new Button("Cancel")); 
    b.addActionListener(this); 
  } 
 
  public void actionPerformed(ActionEvent ae) { 
     dispose(); 
  } 
 
  public void paint(Graphics g) { 
    g.drawString("This is in the dialog box", 10, 70); 
  } 
} 
 
// Create a subclass of Frame. 
class MenuFrame extends Frame { 
  String msg = ""; 
  CheckboxMenuItem debug, test; 
 
  MenuFrame(String title) { 
    super(title); 
 
    // create menu bar and add it to frame 
    MenuBar mbar = new MenuBar(); 
    setMenuBar(mbar); 
 
    // create the menu items 
    Menu file = new Menu("File"); 
    MenuItem item1, item2, item3, item4; 
    file.add(item1 = new MenuItem("New...")); 
    file.add(item2 = new MenuItem("Open...")); 
    file.add(item3 = new MenuItem("Close")); 
    file.add(new MenuItem("-")); 
    file.add(item4 = new MenuItem("Quit...")); 
    mbar.add(file); 
 
    Menu edit = new Menu("Edit"); 
    MenuItem item5, item6, item7; 
    edit.add(item5 = new MenuItem("Cut")); 
    edit.add(item6 = new MenuItem("Copy")); 
    edit.add(item7 = new MenuItem("Paste")); 
    edit.add(new MenuItem("-")); 
 
    Menu sub = new Menu("Special", true); 
    MenuItem item8, item9, item10; 
    sub.add(item8 = new MenuItem("First")); 
    sub.add(item9 = new MenuItem("Second")); 
    sub.add(item10 = new MenuItem("Third")); 
    edit.add(sub); 
 
    // these are checkable menu items 
    debug = new CheckboxMenuItem("Debug"); 
    edit.add(debug); 
    test = new CheckboxMenuItem("Testing"); 
    edit.add(test); 
 
    mbar.add(edit); 
 
    // create an object to handle action and item events 
    MyMenuHandler handler = new MyMenuHandler(this); 
    // register it to receive those events 
    item1.addActionListener(handler); 
    item2.addActionListener(handler); 
    item3.addActionListener(handler); 
    item4.addActionListener(handler); 
    item5.addActionListener(handler); 
    item6.addActionListener(handler); 
    item7.addActionListener(handler); 
    item8.addActionListener(handler); 
    item9.addActionListener(handler); 
    item10.addActionListener(handler); 
    debug.addItemListener(handler); 
    test.addItemListener(handler); 
 
    // create an object to handle window events 
    MyWindowAdapter adapter = new MyWindowAdapter(this); 
     // register it to receive those events 
    addWindowListener(adapter); 
  } 
  public void paint(Graphics g) { 
    g.drawString(msg, 10, 200); 
 
    if(debug.getState()) 
      g.drawString("Debug is on.", 10, 220); 
    else 
      g.drawString("Debug is off.", 10, 220); 
 
    if(test.getState()) 
      g.drawString("Testing is on.", 10, 240); 
    else 
    g.drawString("Testing is off.", 10, 240); 
  } 
} 
 
class MyWindowAdapter extends WindowAdapter { 
  MenuFrame menuFrame; 
  public MyWindowAdapter(MenuFrame menuFrame) { 
    this.menuFrame = menuFrame; 
  } 
  public void windowClosing(WindowEvent we) { 
    menuFrame.dispose(); 
  } 
} 
 
class MyMenuHandler implements ActionListener, ItemListener { 
  MenuFrame menuFrame; 
  public MyMenuHandler(MenuFrame menuFrame) { 
    this.menuFrame = menuFrame; 
  } 
  // Handle action events 
  public void actionPerformed(ActionEvent ae) { 
      String msg = "You selected "; 
      String arg = ae.getActionCommand(); 
     // Activate a dialog box when New is selected. 
     if(arg.equals("New...")) { 
        msg += "New."; 
        SampleDialog d = new 
          SampleDialog(menuFrame, "New Dialog Box"); 
        d.setVisible(true); 
      } 
      // Try defining other dialog boxes for these options. 
      else if(arg.equals("Open...")) 
        msg += "Open."; 
      else if(arg.equals("Close")) 
        msg += "Close."; 
      else if(arg.equals("Quit...")) 
        msg += "Quit."; 
      else if(arg.equals("Edit")) 
        msg += "Edit."; 
      else if(arg.equals("Cut")) 
        msg += "Cut."; 
      else if(arg.equals("Copy")) 
        msg += "Copy."; 
      else if(arg.equals("Paste")) 
        msg += "Paste."; 
      else if(arg.equals("First")) 
        msg += "First."; 
      else if(arg.equals("Second")) 
        msg += "Second."; 
      else if(arg.equals("Third")) 
        msg += "Third."; 
      else if(arg.equals("Debug")) 
        msg += "Debug."; 
      else if(arg.equals("Testing")) 
        msg += "Testing."; 
      menuFrame.msg = msg; 
      menuFrame.repaint(); 
  } 
  public void itemStateChanged(ItemEvent ie) { 
      menuFrame.repaint(); 
  } 
} 
 
// Create frame window. 
public class DialogDemo extends Applet { 
  Frame f; 
 
  public void init() { 
    f = new MenuFrame("Menu Demo"); 
    int width = Integer.parseInt(getParameter("width")); 
    int height = Integer.parseInt(getParameter("height")); 
 
    setSize(width, height); 
 
    f.setSize(width, height); 
    f.setVisible(true); 
  } 
 
  public void start() { 
    f.setVisible(true); 
  } 
 
  public void stop() { 
    f.setVisible(false); 
  } 
}

listing 19
/* Demonstrate File Dialog box.   
  
   This is an application, not an applet.  
*/  
import java.awt.*;  
import java.awt.event.*;  
  
// Create a subclass of Frame  
class SampleFrame extends Frame {  
  SampleFrame(String title) {  
    super(title);  
 
    // Remove the window when closed. 
    addWindowListener(new WindowAdapter() { 
      public void windowClosing(WindowEvent we) { 
        System.exit(0); 
      } 
    }); 
 
  }  
}  
 
// Demonstrate FileDialog. 
class FileDialogDemo {  
  public static void main(String args[]) {  
    // Create a frame that owns the dialog. 
    Frame f = new SampleFrame("File Dialog Demo");  
    f.setVisible(true);  
    f.setSize(100, 100);  
 
    FileDialog fd = new FileDialog(f, "File Dialog");  
 
    fd.setVisible(true);  
  }  
}


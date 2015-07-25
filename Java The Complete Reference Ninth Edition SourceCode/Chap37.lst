listing 1
// A simple Bean. 
import java.awt.*; 
import java.awt.event.*; 
import java.io.Serializable; 
 
public class Colors extends Canvas implements Serializable { 
  transient private Color color; // not persistent 
  private boolean rectangular; // is persistent 
 
  public Colors() { 
    addMouseListener(new MouseAdapter() { 
      public void mousePressed(MouseEvent me) { 
        change(); 
      } 
    }); 
    rectangular = false; 
    setSize(200, 100); 
    change(); 
  } 
 
  public boolean getRectangular() { 
    return rectangular; 
  } 
 
  public void setRectangular(boolean flag) { 
    this.rectangular = flag; 
    repaint(); 
  } 
 
  public void change() { 
    color = randomColor(); 
    repaint(); 
  } 
 
  private Color randomColor() { 
    int r = (int)(255*Math.random()); 
    int g = (int)(255*Math.random()); 
    int b = (int)(255*Math.random()); 
    return new Color(r, g, b); 
  } 
 
  public void paint(Graphics g) { 
    Dimension d = getSize(); 
    int h = d.height; 
    int w = d.width; 
    g.setColor(color); 
    if(rectangular) { 
      g.fillRect(0, 0, w-1, h-1); 
    } 
    else { 
      g.fillOval(0, 0, w-1, h-1); 
    } 
  } 
}

listing 2
// A Bean information class. 
import java.beans.*; 
public class ColorsBeanInfo extends SimpleBeanInfo { 
  public PropertyDescriptor[] getPropertyDescriptors() { 
    try { 
      PropertyDescriptor rectangular = new 
         PropertyDescriptor("rectangular", Colors.class); 
      PropertyDescriptor pd[] = {rectangular}; 
      return pd; 
    } 
    catch(Exception e) { 
      System.out.println("Exception caught. " + e); 
    } 
    return null; 
  } 
}

listing 3
// Show properties and events. 
import java.awt.*; 
import java.beans.*; 
 
public class IntrospectorDemo { 
  public static void main(String args[]) { 
    try { 
      Class<?> c = Class.forName("Colors"); 
      BeanInfo beanInfo = Introspector.getBeanInfo(c); 
 
      System.out.println("Properties:"); 
      PropertyDescriptor propertyDescriptor[] =  
        beanInfo.getPropertyDescriptors(); 
      for(int i = 0; i < propertyDescriptor.length; i++) { 
        System.out.println("\t" + propertyDescriptor[i].getName()); 
      } 
 
      System.out.println("Events:"); 
      EventSetDescriptor eventSetDescriptor[] =  
        beanInfo.getEventSetDescriptors(); 
      for(int i = 0; i < eventSetDescriptor.length; i++) { 
        System.out.println("\t" + eventSetDescriptor[i].getName()); 
      } 
    } 
    catch(Exception e) { 
      System.out.println("Exception caught. " + e); 
    } 
  } 
}


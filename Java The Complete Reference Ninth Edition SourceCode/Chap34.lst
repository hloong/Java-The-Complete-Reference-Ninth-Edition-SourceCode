listing 1
// A JavaFX application skeleton. 
 
import javafx.application.*; 
import javafx.scene.*; 
import javafx.stage.*; 
import javafx.scene.layout.*; 
 
public class JavaFXSkel extends Application { 
 
  public static void main(String[] args) { 
  
    System.out.println("Launching JavaFX application."); 
  
    // Start the JavaFX application by calling launch(). 
    launch(args);   
  } 
 
  // Override the init() method. 
  public void init() { 
    System.out.println("Inside the init() method."); 
  } 
 
  // Override the start() method. 
  public void start(Stage myStage) { 
 
    System.out.println("Inside the start() method."); 
 
    // Give the stage a title. 
    myStage.setTitle("JavaFX Skeleton."); 
 
    // Create a root node. In this case, a flow layout pane 
    // is used, but several alternatives exist. 
    FlowPane rootNode = new FlowPane(); 
 
    // Create a scene. 
    Scene myScene = new Scene(rootNode, 300, 200); 
 
    // Set the scene on the stage. 
    myStage.setScene(myScene); 
 
    // Show the stage and its scene. 
    myStage.show(); 
 
  } 
 
  // Override the stop() method. 
  public void stop() { 
    System.out.println("Inside the stop() method."); 
  } 
}

listing 2
// Demontrate a JavaFX label. 
 
import javafx.application.*; 
import javafx.scene.*; 
import javafx.stage.*; 
import javafx.scene.layout.*; 
import javafx.scene.control.*; 
 
public class JavaFXLabelDemo extends Application { 
 
  public static void main(String[] args) { 
 
    // Start the JavaFX application by calling launch(). 
    launch(args);   
  } 
 
  // Override the start() method. 
  public void start(Stage myStage) { 
 
    // Give the stage a title. 
    myStage.setTitle("Demonstrate a JavaFX label."); 
 
    // Use a FlowPane for the root node. 
    FlowPane rootNode = new FlowPane(); 
 
    // Create a scene. 
    Scene myScene = new Scene(rootNode, 300, 200); 
 
    // Set the scene on the stage. 
    myStage.setScene(myScene); 
 
    // Create a label. 
    Label myLabel = new Label("This is a JavaFX label"); 
 
    // Add the label to the scene graph. 
    rootNode.getChildren().add(myLabel); 
 
    // Show the stage and its scene. 
    myStage.show(); 
  } 
}

listing 3
// Demonstrate JavaFX events and buttons. 
 
import javafx.application.*; 
import javafx.scene.*; 
import javafx.stage.*; 
import javafx.scene.layout.*; 
import javafx.scene.control.*; 
import javafx.event.*; 
import javafx.geometry.*; 
 
public class JavaFXEventDemo extends Application { 
 
  Label response; 
 
  public static void main(String[] args) { 
 
    // Start the JavaFX application by calling launch(). 
    launch(args);   
  } 
 
  // Override the start() method. 
  public void start(Stage myStage) { 
 
    // Give the stage a title. 
    myStage.setTitle("Demonstrate JavaFX Buttons and Events."); 
 
    // Use a FlowPane for the root node. In this case, 
    // vertical and horizontal gaps of 10. 
    FlowPane rootNode = new FlowPane(10, 10); 
 
    // Center the controls in the scene. 
    rootNode.setAlignment(Pos.CENTER); 
 
    // Create a scene. 
    Scene myScene = new Scene(rootNode, 300, 100); 
 
    // Set the scene on the stage. 
    myStage.setScene(myScene); 
 
    // Create a label. 
    response = new Label("Push a Button"); 
 
    // Create two push buttons. 
    Button btnAlpha = new Button("Alpha"); 
    Button btnBeta = new Button("Beta"); 
 
    // Handle the action events for the Alpha button. 
    btnAlpha.setOnAction(new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) { 
        response.setText("Alpha was pressed."); 
      } 
    }); 
 
    // Handle the action events for the Beta button. 
    btnBeta.setOnAction(new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) { 
        response.setText("Beta was pressed."); 
      } 
    }); 
 
    // Add the label and buttons to the scene graph. 
    rootNode.getChildren().addAll(btnAlpha, btnBeta, response); 
 
    // Show the stage and its scene. 
    myStage.show(); 
  } 
}

listing 4
btnAlpha.setOnAction( (ae) ->  
                      response.setText("Alpha was pressed.") 
                    );

listing 5
// Demonstrate drawing. 
 
import javafx.application.*; 
import javafx.scene.*; 
import javafx.stage.*; 
import javafx.scene.layout.*; 
import javafx.scene.control.*; 
import javafx.event.*; 
import javafx.geometry.*; 
import javafx.scene.shape.*; 
import javafx.scene.canvas.*; 
import javafx.scene.paint.*; 
import javafx.scene.text.*; 
 
public class DirectDrawDemo extends Application { 
 
  GraphicsContext gc; 
 
  Color[] colors = { Color.RED, Color.BLUE, Color.GREEN, Color.BLACK }; 
  int colorIdx = 0; 
 
  public static void main(String[] args) { 
 
    // Start the JavaFX application by calling launch(). 
    launch(args);   
  } 
 
  // Override the start() method. 
  public void start(Stage myStage) { 
 
    // Give the stage a title. 
    myStage.setTitle("Draw Directly to a Canvas."); 
 
    // Use a FlowPane for the root node. 
    FlowPane rootNode = new FlowPane(); 
 
    // Center the nodes in the scene. 
    rootNode.setAlignment(Pos.CENTER); 
 
    // Create a scene. 
    Scene myScene = new Scene(rootNode, 450, 450); 
 
    // Set the scene on the stage. 
    myStage.setScene(myScene); 
 
    // Create a canvas. 
    Canvas myCanvas = new Canvas(400, 400); 
   
    // Get the graphics context for the canvas. 
    gc = myCanvas.getGraphicsContext2D(); 
 
    // Create a push button. 
    Button btnChangeColor = new Button("Change Color"); 
 
    // Handle the action events for the Change Color button. 
    btnChangeColor.setOnAction(new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) { 
 
        // Set the stroke and fill color. 
        gc.setStroke(colors[colorIdx]); 
        gc.setFill(colors[colorIdx]); 
 
        // Redraw the line, text, and filled rectangle in the 
        //  new color. This leaves the color of the other nodes 
        // unchanged. 
        gc.strokeLine(0, 0, 200, 200); 
        gc.fillText("This is drawn on the canvas.", 60, 50); 
        gc.fillRect(100, 320, 300, 40); 
 
        // Change the color. 
        colorIdx++; 
        if(colorIdx == colors.length) colorIdx= 0; 
      } 
    }); 
 
    // Draw initial output on the canvas. 
    gc.strokeLine(0, 0, 200, 200); 
    gc.strokeOval(100, 100, 200, 200); 
    gc.strokeRect(0, 200, 50, 200); 
    gc.fillOval(0, 0, 20, 20); 
    gc.fillRect(100, 320, 300, 40); 
 
    // Set the font size to 20 and draw text. 
    gc.setFont(new Font(20)); 
    gc.fillText("This is drawn on the canvas.", 60, 50); 
 
    // Add the canvas and button to the scene graph. 
    rootNode.getChildren().addAll(myCanvas, btnChangeColor); 
 
    // Show the stage and its scene. 
    myStage.show(); 
  } 
}


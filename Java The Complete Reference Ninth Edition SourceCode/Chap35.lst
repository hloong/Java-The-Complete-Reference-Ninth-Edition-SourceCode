listing 1
// Load and display an image. 
  
import javafx.application.*;  
import javafx.scene.*;  
import javafx.stage.*;  
import javafx.scene.layout.*;  
import javafx.geometry.*; 
import javafx.scene.image.*; 
 
  
public class ImageDemo extends Application {  
  
  public static void main(String[] args) {  
  
    // Start the JavaFX application by calling launch().  
    launch(args);    
  }  
  
  // Override the start() method.  
  public void start(Stage myStage) {  
  
    // Give the stage a title.  
    myStage.setTitle("Display an Image");  
  
    // Use a FlowPane for the root node.  
    FlowPane rootNode = new FlowPane();  
 
    // Use center alignment. 
    rootNode.setAlignment(Pos.CENTER); 
  
    // Create a scene.  
    Scene myScene = new Scene(rootNode, 300, 200);  
  
    // Set the scene on the stage.  
    myStage.setScene(myScene);  
 
    // Create an image. 
    Image hourglass = new Image("hourglass.png"); 
 
    // Create an image view that uses the image. 
    ImageView hourglassIV = new ImageView(hourglass); 
  
    // Add the image to the scene graph.  
    rootNode.getChildren().add(hourglassIV);  
 
    // Show the stage and its scene.  
    myStage.show();  
  }  
}

listing 2
// Demonstrate an image in a label.  
  
import javafx.application.*;  
import javafx.scene.*;  
import javafx.stage.*;  
import javafx.scene.layout.*;  
import javafx.scene.control.*;  
import javafx.geometry.*; 
import javafx.scene.image.*; 
  
public class LabelImageDemo extends Application {  
  
  public static void main(String[] args) {  
  
    // Start the JavaFX application by calling launch().  
    launch(args);    
  }  
  
  // Override the start() method.  
  public void start(Stage myStage) {  
  
    // Give the stage a title.  
    myStage.setTitle("Use an Image in a Label");  
  
    // Use a FlowPane for the root node.  
    FlowPane rootNode = new FlowPane();  
 
    // Use center alignment. 
    rootNode.setAlignment(Pos.CENTER); 
  
    // Create a scene.  
    Scene myScene = new Scene(rootNode, 300, 200);  
  
    // Set the scene on the stage.  
    myStage.setScene(myScene);  
 
    // Create an ImageView that contains the specified image. 
    ImageView hourglassIV = new ImageView("hourglass.png"); 
  
    // Create a label that contains both an image and text. 
    Label hourglassLabel = new Label("Hourglass", hourglassIV);  
 
    // Add the label to the scene graph.  
    rootNode.getChildren().add(hourglassLabel);  
 
    // Show the stage and its scene.  
    myStage.show();  
  }  
}

listing 3
// Use an image with a button. 
 
import javafx.application.*; 
import javafx.scene.*; 
import javafx.stage.*; 
import javafx.scene.layout.*; 
import javafx.scene.control.*; 
import javafx.event.*; 
import javafx.geometry.*; 
import javafx.scene.image.*; 
 
public class ButtonImageDemo extends Application { 
 
  Label response; 
 
  public static void main(String[] args) { 
 
    // Start the JavaFX application by calling launch(). 
    launch(args);   
  } 
 
  // Override the start() method. 
  public void start(Stage myStage) { 
 
    // Give the stage a title. 
    myStage.setTitle("Use Images with Buttons"); 
 
    // Use a FlowPane for the root node. In this case, 
    // vertical and horizontal gaps of 10. 
    FlowPane rootNode = new FlowPane(10, 10); 
 
    // Center the controls in the scene. 
    rootNode.setAlignment(Pos.CENTER); 
 
    // Create a scene. 
    Scene myScene = new Scene(rootNode, 250, 450); 
 
    // Set the scene on the stage. 
    myStage.setScene(myScene); 
 
    // Create a label. 
    response = new Label("Push a Button"); 
 
    // Create two image-based buttons. 
    Button btnHourglass = new Button("Hourglass", 
                                     new ImageView("hourglass.png")); 
    Button btnAnalogClock = new    Button("Analog Clock", 
                                     new ImageView("analog.png")); 
 
    // Position the text under the image. 
    btnHourglass.setContentDisplay(ContentDisplay.TOP); 
    btnAnalogClock.setContentDisplay(ContentDisplay.TOP); 
 
    // Handle the action events for the hourglass button. 
    btnHourglass.setOnAction(new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) { 
        response.setText("Hourglass Pressed"); 
      } 
    }); 
 
    // Handle the action events for the analog clock button. 
    btnAnalogClock.setOnAction(new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) { 
        response.setText("Analog Clock Pressed"); 
      } 
    }); 
 
    // Add the label and buttons to the scene graph. 
    rootNode.getChildren().addAll(btnHourglass, btnAnalogClock, response); 
 
    // Show the stage and its scene. 
    myStage.show(); 
  } 
}

listing 4
// Demonstrate a toggle button. 
 
import javafx.application.*; 
import javafx.scene.*; 
import javafx.stage.*; 
import javafx.scene.layout.*; 
import javafx.scene.control.*; 
import javafx.event.*; 
import javafx.geometry.*; 
 
public class ToggleButtonDemo extends Application { 
 
  ToggleButton tbOnOff; 
  Label response; 
 
  public static void main(String[] args) { 
 
    // Start the JavaFX application by calling launch(). 
    launch(args);   
  } 
 
  // Override the start() method. 
  public void start(Stage myStage) { 
 
    // Give the stage a title. 
    myStage.setTitle("Demonstrate a Toggle Button"); 
 
    // Use a FlowPane for the root node. In this case, 
    // vertical and horizontal gaps of 10. 
    FlowPane rootNode = new FlowPane(10, 10); 
 
    // Center the controls in the scene. 
    rootNode.setAlignment(Pos.CENTER); 
 
    // Create a scene. 
    Scene myScene = new Scene(rootNode, 220, 120); 
 
    // Set the scene on the stage. 
    myStage.setScene(myScene); 
 
    // Create a label. 
    response = new Label("Push the Button."); 
 
    // Create the toggle button. 
    tbOnOff = new ToggleButton("On/Off"); 
 
    // Handle action events for the toggle button. 
    tbOnOff.setOnAction(new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) { 
        if(tbOnOff.isSelected()) response.setText("Button is on."); 
        else response.setText("Button is off."); 
      } 
    }); 
 
    // Add the label and buttons to the scene graph. 
    rootNode.getChildren().addAll(tbOnOff, response); 
 
    // Show the stage and its scene. 
    myStage.show(); 
  } 
}

listing 5
// A simple demonstration of Radio Buttons. 
// 
// This program responds to the action events generated 
// by a radio button selection. It also shows how to 
// fire the button under program control. 
 
import javafx.application.*; 
import javafx.scene.*; 
import javafx.stage.*; 
import javafx.scene.layout.*; 
import javafx.scene.control.*; 
import javafx.event.*; 
import javafx.geometry.*; 
 
public class RadioButtonDemo extends Application { 
 
  Label response; 
 
  public static void main(String[] args) { 
 
    // Start the JavaFX application by calling launch(). 
    launch(args);   
  } 
 
  // Override the start() method. 
  public void start(Stage myStage) { 
 
    // Give the stage a title. 
    myStage.setTitle("Demonstrate Radio Buttons"); 
 
    // Use a FlowPane for the root node. In this case, 
    // vertical and horizontal gaps of 10. 
    FlowPane rootNode = new FlowPane(10, 10); 
 
    // Center the controls in the scene. 
    rootNode.setAlignment(Pos.CENTER); 
 
    // Create a scene. 
    Scene myScene = new Scene(rootNode, 220, 120); 
 
    // Set the scene on the stage. 
    myStage.setScene(myScene); 
 
    // Create a label that will report the selection. 
    response = new Label(""); 
 
    // Create the radio buttons. 
    RadioButton rbTrain = new RadioButton("Train"); 
    RadioButton rbCar = new RadioButton("Car"); 
    RadioButton rbPlane = new RadioButton("Airplane"); 
 
    // Create a toggle group. 
    ToggleGroup tg = new ToggleGroup(); 
 
    // Add each button to a toggle group. 
    rbTrain.setToggleGroup(tg); 
    rbCar.setToggleGroup(tg); 
    rbPlane.setToggleGroup(tg); 
 
    // Handle action events for the radio buttons. 
    rbTrain.setOnAction(new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) { 
        response.setText("Transport selected is train."); 
      } 
    }); 
 
    rbCar.setOnAction(new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) { 
        response.setText("Transport selected is car."); 
      } 
    }); 
 
    rbPlane.setOnAction(new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) { 
        response.setText("Transport selected is airplane."); 
      } 
    }); 
 
    // Fire the event for the first selection. This causes 
    // that radio button to be selected and an action event 
    // for that button to occur. 
    rbTrain.fire(); 
 
    // Add the label and buttons to the scene graph. 
    rootNode.getChildren().addAll(rbTrain, rbCar, rbPlane, response); 
 
    // Show the stage and its scene. 
    myStage.show(); 
  } 
}

listing 6
// Use a change listener to respond to a change of selection within 
// the group of radio buttons. 
tg.selectedToggleProperty().addListener(new ChangeListener<Toggle>() { 
  public void changed(ObservableValue<? extends Toggle> changed, 
                      Toggle oldVal, Toggle newVal) { 
 
    // Cast new to RadioButton. 
    RadioButton rb = (RadioButton) newVal;  
 
    // Display the selection. 
    response.setText("Transport selected is " + rb.getText()); 
  } 
}); 
 
// Select the first button. This will cause a change event 
// on the toggle group. 
rbTrain.setSelected(true);

listing 7
// This radio button example demonstrates how the 
// currently selected button in a group can be obtained 
// under program control, when it is needed, rather 
// than responding to action or change events. 
// 
// In this example, no events related to the radio  
// buttons are handled. Instead, the current selection 
// is simply obtained when the Confirm Selection push 
// button is pressed. 
 
import javafx.application.*; 
import javafx.scene.*; 
import javafx.stage.*; 
import javafx.scene.layout.*; 
import javafx.scene.control.*; 
import javafx.event.*; 
import javafx.geometry.*; 
 
public class RadioButtonDemo2 extends Application { 
 
  Label response; 
  ToggleGroup tg; 
 
  public static void main(String[] args) { 
 
    // Start the JavaFX application by calling launch(). 
    launch(args);   
  } 
 
  // Override the start() method. 
  public void start(Stage myStage) { 
 
    // Give the stage a title. 
    myStage.setTitle("Demonstrate Radio Buttons"); 
 
    // Use a FlowPane for the root node. In this case, 
    // vertical and horizontal gaps of 10. 
    FlowPane rootNode = new FlowPane(10, 10); 
 
    // Center the controls in the scene. 
    rootNode.setAlignment(Pos.CENTER); 
 
    // Create a scene. 
    Scene myScene = new Scene(rootNode, 200, 140); 
 
    // Set the scene on the stage. 
    myStage.setScene(myScene); 
 
    // Create two labels. 
    Label choose = new Label("    Select a Transport Type    "); 
    response = new Label("No transport confirmed"); 
 
    // Create push button will be used to confirm the selection. 
    Button btnConfirm = new Button("Confirm Transport Selection"); 
 
    // Create the radio buttons. 
    RadioButton rbTrain = new RadioButton("Train"); 
    RadioButton rbCar = new RadioButton("Car"); 
    RadioButton rbPlane = new RadioButton("Airplane"); 
 
    // Create a toggle group. 
    tg = new ToggleGroup(); 
 
    // Add each button to a toggle group. 
    rbTrain.setToggleGroup(tg); 
    rbCar.setToggleGroup(tg); 
    rbPlane.setToggleGroup(tg); 
 
    // Intially select one of the radio buttons. 
    rbTrain.setSelected(true); 
 
    // Handle action events for the confirm button. 
    btnConfirm.setOnAction(new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) { 
        // Get the radio button that is currently selected. 
        RadioButton rb = (RadioButton) tg.getSelectedToggle(); 
 
        // Display the selection. 
        response.setText(rb.getText() + " is confirmed."); 
      } 
    }); 
 
    // Use a separator to better organize the layout. 
    Separator separator = new Separator(); 
    separator.setPrefWidth(180); 
 
    // Add the label and buttons to the scene graph. 
    rootNode.getChildren().addAll(choose, rbTrain, rbCar, rbPlane, 
                                  separator, btnConfirm, response); 
 
    // Show the stage and its scene. 
    myStage.show(); 
  } 
}

listing 8
// Demonstrate Checkboxes. 
 
import javafx.application.*; 
import javafx.scene.*; 
import javafx.stage.*; 
import javafx.scene.layout.*; 
import javafx.scene.control.*; 
import javafx.event.*; 
import javafx.geometry.*; 
 
public class CheckboxDemo extends Application { 
 
  CheckBox cbWeb; 
  CheckBox cbDesktop; 
  CheckBox cbMobile; 
 
  Label response; 
  Label allTargets; 
 
  String targets = ""; 
 
  public static void main(String[] args) { 
 
    // Start the JavaFX application by calling launch(). 
    launch(args);   
  } 
 
  // Override the start() method. 
  public void start(Stage myStage) { 
 
    // Give the stage a title. 
    myStage.setTitle("Demonstrate Checkboxes"); 
 
    // Use a FlowPane for the root node. In this case, 
    // vertical and horizontal gaps of 10. 
    FlowPane rootNode = new FlowPane(10, 10); 
 
    // Center the controls in the scene. 
    rootNode.setAlignment(Pos.CENTER); 
 
    // Create a scene. 
    Scene myScene = new Scene(rootNode, 230, 140); 
 
    // Set the scene on the stage. 
    myStage.setScene(myScene); 
 
    Label heading = new Label("Select Deployment Options"); 
 
    // Create a label that will report the state of the 
    // selected checkbox. 
    response = new Label("No Deployment Selected"); 
 
    // Create a label that will report all targets selected. 
    allTargets = new Label("Target List: <none>"); 
 
    // Create the checkboxes. 
    cbWeb = new CheckBox("Web"); 
    cbDesktop = new CheckBox("Dekstop"); 
    cbMobile = new CheckBox("Mobile"); 
 
    // Handle action events for the checkboxes. 
    cbWeb.setOnAction(new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) { 
        if(cbWeb.isSelected()) 
          response.setText("Web deployment selected."); 
        else 
          response.setText("Web deployment cleared."); 
 
        showAll(); 
      } 
    }); 
 
    cbDesktop.setOnAction(new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) { 
        if(cbDesktop.isSelected()) 
          response.setText("Desktop deployment selected."); 
        else 
          response.setText("Desktop deployment cleared."); 
 
        showAll(); 
      } 
    }); 
 
    cbMobile.setOnAction(new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) { 
        if(cbMobile.isSelected()) 
          response.setText("Mobile deployment selected."); 
        else 
          response.setText("Mobile deployment cleared."); 
 
        showAll(); 
      } 
    }); 
 
    // Use a separator to better organize the layout. 
    Separator separator = new Separator(); 
    separator.setPrefWidth(200); 
 
    // Add controls to the scene graph. 
    rootNode.getChildren().addAll(heading, separator, cbWeb, cbDesktop, 
                                  cbMobile, response, allTargets); 
 
    // Show the stage and its scene. 
    myStage.show(); 
  } 
 
  // Update and show the targets list. 
  void showAll() { 
    targets = ""; 
    if(cbWeb.isSelected()) targets = "Web "; 
    if(cbDesktop.isSelected()) targets += "Desktop "; 
    if(cbMobile.isSelected()) targets += "Mobile"; 
 
    if(targets.equals("")) targets = "<none>"; 
 
    allTargets.setText("Target List: " + targets); 
  } 
}

listing 9
// Demonstrate a list view. 
 
import javafx.application.*; 
import javafx.scene.*; 
import javafx.stage.*; 
import javafx.scene.layout.*; 
import javafx.scene.control.*; 
import javafx.geometry.*; 
import javafx.beans.value.*; 
import javafx.collections.*; 
 
public class ListViewDemo extends Application { 
 
  Label response; 
 
  public static void main(String[] args) { 
 
    // Start the JavaFX application by calling launch(). 
    launch(args);   
  } 
 
  // Override the start() method. 
  public void start(Stage myStage) { 
 
    // Give the stage a title. 
    myStage.setTitle("ListView Demo"); 
 
    // Use a FlowPane for the root node. In this case, 
    // vertical and horizontal gaps of 10. 
    FlowPane rootNode = new FlowPane(10, 10); 
 
    // Center the controls in the scene. 
    rootNode.setAlignment(Pos.CENTER); 
 
    // Create a scene. 
    Scene myScene = new Scene(rootNode, 200, 120); 
 
    // Set the scene on the stage. 
    myStage.setScene(myScene); 
 
    // Create a label. 
    response = new Label("Select Transport Type"); 
 
    // Create an ObservableList of entries for the list view. 
    ObservableList<String> transportTypes = 
      FXCollections.observableArrayList( "Train", "Car", "Airplane" );  
 
    // Create the list view. 
    ListView<String> lvTransport = new ListView<String>(transportTypes); 
 
    // Set the preferred height and width. 
    lvTransport.setPrefSize(80, 80); 
 
    // Get the list view selection model. 
    MultipleSelectionModel<String> lvSelModel = 
                                     lvTransport.getSelectionModel(); 
 
    // Use a change listener to respond to a change of selection within 
    // a list view. 
    lvSelModel.selectedItemProperty().addListener( 
                                      new ChangeListener<String>() { 
      public void changed(ObservableValue<? extends String> changed, 
                          String oldVal, String newVal) { 
 
        // Display the selection. 
        response.setText("Transport selected is " + newVal); 
      } 
     }); 
 
    // Add the label and list view to the scene graph. 
    rootNode.getChildren().addAll(lvTransport, response); 
 
    // Show the stage and its scene. 
    myStage.show(); 
  } 
}

listing 10
lvSelModel.selectedItemProperty().addListener( 
                                  new ChangeListener<String>() { 
  public void changed(ObservableValue<? extends String> changed, 
                      String oldVal, String newVal) { 
 
    String selItems = ""; 
    ObservableList<String> selected = 
              lvTransport.getSelectionModel().getSelectedItems(); 
 
    // Display the selections. 
    for(int i=0; i < selected.size(); i++) 
      selItems += "\n      " + selected.get(i); 
           
    response.setText("All transports selected: " + selItems); 
  } 
});

listing 11
// Demonstrate a combo box. 
 
import javafx.application.*; 
import javafx.scene.*; 
import javafx.stage.*; 
import javafx.scene.layout.*; 
import javafx.scene.control.*; 
import javafx.geometry.*; 
import javafx.collections.*; 
import javafx.event.*; 
 
 
public class ComboBoxDemo extends Application { 
 
  ComboBox<String> cbTransport; 
  Label response; 
 
  public static void main(String[] args) { 
 
    // Start the JavaFX application by calling launch(). 
    launch(args);   
  } 
 
  // Override the start() method. 
  public void start(Stage myStage) { 
 
    // Give the stage a title. 
    myStage.setTitle("ComboBox Demo"); 
 
    // Use a FlowPane for the root node. In this case, 
    // vertical and horizontal gaps of 10. 
    FlowPane rootNode = new FlowPane(10, 10); 
 
    // Center the controls in the scene. 
    rootNode.setAlignment(Pos.CENTER); 
 
    // Create a scene. 
    Scene myScene = new Scene(rootNode, 280, 120); 
 
    // Set the scene on the stage. 
    myStage.setScene(myScene); 
 
    // Create a label. 
    response = new Label(); 
 
    // Create an ObservableList of entries for the combo box. 
    ObservableList<String> transportTypes = 
      FXCollections.observableArrayList( "Train", "Car", "Airplane" );  
 
    // Create a combo box. 
    cbTransport = new ComboBox<String>(transportTypes); 
 
    // Set the default value. 
    cbTransport.setValue("Train"); 
 
    // Set the response label to indicate the default selection. 
    response.setText("Selected Transport is " + cbTransport.getValue()); 
 
    // Listen for action events on the combo box. 
    cbTransport.setOnAction(new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) { 
        response.setText("Selected Transport is " + cbTransport.getValue()); 
      } 
    }); 
 
    // Add the label and combo box to the scene graph. 
    rootNode.getChildren().addAll(cbTransport, response); 
 
    // Show the stage and its scene. 
    myStage.show(); 
  } 
}

listing 12
// Demonstrate a text field. 
 
import javafx.application.*; 
import javafx.scene.*; 
import javafx.stage.*; 
import javafx.scene.layout.*; 
import javafx.scene.control.*; 
import javafx.event.*; 
import javafx.geometry.*; 
 
public class TextFieldDemo extends Application { 
 
  TextField tf; 
  Label response; 
 
  public static void main(String[] args) { 
 
    // Start the JavaFX application by calling launch(). 
    launch(args);   
  } 
 
  // Override the start() method. 
  public void start(Stage myStage) { 
 
    // Give the stage a title. 
    myStage.setTitle("Demonstrate a TextField"); 
 
    // Use a FlowPane for the root node. In this case, 
    // vertical and horizontal gaps of 10. 
    FlowPane rootNode = new FlowPane(10, 10); 
 
    // Center the controls in the scene. 
    rootNode.setAlignment(Pos.CENTER); 
 
    // Create a scene. 
    Scene myScene = new Scene(rootNode, 230, 140); 
 
    // Set the scene on the stage. 
    myStage.setScene(myScene); 
 
    // Create a label that will report the state of the 
    // selected checkbox. 
    response = new Label("Search String: "); 
 
    // Create a button that gets the text. 
    Button btnGetText = new Button("Get Search String"); 
 
    // Create a text field 
    tf = new TextField(); 
 
    // Set the prompt. 
    tf.setPromptText("Enter Search String"); 
 
    // Set preferred column count. 
    tf.setPrefColumnCount(15); 
 
    // Handle action events for the text field. Action 
    // events are generated when ENTER is pressed while 
    // the textfield has input focus. In this case, the 
    // text in the field is obtained and displayed. 
    tf.setOnAction(new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) { 
        response.setText("Search String: " + tf.getText()); 
      } 
    }); 
 
    // Get text from the text field when the button is pressed 
    // and display it. 
    btnGetText.setOnAction(new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) { 
        response.setText("Search String: " + tf.getText()); 
      } 
    }); 
 
    // Use a separator to better organize the layout. 
    Separator separator = new Separator(); 
    separator.setPrefWidth(180); 
 
    // Add controls to the scene graph. 
    rootNode.getChildren().addAll(tf, btnGetText, separator, response); 
 
    // Show the stage and its scene. 
    myStage.show(); 
  } 
}

listing 13
// Demonstrate a scroll pane.  
// This program scroll the contents of a multi-line 
// label, but any Node can be scrolled. 
  
import javafx.application.*;  
import javafx.scene.*;  
import javafx.stage.*;  
import javafx.scene.layout.*;  
import javafx.scene.control.*;  
import javafx.event.*; 
import javafx.geometry.*; 
  
public class ScrollPaneDemo extends Application {  
  
  ScrollPane scrlPane; 
 
  public static void main(String[] args) {  
  
    // Start the JavaFX application by calling launch().  
    launch(args);    
  }  
  
  // Override the start() method.  
  public void start(Stage myStage) {  
  
    // Give the stage a title.  
    myStage.setTitle("Demonstrate a ScrollPane");  
  
    // Use a FlowPane for the root node. 
    FlowPane rootNode = new FlowPane(10, 10);  
  
    // Center the controls in the scene. 
    rootNode.setAlignment(Pos.CENTER); 
 
    // Create a scene.  
    Scene myScene = new Scene(rootNode, 200, 200);  
  
    // Set the scene on the stage.  
    myStage.setScene(myScene);  
 
    // Create a label that will be scrolled. 
    Label scrlLabel = new Label( 
                          "A ScrollPane streamlines the process of\n" + 
                          "adding scroll bars to a window whose\n" + 
                          "contents exceed the window's dimensions.\n" + 
                          "It also enables a control to fit in a\n" + 
                          "smaller space than it otherwise would.\n" + 
                          "As such, it often provides a superior\n" + 
                          "approach over using individual scrollbars.");  
 
    // Create a scroll pane, setting scrlLabel as the content. 
    scrlPane = new ScrollPane(scrlLabel); 
 
    // Set the viewport width and height. 
    scrlPane.setPrefViewportWidth(130); 
    scrlPane.setPrefViewportHeight(80); 
 
    // Enable paning. 
    scrlPane.setPannable(true); 
 
 
    // Create a reset label. 
    Button btnReset = new Button("Reset Scroll Bar Positions"); 
 
    // Handle action events for the reset button. 
    btnReset.setOnAction(new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) { 
        // Set the scroll bars to their zero position. 
        scrlPane.setVvalue(0); 
        scrlPane.setHvalue(0); 
      } 
    }); 
 
    // Add the label to the scene graph.  
    rootNode.getChildren().addAll(scrlPane, btnReset);  
  
    // Show the stage and its scene.  
    myStage.show();  
  }  
}

listing 14
// Demonstrate a TreeView 
 
import javafx.application.*; 
import javafx.scene.*; 
import javafx.stage.*; 
import javafx.scene.layout.*; 
import javafx.scene.control.*; 
import javafx.event.*; 
import javafx.beans.value.*; 
import javafx.geometry.*; 
 
public class TreeViewDemo extends Application { 
 
  Label response; 
 
  public static void main(String[] args) { 
 
    // Start the JavaFX application by calling launch(). 
    launch(args);   
  } 
 
  // Override the start() method. 
  public void start(Stage myStage) { 
 
    // Give the stage a title. 
    myStage.setTitle("Demonstrate a TreeView"); 
 
    // Use a FlowPane for the root node. In this case, 
    // vertical and horizontal gaps of 10. 
    FlowPane rootNode = new FlowPane(10, 10); 
 
    // Center the controls in the scene. 
    rootNode.setAlignment(Pos.CENTER); 
 
    // Create a scene. 
    Scene myScene = new Scene(rootNode, 310, 460); 
 
    // Set the scene on the stage. 
    myStage.setScene(myScene); 
 
    // Create a label that will report the state of the 
    // selected tree item. 
    response = new Label("No Selection"); 
 
    // Create tree items, starting with the root. 
    TreeItem<String> tiRoot = new TreeItem<String>("Food"); 
     
    // Now add subtrees, begining with fruit. 
    TreeItem<String> tiFruit = new TreeItem<String>("Fruit"); 
  
    // Construct the Apple subtree. 
    TreeItem<String> tiApples = new TreeItem<String>("Apples"); 
    // Add chilc nodes to the Apple node. 
    tiApples.getChildren().add(new TreeItem<String>("Fuji")); 
    tiApples.getChildren().add(new TreeItem<String>("Winesap")); 
    tiApples.getChildren().add(new TreeItem<String>("Jonathan")); 

    // Add varieties to the friut node.
    tiFruit.getChildren().add(tiApples); 
    tiFruit.getChildren().add(new TreeItem<String>("Pears"));
    tiFruit.getChildren().add(new TreeItem<String>("Oranges")); 

    // Finally, add the fruit node to the root. 
    tiRoot.getChildren().add(tiFruit); 
 
    // Now, add vegetables subtree, using the same general process. 
    TreeItem<String> tiVegetables = new TreeItem<String>("Vegetables"); 
    tiVegetables.getChildren().add(new TreeItem<String>("Corn")); 
    tiVegetables.getChildren().add(new TreeItem<String>("Peas")); 
    tiVegetables.getChildren().add(new TreeItem<String>("Broccoli")); 
    tiVegetables.getChildren().add(new TreeItem<String>("Beans")); 
    tiRoot.getChildren().add(tiVegetables); 
 
    // Likewise, add nuts subtree. 
    TreeItem<String> tiNuts = new TreeItem<String>("Nuts"); 
    tiNuts.getChildren().add(new TreeItem<String>("Walnuts")); 
    tiNuts.getChildren().add(new TreeItem<String>("Peanuts")); 
    tiNuts.getChildren().add(new TreeItem<String>("Pecans")); 
    tiRoot.getChildren().add(tiNuts); 
 
    // Create tree view using the tree just created. 
    TreeView<String> tvFood = new TreeView<String>(tiRoot); 
 
    // Get the tree view selection model. 
    MultipleSelectionModel<TreeItem<String>> tvSelModel = 
                                     tvFood.getSelectionModel(); 
 
    // Use a change listener to respond to a selection within 
    // a tree view 
    tvSelModel.selectedItemProperty().addListener( 
                           new ChangeListener<TreeItem<String>>() { 
      public void changed( 
                  ObservableValue<? extends TreeItem<String>> changed, 
                      TreeItem<String> oldVal, TreeItem<String> newVal) { 
 
        // Display the selection and its complete path from the root. 
        if(newVal != null) { 
 
          // Construct the entire path to the selected item. 
          String path = newVal.getValue(); 
          TreeItem<String> tmp = newVal.getParent(); 
          while(tmp != null) { 
            path = tmp.getValue() + " -> " + path; 
            tmp = tmp.getParent(); 
          } 
 
          // Display the selection and the entire path. 
          response.setText("Selection is " + newVal.getValue() + 
                           "\nComplete path is " + path); 
        } 
      } 
     }); 
 
    // Add controls to the scene graph. 
    rootNode.getChildren().addAll(tvFood, response); 
 
    // Show the stage and its scene. 
    myStage.show(); 
  } 
}

listing 15
// Demonstrate rotation, scaling, glowing and inner shadow. 
  
import javafx.application.*;  
import javafx.scene.*;  
import javafx.stage.*;  
import javafx.scene.layout.*;  
import javafx.scene.control.*;  
import javafx.event.*;  
import javafx.geometry.*;  
import javafx.scene.transform.*; 
import javafx.scene.effect.*; 
import javafx.scene.paint.*; 
  
public class EffectsAndTransformsDemo extends Application {  
  
  double angle = 0.0; 
  double glowVal = 0.0; 
  boolean shadow = false; 
  double scaleFactor = 1.0; 
 
  // Create initial effects and transforms. 
  Glow glow = new Glow(0.0); 
  InnerShadow innerShadow = new InnerShadow(10.0, Color.RED); 
  Rotate rotate = new Rotate(); 
  Scale scale = new Scale(scaleFactor, scaleFactor); 
 
  // Create four push buttons.  
  Button btnRotate = new Button("Rotate");  
  Button btnGlow = new Button("Glow");  
  Button btnShadow = new Button("Shadow off"); 
  Button btnScale = new Button("Scale"); 
 
  public static void main(String[] args) {  
  
    // Start the JavaFX application by calling launch().  
    launch(args);    
  }  
  
  // Override the start() method.  
  public void start(Stage myStage) {  
  
    // Give the stage a title.  
    myStage.setTitle("Effects and Transforms Demo");  
  
    // Use a FlowPane for the root node. In this case,  
    // vertical and horizontal gaps of 10 are used. 
    FlowPane rootNode = new FlowPane(10, 10);  
  
    // Center the controls in the scene.  
    rootNode.setAlignment(Pos.CENTER);  
  
    // Create a scene.  
    Scene myScene = new Scene(rootNode, 300, 100);  
  
    // Set the scene on the stage.  
    myStage.setScene(myScene);  
 
    // Set the initial glow effect. 
    btnGlow.setEffect(glow);    
 
    // Add rotation to the transform list for the Rotate button. 
    btnRotate.getTransforms().add(rotate);  
 
    // Add scalling to the transform list for the Scale button. 
    btnScale.getTransforms().add(scale); 
 
    // Handle the action events for the rotate button.  
    btnRotate.setOnAction(new EventHandler<ActionEvent>() {  
      public void handle(ActionEvent ae) {  
        // Each time button is pressed, it is rotated 30 degrees 
        // around its center. 
        angle += 30.0; 
 
        rotate.setAngle(angle);        
        rotate.setPivotX(btnRotate.getWidth()/2); 
        rotate.setPivotY(btnRotate.getHeight()/2); 
      }  
    });  
  
    // Handle the action events for the scale button.  
    btnScale.setOnAction(new EventHandler<ActionEvent>() {  
      public void handle(ActionEvent ae) {  
        // Each time button is pressed, the button's scale is changed. 
        scaleFactor += 0.1; 
        if(scaleFactor > 1.0) scaleFactor = 0.4; 
 
        scale.setX(scaleFactor); 
        scale.setY(scaleFactor);         
 
      }  
    });  
 
 
    // Handle the action events for the Glow button.  
    btnGlow.setOnAction(new EventHandler<ActionEvent>() {  
      public void handle(ActionEvent ae) {  
        // Each time button is pressed, its glow value is changed. 
        glowVal += 0.1; 
        if(glowVal > 1.0) glowVal = 0.0; 
 
        // Set the new glow value. 
        glow.setLevel(glowVal); 
      }  
    });  
 
    // Handle the action events for the Shadow button. 
    btnShadow.setOnAction(new EventHandler<ActionEvent>() {  
      public void handle(ActionEvent ae) {  
        // Each time button is pressed, its shadow status is changed. 
        shadow = !shadow; 
        if(shadow) { 
          btnShadow.setEffect(innerShadow);  
          btnShadow.setText("Shadow on"); 
        } else { 
          btnShadow.setEffect(null); 
          btnShadow.setText("Shadow off"); 
        } 
      }  
    });  
 
    // Add the label and buttons to the scene graph.  
    rootNode.getChildren().addAll(btnRotate, btnScale, btnGlow, btnShadow);  
 
    // Show the stage and its scene.  
    myStage.show();  
  }  
}


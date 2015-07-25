listing 1
// Demonstrate Menus  
  
import javafx.application.*;  
import javafx.scene.*;  
import javafx.stage.*;  
import javafx.scene.layout.*;  
import javafx.scene.control.*;  
import javafx.event.*;  
import javafx.geometry.*;  
  
public class MenuDemo extends Application {  
  
  Label response;  
 
  public static void main(String[] args) {  
  
    // Start the JavaFX application by calling launch().  
    launch(args);    
  }  
  
  // Override the start() method.  
  public void start(Stage myStage) {  
  
    // Give the stage a title.  
    myStage.setTitle("Demonstrate Menus");  
  
    // Use a BorderPane for the root node.  
    BorderPane rootNode = new BorderPane();  
  
     // Create a scene.  
    Scene myScene = new Scene(rootNode, 300, 300);  
  
    // Set the scene on the stage.  
    myStage.setScene(myScene);  
  
    // Create a label that will report the selection.  
    response = new Label("Menu Demo");  
  
    // Create the menu bar. 
    MenuBar mb = new MenuBar(); 
 
    // Create the File menu. 
    Menu fileMenu = new Menu("File"); 
    MenuItem open = new MenuItem("Open"); 
    MenuItem close = new MenuItem("Close"); 
    MenuItem save = new MenuItem("Save"); 
    MenuItem exit = new MenuItem("Exit"); 
    fileMenu.getItems().addAll(open, close, save, 
                               new SeparatorMenuItem(), exit); 
 
    // Add File menu to the menu bar. 
    mb.getMenus().add(fileMenu); 
 
    // Create the Options menu. 
    Menu optionsMenu = new Menu("Options"); 
 
    // Create the Colors submenu. 
    Menu colorsMenu = new Menu("Colors"); 
    MenuItem red = new MenuItem("Red"); 
    MenuItem green = new MenuItem("Green"); 
    MenuItem blue = new MenuItem("Blue"); 
    colorsMenu.getItems().addAll(red, green, blue); 
    optionsMenu.getItems().add(colorsMenu); 
 
    // Create the Priority submenu. 
    Menu priorityMenu = new Menu("Priority"); 
    MenuItem high = new MenuItem("High"); 
    MenuItem low = new MenuItem("Low"); 
    priorityMenu.getItems().addAll(high, low); 
    optionsMenu.getItems().add(priorityMenu); 
 
    // Add a separator. 
    optionsMenu.getItems().add(new SeparatorMenuItem()); 
 
    // Create the Reset menu item. 
    MenuItem reset = new MenuItem("Reset"); 
    optionsMenu.getItems().add(reset); 
 
    // Add Options menu to the menu bar. 
    mb.getMenus().add(optionsMenu); 
 
    // Create the Help menu. 
    Menu helpMenu = new Menu("Help"); 
    MenuItem about = new MenuItem("About"); 
    helpMenu.getItems().add(about); 
 
    // Add Help menu to the menu bar. 
    mb.getMenus().add(helpMenu); 
   
    // Create one event handler that will handle menu action events. 
    EventHandler<ActionEvent> MEHandler = 
                                new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) {  
        String name = ((MenuItem)ae.getTarget()).getText(); 
 
        // If Exit is chosen, the program is terminated. 
        if(name.equals("Exit")) Platform.exit(); 
 
        response.setText( name + " selected"); 
      }  
    };
  
    // Set action event handlers for the menu items. 
    open.setOnAction(MEHandler); 
    close.setOnAction(MEHandler); 
    save.setOnAction(MEHandler); 
    exit.setOnAction(MEHandler); 
    red.setOnAction(MEHandler); 
    green.setOnAction(MEHandler); 
    blue.setOnAction(MEHandler); 
    high.setOnAction(MEHandler); 
    low.setOnAction(MEHandler); 
    reset.setOnAction(MEHandler); 
    about.setOnAction(MEHandler); 
 
    // Add the menu bar to the top of the border pane and 
    // the response label to the center position. 
    rootNode.setTop(mb); 
    rootNode.setCenter(response); 
  
    // Show the stage and its scene.  
    myStage.show();  
  }  
}

listing 2
// Add keyboard accelerators for the File menu. 
open.setAccelerator(KeyCombination.keyCombination("shortcut+O")); 
close.setAccelerator(KeyCombination.keyCombination("shortcut+C")); 
save.setAccelerator(KeyCombination.keyCombination("shortcut+S")); 
exit.setAccelerator(KeyCombination.keyCombination("shortcut+E"));

listing 3
// Create the Options menu. 
Menu optionsMenu = new Menu("Options"); 
 
// Create the Colors submenu. 
Menu colorsMenu = new Menu("Colors"); 
 
// Use check menu items for colors. This allows 
// the user to select more than one color. 
CheckMenuItem red = new CheckMenuItem("Red"); 
CheckMenuItem green = new CheckMenuItem("Green"); 
CheckMenuItem blue = new CheckMenuItem("Blue"); 
colorsMenu.getItems().addAll(red, green, blue); 
optionsMenu.getItems().add(colorsMenu); 
 
// Select green for the default color selection. 
green.setSelected(true); 
 
// Create the Priority submenu. 
Menu priorityMenu = new Menu("Priority"); 
 
// Use radio menu items for the priority setting. 
// This lets the menu show which priority is used 
// and also ensures that one and only one priority 
// can be selected at any one time.  
RadioMenuItem high = new RadioMenuItem("High"); 
RadioMenuItem low = new RadioMenuItem("Low"); 
 
// Create a toggle group and use it for the radio menu items. 
ToggleGroup tg = new ToggleGroup(); 
high.setToggleGroup(tg); 
low.setToggleGroup(tg); 
 
// Select High priority for the default selection. 
high.setSelected(true); 
 
// Add the radio menu items to the priority menu and 
// add the priority menu to the options menu. 
priorityMenu.getItems().addAll(high, low); 
optionsMenu.getItems().add(priorityMenu); 
 
// Add a separator. 
optionsMenu.getItems().add(new SeparatorMenuItem()); 
 
// Create the Reset menu item. 
MenuItem reset = new MenuItem("Reset"); 
optionsMenu.getItems().add(reset); 
 
// Add Options menu to the menu bar. 
mb.getMenus().add(optionsMenu);

listing 4
// Add the context menu to the entire scene graph. 
rootNode.setOnContextMenuRequested( 
            new EventHandler<ContextMenuEvent>() {   
  public void handle(ContextMenuEvent ae) {  
    // Popup menu at the location of the right click. 
    editMenu.show(rootNode, ae.getScreenX(), ae.getScreenY()); 
  }  
});

listing 5
// Define a tool bar. First, create tool bar items. 
Button btnSet = new Button("Set Breakpoint", 
                           new ImageView("setBP.gif")); 
Button btnClear = new Button("Clear Breakpoint", 
                             new ImageView("clearBP.gif")); 
Button btnResume = new Button("Resume Execution", 
                              new ImageView("resume.gif")); 
 
// Now, turn off text in the buttons. 
btnSet.setContentDisplay(ContentDisplay.GRAPHIC_ONLY); 
btnClear.setContentDisplay(ContentDisplay.GRAPHIC_ONLY); 
btnResume.setContentDisplay(ContentDisplay.GRAPHIC_ONLY); 
 
// Set tooltips. 
btnSet.setTooltip(new Tooltip("Set a breakpoint.")); 
btnClear.setTooltip(new Tooltip("Clear a breakpoint.")); 
btnResume.setTooltip(new Tooltip("Resume execution.")); 
 
// Create the tool bar. 
ToolBar tbDebug = new ToolBar(btnSet, btnClear, btnResume);

listing 6
// Create a handler for the tool bar buttons. 
EventHandler<ActionEvent> btnHandler = new EventHandler<ActionEvent>() {  
  public void handle(ActionEvent ae) {  
    response.setText(((Button)ae.getTarget()).getText());  
  }  
};  
 
// Set the tool bar button action event handlers. 
btnSet.setOnAction(btnHandler); 
btnClear.setOnAction(btnHandler); 
btnResume.setOnAction(btnHandler);

listing 7
// Demonstrate Menus -- Final Version 
  
import javafx.application.*;  
import javafx.scene.*;  
import javafx.stage.*;  
import javafx.scene.layout.*;  
import javafx.scene.control.*;  
import javafx.event.*;  
import javafx.geometry.*;  
import javafx.scene.input.*; 
import javafx.scene.image.*; 
import javafx.beans.value.*; 
  
public class MenuDemoFinal extends Application {  
 
  MenuBar mb; 
  EventHandler<ActionEvent> MEHandler; 
  ContextMenu editMenu; 
  ToolBar tbDebug; 
 
  Label response;  
 
  public static void main(String[] args) {  
  
    // Start the JavaFX application by calling launch().  
    launch(args);    
  }  
  
  // Override the start() method.  
  public void start(Stage myStage) {  
  
    // Give the stage a title.  
    myStage.setTitle("Demonstrate Menus -- Final Version");  
  
    // Use a BorderPane for the root node.  
    final BorderPane rootNode = new BorderPane();  
  
     // Create a scene.  
    Scene myScene = new Scene(rootNode, 300, 300);  
  
    // Set the scene on the stage.  
    myStage.setScene(myScene);  
  
    // Create a label that will report the selection.  
    response = new Label();  
  
    // Create one event handler for all menu action events. 
    MEHandler = new EventHandler<ActionEvent>() { 
      public void handle(ActionEvent ae) {  
        String name = ((MenuItem)ae.getTarget()).getText(); 
 
        if(name.equals("Exit")) Platform.exit(); 
 
        response.setText( name + " selected"); 
      }  
    }; 
 
    // Create the menu bar. 
    mb = new MenuBar(); 
 
    // Create the File menu. 
    makeFileMenu(); 
 
    // Create the Options menu. 
    makeOptionsMenu(); 
 
    // Create the Help menu. 
    makeHelpMenu(); 
 
    // Create the context menu. 
    makeContextMenu(); 
 
    // Create a text field and set its column width to 20. 
    TextField tf = new TextField(); 
    tf.setPrefColumnCount(20); 
 
    // Add the context menu to the textfield. 
    tf.setContextMenu(editMenu); 
 
    // Create the tool bar. 
    makeToolBar(); 
 
    // Add the context menu to the entire scene graph. 
    rootNode.setOnContextMenuRequested( 
                new EventHandler<ContextMenuEvent>() {   
      public void handle(ContextMenuEvent ae) {  
        // Popup menu at the location of the right click. 
        editMenu.show(rootNode, ae.getScreenX(), ae.getScreenY()); 
      }  
    });  
 
    // Add the menu bar to the top of the border pane. 
    rootNode.setTop(mb); 
 
    // Create a flow pane that will hold both the response 
    // label and the text field.  
    FlowPane fpRoot = new FlowPane(10, 10); 
 
    // Center the controls in the scene.  
    fpRoot.setAlignment(Pos.CENTER);  
 
    // Use a separator to better organize the layout.  
    Separator separator = new Separator();  
    separator.setPrefWidth(260);  
 
    // Add the label, separator, and text field to the flow pane. 
    fpRoot.getChildren().addAll(response, separator,  tf); 
 
    // Add the tool bar to the bottom of the border pane. 
    rootNode.setBottom(tbDebug); 
 
    // Add the flow pane to the center of the border layout. 
    rootNode.setCenter(fpRoot); 
 
    // Show the stage and its scene.  
    myStage.show();  
  }  
 
  // Create the File menu. 
  void makeFileMenu() { 
    // Create the File menu, including a mnemonic. 
    Menu fileMenu = new Menu("_File");  
 
    // Create the File menu items. 
    MenuItem open = new MenuItem("Open"); 
    MenuItem close = new MenuItem("Close"); 
    MenuItem save = new MenuItem("Save"); 
    MenuItem exit = new MenuItem("Exit"); 
 
    // Add items to File menu. 
    fileMenu.getItems().addAll(open, close, save, 
                               new SeparatorMenuItem(), exit); 
 
    // Add keyboard accelerators for the File menu. 
    open.setAccelerator(KeyCombination.keyCombination("shortcut+O")); 
    close.setAccelerator(KeyCombination.keyCombination("shortcut+C")); 
    save.setAccelerator(KeyCombination.keyCombination("shortcut+S")); 
    exit.setAccelerator(KeyCombination.keyCombination("shortcut+E")); 
 
    // Set action event handlers. 
    open.setOnAction(MEHandler); 
    close.setOnAction(MEHandler); 
    save.setOnAction(MEHandler); 
    exit.setOnAction(MEHandler); 
 
    // Add File menu to the menu bar. 
    mb.getMenus().add(fileMenu); 
  } 
 
  // Create the Options menu. 
  void makeOptionsMenu() { 
    Menu optionsMenu = new Menu("Options"); 
 
    // Create the Colors submenu. 
    Menu colorsMenu = new Menu("Colors"); 
 
    // Use check boxes for colors. This allows 
    // the user to select more than one color. 
    CheckMenuItem red = new CheckMenuItem("Red"); 
    CheckMenuItem green = new CheckMenuItem("Green"); 
    CheckMenuItem blue = new CheckMenuItem("Blue"); 
 
    // Add the check menu items for the colors menu and 
    // add the colors menu to the options menu. 
    colorsMenu.getItems().addAll(red, green, blue); 
    optionsMenu.getItems().add(colorsMenu); 
 
    // Select green for the default color selection. 
    green.setSelected(true); 
 
    // Create the Priority submenu. 
    Menu priorityMenu = new Menu("Priority"); 
 
    // Use radio menu items for the priority setting. 
    // This lets the menu show which priority is used 
    // and also ensures that one and only one priority 
    // can be selected at any one time.  
    RadioMenuItem high = new RadioMenuItem("High"); 
    RadioMenuItem low = new RadioMenuItem("Low"); 
 
    // Create a toggle group and use it for the radio menu items. 
    ToggleGroup tg = new ToggleGroup(); 
    high.setToggleGroup(tg); 
    low.setToggleGroup(tg); 
 
    // Select High priority for the default selection. 
    high.setSelected(true); 
 
    // Add the radio menu items to the priority menu and 
    // add the priority menu to the options menu. 
    priorityMenu.getItems().addAll(high, low); 
    optionsMenu.getItems().add(priorityMenu); 
 
    // Add a separator. 
    optionsMenu.getItems().add(new SeparatorMenuItem()); 
 
    // Create the Reset menu item and add it to the optios menu. 
    MenuItem reset = new MenuItem("Reset"); 
    optionsMenu.getItems().add(reset); 
 
    // Set action event handlers.  
    red.setOnAction(MEHandler); 
    green.setOnAction(MEHandler); 
    blue.setOnAction(MEHandler); 
    high.setOnAction(MEHandler); 
    low.setOnAction(MEHandler); 
    reset.setOnAction(MEHandler); 
 
    // Use a change listener to respond to changes in the radio 
    // menu item setting. 
    tg.selectedToggleProperty().addListener(new ChangeListener<Toggle>() { 
      public void changed(ObservableValue<? extends Toggle> changed, 
                         Toggle oldVal, Toggle newVal) { 
        if(newVal==null) return; 
 
        // Cast newVal to RadioButton. 
        RadioMenuItem rmi = (RadioMenuItem) newVal;  
 
        // Display the selection. 
        response.setText("Priority selected is " + rmi.getText()); 
      } 
    }); 
 
    // Add Options menu to the menu bar. 
    mb.getMenus().add(optionsMenu); 
  } 
 
  // Create the Help menu. 
  void makeHelpMenu() { 
 
    // Create an ImageView for the image. 
    ImageView aboutIV = new ImageView("aboutIcon.gif");  
 
    // Create the help menu. 
    Menu helpMenu = new Menu("Help"); 
 
    // Create the About menu item and add it to the help menu. 
    MenuItem about = new MenuItem("About", aboutIV); 
    helpMenu.getItems().add(about); 
 
    // Set action event handler.  
    about.setOnAction(MEHandler); 
 
    // Add Help menu to the menu bar. 
    mb.getMenus().add(helpMenu); 
  } 
 
  // Create the context menu items. 
  void makeContextMenu() { 
 
    // Create the edit context menu items. 
    MenuItem cut = new MenuItem("Cut"); 
    MenuItem copy = new MenuItem("Copy"); 
    MenuItem paste = new MenuItem("Paste"); 
 
    // Create a context (i.e., popup) menu that shows edit options. 
    editMenu = new ContextMenu(cut, copy, paste); 
 
    // Set the action event handlers. 
    cut.setOnAction(MEHandler); 
    copy.setOnAction(MEHandler); 
    paste.setOnAction(MEHandler); 
  } 
 
  // Create the tool bar. 
  void makeToolBar() { 
    // Create tool bar items. 
    Button btnSet = new Button("Set Breakpoint", 
                               new ImageView("setBP.gif")); 
    Button btnClear = new Button("Clear Breakpoint", 
                                 new ImageView("clearBP.gif")); 
    Button btnResume = new Button("Resume Execution", 
                                  new ImageView("resume.gif")); 
 
    // Turn off text in the buttons. 
    btnSet.setContentDisplay(ContentDisplay.GRAPHIC_ONLY); 
    btnClear.setContentDisplay(ContentDisplay.GRAPHIC_ONLY); 
    btnResume.setContentDisplay(ContentDisplay.GRAPHIC_ONLY); 
 
    // Set tooltips. 
    btnSet.setTooltip(new Tooltip("Set a breakpoint.")); 
    btnClear.setTooltip(new Tooltip("Clear a breakpoint.")); 
    btnResume.setTooltip(new Tooltip("Resume execution.")); 
 
    // Create the tool bar. 
    tbDebug = new ToolBar(btnSet, btnClear, btnResume); 
 
    // Create a handler for the tool bar buttons. 
    EventHandler<ActionEvent> btnHandler = new EventHandler<ActionEvent>() {  
      public void handle(ActionEvent ae) {  
        response.setText(((Button)ae.getTarget()).getText());  
      }  
    };  
 
    // Set the tool bar button action event handlers. 
    btnSet.setOnAction(btnHandler); 
    btnClear.setOnAction(btnHandler); 
    btnResume.setOnAction(btnHandler); 
  } 
}


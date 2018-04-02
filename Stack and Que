# Stack-Que
A final I had to code for java class. 

//Main imports  
	import javafx.application.Application;  			// Adding application 
	import javafx.event.ActionEvent;
	import javafx.event.EventHandler;
	import javafx.scene.Scene;							// Making the scene 
	import javafx.stage.Stage;							// For stage 

	//Adding Scene layout imports 
	import javafx.scene.layout.BorderPane;				// Making bordorpane 
	import javafx.scene.layout.HBox; 					// Making HBox
	import javafx.scene.layout.VBox;					// Making VBox 
 
	//Adding Scene control Inputs & Insets 
	import javafx.scene.control.Label;					// For labels 
	import javafx.scene.control.TextField; 				// For textfeild 
	import javafx.scene.control.Button;					// For Buttons 
	import javafx.scene.control.TextArea;				// Making Text area 
	import javafx.geometry.Insets;						// For Padding

 
	public class Java_Stack_Queue_Project extends Application {
  
	//Making the HBox and Vbox to hold the buttons and textfeild/Area
	HBox Hbox = new HBox();
	VBox Vbox = new VBox();

	 
	// Making all the labels / buttons 
	static Label Stack_Que = new Label("Stacking Order"); 
	Button Toggle = new Button("Toggle "); 				  	  // Switch between que and stack order
    Button Push = new Button("Push "); 					 	  // Changes to Enter when toggled 
    Button Pop = new Button("Pop "); 						  // Changes to Exit when toggled 
    Button Clear = new Button("Clear "); 				      // Clears the output 
	
    //Making the TextArea's and fields
    static TextField txtBox = new TextField(); 		  		  // txtBox allows user's Input 
    static TextArea txtArea = new TextArea();		 		  // Displays the user's input 
    
    //Setting the output box to = textArea 
    HBox Output = new HBox(txtArea); 


	//setting the stage and pane
	Stage Main_Stage; 
	BorderPane Pane = new BorderPane();
	
	//Building a bridge between the this class and Project_Class.
	static Project_Class<String> SecondClass = new Project_Class<String>();  
	

	// Main class starts
    @Override
    public void start(Stage primaryStage) {
	   
	// Setting window to = the primaryStage 
	Main_Stage = primaryStage;  
	
	
	
	//Seetings the padding and Insets
	Pane.setPadding(new Insets(20)); 
	Stack_Que.setPadding(new Insets(5, 10, 10, 10));
	
	
    //Adding the label and buttons to the HBox 
    Hbox.getChildren().addAll(Stack_Que, Toggle,Push,Pop,Clear);
    Vbox.getChildren().addAll(txtBox);
      
      
    //Setting txtbox blank and txtArea to false
    txtArea.setEditable(false);
    Lbl_Check();
      
    //Making the action event
    // Add method - will add user string when Push button is fired 
    // Del method - will Delete according to toggle stage 
    // Toggle method - Switches between stack and queue 
    // Clear - Deletes everything in the output / array_List 
    EventHandler<ActionEvent> add_Event = event -> add();  
    EventHandler<ActionEvent> Del_Event = event -> Del();  
    EventHandler<ActionEvent> Toggle_Event = event -> Toggle();  
    EventHandler<ActionEvent> Clear_Event = event -> Clear();  
    
      
    // Adding the events to the buttons 
    Push.setOnAction(add_Event);
    Pop.setOnAction(Del_Event);
    Toggle.setOnAction(Toggle_Event);
    Clear.setOnAction(Clear_Event);
    
      
	//Setting the height and width of TextArea  
	txtArea.setPrefHeight(200); 
	txtArea.setPrefWidth(500);    
	    
	//Adding the Hbox,Vbox,Output to the borderPane 
	Pane.setTop(Hbox);
	Pane.setLeft(Vbox);
	Pane.setBottom(Output);
		
      
 	primaryStage.setTitle("SDev-200 Stack & Queue GUI Project - Chad Carmickle");
    Scene scene = new Scene(Pane, 500, 300);
    primaryStage.setScene(scene);
    primaryStage.show();
	txtBox.requestFocus();  
  
    }
   
    // Toggle switches between Stack and Queue Order and changes buttons / labels accordingly
    private void Toggle() {

    	if (Stack_Que.getText() == ("Queue Order")) 
			   {
				Stack_Que.setText("Stacking Order");
				Toggle.setText("Toggle");
				Push.setText("Push");
				Pop.setText("Pop");
				Clear.setText("Clear");
				Lbl_Check();
		  		txtBox.requestFocus();
		  		SecondClass.Toggle(true); 
			   }
	   
    	else 
			   { 
				Stack_Que.setText("Queue Order");
				Toggle.setText("Toggle");
				Push.setText("Enter");
				Pop.setText("Exit");
				Clear.setText("Clear");
				Lbl_Check();
				txtBox.requestFocus();
		  		SecondClass.Toggle(false); 

			   }
    }
    
    // Adds user input from textBox to the Array_List 
    public void add() {
	SecondClass.Add(txtBox.getText()); 
	Lbl_Check();	  
	txtBox.requestFocus();
    }
    
    //Deletes dependent upon the toggle Mode. 
    public void Del() {
	SecondClass.Del();
	txtBox.requestFocus();
	Lbl_Check();
    }
    
    // Clears Array_List / Output 
    public void Clear() {
	SecondClass.Clear(); 
	Lbl_Check();	   
	txtBox.requestFocus();
 
    }

    // Returns the ToString Method 
    public static String ToString() { 
	return SecondClass.toString(); 
	   
    } 
    
    //Checks what toggle is activated and displays correct output string. 
    public static void Lbl_Check() { 

	   if (Stack_Que.getText() == ("Stacking Order")) {
	    txtArea.setText(" Bottom --> {        " + ToString() + "        } <-- Top"); 
	   } 
	   else   		       
		txtArea.setText(" Front of Line --> {        " + ToString() + "        } \"<--- Back of line ");
    }
      
    public static void main(String[] args) {
	     Application.launch(args);
    	}
	}

# Calculator Version 2 MVC Separation Ideas

-- Separate control, view, and model code into separate classes (CalculatorGUI, CalculatorTextUI, CalculatorControl, CalculatorModel)

-- Extend the view code class in the control code, create object of view class, instantiate view using object

-- Possibly will be using multiple interfaces for modeling and to work around not being able to do multiple class inheritance in Java

*class CalculatorControl {*

*CalculatorGUI viewGUI = new CalculatorGUI();*

*CalculatorTextUI textUI = new CalculatorTextUI();*

  *public void CalculatorControl("insert preferred UI here") {*

  *... control code*

   *}*
  
*}* 

Required Aspects: 

1.Create an Operations class:
   a.General computing methods for each operation (addition, subtraction, mult, etc), with the inputs being universal. 
   b.Computing methods will be used in the other classes

2. Create a Main class for managing the CLI and GUI classes:

  Basic Process - From Input to Output:
    a.Upon startup would display a main-menu GUI - choose GUI or CLI
    b.Main program loop would start either the GUI or CLI programs - when either program ends, depending on the return value, the Main class either starts the other program or ends the entire Calculator program - 
    c.Will create a new instance of the desired class and call GUI.main() or CLI.main() to start the desired program
    d.The GUI or CLI program takes in the input (text-based or button-clicks respectively)
    e.GUI and CLI classes will manipulate the input before using the Operation class methods for computing
    f.After receiving the return value from the Main methods, the GUI and CLI classes display the output and are ready to take in their input. 

3.Create a class for taking input from console line - CLI
    a.Requires a program loop in main
    b.Requires a way to open up a console window
    c.Will probably use some kind of Buffered Reader or Scanner class to read input from the console window
    d.Can use simple text-based GUI to display allowed operations - select operation by using CLI commands
    e.After selecting the operation, the user will type in the numbers
    f.option to switch to gui by inputting in a certain command (probably gui) (will be shown in the list of available operations)
    g.option to end the calculator program entirely (exit, or click on x button in window)

4.Create a class for taking input from GUI
    a.Automatically generated GUI (buttons, fields)
    b.Use event listeners on buttons
    c.When buttons are clicked the inputs are stored until the equal sign is clicked, at which point the program computes
    d.If the buttons are clicked in an incorrect combination (too many operators, or too many decimal points) then the method that is triggered when the equal sign is clicked will try to catch the exceptions (with try and catch statements)
    OR 
    prevent incorrect combinations from being entered in the first place by disabling certain buttons
    e.Option to switch to CLI by clicking a specific button (labeled CLI)




# p1-robotmania Project Updates

# Week 1

Nakul Nandhakumar and Vihan Jayaraman:

-- Worked on Battleship GUI using SwingDesigner

-- Successfully adapted control code to new UI

-- Kept text and console based elements in code to work in tangent with UI control code

-- Worked on adapting control code for potential ship overlaps

-- Experimented with instantiating GUI after extending GUI class file in other classes

TO-DO

-- Aesthetical improvements to GUI for user satisfaction

-- Adapt control code to better handle ship overlaps and conditions

-- improvements to technical ease of user interaction needed (ex. button pressing, more intuitive button placement/text/names etc.)

-- Potenitally start UI for monopoly/tick-tack-toe/hangman games??? 

-- Work on adding a playerBoard for enemy to guess and attack player ships

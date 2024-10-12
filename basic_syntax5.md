# Basic 5
## interface
public class Main {

	public static void main(String[] ags) {
		
		//interface = a template that can be applied to a class
		//			similar to inheritance, but specifies what a class has/must do
		// 		classes can apply more than one interface, inheritance is limited to 1 super class
		
		Rabbit rabbit = new Rabbit();
		Hawk hawk = new Hawk();
		Fish fish = new Fish();
		
		rabbit.flee();
		hawk.hunt();
		fish.hunt();
		fish.flee();
		

		
		
	}
}   
public class Rabbit implements Prey{

	@Override
	public void flee() {
		System.out.println("The rabbit is fleeing");
		
	}

}   
public  class Hawk implements Predator{

	@Override
	public void hunt() {
		System.out.println("The Hawk is hunting");
		
	} 
	

}   
public class Fish implements Prey, Predator{

	@Override
	public void hunt() {
		System.out.println("The Fish is hunting smaller Fish");
		
	}

	@Override
	public void flee() {
		System.out.println("The Fish is fleeing from bigger Fish");
		
	}

}   
public interface Prey {

	void flee();

}   
public interface Predator {
	
	void hunt();

}   
## polymorphism
public static void main(String[] ags) {
		
		// polymorphism : greek word for poly = many morph= form
		// 				the ability of an object to identify as more than one type
		
		Car car = new Car();
		Bicycle bicycle = new Bicycle();
		Boat boat = new Boat();
		
		// Car[] racers = {car, bicycle, boat}; //error
		// Bicycle [] racers = {car, bicycle, boat}; //error
		
		Vehicle[] racers = {car, bicycle, boat};
		
		for(Vehicle x : racers) {
			x.go();
		}
		
	}
}   
public class Vehicle{

	public void go() {
		
		
	}

	
}   
public  class Car extends Vehicle{

	@Override
	public void go() {
		System.out.println("The Car begins moving");
	}
}   
public class Bicycle extends Vehicle{

	@Override
	public void go() {
		System.out.println("The Bicycle begins moving");
	}

}   
## Dynamic Polymorphism
public static void main(String[] ags) {
		
		// polymorphism : many shapes/forms
		// dynamic = after compilation (during runtime)
		
		// ex. A corvette is a: corvette, and a car, and a vehicle, and an object
		
		
		Scanner scanner = new Scanner(System.in);
		Animal animal;
		
		System.out.println("What animal do you want?");
		System.out.println("(1 = dog) or (2 = cat): ");
		int choice = scanner.nextInt();
		
		if(choice == 1) {
			animal = new Dog();
			animal.speak();
		}
		else if(choice == 2) {
			animal = new Cat();
			animal.speak();
		}
		else {
			animal = new Animal();
			System.out.println("That choice was invalid");
			animal.speak();
		}

		
	}
}   
public class Animal {

	public void speak() {
		System.out.println("Animal goes *brrr*");
	}
}   
public class Dog extends Animal {

	@Override
	public void speak() {
		System.out.println("Dog goes *bark*");
	}
}   
public class Cat extends Animal {
	
	@Override
	public void speak() {
		System.out.println("Cat goes *meow*");
	}

}   
## exception handling
public class Main {

	public static void main(String[] ags) {
		
		// exception = an event that occurs during the execution of a program that
		// 		disrupts the normal flow of instructions
		Scanner scanner = new Scanner(System.in);
		try {

			System.out.println("Enter a whole number to divide: ");
			int x = scanner.nextInt();
			System.out.println("Enter a whole number to divide by: ");
			int y = scanner.nextInt();
		
			int z = x/y;
		
			System.out.println("Result: " + z);
			// when you divide by 0 exception error occurred
		}
		catch(ArithmeticException e) {
			System.out.println("You can't divide by zero! IDIOT!");
		}
		catch(InputMismatchException e) {
			System.out.println("Please enter a number OMFG!!");
		}
		catch(Exception e) { // catch basically all exceptions
			System.out.println("Wooo. something went wrong");
		}
		finally {
			scanner.close();
		}

  ## File Class
  import java.io.File;

public class Main {

	public static void main(String[] ags) {
		
		//file : an abstract representation of file and directory path-names
		
		File file = new File("secret_message.txt"); //detect project unit
		
		if(file.exists()) {
			System.out.println("That file exists! :)");
			System.out.println(file.getPath());
			System.out.println(file.getAbsolutePath());
			System.out.println(file.isFile());
			file.delete();
		}
		else {
			System.out.println("That file doesn't exist :(");
		}
		
	}
}   
## Filer Writer
import java.io.FileWriter;
import java.io.IOException;

public class Main {

	public static void main(String[] ags) {
		
		try {
			FileWriter writer = new FileWriter("poem.txt");
			writer.write("Roses are red. \nViolets are blue \n Booty booty booty \n Rockin everywhere");
			writer.append("\n (A poem by Lee)");
			writer.close();
		} 
		catch (IOException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		
	}
}   

		
	
		
	}
}   
## File Reader
import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;

public class Main {

	public static void main(String[] ags) {
		
		// File Reader : read the contents of a file as a stream of characters.
		//  	 one by one read() returns an int value which contains the byte value
		//		when read() returns -1, there is no more data to be read
		
		try {
			FileReader reader = new FileReader("art.txt");
			int data = reader.read();
			while(data != -1) {
				System.out.print((char)data);
				data = reader.read();
			}
			reader.close();			
			
		} catch(FileNotFoundException e) {
			e.printStackTrace();
		}
		catch (IOException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		
		
		
	}
}

## Audio
import java.io.File;
import java.io.IOException;
import javax.sound.sampled.*;

public class Main {

	public static void main(String[] ags) throws UnsupportedAudioFileException, IOException, LineUnavailableException {

		Scanner scanner = new Scanner(System.in);
		
		File file = new File("Level_Up.wav");
		AudioInputStream audioStream = AudioSystem.getAudioInputStream(file);
		Clip clip = AudioSystem.getClip();
		clip.open(audioStream);
		
		String response = "";
		
		while(!response.equals("Q")) {
			System.out.println("P = play, S = Stop, R = Reset, Q = Quit");
			System.out.print("Enter Your Choice : ");
			
			response = scanner.next();
			response = response.toUpperCase();
			
			switch(response) {
				case ("P") : clip.start();
				break;
				case ("S") : clip.stop();
				break;
				case ("R") : clip.setMicrosecondPosition(0);
				break;
				case ("Q") : clip.close();
				break;
				default: System.out.println("Not a valid response");
			}
			
		}
		System.out.println("Byee!");
		
	}
}   
## Frame in java

import java.awt.Color;
import javax.swing.ImageIcon;
import javax.swing.JFrame;


public class Main {

	public static void main(String[] ags){

		// JFrame = A GUI window to add components to
		
		/*
		JFrame frame = new JFrame(); // create a frame
		
		frame.setTitle("JFrame title goes here"); // set title of frame
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); //exit out of application
		// DO_NOTHING_ON_CLOSE , HIDE_ON_CLOSE
		frame.setResizable(false); //prevent frame from being re-sized
		frame.setSize(500,500); // set x,y dimension of frame
		frame.setVisible(true); //make frame visible
		
		//SETTING ICON
		ImageIcon image = new ImageIcon("JP.gif"); //create an imageIcon
		frame.setIconImage(image.getImage());
		
		// Background color
		frame.getContentPane().setBackground(new Color(40,82,94)); // change color of background		
		*/
		
		
		new MyFrame();// MyFrame myFrame = new MyFrame();
		
	}
}
import javax.swing.ImageIcon;
import javax.swing.JFrame;

public class MyFrame extends JFrame {

	MyFrame(){		
		this.setTitle("Jthis title goes here"); // set title of frame
		this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); //exit out of application
		// DO_NOTHING_ON_CLOSE , HIDE_ON_CLOSE
		this.setResizable(false); //prevent frame from being re-sized
		this.setSize(500,500); // set x,y dimension of frame
		this.setVisible(true); //make frame visible
		
		//SETTING ICON
		ImageIcon image = new ImageIcon("JP.gif"); //create an imageIcon
		this.setIconImage(image.getImage());
		
		// Background color
		this.getContentPane().setBackground(new Color(40,82,94)); // change color of background		
		
	}
}
## labels

import java.awt.Color;
import java.awt.Font;

import javax.swing.BorderFactory;
import javax.swing.ImageIcon;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.border.Border;


public class Main {

	public static void main(String[] ags){

		// JLabel : a GUI display area for a string of text, an image, or both
		
		ImageIcon image = new ImageIcon("JP.gif");
		Border border = BorderFactory.createLineBorder(Color.GREEN,5);
		
		JLabel label = new JLabel(); // create a label
		label.setText("Hey, Do you even code?"); //set text of label
		label.setIcon(image);
		
		label.setHorizontalTextPosition(JLabel.CENTER); // LEFT, CENTER, RIGHT
		label.setVerticalTextPosition(JLabel.TOP);// TOP,CENTER,BOTTOM
		
		label.setForeground(new Color(0,244,0)); // font color
		label.setFont(new Font("MV Boli",Font.PLAIN,50)); // font style
		label.setIconTextGap(50); //set gap of text to image
		label.setBackground(new Color(22,35,5));//set background color
		label.setOpaque(true); //display background color
		label.setBorder(border);
		
		label.setVerticalAlignment(JLabel.CENTER); // set vertical position of icon text within label
		label.setHorizontalAlignment(JLabel.CENTER);// set horizontal position of icon text within label
		
		// label.setBounds(20, 20, 480, 400); // set x,y position with in frame as well as dimensions
		
		MyFrame myFrame = new MyFrame(); //new MyFrame();
		myFrame.add(label);
		myFrame.pack(); // need to use right after add(label)
		
	}
}

import java.awt.Color;

import javax.swing.ImageIcon;
import javax.swing.JFrame;

public class MyFrame extends JFrame {

	MyFrame(){		
		this.setTitle("Jthis title goes here"); // set title of frame
		this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); //exit out of application
		// DO_NOTHING_ON_CLOSE , HIDE_ON_CLOSE
		// this.setResizable(false); //prevent frame from being re-sized
		this.setSize(500,500); // set x,y dimension of frame
		this.setVisible(true); //make frame visible
		// this.setLayout(null); //set layout
		
		//SETTING ICON
		ImageIcon image = new ImageIcon("JP.gif"); //create an imageIcon
		this.setIconImage(image.getImage());
		
		// Background color
		this.getContentPane().setBackground(new Color(40,82,94)); // change color of background		
		
	}
}

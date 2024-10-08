# Basic3

## For Each Loop
public class Main {

	public static void main(String[] ags) {
		
		// for-each loop : traversing technique to iterate through the elements in array/ collection
		// less steps more readable but less flexible
		
		// String[] animals = {"Cat","Dog","Rat","Bird"}; array
		
		ArrayList<String> animals = new ArrayList<String>(); //ArrayList
		
		animals.add("Cat");
		animals.add("Dog");
		animals.add("Rat");
		animals.add("Bird");
		
		
		for(String i : animals) {
			System.out.println(i);
		}
		
	}

}

## methods
public class Main {

	public static void main(String[] ags) {
		
		// method = a block of code that is executed whenever it is called upon
		String name = "Lee";
		int age = 21;
		
		hello(name, age); // we don't need to unify the parameter names with method
		
		int x = 3;
		int y = 4;
		
		System.out.println(add(x,y));
		
	}
	static void hello(String title, int age) { // method called hello with parameters
		System.out.println("hello " + title +" age is " + age); 
	}
	static int add(int x, int y) {
		return x+y;
	}

}

## overload methods
public class Main {

	public static void main(String[] ags) {
		
		// overloads methods = methods that share the same name but have different parameters
		// 			share method name + parameters but it makes specific method signature
		
		double x = add(1.1, 2.2, 3.3);
		System.out.println(x);
		
	}
	
	// each method will be call up when parameter is match
	
	static int add(int a, int b) {
		System.out.println("This is overload method #1");
		return a+b;
	}
	static int add(int a, int b,int c) {
		System.out.println("This is overload method #2");
		return a + b + c;
	}
	static int add(int a, int b,int c, int d) {
		System.out.println("This is overload method #3");
		return a + b + c + d;
	}
	static double add(double a, double b) {
		System.out.println("This is overload method #4");
		return a+b;
	}
	static double add(double a, double b, double c) {
		System.out.println("This is overload method #5");
		return a + b + c;
	}
	static double add(double a, double b, double c, double d) {
		System.out.println("This is overload method #6");
		return a + b + c + d;
	}
	
}
## printf
public class Main {

	public static void main(String[] ags) {
		
		// printf() = an optional method to control, format, and display text to the console window
		// 	   			two argument = format string + (object/variable/value)
		//				% [flags] [precision] [width] [conversion-character]
		System.out.printf("This is a format string %d", 123); //%d will appear number
		System.out.println();
		// conversion character
		boolean myBoolean = true; 	// %b
		char myChar = '@';			// %c
		String myString = "LEE";		// %s
		int myInt = 50;				// %d
		double myDouble = 1000;	// %f
		
		System.out.printf("%.2f",myDouble);
		System.out.println();
		//[width]
		System.out.printf("Hello %10s", myString); //%-10s make blanks on right side
		System.out.println();
		
		
		//[precision]
		// sets the number of digits of precision
		System.out.printf("You havve this much money %.2f",myDouble);
		
		System.out.println();
		//[flags]
		// adds an effect to output based on the flag added to format specifier
		// -: left-justify 
		// + :output a plus or minus sign for an numeric value
		// 0 : numeric values are zero-padded
		// , : comma grouping separator if numbers > 1000
		
	}

}
## Final keyword
public static void main(String[] ags) {
		
		// final keyword
		
		final double pi = 3.14159;
		
		// pi = 4; //if i use final we cannot upgrade anymore
		
		System.out.println(pi);
	
		
		
		
	}
	
}

## OOP
public class Main {

	public static void main(String[] ags) {
		
		// object = an instance of a class that may contain attributes and methods
		// example = phone, desk, computer, etc
		
		Car myCar1 = new Car(); // we call the Car class
		Car myCar2 = new Car();
		
		System.out.println(myCar1.model);
		System.out.println(myCar1.make);
		
		System.out.println(myCar2.model);
		System.out.println(myCar2.make);
		
		myCar1.drive();
		
		
	}
	
}    
public class Car {
	
	String make = "Chevrolet";
	String model = "Corvette";
	int year = 2020;
	String color = "Blue";
	double price = 5000.00;
	
	void drive() {
		System.out.println("you are driving the car");
	}
	void brake() {
		System.out.println("you step on the brakes");
	}

}

## constructors

package fisrtprogram;
import java.util.*;

public class Main {

	public static void main(String[] ags) {
		
		Human human1 = new Human("Rick", 65, 78); //constructor : help to make different attributes
		Human human2 = new Human("Marie", 55, 45);
		
		System.out.println(human1.name);
		System.out.println(human2.name);
		
		human2.eat();
		human1.drink();
	}
	
}   

package fisrtprogram;

public class Human {
	
	String name;
	int age;
	double weight;
		
	Human(String name, int age, double weight){
		
		this.name = name;
		this.age = age;
		this.weight = weight;
		
	}
	void eat() {
		System.out.println(this.name+" is eating");
	}
	void drink() {
		System.out.println(this.name+ " is drinking");
	}
}

## variable scope

public class Main {

	public static void main(String[] ags) {
	
		//local = declared inside a method
		
		// global = declared outside a method but within a class visible to all parts of a class
	
		DiceRoller diceRoller = new DiceRoller();
		
	}
}   
public class DiceRoller{
	
	// global || or you can paste as para
	Random random;
	int num = 0;
	
	DiceRoller(){ //constructor
		random = new Random(); // only visible in this method
					// only visible in this method
		roll();
	}
	
	void roll() {
		num = random.nextInt(6)+1;
		System.out.println(num);
	}
	
}

## overloaded constructors
public class Main {

	public static void main(String[] ags) {
		
		//overloaded constructors = multiple constructors within a class with the same name
		//								but have different paras (name + para + signature)
		
		Pizza pizza = new Pizza("Thick crust","tomato","mozzarella","pepperoni"); //pizza objects
		Pizza pizza2 = new Pizza("Thick crust","tomato","mozzarella");
		Pizza pizza3 = new Pizza("Thick crust","tomato");
		Pizza pizza4 = new Pizza("Thick crust");
		
		System.out.println("Here are the ingredients of your pizza");
		System.out.println(pizza.bread);
		System.out.println(pizza.sauce);
		System.out.println(pizza.cheese);
		System.out.println(pizza.topping);
		
	
	}
}   
public class Pizza{
	
	String bread;
	String sauce;
	String cheese;
	String topping;
	
	Pizza(String bread){
		this.bread = bread;
}
	
	Pizza(String bread,	String sauce){
		this.bread = bread;
		this.sauce = sauce;
}
	
	Pizza(String bread,	String sauce, String cheese){
		this.bread = bread;
		this.sauce = sauce;
		this.cheese = cheese;
}
	
	Pizza(String bread,	String sauce, String cheese, String topping	){
			this.bread = bread;
			this.sauce = sauce;
			this.cheese = cheese;
			this.topping = topping;
	}
	
}

## tostring method
public class Main {

	public static void main(String[] ags) {
		
		// toString() = special method that all objects inherit, that returns a string that
		//				"Textually represents" an objects. 
		//             can be used both implicitly and explicitly
		
		
		Car car = new Car();
		
		
		
		// System.out.println(car.toString()); //show where is the memory
		System.out.println(car); //same results
	
	}
}   
public class Car{
	String make = "Ford";
	String model = "Mustang";
	String color = "red";
	int year = 2021;
	
	public String toString() {
		return make + "\n" + model + "\n" + color + "\n" + year;
	}
	
}


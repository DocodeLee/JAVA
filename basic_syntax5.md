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

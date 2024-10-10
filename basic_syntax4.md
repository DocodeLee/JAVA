# Basic 4
## arrays of objects

public class Main {

	public static void main(String[] ags) {
		
		// Food[] refrigerator = new Food[3];
		
		Food food1 = new Food("Pizza");
		Food food2 = new Food("Hamburger");
		Food food3 = new Food("Gimbap");
		
		Food[] refrigerator = {food1,food2,food3};
		
		//refrigerator[0] = food1;
		//refrigerator[1] = food2;
		//refrigerator[2] = food3;
		
		System.out.println(refrigerator[0].name);
		
		
	
	}
}   
public class Food{
	
	String name;
	
	Food(String name){
		this.name = name;
	}
	
}
## object passing
public class Main {

	public static void main(String[] ags) {
		 
		Garage garage = new Garage();
		
		Car car1 = new Car("BMW");
		Car car2 = new Car("KIA");
		
		garage.park(car1);
		garage.park(car2);
		
		
	}
}   
public class Car{
	
	String name;
	
	Car(String name){
		this.name = name;
	}
	
	
	
}    
void park(Car car) {
		System.out.println("The " +car.name+" is parked in the garage");
	}
}    
## static keyword
public class Main {

	public static void main(String[] ags) {
		 
		//static = modifier, A single copy of a variable/ method is created and shared.
		// The "class owns" the static member
		
		Friend friend1 = new Friend("Spongebob");
		Friend friend2 = new Friend("Patrick");
		
		System.out.println(Friend.numberOfFriends);
		
		Friend.displayFriends();
		
		
		
	}
}    
public class Friend{
	
	String name;
	static int numberOfFriends; // static variable if you don't use static only for instance
	
	Friend(String name){
		this.name = name;
		numberOfFriends++;
	}
	
	static void displayFriends() {
		System.out.println("You have " + numberOfFriends + " friends");
	}
	
}
## inheritance
public class Main {

	public static void main(String[] ags) {
		 
		//inheritance = the process where one class acquires. 
		// 				the attributes and methods of another
		
		Car car = new Car();
		
		car.go();
	
		Bicycle bike = new Bicycle();
		
		bike.stop();
		
		System.out.println(car.doors);
		System.out.println(bike.pedals);
	}
}   
public class Vehicle{
	
	double speed;
	
	void go() {
		System.out.println("This vehicle is moving");
	}
	void stop() {
		System.out.println("This vehicle is stop");
	}

	
}   
public class Car extends Vehicle{

	int wheels = 4;
	int doors = 4;


}   
public class Bicycle extends Vehicle{

	int wheels = 2;
	int pedals = 2;
}
## method overiding

public class Main {

	public static void main(String[] ags) {
	
		//method overriding : declaring a method in sub class/
		// which is already present in parent class, child class can give its own implementation
		
		Animal animal = new Animal();
		Dog dog = new Dog();
		
		dog.speak();
		animal.speak();
		
		
	}
}   

public class Animal{
	
	void speak() { // Overridden method
		System.out.println("The animal speaks");
	}
	

	
}   
public class Dog extends Animal{

	@Override
	void speak() {
		System.out.println("The dog goes bark**");
	}
	

}


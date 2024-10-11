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

## super keyword
public class Main {

	public static void main(String[] ags) {
		
		// super keyword: keyword refers to the superclass(parent) of an object
		// 			very similar to the "this" keyword

		Hero hero1 = new Hero("Batman",42,"$$$");
		Hero hero2 = new Hero("Superman",35,"everything");
		
		System.out.println(hero1.name);
		System.out.println(hero1.power);
		System.out.println(hero2.power);
		
		System.out.println(hero2.toString());
		
		
		
	}
}
public class Person{
	
	String name;
	int age;
	
	Person(String name, int age){
		this.name = name;
		this.age =age;
		
	}
	public String toString() {
		return this.name + "\n" + this.age +"\n";
	}

	
}   
public class Hero extends Person{
	
	String power;
	
	Hero(String name, int age, String power){
		
		super(name, age);
		this.power = power;
	}
	
	public String toString() {
		return super.toString()+this.power;
	}

}   
## abstraction
public class Main {

	public static void main(String[] ags) {
		// abstraction : abstract classes cannot be instantiated, but they can have subclass
		// 				abstract methods are declared without an implementation
		
		// Vehicle vehicle = new Vehicle(); (we cannot declare abstract class)
		Car car = new Car();
		
		car.go();
		
	}
}   
public abstract class Vehicle{ //abstract modifier
	
	abstract void go(); // abstract method does not have body

	
}      
public class Car extends Vehicle{

	@Override
	void go() {
		System.out.println("The driver is driving car");
		
	}
	
	

}

## access modifier
### public : you can use even in other packages
### protected : you can use until child class
### private : you can use only in same class

## encapsulation

public class Main {

	public static void main(String[] ags) {
		
		// Encapsulation : attributes of a class will be hidden or private
		// 			 can be accessed only through methods(getter & setters)
		// you should make attributes private if you don't have a reason to make them public/protected
		
		Car car = new Car("Kia","K5", 2022);
		System.out.println(car.getMake());
		System.out.println(car.getYear());
		
		car.setYear(2023); // can change attributes
		System.out.println(car.getYear());
		
		
	}
}    
public class Car {
	
	//private only open for this class
	private String make;
	private String model;
	private int year;
	
	Car(String make, String model, int year){
		this.setMake(make);
		this.setModel(model);
		this.setYear(year);
	}
	
	// change private to accessable
	public String getMake() {
		return make;
	}
	public String getModel() {
		return model;
	}
	public int getYear() {
		return year;
	}
	
	public void setMake(String make) {
		this.make = make;
	}
	public void setModel(String model) {
		this.model = model;
	}
	public void setYear(int year) {
		this.year = year;
	}

}   
## Copy objcts

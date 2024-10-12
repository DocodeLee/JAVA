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


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

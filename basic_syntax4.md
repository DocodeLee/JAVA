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


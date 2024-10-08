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

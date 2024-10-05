# basic2

## logical operators

public class Main {

	public static void main(String[] ags){
		
		// logical operators : &&, ||, !
		
		
		// &&
		int temp = 15;
		
		if(temp > 30) {
			System.out.println("It is hot outside");
		}
		else if(temp >= 20 && temp <= 30) {
			System.out.println("It is warm outside");
		}
		else {
			System.out.println("It is cold outside");
		}
		
		// ||
		Scanner scanner = new Scanner(System.in);
		
		System.out.println("You are playing a game! Press q or Q to quit");
		String response = scanner.next();
		
		if(response.equals("q") || response.equals("Q")) { //if add ! > reverse it
			System.out.println("You quit the game");
		}
		else {
			System.out.println("You are still playing the game");
		}
	}


 ## while
public static void main(String[] ags){
		
		// while loop : execute as long as it's remains true
		
		Scanner scanner = new Scanner(System.in);
		String name = "";
		
		do {
			System.out.println("Enter Your name: ");
			name = scanner.nextLine();
		}while(name.isEmpty());
		
		System.out.println("Hello " + name);
		
	}
 
## for loop

public class Main {

	public static void main(String[] ags){
		
		//for loop= executes a block of code a limited amout of time
		
		for(int i = 10; i >= 0; i -= 2 ) {
			System.out.println(i);
		}
		System.out.println("Happy new year!");
		
		
	}

}

## nested loop

public class Main {

	public static void main(String[] ags) {
		
		// nested loops = a loop inside of a loop
		
		Scanner scanner = new Scanner(System.in);
		int rows;
		int cols;
		String symbol = "";
		
		System.out.println("Enter # of rows: ");
		rows = scanner.nextInt();
		System.out.println("Enter # of columns: ");
		cols = scanner.nextInt();
		System.out.println("Enter Symbol to use: ");
		symbol = scanner.next();
		
		for(int i = 1; i<=rows; i++) {
			System.out.println();
			for(int j = 1; j <=cols; j++) {
				System.out.print(symbol);
			}
		}
	
	
		
	}

}

## arrays
public class Main {

	public static void main(String[] ags) {
		
	// array = used to store multiple values in a single variable
		
		String[] cars = {"Camero","Corvette","Tesla", "BMW"};
		// data type must be unified
		
		cars[0] = "Mustang"; // camero will be disappear
		
		System.out.println(cars[2]);
		
		String[] cars2 = new String[3];
		
		cars2[0] = "Camero";
		cars2[1] = "Corvette";
		cars2[2] = "Tesla";
		
		System.out.println(cars2[0]);
		
		for(int i = 0; i<cars2.length; i++) {
			System.out.println(cars2[i]);
		}
		
		
	
		
	}

}

## 2D array
public class Main {

	public static void main(String[] ags) {
		
		// 2D array = an array of arrays
		
		String[][] cars = new String[3][3]; // (0~2)(0~2)
		
		/*
		 *  { {"Camero","Corvette","Silverado"},
		 *     {"Mustang","Ranger","F-150"},
		 *      ...}
		 *    };
		 * 
		 * */
		
		cars[0][0] = "Camero";
		cars[0][1] = "Corvette";
		cars[0][2] = "Silverado";
		cars[1][0] = "Mustang";
		cars[1][1] = "Ranger";
		cars[1][2] = "F-150";
		cars[2][0] = "Ferrari";
		cars[2][1] = "Lambo";
		cars[2][2] = "KIA";
		
		for(int i=0; i<cars.length; i++) {
			System.out.println();
			for(int j=0; j<cars[i].length; j++) {
				System.out.print(cars[i][j]+" ");
				
			}
		}
	
		
	}

}

## String Method
public static void main(String[] ags) {
		
		// String = a reference data type that can store one or more characters
		// reference data types have access to useful methods
		
		String name = "Lee";
		
		boolean result = name.equalsIgnoreCase("lee"); //ask equals with String
		//boolean result = name.equals("lee");
		int result2 = name.length();
		char result3 = name.charAt(0); //character at index
		int result4 = name.indexOf("e");
		boolean result5 = name.isEmpty();
		String result6 = name.toUpperCase(); // toLowerCase()
		String result7 = name.trim();
		String result8 = name.replace('L', 'k');
		
		System.out.println(result8);
		
	}

}

## Wrapper classes
public class Main {

	public static void main(String[] ags) {
		
		//Wrapper class = provide a way to use primitive data types as reference
		// reference data types contain useful methods can be use with collections
		
		// primitive = boolean, char, int, double
		// wrapper = Boolean, Character, Integer, Double
		
		// autoboxing = the automatice conversion that the Java compiler makes between the primitive datay types
		// unboxing = the reverse of autoboxing
		
		
		// Reference data type
		Boolean a = true;
		Character b = '@';
		Integer c = 123;
		Double d = 3.14;
		String e = "Lee";
		// using reference data type takes lots of steps .. lots of delay
		
		
	}

}
## ArrayList
import java.util.ArrayList;

public class Main {

	public static void main(String[] ags) {
		
		// Array List = a resizable array
		// elements can be added and removed after compilation phase
		// store reference
		
		ArrayList<String> food = new ArrayList<String>(); // need to use Wrapper class
		
		food.add("pizza");
		food.add("hamburger");
		food.add("hotdog");
		
		food.set(0,"Chicken"); // can change elements
		food.remove(1);
		food.clear();
		
		for(int i=0; i<food.size(); i++) {
			System.out.println(food.get(i));
		}
		
	}

}
## 2D Array List
package fisrtprogram;
import java.util.*;

public class Main {

	public static void main(String[] ags) {
		
		// 2D ArayList = dynamic list of lists
		// change the size of these lists during runtime
		
		ArrayList<ArrayList<String>> groceryList = new ArrayList();
		
		
		ArrayList<String> bakeryList = new ArrayList();
		bakeryList.add("Pasta");
		bakeryList.add("Garlic Bread");
		bakeryList.add("Donuts");
		
		System.out.println(bakeryList.get(0));
		
		ArrayList<String> produceList = new ArrayList();
		produceList.add("Tomatoes");
		produceList.add("Zucchini");
				
		System.out.println(produceList.get(0));
		
		ArrayList<String> drinksList = new ArrayList();
		drinksList.add("soda");
		drinksList.add("coffee");
				
		System.out.println(drinksList.get(0));
		
		groceryList.add(bakeryList);
		groceryList.add(produceList);
		groceryList.add(drinksList);
		
		System.out.println(groceryList);
		System.out.println(groceryList.get(0));
		System.out.println(groceryList.get(0).get(2));
	}

}

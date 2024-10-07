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

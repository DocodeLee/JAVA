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

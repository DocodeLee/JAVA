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
 

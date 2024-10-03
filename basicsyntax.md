# JAVA
system.out.println("Hello World");
## data
/*
* boolean: 1bit : true or false
* int : 4bytes
* double : 8 bytes: fractional number up to 15 digits
* char : 2 bytes : single char with ''
* String: sequence of char
*/
## variable
public class Main {

	public static void main(String[] args) {
		
		int x; // declaration
		x = 123; //assignment
		
		int y = 456; //initialization
		long z = 1231231231123123123L;
		//byte is small to care the value
		float f = 3.14f;
		double b = 3.14; //up to 15digits
		boolean l = true; //or false
		char sym = '@';
		String name = "Michael"; //capital
		System.out.println(f);
		System.out.println(b);
		System.out.println(z);
		System.out.println(l);
		System.out.println(name);
		
	}

}

## Swaping var
public class Main {

	public static void main(String[] args) {
		
		String x = "water";
		String y = "Kool-Aid";
		
		String temp;
		temp = x;
		x = y ;
		y = temp;
		
		
		System.out.println("x: " + x);
		System.out.println("y: " + y);
		
		// x=y : y y=x :x follow back
	}

}

## Input data
package fisrtprogram;   
import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		
		Scanner scanner = new Scanner(System.in); // when getting input
		
		System.out.println("What is your name? ");
		String name = scanner.nextLine();
		System.out.println("How old are you? ");
		int age = scanner.nextInt(); // it only get int
		// next line doesn't work : nextint doesn't read new line
		scanner.nextLine(); // clean the scanner for the next question
		System.out.println("What is your favorite food?");
		String food = scanner.nextLine();
		
		System.out.println("Hello " + name);
		System.out.println("Your age " + age + " years old");
		System.out.println("You like " + food);
		
		
	}

}
## expression
public class Main {

	public static void main(String[] ags){
		// expression = operands & operators
		// operands = values, variables, numbers, quantity
		// operators = + - * / (% = remain)
		
		double friends = 10; // int friends = 10;
		
		friends = friends + 1;
		friends++;
		friends--;
		// friends = friends / 2; // "/" only store integar
		friends = friends / 3;
		
		System.out.println(friends);
	}

}

## GUI info
import javax.swing.JOptionPane;

public class Main {

	public static void main(String[] ags){
		
		String name = JOptionPane.showInputDialog("Enter your name");
		JOptionPane.showMessageDialog(null,"Hello "+ name);
		
		int age = Integer.parseInt(JOptionPane.showInputDialog("Enter your age"));
		JOptionPane.showMessageDialog(null, "Your age " + age + " old");
		
		double height = Double.parseDouble(JOptionPane.showInputDialog("Enter your height"));
		JOptionPane.showMessageDialog(null, "Your age " + height + " cm tall");
		
	}

}

## Simple math
public class Main {

	public static void main(String[] ags){
		
		double x = 3.14;
		double y = -10;
		//abs,sqrt, round
		double z = Math.min(x, y);
		double zz = Math.sqrt(x);
		
		System.out.println(z);
		System.out.println(zz);
	}

}

import java.util.Scanner;

public class Main {

	public static void main(String[] ags){
		
		double x;
		double y;
		double z;
		
		Scanner scanner = new Scanner(System.in);
		
		
		System.out.println("Enter Side x: ");
		x = scanner.nextDouble();
		System.out.println("Enter Side y: ");
		y = scanner.nextDouble();
		
		z = Math.sqrt((x*x) + (y*y));
		
		System.out.println("The hypotenuse is :" + z);
		
		scanner.close();

		
	}

}

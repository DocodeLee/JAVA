## KeyBinding
public class Game {
	JFrame frame;
	JLabel label;
	
	Action upAction;
	Action downAction;
	Action leftAction;
	Action rightAction;
	
	
	Game(){
		frame = new JFrame("KeyBinding Demo");
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.setSize(420,420);
		frame.setLayout(null);
		
		label = new JLabel();
		label.setBackground(Color.red);
		label.setBounds(100, 100, 100,100);
		label.setOpaque(true);
		
		upAction = new UpAction();
		downAction = new DownAction();
		leftAction = new LeftAction();
		rightAction = new RightAction();
		
		label.getInputMap().put(KeyStroke.getKeyStroke("w"), "upAction");
		label.getActionMap().put("upAction",upAction);
		
		label.getInputMap().put(KeyStroke.getKeyStroke("s"), "downAction");
		label.getActionMap().put("downAction",downAction);
		
		label.getInputMap().put(KeyStroke.getKeyStroke("a"), "leftAction");
		label.getActionMap().put("leftAction",leftAction);
		
		label.getInputMap().put(KeyStroke.getKeyStroke("d"), "rightAction");
		label.getActionMap().put("rightAction",rightAction);
		
		frame.add(label);
		frame.setVisible(true);
		
	}
	
	public class UpAction extends AbstractAction{

		@Override
		public void actionPerformed(ActionEvent e) {
			label.setLocation(label.getX(),label.getY()-10);
			
		}
		
	}
	public class DownAction extends AbstractAction{

		@Override
		public void actionPerformed(ActionEvent e) {
			label.setLocation(label.getX(),label.getY()+10);
			
		}
		
	}
	public class LeftAction extends AbstractAction{

		@Override
		public void actionPerformed(ActionEvent e) {
			label.setLocation(label.getX() -10 ,label.getY());
			
		}
		
	}
	
	public class RightAction extends AbstractAction{

		@Override
		public void actionPerformed(ActionEvent e) {
			label.setLocation(label.getX() + 10 ,label.getY());
			
		}
		
	}

}
## 2D Graphics
public class MyFrame extends JFrame{
	
	MyPanel panel;
	
	MyFrame(){
		
		panel = new MyPanel();
		
		this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		
		this.add(panel);
		this.pack();
		this.setLocationRelativeTo(null);
		this.setVisible(true);
	}
	
	
	
}
public void paint(Graphics g) {
		
	
		
		Graphics2D g2D = (Graphics2D)g;
		g2D.drawImage(image, 0,0, null);
		g2D.setPaint(Color.blue);
		g2D.setStroke(new BasicStroke(5));//thickness
		//g2D.drawLine(0, 0, 500, 500);
		
		//g2D.setPaint(Color.pink);
		//g2D.drawRect(0, 0, 100, 100); //not filled
		//g2D.fillRect(0, 0, 100, 100);
		
		//g2D.setPaint(Color.orange);
		//g2D.drawOval(20, 20, 100, 100);
		//g2D.fillOval(200, 200, 100, 100);
		//g2D.setPaint(Color.red);
		//g2D.fillArc(0,0,100,100, 0, 180);
		//g2D.setPaint(Color.white);
		//g2D.fillArc(0,0,100,100, 180, 180);
		
		int[] xPoints = {150,250,350};
		int[] yPoints = {300,150,300};
		g2D.setColor(Color.black);
		g2D.drawPolygon(xPoints,yPoints,3);
		g2D.fillPolygon(xPoints,yPoints,3);
		
		g2D.setColor(Color.magenta);
		g2D.setFont(new Font("Ink Free",Font.BOLD,50));
		g2D.drawString("U R A winner", 50, 50);
		
		g2D.drawImage(image, 0,0, null);
	}

}
## 2D animation
public class MyFrame extends JFrame{
	
	MyPanel panel;
	
	MyFrame(){
		panel = new MyPanel();
		
		this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		this.add(panel);
		this.pack();
		this.setLocationRelativeTo(null);
		this.setVisible(true);
	}
	
	
	
}

public class MyPanel extends JPanel implements ActionListener{

	final int PANEL_WIDTH = 500;
	final int PANEL_HEIGHT = 500;
	Image enemy;
	Image backgroundImage;
	Timer timer;
	int xVelocity = 2;
	int yVelocity = 2;
	int x  = 0;
	int y = 0;
	
	MyPanel(){
		
		this.setPreferredSize(new Dimension(PANEL_WIDTH,PANEL_HEIGHT));
		this.setBackground(Color.black);
		enemy = new ImageIcon("JP.gif").getImage();
		timer = new Timer(10, this); //swing timer and awt timer is different
		timer.start();
	}
	
	public void paint(Graphics g) {
		
		super.paint(g); //paint background
		
		Graphics2D g2D = (Graphics2D) g;
		
		g2D.drawImage(enemy,x,y,null);
	}

	@Override
	public void actionPerformed(ActionEvent e) {
		// x
		if(x >= PANEL_WIDTH - enemy.getWidth(null) || x < 0) {
			xVelocity = xVelocity * -1;
		}
		x = x + xVelocity;
		//y
		if(y >= PANEL_HEIGHT - enemy.getHeight(null) || y < 0) {
			yVelocity = yVelocity * -1;
		}
		y = y + yVelocity;
		repaint();
		
	}


}
## Generics
public class Main {
	
	
	public static void main(String[] ags){
		
		//Generics = enable types (classes and interfaces) to be parameters when defining:
		// 			classes, interfaces and methods
		//			a benefit is to eliminate the need to create multiple versions
		// 			of methods or classes for various data types.
		//			use 1 version for all reference data types
		
		Integer[] intArray = {1,2,3,4,5};
		Double[] doubleArray = {1.1,2.2,3.3,4.4,5.5};
		Character[] charArray = {'H','M','E'};
		String[] stringArray = {"B","E","D"};
		
		//displayArray(intArray);
		//displayArray(doubleArray);
		//displayArray(charArray);
		//displayArray(stringArray);
		
		System.out.println(getFirst(intArray));
		System.out.println(getFirst(doubleArray));
		System.out.println(getFirst(charArray));
		System.out.println(getFirst(stringArray));
		
		
	}
	
	public static <Thing> void displayArray(Thing[] array) {
		for(Thing x : array) {
			System.out.print(x + " ");
		}
		System.out.println();
	}
	
	public static <Thing> Thing getFirst(Thing[] array) {
		return array[0];
	}	
 }
## Generics
public class Main {
	
	
	public static void main(String[] ags){
		
		// bounded types : you can create objects of a generic class to have data of specific
		// 					derived types (ex.number
		MyGenericClass <Integer, Integer> myInt = new MyGenericClass<>(1,2);
		MyGenericClass <Double, Double> myDouble = new MyGenericClass<>(3.14,4.3);
		// extends Number  make this cannot work
		//MyGenericClass <Character, Character> myChar = new MyGenericClass<>('a','b');
		//MyGenericClass <String, Character> myString = new MyGenericClass<>("a",'#');
		
		ArrayList<String> myFriends = new ArrayList<>(); //similar with generic class
		HashMap<Integer, String> users = new HashMap<>(); // similar with generic class 2 para
		
		System.out.println(myInt.getValue());
		System.out.println(myDouble.getValue());
		//System.out.println(myChar.getValue());
		//System.out.println(myString.getValue());
		
		
	}
}    
public class MyGenericClass <Thing extends Number , Thing2 extends Number> { //Class Number (Double, Integer..)
	//Number bound the parameter as numbers

	Thing x;
	Thing2 y;
	
	MyGenericClass(Thing x, Thing2 y){
		this.x = x;
		this.y = y;
	}
	
	public Thing2 getValue() {
		return y;
	}
	
}

## Serialization
public class Main {
	
	
	public static void main(String[] ags) throws IOException{
		
		// Serialization : the process of converting an object into a byte stream
		//					Persists (saves the state) the object after program exits
		//					This byte stream can be saved as a file or sent over a network
		//					Can be sent to a different machine
		//					Byte stream can be saved as a file(.ser) which is platform independent
		//					(Think of this as if you're saving a file with the objects information)
		
		// Deserialization : The reverse process of converting a byte stream into object
		//								(loading file)
		
		User user = new User();
		
		user.name = "Lee";
		user.password = "I<3Pizza";
		
		FileOutputStream fileOut = new FileOutputStream("UserInfo.ser");
		ObjectOutputStream out = new ObjectOutputStream(fileOut);
		out.writeObject(user);
		out.close();
		fileOut.close();
		
		System.out.println("object info saved! : ");
	}
 }   
 public class User implements Serializable{
	
	String name;
	String password;
	
	public void sayHello() {
		System.out.println("Hello " + name);
	}
	
}
## Deserializing
public class Main {
	
	
	public static void main(String[] ags) throws IOException, ClassNotFoundException{
	
		User user = null; // declare do not instantiate
		
		FileInputStream fileIn = new FileInputStream("D:\\JAVA\\eclipse-workspace\\fisrtprogram\\UserInfo.ser");
		ObjectInputStream in = new ObjectInputStream(fileIn);
		user= (User) in.readObject();
		in.close();
		fileIn.close();
		
		System.out.println(user.name);		
		System.out.println(user.password);
		user.sayHello();
		
		
	}
 }

 public class User implements Serializable{
	
	String name;
	String password;
	
	public void sayHello() {
		System.out.println("Hello " + name);
	}
	
}
## serialize notes
1. children class of a parent class that implements Serializable will do as so as well
2. static fields are not serialized (they belong to the class , not an individual object)
3. theclass's definition ("class file") itself is not recorded , cast need
4. Fields declared as "transient" are not serialized, ignored
5. serialVersionUID is a unique version ID for a class that serializable

6. serialVersionUID : serialVersionUID is a unique id taht function like a version #

long serialVersionUID = ObjectStreamClass.Lookup(user.getClass()).getSerialVersionUID(); //use UID as address
## Timer
public class Main {
	
	
	public static void main(String[] ags) {
	
		//Timer : a facility for threads to schedule tasks
		// 			for future execution in a background thread
		// Timer Task : a Task that can be scheduled for one-time
		//		or repeated execution by a TImer


		Timer timer = new Timer();
		
		TimerTask task = new TimerTask() {

			int counter = 10;
			@Override
			public void run() {
					if(counter > 0) {
						System.out.println(counter+ " Seconds");
						counter--;
					}
					else {
						System.out.println("HAPPY NEW YEAR");
						timer.cancel();
					}
			}
		};
		
		Calendar date = Calendar.getInstance();
		date.set(Calendar.YEAR,2024);
		date.set(Calendar.MONTH,Calendar.OCTOBER);
		date.set(Calendar.DAY_OF_MONTH,22);
		date.set(Calendar.HOUR_OF_DAY, 20);
		date.set(Calendar.MINUTE, 59);
		date.set(Calendar.SECOND, 5);
		date.set(Calendar.MILLISECOND, 0);
		
		
		//timer.schedule(task,3000);
		//timer.schedule(task, date.getTime());
		//timer.scheduleAtFixedRate(task, 0, 1000); // run every second
		
		
	}
 }
 ## Threads
 public class Main {
	
	
	public static void main(String[] ags) throws InterruptedException {
	/* A thread of execution in a program( kind of like a virtual CPu)
		When JVM starts up, there is a thread which calls the main method
	 */
		
		//System.out.println(Thread.activeCount());
		//Thread.currentThread().setName("MAINN");
		//System.out.println(Thread.currentThread().getName());
		
		//Thread.currentThread().setPriority(10);
		//System.out.println(Thread.currentThread().getPriority()); // higher number , higher priority
		
		//System.out.println(Thread.currentThread().isAlive());
		/*
		for(int i =3; i>0; i--) {
			System.out.println(i);
			Thread.sleep(1000);//sleep one second awake again:)
		}
		System.out.println("You are done");
		*/
		
		MyThread thread2 = new MyThread();
		
		thread2.setDaemon(false);
		System.out.println(thread2.isDaemon());
		//daemon thread in Java is a low-priority thread that 
		// runs in the background to perform tasks 
		//such as garbage collection or other housekeeping activities
		
		thread2.start(); // run() shows false
		
		//System.out.println(thread2.isAlive()); 
		
		//thread2.setName("2nd Thread");
		//System.out.println(thread2.getName());
		
		//System.out.println(Thread.activeCount()); //2
		
		
		
	}
 }   
 public class MyThread extends Thread{

	
	@Override
	public void run() {
		
		if(this.isDaemon()) {
			System.out.println("Daemon thread is running");
		}
		else {
			System.out.println("This is a user thread that is running");
		}
		
	}
}

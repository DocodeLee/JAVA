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

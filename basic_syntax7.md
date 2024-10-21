## JRadioButton
public class Main {
	
	public static void main(String[] ags){
	
		//JRadioButton: one or more button in a grouping in which only 1 may be selected
		
		new MyFrame();
	}
		
 }    
 public class MyFrame extends JFrame implements ActionListener{

	JRadioButton pizzaButton;
	JRadioButton hamburgerButton;
	JRadioButton hotdogButton;
	MyFrame(){
		this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		this.setLayout(new FlowLayout());
		
		pizzaButton = new JRadioButton("Pizza");
		hamburgerButton = new JRadioButton("Hamburg");
		hotdogButton = new JRadioButton("Hotdog");
		
		pizzaButton.addActionListener(this);
		hamburgerButton.addActionListener(this);
		hotdogButton.addActionListener(this);
		
		ButtonGroup group = new ButtonGroup(); // only can select one
		group.add(pizzaButton);
		group.add(hamburgerButton);
		group.add(hotdogButton);
		
		this.add(pizzaButton);
		this.add(hamburgerButton);
		this.add(hotdogButton);
		
		this.pack();
		this.setVisible(true);
	}
	
	@Override
	public void actionPerformed(ActionEvent e) {
	
		if(e.getSource() ==pizzaButton) {
			System.out.println("You ordered Pizza!");
			
		}
		else if(e.getSource() == hamburgerButton) {
			System.out.println("You ordered hamburger");	
		}
		else if(e.getSource() == hotdogButton) {
			System.out.println("you ordered hotdog!");
		}
		
	}
}
## ComboBox
public class MyFrame extends JFrame implements ActionListener{

	JComboBox comboBox;
	
	MyFrame(){
		this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		this.setLayout(new FlowLayout());
		
		String[] animals = {"Dog", "Cat", "Bird"}; //we need pass reference data type for combobox
		
		comboBox = new JComboBox(animals);
		comboBox.addActionListener(this);
		
		//comboBox.setEditable(true);
		//System.out.println(comboBox.getItemCount());
		//comboBox.addItem("Horse");
		//comboBox.insertItemAt("Pig", 2);
		//comboBox.setSelectedIndex(0);
		//comboBox.removeItem("Cat");
		//comboBox.removeItemAt(0);
		//comboBox.removeAll();
		
		this.add(comboBox);
		this.pack();
		this.setVisible(true);
	}
	
	@Override
	public void actionPerformed(ActionEvent e) {
		if(e.getSource() == comboBox) {
		System.out.println(comboBox.getSelectedItem());
		// System.out.println(comboBox.getSelectedIndex());
		
	}
		
	}
}
## Slider Demo
public class Main {
	
	public static void main(String[] ags){
	
		// JSlider : GUI component that lets user enter a value by using an adjustable sliding knob
		
		SliderDemo sliderDemo = new SliderDemo();
		
	}
		
 }
public class SliderDemo implements ChangeListener{

	JFrame frame;
	JPanel panel;
	JLabel label;
	JSlider slider;
	
	SliderDemo(){
		
		frame = new JFrame("Slider Demo");
		panel = new JPanel();
		label = new JLabel();
		slider = new JSlider(0, 100,50);
		
		slider.setPreferredSize(new Dimension(400,200));
		
		//small tick
		slider.setPaintTicks(true);
		slider.setMinorTickSpacing(10);
		
		//larger tick
		slider.setPaintTrack(true);
		slider.setMajorTickSpacing(25);
		
		slider.setPaintLabels(true);
		slider.setFont(new Font("MV Boli",Font.PLAIN,15));
		label.setFont(new Font("MV Boli",Font.PLAIN,25));
		//turn vertical
		slider.setOrientation(SwingConstants.VERTICAL);
		//slider.setOrientation(SwingConstants.HORIZONTAL);
		
		label.setText("C = " + slider.getValue());
		slider.addChangeListener(this);
		
		panel.add(slider);
		panel.add(label);
		frame.add(panel);
		frame.setSize(420,420);
		frame.setVisible(true);
		
		
	}
	
	@Override
	public void stateChanged(ChangeEvent e) {
		// TODO Auto-generated method stub
		label.setText("C = " + slider.getValue());
	}

}
## JProgressBar
public static void main(String[] ags){
	
		// PROGRESS BAR : visual aid to let the user know that an operation is on progression
		
		ProgressBarDemo pro = new ProgressBarDemo();
		
	}
		
 }
public class ProgressBarDemo {
	
	JFrame frame = new JFrame();
	JProgressBar bar = new JProgressBar(0,500);
	
	ProgressBarDemo(){
	
		bar.setValue(0);
		bar.setBounds(0,0,420,50);
		bar.setStringPainted(true);//add 0%
		bar.setFont(new Font("MV Boli",Font.BOLD,25));
		bar.setForeground(Color.red);
		bar.setBackground(Color.black);
		
		frame.add(bar);		
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.setSize(420,420);
		frame.setLayout(null);
		frame.setVisible(true);
		
		fill();
	}

	public void fill() {
		int counter = 0;

		while(counter <= 100) {
			
			bar.setValue(counter);
			try {
				Thread.sleep(50);
			} catch (InterruptedException e) {
				// TODO Auto-generated catch block
				e.printStackTrace();
			}
			counter +=1;
		}
		bar.setString("Done! :)");
		
	}

}
## MenuBar
public class Main {
	
	public static void main(String[] ags){
	
		new MyFrame();
		
	}
		
 }
public class MyFrame extends JFrame implements ActionListener{
	
	JMenuBar menuBar;
	JMenu fileMenu;
	JMenu editMenu;
	JMenu helpMenu;
	JMenuItem loadItem;
	JMenuItem saveItem;
	JMenuItem exitItem;
	
	MyFrame(){
		this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		this.setSize(500,500);
		this.setLayout(new FlowLayout());
		
		menuBar = new JMenuBar();
		
		fileMenu = new JMenu("File");
		editMenu = new JMenu("Edit");
		helpMenu = new JMenu("Help");
		
		loadItem = new JMenuItem("Load");
		saveItem = new JMenuItem("Save");
		exitItem = new JMenuItem("Exit");
		
		loadItem.addActionListener(this);
		saveItem.addActionListener(this);
		exitItem.addActionListener(this);
		
		//menu get automatically alt
		fileMenu.setMnemonic(KeyEvent.VK_F);// alt + F for file
		editMenu.setMnemonic(KeyEvent.VK_E);// alt + E for edit
		helpMenu.setMnemonic(KeyEvent.VK_H);// alt + H for help
		
		loadItem.setMnemonic(KeyEvent.VK_L);// L for load
		saveItem.setMnemonic(KeyEvent.VK_S);// S for Save
		exitItem.setMnemonic(KeyEvent.VK_E);// E for Exit
		
		fileMenu.add(loadItem);
		fileMenu.add(saveItem);
		fileMenu.add(exitItem);
		
		menuBar.add(fileMenu);
		menuBar.add(editMenu);
		menuBar.add(helpMenu);
		
		this.setJMenuBar(menuBar);
		this.setVisible(true);
		
	}

	@Override
	public void actionPerformed(ActionEvent e) {
		
		if(e.getSource() == loadItem) {
			System.out.println("*Beep* You loaded a file");
		}
		if(e.getSource() == saveItem) {
			System.out.println("*Beep* You saved a file");
		}
		if(e.getSource() == exitItem) {
			System.exit(0);
		}		
	}

}
## select file
public static void main(String[] ags){
		
		//JFilechooser: GUI mechanism that let's a user chosse a file
		new MyFrame();
		
	}
 public class MyFrame extends JFrame implements ActionListener{
	
	JButton button;
	
	MyFrame(){
		this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		this.setSize(500,500);
		this.setLayout(new FlowLayout());
		
		button = new JButton("Select File");
		button.addActionListener(this);
		
		this.add(button);
		this.pack();
		this.setVisible(true);
		
	}

	@Override
	public void actionPerformed(ActionEvent e) {
		if(e.getSource() ==button) {
			
			JFileChooser fileChooser = new JFileChooser();
			
			fileChooser.setCurrentDirectory(new File(".")); //change to present directory
			
			//int response = fileChooser.showOpenDialog(null); // select file to open
			int response = fileChooser.showSaveDialog(null); //select file to save
			
			if(response == JFileChooser.APPROVE_OPTION) {
				File file = new File(fileChooser.getSelectedFile().getAbsolutePath());
				System.out.println(file); //show file path
			}
			
		}
	}

}
## JCOlorChooser
public class MyFrame extends JFrame implements ActionListener{
	
	JButton button;
	JLabel label;
	
	MyFrame(){
		this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		this.setSize(500,500);
		this.setLayout(new FlowLayout());
		
		button = new JButton("Pick a color");
		button.addActionListener(this);
		
		label = new JLabel();
		label.setBackground(Color.white);
		label.setText("This is some text :D");
		label.setFont(new Font("MV Boli",Font.PLAIN,100));
		label.setOpaque(true);
		
		this.add(button);
		this.add(label);
		this.pack();
		this.setVisible(true);
		
	}

	@Override
	public void actionPerformed(ActionEvent e) {
		if(e.getSource() == button) {
			JColorChooser colorChooser = new JColorChooser();
			
			Color color = JColorChooser.showDialog(null, "Pick a color...",Color.black);
			
			//label.setForeground(color);
			label.setBackground(color);
		}
			
			
		
	}

}
## KeyboardListener
public class MyFrame extends JFrame implements KeyListener{
	
	JButton button;
	JLabel label;
	
	MyFrame(){
		this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		this.setSize(500,500);
		this.setLayout(null);
		this.addKeyListener(this);
		
		label = new JLabel();
		label.setBounds(0,0,100,100);
		label.setBackground(Color.red);
		label.setOpaque(true);
		
		this.add(label);
		this.pack();
		this.setVisible(true);		
	}

	@Override
	public void keyTyped(KeyEvent e) {
		//KeyTyped : invoke when a key is typed. uses KeyChar, char output
		switch(e.getKeyChar()) {
		case 'a':label.setLocation(label.getX()-10,label.getY());
			break;
		case 'w':label.setLocation(label.getX(),label.getY()-10);
		break;
		case 'd':label.setLocation(label.getX()+10,label.getY());
		break;
		case 's':label.setLocation(label.getX(),label.getY()+10);
		break;
		
		
		}
		
	}

	@Override
	public void keyPressed(KeyEvent e) {
		//KeyPressed = invoke when a physical key is pressed down. Uses Keycode, int output
		switch(e.getKeyCode()) {
		case 37:label.setLocation(label.getX()-10,label.getY());
			break;
		case 38:label.setLocation(label.getX(),label.getY()-10);
		break;
		case 40:label.setLocation(label.getX()+10,label.getY());
		break;
		case 39:label.setLocation(label.getX(),label.getY()+10);
		break;
		
		
		}
	}

	@Override
	public void keyReleased(KeyEvent e) {
		// whenever button is released
		System.out.println("You released key char : " + e.getKeyChar());
		System.out.println("You released key code : " + e.getKeyCode());
		
	}


	
}
## MouseListener
public class MyFrame extends JFrame implements MouseListener{
	
	JButton button;
	JLabel label;
	
	MyFrame(){
		this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		this.setSize(500,500);
		this.setLayout(null);
		
		label = new JLabel();
		label.setBounds(0,0, 100, 100);
		label.setBackground(Color.red);
		label.setOpaque(true);
		this.addMouseListener(this); // the place is important
		this.add(label);
		this.setVisible(true);		
	}

	@Override
	public void mouseClicked(MouseEvent e) {
		// when a mouse button has been clicked and released
		//System.out.println("You clicked the mouse");
	}

	@Override
	public void mousePressed(MouseEvent e) {
		// when a mouse button has been pressed
		System.out.println("You pressed the mouse");
		label.setBackground(Color.yellow);
	}

	@Override
	public void mouseReleased(MouseEvent e) {
		// when a mouse button has been released
		System.out.println("You released the mouse");
		label.setBackground(Color.green);
	}

	@Override
	public void mouseEntered(MouseEvent e) {
		// when a mouse enter the area
		System.out.println("You entered the mouse");
		label.setBackground(Color.blue);
	}

	@Override
	public void mouseExited(MouseEvent e) {
		// when a mouse exit the area
		System.out.println("You exited the mouse");
		label.setBackground(Color.red);
	}

	
}
## Drag and drop
public class MyFrame extends JFrame{
	
	DragPanel dragPanel = new DragPanel();
	
	MyFrame(){
		
		this.add(dragPanel);
		this.setTitle("Drag & Drop demo");
		this.setSize(600,600);
		this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		this.setVisible(true);
	}
	
}    
public class DragPanel extends JPanel{

	ImageIcon image = new ImageIcon("JP.gif");
	final int Width = image.getIconWidth();
	final int Height = image.getIconHeight();
	Point imageCorner;
	Point prevPt;
	
	
	DragPanel(){
		imageCorner = new Point(0,0);
		ClickListener clickListener = new ClickListener();
		DragListener dragListener = new DragListener();
		this.addMouseListener(clickListener);
		this.addMouseMotionListener(dragListener);
	}
	public void paintComponent(Graphics g) {
		super.paintComponent(g);
		image.paintIcon(this, g, (int)imageCorner.getX(), (int)imageCorner.getY());
	}
	
	private class ClickListener extends MouseAdapter{
		
		public void mousePressed(MouseEvent e) {
			prevPt = e.getPoint();
		}
		
	}
	private class DragListener extends MouseMotionAdapter{
		
		public void mouseDragged(MouseEvent e) {
			Point currentPt = e.getPoint();
			
			imageCorner.translate(
					(int)(currentPt.getX() - prevPt.getX()),
					(int)(currentPt.getY() - prevPt.getY())
					);
			prevPt = currentPt;
			repaint();
		}
	}
}

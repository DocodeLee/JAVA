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

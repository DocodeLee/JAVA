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

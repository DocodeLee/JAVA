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

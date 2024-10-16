# Basic 6

## Panels
import java.util.*;
import java.awt.BorderLayout;
import java.awt.Color;
import java.awt.Font;

import javax.swing.BorderFactory;
import javax.swing.ImageIcon;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;
import javax.swing.border.Border;


public class Main {

	public static void main(String[] ags){
		
		// Jpanel = a GUI component that functions as a container to hold other components
		
		ImageIcon icon = new ImageIcon("JP.gif");
		
		JLabel label = new JLabel();
		label.setText("Hi");
		label.setIcon(icon);
		//label.setVerticalAlignment(JLabel.BOTTOM);
		//label.setHorizontalAlignment(JLabel.RIGHT);
		label.setBounds(100,100,200,200); // instead of stebounds
		
		
		JPanel  redPanel = new JPanel();
		redPanel.setBackground(Color.red);
		redPanel.setBounds(0,0,250,250);
		redPanel.setLayout(new BorderLayout());
		
		JPanel  bluePanel = new JPanel();
		bluePanel.setBackground(Color.blue);
		bluePanel.setBounds(250,0,250,250);
		
		JPanel  greenPanel = new JPanel();
		greenPanel.setBackground(Color.green);
		greenPanel.setBounds(0,250,500,250);
		greenPanel.setLayout(new BorderLayout());
		
		JFrame frame = new JFrame();
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.setLayout(null);
		frame.setSize(750,750);
		frame.setVisible(true);
		greenPanel.add(label);
		frame.add(redPanel);
		frame.add(bluePanel);
		frame.add(greenPanel);	
	}
}
## Button
public class Main {

	public static void main(String[] ags){
		
		//JButton = a button that performs an action when clicked on
		
		new MyFrame();
		
		
	}
}   
import java.awt.Color;
import java.awt.Font;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.BorderFactory;
import javax.swing.ImageIcon;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;

public class MyFrame extends JFrame implements ActionListener{

	JButton button;
	JLabel label;
	
	MyFrame(){
		
		ImageIcon icon = new ImageIcon("JP.gif");
		ImageIcon icon2 = new ImageIcon("JP.gif");
		
		label = new JLabel();
		label.setIcon(icon2);
		label.setBounds(150, 250, 150, 150);
		label.setVisible(false);
		
		button = new JButton();
		button.setBounds(20,100, 350, 250);
		button.addActionListener(this);
		button.setText("Button");
		button.setFocusable(false); // erase dot border
		button.setIcon(icon);
		button.setHorizontalTextPosition(JButton.CENTER);
		button.setVerticalTextPosition(JButton.BOTTOM);
		button.setFont(new Font("Comic Sans",Font.BOLD,25));
		button.setIconTextGap(-10);
		button.setForeground(Color.cyan);
		button.setBackground(Color.LIGHT_GRAY);
		button.setBorder(BorderFactory.createEtchedBorder());
		// button.setEnabled(false); // make it unavailable
		
		this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		this.setLayout(null);
		this.setSize(500,500);
		this.setVisible(true);
		this.add(button);
		this.add(label);

		
	}
	@Override
	public void actionPerformed(ActionEvent e) {
		// TODO Auto-generated method stub
		System.out.println("Welcome");
		// button.setEnabled(false); // make it unavailable
		label.setVisible(true);
	}
}
## Border Layout
public class Main {

	public static void main(String[] ags){
		
		// Layout Manager - Defines the natural layout for components within a container
		// 3 common managers
		// BorderLayout = a BorderLayout places components in five area: north, west, south, east center
		// 				all extra space is placed in the center
		
		JFrame frame = new JFrame();
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.setSize(500,500);
		
		frame.setLayout(new BorderLayout(10,10)); //(margin width, margin height)
		frame.setVisible(true);
		
		JPanel panel1 = new JPanel();
		JPanel panel2 = new JPanel();
		JPanel panel3 = new JPanel();
		JPanel panel4 = new JPanel();
		JPanel panel5 = new JPanel();
		
		panel1.setBackground(Color.red);
		panel2.setBackground(Color.green);
		panel3.setBackground(Color.yellow);
		panel4.setBackground(Color.magenta);
		panel5.setBackground(Color.blue);
		
		panel1.setPreferredSize(new Dimension(100,50));
		panel2.setPreferredSize(new Dimension(100,50));
		panel3.setPreferredSize(new Dimension(100,50));
		panel4.setPreferredSize(new Dimension(100,50));
		panel5.setPreferredSize(new Dimension(100,50));
		
		
		//---------- sub panels
		JPanel panel6 = new JPanel();
		JPanel panel7 = new JPanel();
		JPanel panel8 = new JPanel();
		JPanel panel9 = new JPanel();
		JPanel panel10 = new JPanel();
		
		panel6.setBackground(Color.black);
		panel7.setBackground(Color.DARK_GRAY);
		panel8.setBackground(Color.gray);
		panel9.setBackground(Color.LIGHT_GRAY);
		panel10.setBackground(Color.white);
		
		panel5.setLayout(new BorderLayout(5,5));
		
		panel6.setPreferredSize(new Dimension(100,50));
		panel7.setPreferredSize(new Dimension(100,50));
		panel8.setPreferredSize(new Dimension(100,50));
		panel9.setPreferredSize(new Dimension(100,50));
		panel10.setPreferredSize(new Dimension(100,50));
		
		frame.add(panel1,BorderLayout.NORTH);
		frame.add(panel2,BorderLayout.WEST);
		frame.add(panel3,BorderLayout.EAST);
		frame.add(panel4,BorderLayout.SOUTH);
		frame.add(panel5,BorderLayout.CENTER);
		
		panel5.add(panel6,BorderLayout.NORTH);
		panel5.add(panel7,BorderLayout.WEST);
		panel5.add(panel8,BorderLayout.EAST);
		panel5.add(panel9,BorderLayout.SOUTH);
		panel5.add(panel10,BorderLayout.CENTER);
		
		
		
		
	}
}

## Flow Layout
public class Main {

	public static void main(String[] ags){
		
		// Layout manager = Defines the natural layout for components within a container
		
		
		// FlowLayout = places components in a row, sized at their preferred size,
		// 				if the horizontal space in the container is too small.
		//				the FlowLayout class uses the next available row.
		
		
		JFrame frame = new JFrame();
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.setSize(500,500);
		frame.setLayout(new FlowLayout(FlowLayout.CENTER,10,10)); //TRAILING: RIGHT,(spacing)
		
		JPanel panel = new JPanel();
		panel.setPreferredSize(new Dimension(250,250));
		panel.setBackground(Color.DARK_GRAY);
		panel.setLayout(new FlowLayout());
		
		panel.add(new JButton("1"));
		panel.add(new JButton("2"));
		panel.add(new JButton("3"));
		panel.add(new JButton("4"));
		panel.add(new JButton("5"));
		panel.add(new JButton("6"));
		panel.add(new JButton("7"));
		panel.add(new JButton("8"));
		panel.add(new JButton("9"));
		
		frame.add(panel);
		
		frame.setVisible(true);
		
	}
}
## Grid Layout
public class Main {

	public static void main(String[] ags){
		
		// Layout manager = Defines the natural layout for components within a container
		
		
		// GridLayout = places components in a grid of cells
		// 				each components takes all the available space within its cell
		//				and each cell is the same size
		
		
		JFrame frame = new JFrame();
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.setSize(500,500);
		
		frame.setLayout(new GridLayout(3,3,10,10)); //(rows, cols, margin, margin)
		
		frame.add(new JButton("1"));
		
		frame.add(new JButton("2"));
		frame.add(new JButton("3"));
		frame.add(new JButton("4"));
		frame.add(new JButton("5"));
		frame.add(new JButton("6"));
		frame.add(new JButton("7"));
		frame.add(new JButton("8"));
		frame.add(new JButton("9"));
		
		frame.setVisible(true);
		
	}
}   
## layered Pane

import java.awt.Color;
import java.awt.Dimension;
import java.awt.GridLayout;
import java.util.*;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JLayeredPane;
import javax.swing.JPanel;


public class Main {

	public static void main(String[] ags){
		
		// JLayerPane = swing contaienr that provides a third dimension for positioning components
		//				ex. depth, z-index
		
		JLabel label1 = new JLabel();
		label1.setOpaque(true);
		label1.setBackground(Color.red);
		label1.setBounds(50,50,200,200);
		
		JLabel label2 = new JLabel();
		label2.setOpaque(true);
		label2.setBackground(Color.green);
		label2.setBounds(100,100,200,200);
		
		JLabel label3 = new JLabel();
		label3.setOpaque(true);
		label3.setBackground(Color.blue);
		label3.setBounds(150,150,200,200);
		
		
		JLayeredPane layeredPane = new JLayeredPane();
		layeredPane.setBounds(0,0,500,500);
		
		layeredPane.add(label1, Integer.valueOf(0));
		layeredPane.add(label2, Integer.valueOf(2));
		layeredPane.add(label3, Integer.valueOf(1));
		
		JFrame frame = new JFrame("JLayerPane");
		frame.add(layeredPane);	
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.setSize(new Dimension(500,500));
		frame.setLayout(null);
		frame.setVisible(true);
		
		
		
	}
}
## New GUI
public class Main {

	public static void main(String[] ags){
		LaunchPage launchPage = new LaunchPage();
		
		
		
	}
}
public class LaunchPage implements ActionListener{
	
	JFrame frame = new JFrame();
	JButton myButton = new JButton("New Window");
	
	LaunchPage(){
		
		myButton.setBounds(100,160,200,40);
		myButton.setFocusable(false);
		myButton.addActionListener(this);
		
		frame.add(myButton);
		
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.setSize(420,420);
		frame.setLayout(null);
		frame.setVisible(true);
	}

	@Override
	public void actionPerformed(ActionEvent e) {
		if(e.getSource()==myButton) {
			frame.dispose();
			NewWindow myWindow = new NewWindow();
		}
		
	}

}
public  class NewWindow{
	
	JFrame frame = new JFrame();
	JLabel label = new JLabel("Hello!");
	
	NewWindow(){
		label.setBounds(0,0,100,50);
		label.setFont(new Font(null,Font.PLAIN,25));
		
		frame.add(label);
		
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.setSize(420,420);
		frame.setLayout(null);
		frame.setVisible(true);
		
	}
	
}

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

import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class HomePage extends JFrame implements ActionListener {
    JButton homeButton, aboutUsButton, loginButton, registerButton, reportButton, newExamButton, enterQuizCodeButton;
    private Image backgroundImage;

    HomePage() {
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setSize(1200, 700);

        // Load the background image
        backgroundImage = new ImageIcon(ClassLoader.getSystemResource("icon/quizz12.jpg")).getImage();

        // Create a custom JPanel to serve as the content pane
        JPanel contentPane = new JPanel() {
            @Override
            protected void paintComponent(Graphics g) {
                super.paintComponent(g);
                // Draw the background image
                g.drawImage(backgroundImage, 0, 0, getWidth(), getHeight(), this);
            }
        };

        // Set the layout to null for absolute positioning
        contentPane.setLayout(null);

        ImageIcon imageIcon = new ImageIcon(ClassLoader.getSystemResource("icon/home.jpeg"));
        JLabel image = new JLabel(imageIcon);
        image.setBounds(0, 0, 1200, 500);
        add(image);

        JLabel heading = new JLabel("Simple Minds");
        heading.setBounds(500, 30, 300, 45);
        heading.setFont(new Font("Viner Hand ITC", Font.BOLD, 40));
        heading.setForeground(new Color(30, 144, 254));
        add(heading);

        homeButton = new JButton("Home");
        homeButton.setBounds(50, 550, 100, 30);
        homeButton.setBackground(new Color(30, 144, 254));
        homeButton.setForeground(Color.WHITE);
        homeButton.addActionListener(this);
        add(homeButton);

        aboutUsButton = new JButton("About Us");
        aboutUsButton.setBounds(200, 550, 100, 30);
        aboutUsButton.setBackground(new Color(30, 144, 254));
        aboutUsButton.setForeground(Color.WHITE);
        aboutUsButton.addActionListener(this);
        add(aboutUsButton);

        loginButton = new JButton("Login");
        loginButton.setBounds(350, 550, 100, 30);
        loginButton.setBackground(new Color(30, 144, 254));
        loginButton.setForeground(Color.WHITE);
        loginButton.addActionListener(this);
        add(loginButton);

        registerButton = new JButton("Register");
        registerButton.setBounds(500, 550, 100, 30);
        registerButton.setBackground(new Color(30, 144, 254));
        registerButton.setForeground(Color.WHITE);
        registerButton.addActionListener(this);
        add(registerButton);

        reportButton = new JButton("Report");
        reportButton.setBounds(700, 550, 100, 30);
        reportButton.setBackground(new Color(30, 144, 254));
        reportButton.setForeground(Color.WHITE);
        reportButton.addActionListener(this);
        add(reportButton);

        newExamButton = new JButton("New Exam");
        newExamButton.setBounds(850, 550, 100, 30);
        newExamButton.setBackground(new Color(30, 144, 254));
        newExamButton.setForeground(Color.WHITE);
        newExamButton.addActionListener(this);
        add(newExamButton);

        enterQuizCodeButton = new JButton("Enter Quiz Code");
        enterQuizCodeButton.setBounds(1000, 550, 140, 30);
        enterQuizCodeButton.setBackground(new Color(30, 144, 254));
        enterQuizCodeButton.setForeground(Color.WHITE);
        enterQuizCodeButton.addActionListener(this);
        add(enterQuizCodeButton);
    }

    public void actionPerformed(ActionEvent e) {
        if (e.getSource() == homeButton) {
            // Code to handle the Home button click (Do nothing as it's the same page)
        } else if (e.getSource() == aboutUsButton) {
            setVisible(false);
            new AboutUsPage();
        } else if (e.getSource() == loginButton) {
            setVisible(false);
            new LoginPage();
        } else if (e.getSource() == registerButton) {
            setVisible(false);
            new RegisterPage();
        } else if (e.getSource() == reportButton) {
            // Code to handle the Report button click
        } else if (e.getSource() == newExamButton) {
            // Code to handle the New Exam button click
        } else if (e.getSource() == enterQuizCodeButton) {
            setVisible(false);
            new EnterQuizCodeFrame();
        }
    }

    public static void main(String[] args) {
        new HomePage();
    }
}

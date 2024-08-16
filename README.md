#  Quiz Application

This project is a Java Swing-based graphical user interface (GUI) application designed for a quiz platform. The application features multiple buttons that navigate between different pages like Home, About Us, Login, Register, New Exam, and Enter Quiz Code.

## Table of Contents
- [Project Overview](#project-overview)
- [Installation](#installation)
- [Usage](#usage)
- [Code Explanation](#code-explanation)

## Project Overview

The Simple Minds Quiz Application provides a simple and interactive GUI for users to navigate through different sections of the quiz platform. The application uses Java Swing to create a user-friendly interface with buttons that lead to different functionalities such as logging in, registering, and starting a new exam.


## Installation
To run this project, you need to have Java Development Kit (JDK) installed on your system. You can download it from the official Oracle website.
-  Ensure you have a JDK installed on your system.
-  Download or clone the repository
  
```bash
git clone https://github.com/yourusername/simple-minds-quiz.git
cd simple-minds-quiz
```
-  Open the project in your preferred Java Integrated Development Environment (IDE), such as IntelliJ IDEA, Eclipse, or NetBeans

## Usage

- Compile and run the HomePage.java file in your IDE.
- The main window will open, displaying the quiz application's home page with buttons for various 
  functionalities.
- Clicking each button will navigate you to different parts of the application, such as Login, Register, 
  About Us, etc.


## Code Explanation

```java
public class HomePage extends JFrame implements ActionListener {
    // Button declarations
    JButton homeButton, aboutUsButton, loginButton, registerButton, reportButton, newExamButton, enterQuizCodeButton;
    private Image backgroundImage;

    HomePage() {
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setSize(1200, 700);

        // Load and set background image
        backgroundImage = new ImageIcon(ClassLoader.getSystemResource("icon/quizz12.jpg")).getImage();
        // Custom JPanel for background image
        JPanel contentPane = new JPanel() {
            @Override
            protected void paintComponent(Graphics g) {
                super.paintComponent(g);
                g.drawImage(backgroundImage, 0, 0, getWidth(), getHeight(), this);
            }
        };
        contentPane.setLayout(null);
        // Add components to the panel
        addComponentsToPanel(contentPane);
        setContentPane(contentPane);
        setVisible(true);
    }
    // Other methods and event handling
}

```
-**Action Listeners**:
The application implements the ActionListener interface to handle button clicks, which trigger navigation to different pages of the application.
```java
public void actionPerformed(ActionEvent e) {
    if (e.getSource() == homeButton) {
        // Handle Home button click
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
        // Handle Report button click
    } else if (e.getSource() == newExamButton) {
        // Handle New Exam button click
    } else if (e.getSource() == enterQuizCodeButton) {
        setVisible(false);
        new EnterQuizCodeFrame();
    }
}

```
- **Images and Resources**:
- The application loads images from the icon folder using `ClassLoader.getSystemResource()`.
```java
backgroundImage = new ImageIcon(ClassLoader.getSystemResource("icon/quizz12.jpg")).getImage();
```

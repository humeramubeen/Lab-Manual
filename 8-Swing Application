import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class StudentRegistration extends JFrame implements ActionListener {
    // UI Components
    JTextField tfUsn, tfName;
    JComboBox<String> cbBranch;
    JRadioButton rbMale, rbFemale;
    ButtonGroup bgGender;
    JCheckBox chkJava, chkPython;
    JButton btnSubmit, btnClear;
    JTextArea taDisplay;

    public StudentRegistration() {
        // Frame Configuration
        setTitle("Student Registration Form");
        setSize(420, 520);
        setLayout(null);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // Title Label
        JLabel lblTitle = new JLabel("STUDENT REGISTRATION FORM", JLabel.CENTER);
        lblTitle.setBounds(50, 10, 300, 25);
        lblTitle.setFont(new Font("Arial", Font.BOLD, 14));
        add(lblTitle);

        // USN
        JLabel lblUsn = new JLabel("USN :");
        lblUsn.setBounds(40, 50, 80, 25);
        add(lblUsn);

        tfUsn = new JTextField();
        tfUsn.setBounds(130, 50, 200, 25);
        add(tfUsn);

        // Name
        JLabel lblName = new JLabel("Name :");
        lblName.setBounds(40, 85, 80, 25);
        add(lblName);

        tfName = new JTextField();
        tfName.setBounds(130, 85, 200, 25);
        add(tfName);

        // Branch
        JLabel lblBranch = new JLabel("Branch :");
        lblBranch.setBounds(40, 120, 80, 25);
        add(lblBranch);

        String[] branches = {"Computer Science", "Information Science", "Electronics & Comm.", "Mechanical", "Civil"};
        cbBranch = new JComboBox<>(branches);
        cbBranch.setBounds(130, 120, 200, 25);
        add(cbBranch);

        // Gender
        JLabel lblGender = new JLabel("Gender :");
        lblGender.setBounds(40, 155, 80, 25);
        add(lblGender);

        rbMale = new JRadioButton("Male");
        rbFemale = new JRadioButton("Female");
        rbMale.setBounds(130, 155, 70, 25);
        rbFemale.setBounds(210, 155, 80, 25);

        bgGender = new ButtonGroup();
        bgGender.add(rbMale);
        bgGender.add(rbFemale);

        add(rbMale);
        add(rbFemale);

        // Skills
        JLabel lblSkills = new JLabel("Skills :");
        lblSkills.setBounds(40, 190, 80, 25);
        add(lblSkills);

        chkJava = new JCheckBox("Java");
        chkPython = new JCheckBox("Python");
        chkJava.setBounds(130, 190, 70, 25);
        chkPython.setBounds(210, 190, 80, 25);

        add(chkJava);
        add(chkPython);

        // Buttons
        btnSubmit = new JButton("Submit");
        btnSubmit.setBounds(90, 235, 90, 30);
        btnSubmit.addActionListener(this);
        add(btnSubmit);

        btnClear = new JButton("Clear");
        btnClear.setBounds(200, 235, 90, 30);
        btnClear.addActionListener(this);
        add(btnClear);

        // Student Details Label
        JLabel lblDetails = new JLabel("Student Details", JLabel.CENTER);
        lblDetails.setBounds(40, 280, 320, 20);
        lblDetails.setFont(new Font("Arial", Font.BOLD, 12));
        add(lblDetails);

        // Text Area for Output
        taDisplay = new JTextArea();
        taDisplay.setBounds(40, 305, 320, 150);
        taDisplay.setEditable(false);
        add(taDisplay);

        setVisible(true);
    }

    @Override
    public void actionPerformed(ActionEvent e) {
        if (e.getSource() == btnSubmit) {
            String usn = tfUsn.getText().trim();
            String name = tfName.getText().trim();

            if (usn.isEmpty() || name.isEmpty()) {
                JOptionPane.showMessageDialog(this, "Please fill in mandatory fields (USN and Name).", "Input Error", JOptionPane.ERROR_MESSAGE);
                return;
            }

            String branch = (String) cbBranch.getSelectedItem();
            String gender = rbMale.isSelected() ? "Male" : (rbFemale.isSelected() ? "Female" : "Not Specified");

            StringBuilder skills = new StringBuilder();
            if (chkJava.isSelected()) skills.append("Java ");
            if (chkPython.isSelected()) skills.append("Python ");
            if (skills.length() == 0) skills.append("None");

            taDisplay.setText("USN : " + usn + "\n" +
                    "Name : " + name + "\n" +
                    "Branch : " + branch + "\n" +
                    "Gender : " + gender + "\n" +
                    "Skills : " + skills.toString().trim());

        } else if (e.getSource() == btnClear) {
            tfUsn.setText("");
            tfName.setText("");
            cbBranch.setSelectedIndex(0);
            bgGender.clearSelection();
            chkJava.setSelected(false);
            chkPython.setSelected(false);
            taDisplay.setText("");
        }
    }

    public static void main(String[] args) {
        new StudentRegistration();
    }
}

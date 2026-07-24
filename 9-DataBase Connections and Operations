import java.sql.*;

public class StudentJDBC {
    static final String URL = "jdbc:mysql://localhost:3306/college";
    static final String USER = "root";
    static final String PASS = "password"; // Replace with your MySQL password

    public static void main(String[] args) {
        try {
            // Load Driver and Connect
            Class.forName("com.mysql.cj.jdbc.Driver");
            Connection conn = DriverManager.getConnection(URL, USER, PASS);

            // 1. Insert Records
            String insertSQL = "INSERT INTO student (rollno, name, department, marks) VALUES (?, ?, ?, ?)";
            PreparedStatement pstmtInsert = conn.prepareStatement(insertSQL);

            pstmtInsert.setInt(1, 101);
            pstmtInsert.setString(2, "Rahul");
            pstmtInsert.setString(3, "CSE");
            pstmtInsert.setInt(4, 87);
            pstmtInsert.executeUpdate();

            pstmtInsert.setInt(1, 102);
            pstmtInsert.setString(2, "Sneha");
            pstmtInsert.setString(3, "ISE");
            pstmtInsert.setInt(4, 91);
            pstmtInsert.executeUpdate();

            System.out.println("Records Inserted Successfully.\n");

            // 2. Update Record
            String updateSQL = "UPDATE student SET marks = ? WHERE rollno = ?";
            PreparedStatement pstmtUpdate = conn.prepareStatement(updateSQL);
            pstmtUpdate.setInt(1, 95);
            pstmtUpdate.setInt(2, 101);
            pstmtUpdate.executeUpdate();

            System.out.println("Record Updated Successfully.\n");

            // 3. Search and Display Student Details
            String searchSQL = "SELECT * FROM student WHERE rollno = ?";
            PreparedStatement pstmtSearch = conn.prepareStatement(searchSQL);
            pstmtSearch.setInt(1, 101);
            ResultSet rsSearch = pstmtSearch.executeQuery();

            System.out.println("Student Details");
            if (rsSearch.next()) {
                System.out.println("Roll No : " + rsSearch.getInt("rollno"));
                System.out.println("Name    : " + rsSearch.getString("name"));
                System.out.println("Department : " + rsSearch.getString("department"));
                System.out.println("Marks   : " + rsSearch.getInt("marks"));
            }

            // 4. Display All Student Records
            String displaySQL = "SELECT * FROM student";
            PreparedStatement pstmtDisplay = conn.prepareStatement(displaySQL);
            ResultSet rsDisplay = pstmtDisplay.executeQuery();

            System.out.println("\nStudent Records");
            System.out.println("---------------------------------------------");
            System.out.printf("%-7s %-7s %-15s %-5s\n", "Roll", "Name", "Department", "Marks");
            System.out.println("---------------------------------------------");

            while (rsDisplay.next()) {
                System.out.printf("%-7d %-7s %-15s %-5d\n",
                        rsDisplay.getInt("rollno"),
                        rsDisplay.getString("name"),
                        rsDisplay.getString("department"),
                        rsDisplay.getInt("marks"));
            }

            // Close resources
            conn.close();

        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}

import java.util.*;

// Student class definition
class Student {
    int rollNo;
    String name;
    double percentage;

    // Constructor
    public Student(int rollNo, String name, double percentage) {
        this.rollNo = rollNo;
        this.name = name;
        this.percentage = percentage;
    }

    // Display student details
    @Override
    public String toString() {
        return "Roll No: " + rollNo + ", Name: " + name + ", Percentage: " + percentage + "%";
    }
}

public class StudentRecord {
    public static void main(String[] args) {
        // 1. Create ArrayList and HashMap
        List<Student> studentList = new ArrayList<>();
        Map<Integer, Student> studentMap = new HashMap<>();

        // 2. Create Student Objects
        Student s1 = new Student(101, "Rahul", 85.5);
        Student s2 = new Student(102, "Sneha", 91.0);
        Student s3 = new Student(103, "Kiran", 78.2);

        // 3. Add to ArrayList
        studentList.add(s1);
        studentList.add(s2);
        studentList.add(s3);

        // 4. Add to HashMap (Key: Roll Number)
        studentMap.put(s1.rollNo, s1);
        studentMap.put(s2.rollNo, s2);
        studentMap.put(s3.rollNo, s3);

        // 5. Display All Students from ArrayList
        System.out.println("--- All Student Records (ArrayList) ---");
        for (Student s : studentList) {
            System.out.println(s);
        }

        // 6. Search Student from HashMap using Roll Number
        int searchRoll = 102;
        System.out.println("\n--- Searching Student with Roll No: " + searchRoll + " (HashMap) ---");
        if (studentMap.containsKey(searchRoll)) {
            System.out.println("Found: " + studentMap.get(searchRoll));
        } else {
            System.out.println("Student record not found.");
        }

        // 7. Remove a Student Record from ArrayList
        studentList.remove(s3); // Removing Kiran
        System.out.println("\n--- Updated Student Records after Deletion (ArrayList) ---");
        for (Student s : studentList) {
            System.out.println(s);
        }

        // 8. Display All Entries stored in HashMap
        System.out.println("\n--- All Entries in HashMap ---");
        for (Map.Entry<Integer, Student> entry : studentMap.entrySet()) {
            System.out.println("Key (Roll No): " + entry.getKey() + " => Value: " + entry.getValue());
        }
    }
}

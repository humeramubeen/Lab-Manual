import java.io.*;
import java.util.Scanner;

public class StudentFile {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String fileName = "students.txt";

        System.out.println("Enter Details of 3 Students\n");

        try (BufferedWriter bw = new BufferedWriter(new FileWriter(fileName))) {
            for (int i = 1; i <= 3; i++) {
                System.out.println("Student " + i);
                System.out.print("Roll No : ");
                String roll = scanner.nextLine();
                
                System.out.print("Name : ");
                String name = scanner.nextLine();
                
                System.out.print("Marks : ");
                String marks = scanner.nextLine();
                
                System.out.println();

                // Save record to file
                bw.write(roll + "," + name + "," + marks);
                bw.newLine();
            }
            System.out.println("Student records saved successfully.");
        } catch (IOException e) {
            System.out.println("Error writing to file: " + e.getMessage());
        }

        // Display saved records
        System.out.println("----- Student Records -----");
        try (BufferedReader br = new BufferedReader(new FileReader(fileName))) {
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.out.println("Error reading file: " + e.getMessage());
        }

        // Search for a student by Roll Number
        System.out.print("\nEnter Roll Number to Search : ");
        String searchRoll = scanner.nextLine().trim();
        System.out.println();

        boolean found = false;
        try (BufferedReader br = new BufferedReader(new FileReader(fileName))) {
            String line;
            while ((line = br.readLine()) != null) {
                String[] details = line.split(",");
                if (details[0].trim().equals(searchRoll)) {
                    System.out.println("Student Found\n");
                    System.out.println("Roll No : " + details[0]);
                    System.out.println("Name : " + details[1]);
                    System.out.println("Marks : " + details[2]);
                    found = true;
                    break;
                }
            }
            if (!found) {
                System.out.println("Student record not found.");
            }
        } catch (IOException e) {
            System.out.println("Error searching file: " + e.getMessage());
        }

        scanner.close();
    }
}

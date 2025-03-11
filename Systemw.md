import java.util.ArrayList;
import java.util.Scanner;

class Employee {
    String name;
    int id;
    double salary;

    Employee(int id, String name, double salary) {
        this.id = id;
        this.name = name;
        this.salary = salary;
    }

    public String toString() {
        return "ID: " + id + ", Name: " + name + ", Salary: $" + salary;
    }
}

public class EmployeeManager {
    public static void main(String[] args) {
        ArrayList<Employee> employees = new ArrayList<>();
        Scanner scanner = new Scanner(System.in);
        
        while (true) {
            System.out.println("1. Add Employee\n2. View Employees\n3. Exit");
            int choice = scanner.nextInt();
            
            if (choice == 1) {
                System.out.print("Enter ID: ");
                int id = scanner.nextInt();
                scanner.nextLine(); // Consume newline
                System.out.print("Enter Name: ");
                String name = scanner.nextLine();
                System.out.print("Enter Salary: ");
                double salary = scanner.nextDouble();
                employees.add(new Employee(id, name, salary));
            } else if (choice == 2) {
                employees.forEach(System.out::println);
            } else {
                break;
            }
        }
    }
}

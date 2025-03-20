[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/pAwhWXY5)
import java.util.*;
//ques1
class Employee {
    String name;
    int age;
    double salary;

    // Constructor
    public Employee(String name, int age, double salary) {
        this.name = name;
        this.age = age;
        this.salary = salary;
    }

    // Getter methods
    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }

    public double getSalary() {
        return salary;
    }

    // Override toString() to print employee details easily
    @Override
    public String toString() {
        return "Employee{name='" + name + "', age=" + age + ", salary=" + salary + "}";
    }
}

public class EmployeeSort {
    public static void main(String[] args) {
        // Create a list of Employee objects
        List<Employee> employees = new ArrayList<>();
        employees.add(new Employee("Alice", 30, 55000));
        employees.add(new Employee("Bob", 25, 60000));
        employees.add(new Employee("Charlie", 28, 45000));
        employees.add(new Employee("David", 35, 70000));

        // Sorting by name
        Collections.sort(employees, Comparator.comparing(Employee::getName));
        System.out.println("Sorted by Name:");
        employees.forEach(System.out::println);

        System.out.println();

        // Sorting by age
        Collections.sort(employees, Comparator.comparingInt(Employee::getAge));
        System.out.println("Sorted by Age:");
        employees.forEach(System.out::println);

        System.out.println();

        // Sorting by salary
        Collections.sort(employees, Comparator.comparingDouble(Employee::getSalary));
        System.out.println("Sorted by Salary:");
        employees.forEach(System.out::println);
    }
}

//ques2

import java.util.*;
import java.util.stream.*;

class Student {
    String name;
    double marks;

    // Constructor
    public Student(String name, double marks) {
        this.name = name;
        this.marks = marks;
    }

    // Getter methods
    public String getName() {
        return name;
    }

    public double getMarks() {
        return marks;
    }
}

public class StudentFilterSort {
    public static void main(String[] args) {
        // Create a list of Student objects
        List<Student> students = Arrays.asList(
            new Student("Alice", 85.5),
            new Student("Bob", 72.0),
            new Student("Charlie", 78.4),
            new Student("David", 90.0),
            new Student("Eva", 60.0)
        );

        // Using Lambda expressions and Stream API
        students.stream()
                .filter(s -> s.getMarks() > 75)           // Filter students with marks > 75%
                .sorted(Comparator.comparingDouble(Student::getMarks)) // Sort by marks
                .forEach(s -> System.out.println(s.getName()));  // Display student names
    }
}


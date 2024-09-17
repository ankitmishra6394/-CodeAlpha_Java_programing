# -CodeAlpha_Java_programing
codeAlpha internship in java programing
//Task 1.  Student Grade Tracker


import java.util.ArrayList;
import java.util.Collections;
import java.util.Scanner;

public class codeAlpha_intern {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ArrayList<Integer> grades = new ArrayList<>();

        System.out.println("Enter the number of students:");
        int numberOfStudents = scanner.nextInt();

        for (int i = 0; i < numberOfStudents; i++) {
            System.out.println("Enter grade for student " + (i + 1) + ":");
            int grade = scanner.nextInt();
            grades.add(grade);
        }

        int sum = 0;
        for (int grade : grades) {
            sum += grade;
        }

        double average = (double) sum / grades.size();
        int highest = Collections.max(grades);
        int lowest = Collections.min(grades);

        System.out.println("Average grade: " + average);
        System.out.println("Highest grade: " + highest);
        System.out.println("Lowest grade: " + lowest);
    }
}

Task 2 Banking application

import java.util.Scanner;

public class codeAlpha_intern {
    private static double balance = 0;

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        boolean exit = false;

        while (!exit) {
            System.out.println("Welcome to the Simple Banking Application");
            System.out.println("1. Deposit");
            System.out.println("2. Withdraw");
            System.out.println("3. Check Balance");
            System.out.println("4. Exit");
            System.out.print("Choose an option: ");
            int choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    deposit(scanner);
                    break;
                case 2:
                    withdraw(scanner);
                    break;
                case 3:
                    checkBalance();
                    break;
                case 4:
                    exit = true;
                    System.out.println("Thank you for using the Simple Banking Application. Goodbye!");
                    break;
                default:
                    System.out.println("Invalid option. Please try again.");
            }
        }
        scanner.close();
    }

    private static void deposit(Scanner scanner) {
        System.out.print("Enter amount to deposit: ");
        double amount = scanner.nextDouble();
        if (amount > 0) {
            balance += amount;
            System.out.println("Successfully deposited " + amount);
        } else {
            System.out.println("Invalid amount. Please enter a positive number.");
        }
    }

    private static void withdraw(Scanner scanner) {
        System.out.print("Enter amount to withdraw: ");
        double amount = scanner.nextDouble();
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            System.out.println("Successfully withdrew " + amount);
        } else {
            System.out.println("Invalid amount or insufficient balance.");
        }
    }

Task 3
import java.util.ArrayList;
import java.util.Scanner;

class Destination {
    String name;
    String date;
    String preferences;

    Destination(String name, String date, String preferences) {
        this.name = name;
        this.date = date;
        this.preferences = preferences;
    }
}

class Itinerary {
    ArrayList<Destination> destinations = new ArrayList<>();
    double budget;

    void addDestination(Destination destination) {
        destinations.add(destination);
    }

    void setBudget(double budget) {
        this.budget = budget;
    }

    void displayItinerary() {
        System.out.println("Travel Itinerary:");
        for (Destination destination : destinations) {
            System.out.println("Destination: " + destination.name);
            System.out.println("Date: " + destination.date);
            System.out.println("Preferences: " + destination.preferences);
            // Placeholder for map and weather information
            System.out.println("Map: [Map URL]");
            System.out.println("Weather: [Weather Info]");
            System.out.println();
        }
        System.out.println("Total Budget: " + budget);
    }
}

public class codeAlpha_intern {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Itinerary itinerary = new Itinerary();

        System.out.println("Enter your budget:");
        double budget = scanner.nextDouble();
        itinerary.setBudget(budget);

        boolean addMore = true;
        while (addMore) {
            System.out.println("Enter destination name:");
            String name = scanner.next();
            System.out.println("Enter travel date (YYYY-MM-DD):");
            String date = scanner.next();
            System.out.println("Enter your preferences:");
            String preferences = scanner.next();

            Destination destination = new Destination(name, date, preferences);
            itinerary.addDestination(destination);

            System.out.println("Do you want to add another destination? (yes/no)");
            String response = scanner.next();
            addMore = response.equalsIgnoreCase("yes");
        }

        itinerary.displayItinerary();
        scanner.close();
    }
}


    private static void checkBalance() {
        System.out.println("Your current balance is: " + balance);
    }
}


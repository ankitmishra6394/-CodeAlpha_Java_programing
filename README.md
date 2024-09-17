# -CodeAlpha_Java_programing
codeAlpha internship in java programing
//Task 1.  Student Grade Tracker
//Develop a program that allows a teacher to enter
//students' grades and compute their average,
//highest, and lowest scores. You can use arrays or
//ArrayLists to store the student data.

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

# quizzwizz-application-
Java Quiz Application - Description This is a simple console-based quiz application written in Java. It tests the user’s general knowledge by asking a series of multiple-choice questions and keeps track of their score.  Key Features:  Multiple Choice Questions: The quiz consists of 5 questions, each with four options labeled A, B, C, and D.  
import java.util.Scanner;

public class QuizApp {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Questions, options, and answers
        String[] questions = {
            "1. What is the capital of France?",
            "2. Who wrote 'Romeo and Juliet'?",
            "3. What is the largest planet in our Solar System?",
            "4. What language is primarily used for Android development?",
            "5. What is the result of 3 + 5 * 2?"
        };

        String[][] options = {
            {"A) Berlin", "B) Madrid", "C) Paris", "D) Rome"},
            {"A) Charles Dickens", "B) William Shakespeare", "C) Jane Austen", "D) Mark Twain"},
            {"A) Earth", "B) Mars", "C) Jupiter", "D) Venus"},
            {"A) Python", "B) Kotlin", "C) Swift", "D) Ruby"},
            {"A) 13", "B) 16", "C) 11", "D) 10"}
        };

        char[] answers = {'C', 'B', 'C', 'B', 'C'};
        int score = 0;

        System.out.println("📚 Welcome to the Java Quiz!");
        System.out.println("----------------------------");

        // Loop through questions
        for (int i = 0; i < questions.length; i++) {
            System.out.println("\n" + questions[i]);
            for (String option : options[i]) {
                System.out.println(option);
            }

            System.out.print("Your answer (A/B/C/D): ");
            char userAnswer = scanner.next().toUpperCase().charAt(0);

            if (userAnswer == answers[i]) {
                System.out.println("✅ Correct!");
                score++;
            } else {
                System.out.println("❌ Wrong! The correct answer was: " + answers[i]);
            }
        }

        System.out.println("\n🎉 Quiz Finished!");
        System.out.println("Your Score: " + score + " out of " + questions.length);

        scanner.close();
    }
}

import java.util.Random;
import java.util.Scanner;

public class ESPGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        String[] colors = {"Red", "Green", "Blue", "Orange", "Yellow"};

        System.out.print("Enter your name: ");
        String name = scanner.nextLine();

        System.out.print("Enter your MC M#: ");
        String mcMNumber = scanner.nextLine();

        System.out.print("Describe yourself: ");
        String description = scanner.nextLine();

        System.out.print("Due Date: ");
        String dueDate = scanner.nextLine();

        System.out.println("CMSC203 Assignment1: Test your ESP skills!");

        int correctGuesses = 0;

        for (int round = 1; round <= 11; round++) {
            System.out.println("\nRound " + round + "\nI am thinking of a color.");
            String selectedColor = colors[random.nextInt(colors.length)];
            System.out.print("Is it Red, Green, Blue, Orange, or Yellow?\nEnter your guess: ");
            String userGuess = scanner.nextLine();

            if (userGuess.equalsIgnoreCase(selectedColor)) {
                correctGuesses++;
                System.out.println("\nI was thinking of " + selectedColor + ".");
            } else {
                System.out.println("You entered incorrect color. Is it Red, Green, Blue, Orange, or Yellow?");
                do {
                    System.out.print("Enter your guess again: ");
                    userGuess = scanner.nextLine();
                } while (!userGuess.equalsIgnoreCase(selectedColor));
                correctGuesses++;
                System.out.println("\nI was thinking of " + selectedColor + ".");
            }
        }

        System.out.println("\nGame Over\n\nYou guessed " + correctGuesses + " out of 11 colors correctly.");
        System.out.println("Student Name: " + name);
        System.out.println("User Description: " + description);
        System.out.println("Due Date: " + dueDate);
    }
}

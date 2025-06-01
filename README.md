import java.util.Scanner;
import java.util.Random;

public class Number {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        int numberToGuess = random.nextInt(100) + 1;  // 1 to 100
        int maxAttempts = 10;
        int attempts = 0;
        boolean guessed = false;

        System.out.println("Guess the number between 1 and 100. You have " + maxAttempts + " attempts.");

        while (attempts < maxAttempts && !guessed) {
            System.out.print("Enter your guess: ");
            int guess = scanner.nextInt();
            attempts++;

            if (guess == numberToGuess) {
                System.out.println("Congrats! You guessed it in " + attempts + " attempts.");
                guessed = true;
            } else if (guess < numberToGuess) {
                System.out.println("Too low!");
            } else {
                System.out.println("Too high!");
            }
        }

        if (!guessed) {
            System.out.println("Sorry! You used all attempts. The number was " + numberToGuess);
        }

        scanner.close();
    }
}

# Number-Guessing-

package NumberGame;
import java.util.Random;
import java.util.Scanner;
public class Task1 {


	 
	    public static void main(String[] args) {
	        playGame();
	    }

	    public static void playGame() {
	        Scanner scanner = new Scanner(System.in);
	        Random random = new Random();
	        int score = 0;
	        int rounds = 0;

	        System.out.println("Welcome to the Guessing Game!");

	        while (true) {
	            int generatedNumber = random.nextInt(100) + 1;
	            int attempts = 0;
	            int guess;

	            System.out.println("\n===== New Round =====");

	            while (true) {
	                System.out.print("Guess the number between 1 and 100: ");
	                guess = scanner.nextInt();
	                attempts++;

	                if (guess == generatedNumber) {
	                    System.out.println("Congratulations! You guessed the correct number.");
	                    break;
	                } else if (guess < generatedNumber) {
	                    System.out.println("Too low! Try guessing a higher number.");
	                } else {
	                    System.out.println("Too high! Try guessing a lower number.");
	                }

	                if (attempts == 5) {
	                    System.out.println("Oops! You've reached the maximum number of attempts.");
	                    break;
	                }
	            }

	            score += attempts;
	            rounds++;

	            System.out.print("Do you want to play again? (yes/no): ");
	            String playAgain = scanner.next();

	            if (!playAgain.equalsIgnoreCase("yes")) {
	                System.out.println("Game over! Your total score is " + score + " based on " + rounds + " round(s).");
	                break;
	            }
	        }

	        scanner.close();
	    }
	}

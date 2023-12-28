import java.util.Scanner;

public class Main {
  public static void main(String[] args) {
    Scanner scanner = new Scanner(System.in);
    Hangman game = new Hangman();

    System.out.println("Welcome to Hangman!");
    while (!game.isGameOver()) {
      System.out.println("\nHere's what you have so far: " + game.getCurrentProgress());
      System.out.println("You have " + game.getRemainingGuesses() + " guesses left.");
      System.out.println("Here are the letters you've guessed so far: " + game.getGuessedLetters());
      System.out.println("Hangman: \n" + game.getHangmanGraphic());

      System.out.print("What letter would you like to guess next?");
      String guess = scanner.nextLine();
      game.makeGuess(guess);
  }

    if (game.isWin()) {
      System.out.println("\nCongratulations! You won, by guessing the word, " + game.getSecretWord() + " correctly!");
    } else {
      System.out.println("\nSorry, you've run out of guesses. The word was " + game.getSecretWord() + ".");
    }
  }  
 }

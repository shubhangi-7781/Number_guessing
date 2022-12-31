# Number_guessing
import java.util.Scanner;
import java.lang.Math;
import java.util.concurrent.ThreadLocalRandom;

public class Number_guessing {

        private static final int min_num = 1;
        private static final int max_num = 100;

        public static void main(String[] args) {
            Number_guessing game = new Number_guessing();
            game.Number_guessing();
        }


        public void Number_guessing() {
            boolean isUserGuessCorrect = false;
            int guessNum = 0;

            int computerNumber = getNumByComputer();


            while(!isUserGuessCorrect) {
                int userNumber = getUserGuessedNumber();
                if(userNumber > computerNumber) {
                    System.out.println("Try lower number");
                }else if(userNumber < computerNumber) {
                    System.out.println("Try higher number");
                }else if(userNumber == computerNumber) {
                    System.out.println("Congratulations! Your guess is correct!");
                    isUserGuessCorrect = true;
                }
                guessNum++;
            }
            System.out.println("You found the number in "+guessNum+" guesses");
        }


        public int getNumByComputer() {
            return ThreadLocalRandom.current().nextInt(min_num,max_num+1);
        }


        public int getUserGuessedNumber() {
            Scanner sn = new Scanner(System.in);
            System.out.println("Please guess the number: ");
            return sn.nextInt();
        }
    }


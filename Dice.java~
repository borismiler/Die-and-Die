import java.util.*;
import java.util.Random;

public class Dice
{
  public static void main (String [] args)
  {
    Random rand = new Random();
    Scanner myInput = new Scanner(System.in);
    
    int playerTotalScore = 0;
    int computerTotalScore = 0;
    
    int roundScore = 0;
    
    boolean computersTurn = false;
    String name; // user's name
     System.out.println("What is your name?");
     name = myInput.nextLine();
    
    String input = ""; //user's controlling input
     System.out.println("Commands:");
     System.out.println("I: Instructions");
     System.out.println("R: Roll");
     System.out.println("E: End starting turn");
     System.out.println("S: Score");
     System.out.println("Q: Quit");
     
     
     while (true){
       int playerFirstDie = rand.nextInt(6) + 1;
       int playerSecondDie = rand.nextInt(6) + 1;
       int playerStartValue = playerFirstDie + playerSecondDie;
       System.out.println(name + ", your rolls were a " + playerFirstDie + " and " + playerSecondDie);
       System.out.println("Your score is " + playerStartValue);
       
       int computerFirstDie = rand.nextInt(6) + 1;
       int computerSecondDie = rand.nextInt(6) + 1;
       int computerStartValue = computerFirstDie + computerSecondDie;
       System.out.println("The computer's rolls were a " + computerFirstDie + " and " + computerSecondDie);
       System.out.println("Their score is " + computerStartValue);
     
       
       if (playerStartValue > computerStartValue) //player's score is greater
       {
         System.out.println("Your score was greater.");
         break;
       }
       else if(playerStartValue < computerStartValue) //computer's score is greater
       {
         System.out.println("The computer's score was greater.");
         computersTurn = true;
        
         break;
       }
       else //scores are equal
       {
         System.out.println("Scores were equal. Reroll");
       }
       myInput.close;
     }
     

     int computerRoundScore = 0;
     while (true){
       // check to see the winner
       if (computerTotalScore >= 1000)
       {
         System.out.println("The computer won");
         break;
       }
       if (playerTotalScore >= 1000)
       {
         System.out.println(name + " won");
         break;
       }
       
       // if it's the computer's turn
       if (computersTurn)
       {
         System.out.println("Computer starts.");
       while (true){
       int firstDie = rand.nextInt(6) + 1;
       System.out.println("The computer's first roll was " + firstDie);
       int secondDie = rand.nextInt(6) + 1;
       System.out.println("The computer's second roll was " + secondDie);
       computerRoundScore += Roll(firstDie, secondDie);
       System.out.println("The computer's round score is " + computerRoundScore); 
       
       if (computerRoundScore > 40){
         System.out.println("The computer busted");
         playerTotalScore += computerRoundScore;
         System.out.println("Your total score is " + playerTotalScore);
         computerRoundScore = 0;
         roundScore = 0;
         computersTurn = false;
         break;
       }
       if (computerRoundScore == 40){
         System.out.println("The computer scored a perfect 40");
         computerTotalScore += 40*2;
         roundScore = 0;
         computerRoundScore = 0;
         computersTurn = true;
         continue;
       }
       // the starting round ending condition
       if (computerRoundScore > roundScore && computerRoundScore < 40){
         System.out.println("The computer ends their turn");
         System.out.println("Their round score is " + computerRoundScore);
         computersTurn = false;
         break;
       }
    }
       }
       
       System.out.println("Your turn");
       System.out.println("Please enter in a command");
       input = myInput.nextLine();
     
       if (input.equals("I"))
       {
         Instructions();
       }
       if (input.equals("R"))
     {
       int firstDie = rand.nextInt(6) + 1;
       System.out.println("Your first roll was " + firstDie);
       int secondDie = rand.nextInt(6) + 1;
       System.out.println("Your second roll was " + secondDie);
       roundScore += Roll(firstDie, secondDie);
       System.out.println("Your round score is " + roundScore);
       
       
       if (roundScore > 40){
         System.out.println("You busted");
         computerTotalScore += roundScore;
         System.out.println("The computer's total score is " + computerTotalScore);
         roundScore = 0;
         computerRoundScore = 0;
         computersTurn = true;
         continue;
       }
       if (roundScore == 40){
         System.out.println("You scored a perfect 40");
         playerTotalScore += 40*2;
         System.out.println("Your total score is " + playerTotalScore);
         System.out.println("New round");
         roundScore = 0;
         computerRoundScore = 0;
         computersTurn = false;
         continue;
       }
       if (roundScore > computerRoundScore && computerRoundScore != 0)
       {
         System.out.println(name + " ends their turn since their score is greater than the computer's score");
         computersTurn = true;
         continue;
       }
       System.out.println("Type R to roll again");
     }
       if (input.equals("E") && computerRoundScore == 0)
       {
         System.out.println(name + " ends their starting turn");
         computersTurn = true;
         continue;
       }
     if (input.equals("S"))
     {
       Score(computerTotalScore, playerTotalScore);
       System.out.println("Your round score is " + roundScore);
       System.out.println("The computer's round score is " + computerRoundScore);
     }
     if (input.equals("Q"))
     {
       System.exit(0);
     }
     }
    
  }
  
  public static void Instructions()
  {
    System.out.println("Object:  is to get a score as close to the score of 40 " + 
                       "without going over in each round");
    System.out.println("Each player roll 2 dice to determine who starts. Player with the highest roll goes first. " +
                       "High ties reroll.");
    System.out.println("Each score starts at 0, players roll both dice and the scores are added according to the following rules");
    System.out.println("- If doubles are rolled, score is double the result of multiplying the pips.");
    System.out.println("- If there is one or more even dice, score is result of multiplying pips.");
    System.out.println("- If both dice are odd, score is the result of multiplying the pips and subtracting the lower of the two.");
    System.out.println("Every turn, players role and identify their new score and can chose to role again if they wish");
    System.out.println("- If the player scores 40 exactly, the round ends and they earn 40 times the number of players " + 
                       "as points. Next round starts with the player on the left (clockwise).");
    System.out.println("The starting player in the round must roll once and may choose to stop at any time as long as there score is under 40.");
    System.out.println("- If a players score goes above 40, they bust and their score will be counted to be awarded to the winner of the round.");
    System.out.println("Once the starting player stops, play passes to the left and they roll until they get a score higher than the previous player and closer to 40 or bust.");
    System.out.println("Round ends when one player reaches exactly a score of 40 or everyone but one person busts. ");
    System.out.println("Winner of the round accumulates points at the end of the round by the sum of all the busted player scores or if they earn exactly 40, they earn 40 times the number of players in the game for the round.");
    System.out.println("First player who reaches 1000 points wins.");
  }
  public static int Roll(int firstDie, int secondDie)
  {
    if (firstDie == secondDie)
    {
      return 2*firstDie*secondDie;
    }
    
    if (firstDie % 2 == 0 || secondDie % 2 == 0)
    {
      return firstDie*secondDie;
    }
    else // both are odd
    {
      return firstDie*secondDie - Math.min(firstDie, secondDie);
    }
    
  }
  
  public static void Score (int computerScore, int playerScore)
  {
    
    System.out.println("Your total score is " + playerScore);
    System.out.println("The computer's total score is " + computerScore);

  }
}
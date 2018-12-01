# Savings-Account
This program calculates the balance of a savings account at the end of a period of time.

import java.util.Scanner;

public class SavingsAccount {
    public static void main (String [] args) {

     /*Declare variables for the starting balance, interest rate, and number of months. Also include a scanner class that
      will ask for user input for each.*/

        System.out.println("This program will calculate the balance of your savings account. It will take into account " +
                "deposits, withdrawals, and interest.");
        Scanner sc = new Scanner(System.in);

        System.out.println("Please enter your starting balance: ");
        double startingBalance= sc.nextDouble();

        System.out.println("What is your monthly interest rate? ");
        double monthlyInterestRate= sc.nextDouble();

        System.out.println("How many months has the account been opened for? ");
        int numOfMonths = sc.nextInt();

     //Declare variables for the monthly deposit, withdrawals, and interest, etc.

        double monthlyDeposit, monthlyWithdrawals, monthlyInterest;
        double accountBalance=startingBalance;
        int totalDeposits= 0;
        int totalWithdrawals= 0;
        double totalInterest= 0;

     //Open a for loop that will ask for amount deposited, withdrawn, and will calculate interest.
        for (int i=1;  i<= numOfMonths; i++) {

            //Ask for amount deposited and add it to the accountBalance.
            System.out.println("How much did you deposit this month?");
            monthlyDeposit = sc.nextDouble();
            accountBalance+=monthlyDeposit;
            totalDeposits+=monthlyDeposit;

            //Ask for amount withdrawn and subtract that from the accountBalance.
            System.out.println("How much did you withdraw this month?");
            monthlyWithdrawals = sc.nextDouble();
            accountBalance-=monthlyWithdrawals;
            totalWithdrawals+=monthlyWithdrawals;

            //Calculate the monthly interest.
            monthlyInterest = ((monthlyInterestRate/100) * accountBalance);
            accountBalance+=monthlyInterest;
            System.out.println("Your monthly interest is $" + monthlyInterest + " , bringing your total balance for this month" +
                    " to $" + accountBalance + "\n");
            totalInterest+=monthlyInterest;


        }
     //Print out the totalDeposits, totalWithdrawals, and totalInterest. And the final balance.
        System.out.println("The total amount of money deposited within the past " + numOfMonths + " months is $" +
                        totalDeposits + "\n" + "The total amount of money withdrawn within the past "+ numOfMonths+" months" +
                        " is $"+ totalWithdrawals +"\n"+"You have collected a total interest of $" + totalInterest +
                        " over the past "+ numOfMonths + " months.");
        System.out.println("Your current balance is $" + accountBalance);


    }

}

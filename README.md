# Java-ATM-Transaction
import java.util.Scanner;
class Main {
    int bal = 1000;
    void showBalance() {
        System.out.println("Balance: " + bal);
    }
    void credit(int amt) {
        bal = bal + amt;
        System.out.println("Amount Credited: " + amt);
    }
    void debit(int amt) {
        if (bal < amt) {
            System.out.println("Insufficient Funds");
        } else {
            bal = bal - amt;
            System.out.println("Amount Debited: " + amt);
        }
    }
    public static void main(String[] args) {
        Scanner A = new Scanner(System.in);
        Main m = new Main();
        int choice = 0;
        System.out.println("Welcome to Simple Banking System");
        while (true) {
            System.out.println("Enter Requirement: ");
            System.out.println("1 = Balance");
            System.out.println("2 = Withdraw");
            System.out.println("3 = Deposit");
            System.out.println("4 = Exit");
            choice = A.nextInt();
            if (choice == 1) {
                m.showBalance();
            } else if (choice == 2) {
                System.out.print("Enter Withdraw Amount: ");
                int amt = A.nextInt();
                m.debit(amt);
            } else if (choice == 3) {
                System.out.print("Enter Credit Amount: ");
                int amt = A.nextInt();
                m.credit(amt);
            } else if (choice == 4){
                System.out.println("Thank you! Exiting...");
                break;
            } else {
                System.out.println("Invalid Option. Try again.");
            }
            System.out.println("Would you like to continue? Press 0 to continue, any other number to exit.");
            int cont = A.nextInt();
            if (cont != 0) {
                System.out.println("Thank you! Exiting...");
                break;
            }
        }
    }
}

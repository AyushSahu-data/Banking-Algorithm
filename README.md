# Banking-Algorithm

public class BankingApplication {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		BankAccount obj1 = new BankAccount("Mr. Rustom","A785469");
		obj1.showMenu();

	}

}

Class BankingApplication used so as to use main  class inside to declare the Bank Accounts and show the relatoive menu.

  class BankAccount{
	int balance;
	int previousTransaction;
	String customerName;
	String customerId;
  
Declaring the variables.

  BankAccount(String cname, String cid){
		customerName = cname;
		customerId = cid;
	}
  
Constructor for class BankAccount.

  void deposit(int amount) {
		if(amount!=0) {
			balance += amount;
			previousTransaction = amount;
		}
	}
  
To deposit the amount and update balance in the account.

  void withdraw(int amount) {
		if(amount != 0) {
			balance -= amount;
			previousTransaction = -amount;
		}
	}
  
Displays withdrawn money and updates the balance left in the account.

  void getPreviousTransaction() {
		if(previousTransaction > 0) {
			System.out.println("Deposited: " +previousTransaction);
		}
		else if(previousTransaction < 0){
			System.out.println("Withdrawn: " +Math.abs(previousTransaction));
		}
		else {
			System.out.println("No transaction occurred");
		}
	}
  
Displays the details of the previous transaction.

  void showMenu() {
		char option = '\0';
		Scanner scanner = new Scanner(System.in);
		
		System.out.println("Welcome " +customerName);
		System.out.println("Your ID is " + customerId);
		System.out.println("\n");
		System.out.println("A. Check Balance");
		System.out.println("B. Deposit");
		System.out.println("C. Withdraw");
		System.out.println("D. Previous Transaction");
		System.out.println("E. Exit");
		
		do {
			System.out.println("----------------------------------------------------------------------------------------");
			System.out.println("Enter an option");
			System.out.println("----------------------------------------------------------------------------------------");
			option = scanner.next().charAt(0);
			System.out.println("\n");
			
			switch(option) {
			case 'A':
				System.out.println("---------------------------------------");
				System.out.println("Balance = " +balance);
				System.out.println("---------------------------------------");
				System.out.println("\n");
				break;
				
			case 'B':
				System.out.println("---------------------------------------");
				System.out.println("Enter an amount to deposit: ");
				System.out.println("---------------------------------------");
				int amount = scanner.nextInt();
				deposit(amount);
				System.out.println("\n");
				break;
				
			case 'C':
				System.out.println("---------------------------------------");
				System.out.println("Enter an amount to withdraw: ");
				System.out.println("---------------------------------------");
				int amount2 = scanner.nextInt();
				withdraw(amount2);
				System.out.println("\n");
				break;
				
			case 'D':
				System.out.println("---------------------------------------");
				getPreviousTransaction();
				System.out.println("---------------------------------------");
				System.out.println("\n");
				break;
				
			case 'E':
				System.out.println("********************************************");
				break;
				
			default:
				System.out.println("Invalid Option! Please enter again");
				break;
			}
		} while(option != 'E');
		
		System.out.println("Thank You for using our services");
	}
}

This is the main method to show options so as to what things we want the ATM to perform as per the given options. Also, if there is any error like we selected wrong option, the window closes and displays "Thank You" message,

Thank You!

# Bank-Account

package bankaccount;
import java.util.Scanner;

public class bankaccount {
	int acc_no;
	String name;
	float amount;
	
	void insert(int a, String n, float amt) {
		acc_no=a;
		name=n;
		amount=amt;
	}
	
	void deposit(float amt) {
		amount=amount+amt;
		System.out.println("Deposit: "+amt);
	}
	
	void withdraw(float amt) {
		if(amount<amt) {
			System.out.println("Amount is insufficient");
		}
		else
			amount=amount-amt;
		System.out.println("Withdraw is " + amount);
	}
	
	void checkbalance() {
		System.out.println("Balance is " + amount);
	}
	
	void display() {
		System.out.println("\n" +"Account Details: "+"\n" +"AccountNo: "+ acc_no + "\n" +"Account Name: " +name + "\n" +"Amount: " +amount);	
	}
	
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		
		bankaccount b1 = new bankaccount();
		System.out.println();
		System.out.println("=== National Bank of Bangladesh ===");
		System.out.println("-------------------------------");
		System.out.println("Enter Account_No: , Name and Amount");
		int a = sc.nextInt();
		sc.nextLine();
		String n = sc.nextLine();
		float amt = sc.nextFloat();
		b1.insert(a, n, amt);
		b1.display();
		
		b1.checkbalance();
		System.out.println();
		System.out.println("Enter amount for deposit");
		float d = sc.nextFloat();
		
		b1.deposit(d);
		b1.checkbalance();
		System.out.println();
		
		System.out.println("Enter amount for withdraw");
		float w = sc.nextFloat();
		b1.withdraw(w);
		b1.checkbalance();
		
	}

}

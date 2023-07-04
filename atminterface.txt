import java.util.Scanner;
class ATMINTERFACE
{
    public static void main(String args[] )
    {
        int balance = 100000;
        int withdraw=0,deposit,ch,transfer_amount=0,w=0,t=0;
        Scanner sc = new Scanner(System.in);
        while(true)
        {
            System.out.println("1. Transactions history");
            System.out.println("2. Withdraw");
            System.out.println("3. Deposit");
            System.out.println("4. Transfer");
            System.out.println("5. Quit");
            System.out.println("Choose an operation to perform:");
            ch=sc.nextInt();
            switch(ch)
             {            
                case 1:
                    {
                        System.out.println(" ATM TRANSACTION DETAILS RECORD ");
                        if(w==1){
                        System.out.println("Transaction: Cash Withdrawal");
                        System.out.println("Amount withdrawal: "+withdraw);
                        }
                        if(t==1){
                        System.out.println("Transaction: Cash Transfer");
                        System.out.println("Amount transferred: "+transfer_amount);
                        }
                        System.out.println("Current Balance.: "+balance);
                        System.out.println("Available Balance.: "+balance);
                        break;
                    }
                case 2:
                    {
                        System.out.println("Enter the amount to be withdrawn:");
                        withdraw = sc.nextInt();
                        if(balance >= withdraw)
                        {
                            balance = balance - withdraw;
                            System.out.println("Please collect your cash");
                            System.out.println("After withdrawl, available balance: "+balance);
                            w=1;
                        }
                        else
                        {
                            System.out.println("Insufficient Balance");
                        }
                        System.out.println("");
                        break;
                    }
                 
                case 3:
                    {
                        System.out.println("Enter the amount to be deposited:");
                        deposit = sc.nextInt();
                        balance = balance + deposit;
                        System.out.println("Amount rupees "+deposit+" has been deposited successfully");
                        System.out.println("After deposit, your account balance: "+balance);
                        System.out.println("");
                        break;
                    }
                case 4:
                    {
                        
                        System.out.println("Enter the amount to be transferred: \n");
                        transfer_amount=sc.nextInt();
                        if(transfer_amount > 0 && balance > transfer_amount)
                        {
                           
                            balance = balance-transfer_amount;
                            System.out.println("Amount rupees "+ transfer_amount +" transferred successfully");
                            System.out.println("After transaction, your account balance: "+balance);
                            t=1;
                        }
                        else
                        System.out.println("your current balance is low\n");
                        break;
                    }
                case 5:
                System.exit(0);
            }
        }
    }
}
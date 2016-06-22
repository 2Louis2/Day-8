# Day-8

import java.text.DecimalFormat;

import javax.swing.JOptionPane;


public class Program7 {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
        String hours;
        String rate;
        
        int workHours;
        int overHours;
        int doubleHours;
        
        double payRate;
        double overRate;
        double doubleOver;
        
        double payCheck;
        double overCheck;
        double doubleCheck;
        
        hours = JOptionPane.showInputDialog("How many hours did you work this week?");
        workHours = Integer.parseInt(hours);
        
        rate = JOptionPane.showInputDialog("What is the normal hourly rate of pay?");
        payRate = Double.parseDouble(rate);
        
        overHours = workHours - 40;
        doubleHours = workHours - 80;
        
        overRate = payRate * 1.5;
        doubleOver = payRate * 2;
        
        payCheck = workHours * payRate;
        overCheck = (workHours * payRate) + (overHours * overRate) ;
        doubleCheck = (workHours * payRate) + (overHours * overRate) + (doubleHours * doubleOver);
        
        DecimalFormat fmt = new DecimalFormat ("0.##");
        
        System.out.println("Number of hours worked: " + workHours);
        System.out.println("Normal hourly rate of pay: $" + fmt.format(payRate) );
        
        System.out.println("");
        
        if ( workHours <= 40)
        {
            System.out.println("For this week, you worked " + workHours + " hours at $" + payRate + " per hour and were paid $" + fmt.format(payCheck) + " before taxes.");
        }
            else if ( workHours <= 80)
            {
                System.out.println("For this week, you worked overtime for " + workHours + " hours. The first 40 hours were for $" + payRate + " per hour and the rest for $" + overRate + " per hour. You were paid $" + fmt.format(overCheck) + " before taxes.");
            }
                else
                {
                    System.out.println("For this week, you worked double time for " + workHours + " hours. The first 40 hours were for $" + payRate + " per hour and the next 40 hours after those were for $" + overRate + " per hour. You were then payed $" + doubleOver + " per hour for the rest of your time. You were paid $" + fmt.format(doubleCheck) + " before taxes.");
                }
	}

}

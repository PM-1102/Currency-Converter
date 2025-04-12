# Currency-Converter
import java.util.Scanner;

public class CurrencyConverter {


    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Currency Converter");
        System.out.println("Supported currencies: USD, INR, EUR");

        System.out.print("Enter source currency (e.g. USD): ");
        String fromCurrency = scanner.next().toUpperCase();

        System.out.print("Enter target currency (e.g. INR): ");
        String toCurrency = scanner.next().toUpperCase();

        System.out.print("Enter amount: ");
        double amount = scanner.nextDouble();

        double convertedAmount = convertCurrency(fromCurrency, toCurrency, amount);

        if (convertedAmount == -1) {
            System.out.println("Unsupported currency or conversion.");
        } else {
            System.out.printf("%.2f %s = %.2f %s\n", amount, fromCurrency, convertedAmount, toCurrency);
        }

        scanner.close();
    }

    public static double convertCurrency(String from, String to, double amount) {
        if (from.equals("USD") && to.equals("INR")) {
            return amount * 83.2;
        } else if (from.equals("INR") && to.equals("USD")) {
            return amount / 83.2;
        } else if (from.equals("EUR") && to.equals("INR")) {
            return amount * 90.5;
        } else if (from.equals("INR") && to.equals("EUR")) {
            return amount / 90.5;
        } else if (from.equals("USD") && to.equals("EUR")) {
            return amount * 0.92;
        } else if (from.equals("EUR") && to.equals("USD")) {
            return amount * 1.09;
        } else if (from.equals(to)) {
            return amount; 
        } else {
            return -1;
        }
    }
}

#Output
Currency Converter
Supported currencies: USD, INR, EUR
Enter source currency (e.g. USD): inr
Enter target currency (e.g. INR): usd
Enter amount: 100
100.00 INR = 1.20 USD


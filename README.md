# MiniProject-JAVA

import java.util.*;

public class MiniProject {

    // Function to check repeated digits
    static boolean hasRepeatedDigits(int num) {
        boolean[] digit = new boolean[10];

        while (num > 0) {
            int d = num % 10;

            if (digit[d]) {
                return true;
            }

            digit[d] = true;
            num = num / 10;
        }
        return false;
    }

    // Fibonacci series
    static void fibonacci(int n) {
        int a = 0, b = 1;
        System.out.print("Fibonacci: ");
        for (int i = 0; i < n; i++) {
            System.out.print(a + " ");
            int c = a + b;
            a = b;
            b = c;
        }
        System.out.println();
    }

    // Prime check
    static boolean isPrime(int n) {
        if (n <= 1) return false;
        for (int i = 2; i <= n/2; i++) {
            if (n % i == 0)
                return false;
        }
        return true;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("1. Fibonacci Series");
        System.out.println("2. Prime Numbers in Range");
        System.out.println("3. Count Non-Repeated Digit Numbers");
        System.out.print("Enter choice: ");
        int choice = sc.nextInt();

        switch (choice) {

            case 1:
                System.out.print("Enter n: ");
                int n = sc.nextInt();
                fibonacci(n);
                break;

            case 2:
                System.out.print("Enter range: ");
                int a = sc.nextInt();
                int b = sc.nextInt();

                System.out.print("Primes: ");
                for (int i = a; i <= b; i++) {
                    if (isPrime(i)) {
                        System.out.print(i + " ");
                    }
                }
                break;

            case 3:
                System.out.print("Enter range: ");
                int x = sc.nextInt();
                int y = sc.nextInt();
                int count = 0;

                for (int i = x; i <= y; i++) {
                    if (!hasRepeatedDigits(i)) {
                        count++;
                    }
                }

                System.out.println("Count: " + count);
                break;

            default:
                System.out.println("Invalid choice");
        }
    }
}

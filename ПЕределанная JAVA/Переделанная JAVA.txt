import java.util.Scanner;

public class Main
{
    public static long fact(int num) {
        long res = 1;

        for (int i = 2; i <= num; i++) {
            res *= i;
        }

        return res;
    }
    
	public static void main(String args[]) {
        Scanner input = new Scanner(System.in);
        long ans;
        int N;
        int score = 0;
        
        for (int i = 1; i <= 10; i++) {
            System.out.print("Введите число: ");
            N = input.nextInt();
            for (int j = 0; j < 5; j++) {
                System.out.println("Введите правильный ответ (осталось " + (5 - j) + " попыток): ");
                System.out.print(N + "! = ");
                ans = input.nextLong();
                if (ans == fact(N)) {
                    System.out.println("Верно!");
                    score++;
                    break;
                } else {
                    System.out.println("Неверно!");
                }
            }
        }
        
        if (score == 10) {
            System.out.println("Оценка: Отлично");
        } else if (score == 9) {
            System.out.println("Оценка: Хорошо");
        } else if (score == 8) {
            System.out.println("Оценка: Удовл");
        } else {
            System.out.println("Оценка: Неуд");
        }
    }
}

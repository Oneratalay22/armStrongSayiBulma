import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.println("Sayı giriniz:");
        int number = input.nextInt();

        if (number > 99 &&  number < 1000) {
        }else{
            System.out.println("Lütfen 3 basamaklı sayı giriniz!:");
            return;
        }

        int basNumber = 0;
        int tempNumber = number;
        int basValue;
        int result = 0;
        int basPow;

        // Basamak sayısını bulma
        while (tempNumber != 0) {
            tempNumber /= 10;
            basNumber++;
        }

        tempNumber = number;

        // Armstrong sayısını kontrol etme
        while (tempNumber != 0) {
            basValue = tempNumber % 10;
            basPow = 1;
            for (int i = 1; i <= basNumber; i++) {
                basPow *= basValue;
            }
            result += basPow;
            tempNumber /= 10;
        }

        if (result == number) {
            System.out.println(number + " sayısı bir Armstrong sayıdır");
        } else {
            System.out.println(number + " sayısı bir Armstrong sayısı değildir");
        }
    }
}

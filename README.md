# InverseWord

#### Introduction to Progamming
#### Repetition and Jump Operation (OL) #3

```java
package id.bagaswirapradana.i2p;

import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        // scanner declaration
        Scanner input = new Scanner(System.in);

        // Asking user to input a word or words
        System.out.print("Masukan Kalimat: ");
        if (!input.hasNextLine()) {
            System.out.println("Kesalahan pada input, silahkan coba lagi lain waktu. ");
            input.close();
            return;
        }

        String words = input.nextLine();
        // check if word or words is anagram
        // Print result
        System.out.println((CheckAnagram(words) ? "COOL" : "BAD"));
        input.close();
    }

    private static boolean CheckAnagram(String words) {
        // temp variable for reverse words
        String reversedWords = "";

        // Loop from the last char of words to the first
        for (int i = words.length() - 1; i >= 0; i--) {
            reversedWords = String.format("%s%s", reversedWords, words.charAt(i));
        }

        // return if words is anagram or not
        return words.equals(reversedWords);
    }
}

```
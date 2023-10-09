# Paragram-Checker
.Check if the input is panagram or not. (Panagram is a sentence that contains all the alphabets from a-z)
public class ParagramChecker {
    public static boolean isPangram(String str) {
        
        // Create an array to keep track of alphabet occurrences
        boolean[] alphabetOccurrence = new boolean[26];

        // Convert the input string to lowercase for case-insensitive checking
        str = str.toLowerCase();

        // Iterate through the characters in the input string
        for (int i = 0; i < str.length(); i++) {
            char ch = str.charAt(i);

            // Check if the character is an English alphabet (a-z)
            if (ch >= 'a' && ch <= 'z') {
                // Set the corresponding index in the array to true
                alphabetOccurrence[ch - 'a'] = true;
            }
        }

        // Check if all alphabet occurrences are true (i.e., all alphabets are present)
        for (boolean b : alphabetOccurrence) {
            if (!b) {
                return false;
            }
        }

        return true;
    }

    public static void main(String[] args) {
        String input = "The quick brown fox jumps over the lazy dog";
        boolean result = isPangram(input);

        if (result) {
            System.out.println("The input is a pangram.");
        } else {
            System.out.println("The input is not a pangram.");
        }
    }
}

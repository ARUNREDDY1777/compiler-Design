#include <stdio.h>
#include <ctype.h>
#include <string.h>

int main() {
    char ch;
    int charCount = 0, wordCount = 0, lineCount = 0;
    int inWord = 0;
    char input[1000];  // Buffer to store input

    printf("Enter text (enter '-1' to end):\n");

    while (1) {
        // Read input as a string
        fgets(input, sizeof(input), stdin);

        // Check if the input is '-1', indicating end of input
        if (strcmp(input, "-1\n") == 0 || strcmp(input, "-1") == 0) {
            break;
        }

        // Iterate through each character in the input string
        for (int i = 0; input[i] != '\0'; i++) {
            ch = input[i];
            charCount++;

            // Check for newline to count lines
            if (ch == '\n') {
                lineCount++;
            }

            // Check for spaces and other whitespace characters to determine words
            if (isspace(ch)) {
                inWord = 0;
            } else if (!inWord) {
                inWord = 1;
                wordCount++;
            }
        }
    }

    // To account for the last line if it doesn't end with a newline
    if (charCount > 0 && input[strlen(input) - 1] != '\n') {
        lineCount++;
    }

    // Output the final counts
    printf("Characters: %d\n", charCount);
    printf("Words: %d\n", wordCount);
    printf("Lines: %d\n", lineCount);

    return 0;
}

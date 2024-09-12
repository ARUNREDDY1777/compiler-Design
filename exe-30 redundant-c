#include <stdio.h>
#include <string.h>
char *input;  
int i = 0;    
char output[100];  
int j = 0;    
void skipWhitespaceAndSingleLineComments() {
    while (input[i] == ' ' || input[i] == '\t' || input[i] == '\n' || input[i] == '\r') {
        i++;
    }
    if (input[i] == '/' && input[i + 1] == '/') {
        i += 2;
        while (input[i] != '\n' && input[i] != '\0') i++;  
        skipWhitespaceAndSingleLineComments(); 
    }
}
void skipMultiLineComments() {
    if (input[i] == '/' && input[i + 1] == '*') {
        i += 2;
        while (!(input[i] == '*' && input[i + 1] == '/') && input[i] != '\0') i++; 
        if (input[i] == '*' && input[i + 1] == '/') i += 2; 
        skipWhitespaceAndSingleLineComments(); 
    }
}
void processInput() {
    skipWhitespaceAndSingleLineComments();
    skipMultiLineComments();
    while (input[i] != '\0') {
        skipWhitespaceAndSingleLineComments();
        skipMultiLineComments();
        if (input[i] == '/' && input[i + 1] == '*') {
            skipMultiLineComments();
        } else if (input[i] == '/' && input[i + 1] == '/') {
            skipWhitespaceAndSingleLineComments();
        } else {
            if (input[i] != '\0') {
                output[j++] = input[i++];
            }
        }
    }
    output[j] = '\0';  
}
int main() {
    char inputString[100];  
    printf("Enter an expression: ");
    fgets(inputString, 100, stdin); 
    input = inputString; 
    i = 0;  
    j = 0;  
    processInput();
    printf("Cleaned expression: %s\n", output); 
    return 0;
}

#include <stdio.h>
#include <string.h>

char *input;
int i = 0;
int E();
int T();
int F();
int match(char c) {
    if (input[i] == c) {
        i++;
        return 1;
    }
    return 0;
}
int E() {
    if (T()) {
        while (match('+')) {
            if (!T()) return 0;
        }
        return 1;
    }
    return 0;
}
int T() {
    if (F()) {
        while (match('*')) {
            if (!F()) return 0;
        }
        return 1;
    }
    return 0;
}
int F() {
    return (match('a') || match('b'));
}
int main() {
    char inputString[100];  
    printf("Enter an expression: ");
    scanf("%s", inputString); 
    input = inputString;  
    i = 0;  
    if (E() && i == strlen(input)) {
        printf("Parsing successful!\n");
    } else {
        printf("Parsing failed!\n");
    }
    return 0;
}

#include <stdio.h>
#include <string.h>
void checkComment(char line[]) {
    int length = strlen(line);
    if (length >= 2 && line[0] == '/' && line[1] == '/') {
        printf("This is a single-line comment.\n");
        return;
    }
    if (length >= 4 && line[0] == '/' && line[1] == '*') {
        char *endComment = strstr(line, "*/");
        if (endComment != NULL) {
            printf("This is a multi-line comment.\n");
        } else {
            printf("This is an unclosed multi-line comment.\n");
        }
        return;
    }
    printf("This is not a comment.\n");
}
int main() {
    char input[1000];
    printf("Enter a line of code: ");
    fgets(input, sizeof(input), stdin);
    input[strcspn(input, "\n")] = '\0';
    checkComment(input);
    return 0;
}

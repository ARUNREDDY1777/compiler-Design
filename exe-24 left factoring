#include <stdio.h>
#include <string.h>
int main() {
    char p[20], part1[20], part2[20], modifiedp[20], newp[20];
    int i, j = 0, k = 0, l = 0, pos;
    printf("Enter Production: ");
    scanf("%s",p);
    char n = p[0];
    for (i = 3; p[i] != '|'; i++, j++) {
        part1[j] = p[i];
    }
    part1[j] = '\0';
    for (j = ++i, i = 0; p[j] != '\0'; j++, i++) {
        part2[i] = p[j];
    }
    part2[i] = '\0';
    int foundCommonPrefix = 0;
    for (i = 0; i < strlen(part1) && i < strlen(part2); i++) {
        if (part1[i] == part2[i]) {
            modifiedp[k] = part1[i];
            k++;
            pos = i + 1;
            foundCommonPrefix = 1;
        } else {
            break;
        }
    }
    if (foundCommonPrefix) {
        modifiedp[k] = '\0';
       if (strlen(part1) > pos) {
        for (i = pos, j = 0; part1[i] != '\0'; i++, j++) {
            newp[j] = part1[i];
        }
    }else {
            newp[0] = 'e'; 
            newp[1] = '\0';
        }
        j=2;
        newp[j++] = '|';
        for (i = pos; part2[i] != '\0'; i++, j++) {
            newp[j] = part2[i];
        }
        newp[j]= '\0';
        printf("\nGrammar Without Left Factoring:\n");
        printf(" %c->%s%c'\n", n, modifiedp, n);
        printf(" %c'->%s\n", n, newp);
    } else {
        printf("No common prefix found. it can't factored.\n");
}
    return 0;
}

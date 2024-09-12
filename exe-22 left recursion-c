#include <stdio.h>
#include <string.h>
#define SIZE 10
int main() {
    char non_terminal, beta, alpha,production[10][SIZE], left_recursive[10][SIZE]; 
    int left_recursive_count = 0,index = 3;
    printf("Enter the grammar:\n");    
	for (int i = 0; i < 1; i++) {
        scanf("%s", production[i]);
    }
    for (int i = 0; i < 1; i++) {
        printf("\nGRAMMAR : %s", production[i]);
        non_terminal = production[i][0];
        if (non_terminal == production[i][index]) {
            alpha = production[i][index + 1];
            printf(" is left recursive.\n");
            while (production[i][index] != 0 && production[i][index] != '|') {
                index++;
            }
            if (production[i][index] != 0) {
                beta = production[i][index + 1];
                printf("Grammar without left recursion:\n");
                printf("%c->%c%c\'", non_terminal, beta, non_terminal);
                printf("\n%c\'->%c%c%c\'|Epi\n", non_terminal , alpha,beta, non_terminal);
                sprintf(left_recursive[left_recursive_count], "%c->%c%c\'\n%c\'->%c%c\'|Epi\n", non_terminal, beta, non_terminal, non_terminal, alpha, non_terminal);
                left_recursive_count++;
            } 
        } else {
            printf(" is not left recursive.\n");
        }
        index = 3;
    }
    for (int i = 0; i < left_recursive_count - 1; i++) {
        for (int j = i + 1; j < left_recursive_count; j++) {
            if (strcmp(left_recursive[i], left_recursive[j]) > 0) {
                char temp[SIZE];
                strcpy(temp, left_recursive[i]);
                strcpy(left_recursive[i], left_recursive[j]);
                strcpy(left_recursive[j], temp);
            }
        }
    }
    return 0;
}

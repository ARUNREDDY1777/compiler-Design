#include <stdio.h>
#include <string.h>
#include <ctype.h>
#include <stdlib.h>

int tempVarCount = 0;

char* newTemp() {
    // Create a new temporary variable name like t0, t1, etc.
    char* temp = (char*)malloc(5);  // Allocate memory for temp variable name
    sprintf(temp, "t%d", tempVarCount++); // Store t0, t1,... in temp
    return temp;
}

void generateTAC(char* left, char op, char* right, char* result) {
    // Generate three-address code in the form: result = left op right
    printf("%s = %s %c %s\n", result, left, op, right);
}

char* parseExpression(char* expr, int start, int end) {
    int i, lastOp = -1, opPosition = -1, parentheses = 0;

    // Find the operator of lowest precedence outside any parentheses
    for (i = start; i <= end; i++) {
        if (expr[i] == '(') {
            parentheses++;
        } else if (expr[i] == ')') {
            parentheses--;
        } else if (parentheses == 0 && (expr[i] == '+' || expr[i] == '-')) {
            lastOp = i;
        } else if (parentheses == 0 && (expr[i] == '*' || expr[i] == '/') && lastOp == -1) {
            opPosition = i;
        }
    }

    if (lastOp == -1) {
        lastOp = opPosition;
    }

    if (lastOp == -1) {
        // If there is no operator, check if it’s an expression enclosed in parentheses
        if (expr[start] == '(' && expr[end] == ')') {
            return parseExpression(expr, start + 1, end - 1);
        } else {
            // If it's a single operand, return it as a string
            char* operand = (char*)malloc(2); 
            operand[0] = expr[start];
            operand[1] = '\0';
            return operand;
        }
    }

    // Parse the left and right parts of the expression
    char* left = parseExpression(expr, start, lastOp - 1);
    char* right = parseExpression(expr, lastOp + 1, end);
    char op = expr[lastOp];

    // Generate a new temporary variable and generate TAC
    char* result = newTemp();
    generateTAC(left, op, right, result);

    return result;
}

int main() {
    char expr[100];

    printf("Enter an arithmetic expression: ");
    scanf("%s", expr);

    int len = strlen(expr);
    parseExpression(expr, 0, len - 1);

    return 0;
}

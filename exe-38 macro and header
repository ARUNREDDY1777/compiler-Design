%{
#include <stdio.h>

int macro_count = 0;
int include_count = 0;
%}

%%
#include[ \t]*<[^>]+>   { include_count++; }
#define[ \t]+[a-zA-Z_][a-zA-Z0-9_]*   { macro_count++; }
.|\n                 { /* ignore other characters */ }
%%
int yywrap(){}
int main() {
    yylex();
    printf("Number of macros defined: %d\n", macro_count);
    printf("Number of header files included: %d\n", include_count);
    return 0;
}

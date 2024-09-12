%{
#include<stdio.h>
int n=0;
%}

%%
"/*"([^*]|[\r\n]|(\*+([^*/]|[\r\n])))*\*+"/" {n++;}
"//".* {n++;}
%%

int yywrap()
{}

int main()
{
yyin=fopen("commentline.txt","r");
yylex();
printf("Number of comment lines: %d", n);
return 0;
} 

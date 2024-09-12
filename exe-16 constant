%{
%}
%%
[0-9]+|[0-9]*\.[0-9]+ {printf(" \nthe constant is:%s", yytext);}
%%
int yywrap(){}
int main()
{
printf("\nEnter input:\n");
yylex();
return 0;
}

%{
%}
%%
\+ printf("(plus)");
\- printf("(Minus)");
\* printf("(star)");
\/ printf("(divide)");
. printf("%s",yytext);
%%
int yywrap(void) {}
int main()
{
	printf("Enter the Operation Statement:");
	yylex();
	return 0;
}

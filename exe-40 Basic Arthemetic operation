%{
	#include <stdio.h>
	#include <stdlib.h>
	int op1=0,op2=0;
	char op;
%}
%%
[0-9]+  {if(op1!=0){op2=atoi(yytext);} else {op1=atoi(yytext);}}
("+"|"-"|"*"|"/") {op=yytext[0];}
\n    {
	      switch(op)
	      {
	      	case '+':printf("Result=%d\n",op1+op2);break;
	      	case '-':printf("Result=%d\n",op1-op2);break;
	      	case '*':printf("Result=%d\n",op1*op2);break;
	      	case '/':
			  printf("Result=%d\n",op1/op2);
			  break;
		  }
		  op1=op2=0;
    }	
%%
int yywrap(void){}
int main()
{
	printf("Enter the Expression:");
	yylex();
	return 0;
}

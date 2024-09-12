%{
int lcount=0;
int wcount=0;
int chcount=0;
%}
%% 
\n {lcount++;}
[a-zA-Z]+ {wcount++;chcount+=yyleng;}

%%
int yywrap(){}
int main()
{
printf("\nEnter input:");
yylex();
printf("\nNo.of lines:%d\n",lcount);
printf("\nNo.of characters:%d\n",chcount);
printf("\nNo.of words:%d\n",wcount);
return 0;
}

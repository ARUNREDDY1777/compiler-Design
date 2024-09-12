%{
int html=0;
%}
%%
"<"[^>]*> {printf("%s\n",yytext);}
. ;
%%
int yywrap(){}
int main()
{
yyin=fopen("htmlcode.txt","r");
yylex();
return 0;
}

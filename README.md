# numbercheck
# c program
# Let's use the preprocessor to take a number as input, find out who is large and odd, and take a letter and check lowercase and uppercase letters! 전처리기를 사용해서 숫자를 입력받아 누가 큰지 홀수인지와 문자를 입력받아 소문자, 대문자를 확인해보자!
#include <stdio.h>
#include <ctype.h> 
#define RANGE(x,y,z) ((x<y)||(x>z)?0:1)
#define ODD_GT(x,y) (((x%2)==1)&&(x>y)?1:0)
#define IS_UPPER(c) isupper(c)
int main(void){
    int num1,num2,num3;
    int cnum1,cnum2;
    char c;
    printf("세개의 정수 입력(x,y,z):");
    scanf("%d %d %d",&num1,&num2,&num3);
    printf("두개의 정수 입력:");
    scanf("%d %d",&cnum1,&cnum2);
    rewind(stdin);
    printf("문자를 입력:");
    c=getchar();
    if(!RANGE(num1,num2,num3))
       printf("x는 y보다 작거나 z보다 크다. ");
    else
	   printf("x는 y보다 크거나 z보다 작다. ");
	if(ODD_GT(cnum1,cnum2))
	   printf("x는 홀수이거나  y보다크지않다. ");
    else
	   printf("x는 짝수이고 y보다 크지 않다! ");
	if(IS_UPPER(c)) 
	   printf("c는 대문자다! ");
	else
	   printf("c는 소문자다! ");
    return 0;
}
#input--> 3 4 5  13 22  c
#result--> x는y보다 작거나 z보다 크다. x는 짝수이고 y보다 크지 않다! c는 소문자다!

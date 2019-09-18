##控制语句  
###**2.1 求1到N的整数的总和**  
    ####**代码**  
~~~  
#include <stdio.h>  
 
main(){
int intN, intCounter, flag;
unsigned long int uLngSum;
char ch;

do{
  do{
  flag=0;
  printf("Enter a number ( 0 < N < 30000):");
  scanf("%d",&intN);
  if ((intN<=0)||(intN>30000))
    flag=1;
    }while(flag);
    
    uLngSum=0;
    
    for(intCounter=1; intCounter<=intN; intCounter++){
    ulngSum= ulngSun + intCounter;
    }
    
    printf("Required sum is %lu\n", uLngSum);
    printf("Do you want to continue ? (Y/N):");
    scanf("%c",ch);
    
  }while((ch=='y')||(ch=='Y'));
  
  printf("Thank you. \n");
  return (0);
}
~~~

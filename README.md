# CHAPTER6

6-1
#include <stdio.h>
#include<math.h>
int main(void) {
  double X1, Y1, X2, Y2, CORDX, CORDY, DISTANCE ;

  printf("ENTER YOUR x,y COMPONENTS FOR THE 1ST POINT\n");
  scanf("%lf %lf", &X1, &Y1);
  printf("ENTER YOUR x,y COMPONENTS FOR THE 2ND POINT\n");
  scanf("%lf %lf", &X2, &Y2);
  CORDX = (Y2-Y1)*(Y2-Y1);
  CORDY = (X2-X1)*(X2-X1);
DISTANCE = sqrt(CORDX+CORDY);
printf("THE DISTANCE BETWEEN THE POINTS IS: %lf", DISTANCE);


  return 0;
}


6-2
#include <stdio.h>

int main(void) {
  int PERC;
  printf("\n   %%     GRADE\n\n0  - 60    F\n61 - 70    D\n71 - 80    C\n81 - 90    B\n91 - 100   A");
  printf("\n\nENTER THE %% GRADE\n");
  scanf("%d", &PERC); 

  if(PERC>=0&&PERC<61)
  printf("\nTHE LETTER GRADE IS: F");
  else if(PERC>60&&PERC<71)
  printf("\nTHE LETTER GRADE IS: D");
 else if(PERC>70&&PERC<81)
  printf("\nTHE LETTER GRADE IS: C");
   else if(PERC>80&&PERC<91)
  printf("\nTHE LETTER GRADE IS: B");
   else if(PERC>90&&PERC<101)
  printf("\nTHE LETTER GRADE IS: A");

  return 0;
}


6-3
#include <stdio.h>

int main(void) {

  int PERC, MO;
  char MOD;

  printf("\n   %%     GRADE\n\n0  - 60    F\n61 - 70    D\n71 - 80    C\n81 - 90    B\n91 - 100   A");
  printf("\n\nENTER THE %% GRADE\n");
  scanf("%d", &PERC); 

  if(PERC==100)
  MOD='+'; 
  else
  {
  MO=PERC%10;
  if(MO<4&&MO>0)
  MOD='-';
  else if(MO>3&&MO<8)
  MOD=' ';
  else if(MO>7&&MO<10)
  MOD='+';
  else if(MO==0)
  MOD='+';
  }


  if(PERC>=0&&PERC<61)
  printf("\nTHE LETTER GRADE IS: F" );
  else if(PERC>60&&PERC<71)
  printf("\nTHE LETTER GRADE IS: D%c", MOD );
 else if(PERC>70&&PERC<81)
  printf("\nTHE LETTER GRADE IS: C%c", MOD );
   else if(PERC>80&&PERC<91)
  printf("\nTHE LETTER GRADE IS: B%c", MOD );
   else if(PERC>90&&PERC<101)
  printf("\nTHE LETTER GRADE IS: A%c", MOD );



  return 0;

}


6-4
#include <stdio.h>
//PROGRAMM TO CONVERT MONEY IN CHANGE. 
//20, 50, 10, 5, 2 y 1 pesos
int main(void) {
  int M;
  int V, CT, Z, CN, D, U;

  V=0;
  CT=0;
  Z=0;
  CN=0;
  D=0;
  U=0;
  printf("ENTER MONEY\n");
  scanf("%d", &M);

while(M>=50)
{
M=M-50;
CT=CT+1;
}
while(M>=20)
{
M=M-20;
V=V+1;

}
while(M>=10)
{
M=M-10;
Z=Z+1;
}

while(M>=5)
{
M=M-5;
CN=CN+1;
}

while(M>=2)
{
M=M-2;
D=D+1;
}
//THE U IS $1, WHICH IS M BECAUSE IS WHAT LEFT OF THE PREVIOUS CHANGES.
U=M;

printf("$50: %d\n$20: %d\n$10: %d\n$5:  %d\n$2:  %d\n$1:  %d", CT, V, Z, CN, D, U);

  return 0;
}


6-5
#include <stdio.h>
//LEAP YEAR DIVISIBLE BY 4 AND 400, BUT NOT BY 100.
int main(void) {
  int Y, d4, d100, d400;
  printf("INSERT THE YEAR\n");
  scanf("%d", &Y );
  d4=Y%4;
  d100=Y%100;
  d400=Y%400;


  if(d4==0&&d400==0&&d100==0)
  {
  printf("IT IS A LEAP YEAR");
  }
  else
  {
    if(d4==0&&d100==0&&d400!=0)
    {
    printf("IT IS -NOT- A LEAP YEAR");
    }
    else
    {
    if(d4==0&&d100!=0&&d400!=0)
    printf("IT IS A LEAP YEAR");
    }
  }

  return 0;
}


6-6
#include <stdio.h>
//PROGRAMM TO CALCULATE A EMPLOYEE´S WEEKLY PAY
//AFTER 40 HOURS, 1 HOUR = 1.5 HOURS. 
int main(void) {
  double PPH, H, TH, P, TEH, EXP;
  int i, D, DD;
  printf("ENTER PAYMENT PER HOUR\n$");
  scanf("%lf", &PPH);
  printf("HOW MANY DAYS PER WEEK DOES THE EMPLOYEE WORKS?\n");
  scanf("%d", &D);
  TH=0;

  printf("\n\n");
  for(i=1; i<=D; i++)
  {
  printf("DAY %d : HOURS WORKED\n", i);
  scanf("%lf", &H);
  TH=TH+H;

  }
  if(TH>40)
  {
    TEH=TH-40;
    EXP=TEH*1.5;
    P=(40+EXP)*PPH;
  }
  else
  {
    TEH=0;
    P=TH*PPH;
  }

  printf("\n\nTOTAL HOURS %.0lf , WHICH %.0lf ARE EXTRA HOURS", TH, TEH);
  printf("\n\nPAYMENT THIS WEEK $%.2lf ", P);
  return 0;
}


6-7
#include <stdio.h>
#include <string.h>


//PROGRAMM MAKE APPOINTMENTS FOR TODAY AND PUT IT IN ORDER FROM 1 TO 10
int main(void) {
int i=1;
int c;
char AP[i], WW[i];
char line[100]; 

printf("DOCTOR : D\n"); 
printf("SCHOOL : S\n"); 
printf("JOB    : J\n"); 
printf("TASKS  : T\n"); 
printf("FAMILY : F\n");  
printf("0 - 10 WHERE 10 IS HIGH IMPORTANCE LEVEL");
printf("\n\nIF THERE IS NO MORE DATES, ENTER ""0""\n\n");
  while(1)
  {

  printf("\nAPPOINTMENT\n");
  fgets(line, sizeof(line), stdin);
  sscanf(line, "%s", &AP[i]);

  printf("\nLEVEL OF IMPORTANCE\n");
  fgets(line, sizeof(line), stdin);
  sscanf(line, "%s", &WW[i]);

  if(AP[i]=='0')
  break;
  if(AP[i]!='0')
  {
  i=i+1;
  continue;
  }

  }
  for(c=1;c<=i;c++)
{

  printf("%c   %c\n", AP[c], WW[c]);
}
  return 0;
}

# CSunit3

Table of contents
------
1. [Planning](#Planning)
1. [Development](#Development)
1. [Evaluation](#Evaluation)
1. [References](#References)

Planning
------

Development
------
**what is VPN??**

|Protocol|Created by      |Used in      |
|-|------------- |----------- |
|VPN| Gurdeep Sighpall| Private network connection|

VPN stands for Virtual Private Network and created by Gurdeep Sighpall. It was originally used for microsoft's business connections but it spread out and became popular due to wikileaks or warning from Snowden. It is a service that uses different tunneling protocols to encrypt user's IP address.

**//Standard C arrays**

This program give an array of 10 numbers, that shows the elements in the following way:
```
#include <stdio.h>
 
int main () {

   int n[ 10 ]; 
   int i,j;
        
   for ( i = 0; i < 10; i++ ) {
      n[ i ] = rand() % 100 + 1;
   }
   
   for (j = 0; j < 10; j++ ) {
      printf("element[%i] = %i\n", j, n[j] );
   }
 
   return 0;
}
```


**//Reading texts in standard C**

This program reads the input of user and output to isak's email format.
```
#include <stdio.h>
 
int main () {

   int year= 0;
   char str1[100];
   char str2[100];
   printf("Enter your school year, first_name and last_name.\n");
   printf("Example 2021 keitaro mae\n");

   scanf("%d", &year);
   scanf("%s", &str1);
   scanf("%s", &str2);

   printf("%d.%s.%s@uwcisak.jp",year, str1, str2);

   return 0;
}
```
Evaluation
------

References
------

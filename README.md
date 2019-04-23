

#include<stdio.h>

int main(){
   int a[100] = {24,60,35,75,76,77,23,24,19,14,53,97,10,76,41,31,18,66,0,72,60,85,29,48,18,75,81,75,77,10,46,56,46,29,54,78,50,18,50,89,63,34,82,52,53,57,7,73,2,0,95,83,51,62,79,84,61,66,8,13,31,51,15,10,25,16,49,46,88,85,69,71,39,57,6,59,77,74,7,18,47,63,48,72,60,97,38,58,81,70,90,11,28,18,50,58,52,54,37,72};

   int i,j,temp;
   for(i=0;i<100;i++){
       for(j=99;j>i;j--){
           if(a[j-1] > a[j]){
               temp=a[j-1];
               a[j-1]=a[j];
               a[j]=temp;
           }
       }
   }
   printf("number is:");
   for( i = 0;i < 100;i++){
    printf("%2d\n",a[i]);
   }

   int search,start,middel,last;

   printf("enter your number you want to search:");
   scanf("%d",&search);
   start=0;
   last=100-1;
   middel=(start+last)/2;
   while(start<=last){
        if(a[middel]<search){
            start=middel+1;
        }
        else if(a[middel]==search){
            printf("%d found at location %d\n", search, middel+1);
            break;
        }
        else
            last=middel-1;

       middel=(start+last)/2;
   }
   if (start > last)
      printf("Not found! %d isn't present in the list.\n", search);

   return 0;



}

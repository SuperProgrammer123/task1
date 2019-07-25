# task1
#include <iostream>
using namespace std;
#define null 0
bool dup(int numbers[],int length,int *duplication)
{
   if(numbers==null||length<=0)
   {
    return false;
   }

   for(int i=0;i<length;i++)
   {
     if(numbers[i]<0||numbers[i]>length-1)
		 return false;
   } 

   for(i=0;i<length;i++)
   {
	while(numbers[i]!=i)
	{
		if(numbers[i]==numbers[numbers[i]])
		{
			*duplication=numbers[i];
		   
				return true;
		}
	
      
		int temp=numbers[i];
		numbers[i]=numbers[temp];
        numbers[temp]=temp;
	}

   }

  return false;

}
 int main()
 {
	 int numbers[]={0,1,2,2,5,4,3};
	 int length=0;
	 int duplication;
    length = sizeof(numbers)/sizeof(int); 
 dup(numbers,length,&duplication);
		 cout<<duplication<<endl;
	return 0;
 }

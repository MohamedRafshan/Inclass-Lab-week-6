# Inclass-Lab-week-6
Stack and Linked List


// code for stack

#include <iostream>
#include <chrono>
using namespace std;

int stack[100], n=100, top=-1;
void push(int val) {
   
   if(top>=n-1){
   cout<<"Stack Overflow"<<endl;
   }
   else {
      top++;
      stack[top]=val;
   }
}
void pop() {
   if(top<=-1){
   cout<<"Stack Underflow"<<endl;
   }
   else {
      cout<<"The popped element is "<< stack[top] <<endl;
      top--;
   }
}
void display() {
   if(top>=0) {
      cout<<"Stack elements are:";
      for(int i=top; i>=0; i--)
      cout<<stack[i]<<" ";
      cout<<endl;
   }else
   cout<<"Stack is empty";
}

int main (){
    int arr[20]={23,5,6,80,12,45,67,100,21,34,67,54,65,20,53,85,96,92,16,83};
    for (int i=0;i<20;i++){
        auto start = chrono::high_resolution_clock::now();
        push(arr[i]);
        auto end = chrono::high_resolution_clock::now();
        auto duration = chrono::duration_cast <chrono::nanoseconds>(end - start);
        cout<<"run time for push an element " <<duration.count()<<" nonosecond "<<endl;
        
    }
    cout<<endl;
    
    for (int i=0;i<5;i++){
        auto start = chrono::high_resolution_clock::now();
        display();
        auto end = chrono::high_resolution_clock::now();
        auto duration = chrono::duration_cast <chrono::nanoseconds>(end - start);
        cout<<"run time for display an element " <<duration.count()<<" nonosecond "<<endl;
        
    }
    cout<<endl;
    for (int i=0;i<10;i++){
        auto start = chrono::high_resolution_clock::now();
        pop();
        auto end = chrono::high_resolution_clock::now();
        auto duration = chrono::duration_cast <chrono::nanoseconds>(end - start);
        cout<<"run time for pop an element " <<duration.count()<<" nanosecond "<<endl;
        
    }
}

# Palindrome-Linked-list-
#Given a singly linked list of size N of integers. The task is to check if the given linked list is palindrome or not.
#include <iostream>
using namespace std;

struct node
{
  int data;
  node *next;
};
bool isPalindrome(node *head)
    {
        //Your code here
        int num=0;
        while(head!=NULL)
        {
            num=head->data+num*10;
            head=head->next;
        }
        int n=num,rev=0,rem;
        while(num!=0)
        {
            rem=num%10;
            rev=rev*10+rem;
            num=num/10;
        }
        if(rev==n)
        return 1;
        else
        return 0;
    }

int main() {
  int n;
  cout<<"Enter the number of items in Linked list:";
  cin>>n;
  node *ptr = NULL, *head = NULL, *newnode;
  ptr = new node;
  head = ptr;
  cout<<"Enter the Linked List:";
  while(n!=0)
    {
    newnode = new node;
    cin>>newnode->data;
    newnode->next=NULL;
    if(head==NULL)
    {
      head = newnode;
      ptr = newnode;
    }
    else
    {
      ptr->next = newnode;
      ptr = newnode;
    }
    n--;
    }
  if(isPalindrome(head)==1)
  {
    cout<<"Is Palindrome";
  }
  else
    cout<<"Is Not Palindrome";
  
}

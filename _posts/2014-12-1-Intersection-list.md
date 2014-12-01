---
layout: post
title: Intersection of Two Linked Lists
---
#Intersection of Two Linked Lists
> Write a program to find the node at which the intersection of two singly linked lists begins.

> For example, the following two linked lists:

> A:    a1 → a2
                   ↘
                     c1 → c2 → c3
                   ↗            
> B:     b1 → b2 → b3

> begin to intersect at node c1.

> Notes:

 > If the two linked lists have no intersection at all, return null.
> The linked lists must retain their original structure after the function returns.
>  You may assume there are no cycles anywhere in the entire linked structure.
>  Your code should preferably run in O(n) time and use only O(1) memory.

`
	        
	class Solution{
	public:
		listNode *getIntersectionNode(ListNode *headA, ListNode *headB){
		if (headA == NULL || headB == NULL) return NULL;
        int icount1(0),icount2(0);
        ListNode *TempList1 = headA;
        ListNode *TempList2 = headB;
        
        while(TempList1->next != NULL){
            icount1++;
            TempList1 = TempList1->next;
        }
        while(TempList2->next != NULL){
            icount2++;
            TempList2 = TempList2->next;
        }
        if (TempList2!=TempList1){
            return NULL;
        }
        else{
            int diff = abs(icount1-icount2);
            if (icount1>icount2){
                TempList1 = headA;
                TempList2 = headB;
            }
            else{
                TempList1 = headB;
                TempList2 = headA;
            }
            while(diff>0){
                TempList1 = TempList1->next;
                diff--;
            }
            while(TempList1 != TempList2){
                TempList1 = TempList1->next;
                TempList2 = TempList2->next;
            }
            return TempList1;
               
            }
		}
	};      
`
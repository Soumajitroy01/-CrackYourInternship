class Solution {
public:
    ListNode* MergeSort(ListNode* head,int n){
    
        if (head && n==1 ) { 
            head->next=nullptr; 
            return head; 
        }
        
        if(n==2) {
            ListNode *one=head, *two=head->next;
            
            if(one->val > two->val) {
                two->next=one;
                one->next=nullptr;
                head=two;
            }
            else two->next=nullptr;
            
            return head;
        }
        
        ListNode* first = head,*second=head;
        
        for(int i=0;i<(n+1)/2;++i) second=second->next;
        
        first = MergeSort(first,(n+1)/2);
        second= MergeSort(second,n-(n+1)/2);
        
        ListNode* retList = Merge(first,second);
        return retList;
    }
    
    ListNode* Merge(ListNode* head1, ListNode* head2) {
            ListNode* retHead=nullptr, *cur=nullptr,*prev=nullptr;

            if(head1 && !head2) return head1;
            if(head2 && !head1) return head2;
            
            while(head1 && head2) {
                
                if(head1->val <= head2->val) 
                { 
                    cur = head1; head1=head1->next;
                }
                else 
                { 
                    cur = head2; head2=head2->next;
                }
                
                if(!retHead) 
                { 
                    retHead=cur; 
                    prev=cur;
                }
                else 
                {  
                    prev->next=cur;
                    prev=cur;
                }
            }
        
            if(head1) prev->next=head1;
            if(head2) prev->next=head2;
            
        return retHead;
    }
    
    ListNode* sortList(ListNode* head) {
        ListNode* left=head;
        if(!head || !head->next) return head;
        
        ListNode* cur=head;
        int n=0; //node-count
        
        while(cur!=NULL) {
            cur=cur->next;
            ++n;
        }
        head = MergeSort(head,n);
        return head;    
    }
};

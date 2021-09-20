##Count Pairs whose sum is equal to X 

```
int countPairs(struct Node* head1, struct Node* head2, int x) {
        int count = 0;
        
        unordered_set<int> st;
        while(head1!=NULL){
            st.insert(head1->data);
            head1 = head1->next;
        }
        
        while(head2!=NULL)
        {
            if(st.find(x-head2->data)!=st.end())
              count++;
              head2 = head2->next;
        }
        
        return count;
    }
    
    ```
    ## Complexity :  O(N+M)
    
    You can also do this O(n^2) 
    
    ```
    int countPairs(struct Node* head1, struct Node* head2, int x)
    {
       int count = 0;
    
       struct Node *p1, *p2;
    
       // traverse the 1st linked list
        for (p1 = head1; p1 != NULL; p1 = p1->next)

        // for each node of 1st list
        // traverse the 2nd list

        for (p2 = head2; p2 != NULL; p2 = p2->next)

            // if sum of pair is equal to 'x'
            // increment count
            if ((p1->data + p2->data) == x)
                count++;            
        
       // required count of pairs     
      return count;
      }
    
    
    ```

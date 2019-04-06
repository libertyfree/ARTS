### 
https://leetcode-cn.com/problems/add-two-numbers/

"""

/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode sumNode = new ListNode(0);
        ListNode tempNode = sumNode;
        int carry = 0;
        ListNode p = l1 , q = l2;
        while(p != null ||  q != null ){
            int x = (p != null) ? p.val :0;
            int y = (q != null) ? q.val :0;
            int sum = carry + x + y;
            carry = sum / 10;
            tempNode.next = new ListNode(sum%10);
            tempNode = tempNode.next;
            if (p != null) p = p.next;
            if (q != null) q = q.next;
        }
        if(carry > 0){
                tempNode.next = new ListNode(carry);
        }
        
        return sumNode.next;
    }
}
"""

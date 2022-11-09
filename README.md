# Design-and-Analysis-of-Algorithm

Name : Rajesh Thakare

Sec : A

Roll : 54



## Problem Statement : Possible Maximum Sum of Three Stacks: (Queue Implementation)

Finding the Maximum sum of three Stacks using queue data structure .

Given :
Three stacks of the positive numbers.


Find :
Possible equal maximum sum of the stacks.




Code:
```
import java.util.LinkedList;
import java.util.Queue;

class MaximumEqualSum {
	
	public static int maxSum(Queue q1, Queue q2, Queue q3)
	{
	int sum1 = 0, sum2 = 0, sum3 = 0;
	
	// finding the initial sum of queue1
	for (Object i:q1)
		sum1 += (Integer)i;
	
	// finding the initial sum of queue2
	for (Object i:q2)
		sum2 += (Integer)i;
	
	// finding the initial sum of queue3
	for (Object i:q3)
		sum3 += (Integer)i;
	
        // logic
	while (true)
	{
		// if any queue is empty
		if (q1.isEmpty() || q1.isEmpty() || q1.isEmpty())
			return 0;
	
		// if sum of all three queue are equal
		if (sum1 == sum2 && sum2 == sum3)
			return sum1;
		
		// finding the queue with maximum sum and removing its front element
		if (sum1 >= sum2 && sum1 >= sum3)
            		sum1 -= (Integer)q1.poll();
		else if (sum2 >= sum1 && sum2 >= sum3)
			sum2 -= (Integer)q2.poll();
		else if (sum3 >= sum2 && sum3 >= sum1)
			sum3 -= (Integer)q3.poll();
	}
	}
	
	// Driver code 
	public static void main(String[] args)
	{
        Queue<Integer> queue1 = new LinkedList<>();
        Queue<Integer> queue2 = new LinkedList<>();
        Queue<Integer> queue3 = new LinkedList<>();

        //initializing queue 1
        queue1.add(6);
        queue1.add(1);
        queue1.add(0);
        queue1.add(1);
        

        //initializing queue 2
        queue2.add(6);
        queue2.add(1);
        queue2.add(1);
	    
        //initializing queue 3
        queue3.add(5);
        queue3.add(2);
        queue3.add(8);
       

	System.out.println("Possible Equal Maximum Sum: "+maxSum(queue1, queue2, queue3));
		
	}
}
```


Output of the Code  :

Possible Equal Maximum Sum:  8


TEST CASES

INPUT 1 :

Queue 1 : 6 1 0 1

Queue 2 : 6 1 1 

Queue 3 : 5 2 8

OUTPUT 1  :

Possible Equal Maximum Sum : 8


INPUT 2 :

Queue 1 : 8 5 3

Queue 2 : 6 9 4 2 2

Queue 3 : 3 2 1 2

OUTPUT 2  :

Possible Equal Maximum Sum : 8


INPUT 3 :

Queue 1 : 9 1 4 2

Queue 2 : 3 6 1

Queue 3 : 1 2 5

OUTPUT 3 :

Possible Equal Maximum Sum : 7




Explanation :

Data structure used: Queue
Three queues q1,q2,q3 to store the elements.
s1,s2,s3 to store respective sums of q1,q2 and q3 respectively.

The approach to the problem is as follows:
Step1:We store the sums of q1,q2,q3 in s1,s2,s3
Step2:we add conditionals to satisfy the max possible equal  sum-condition.if the queue is empty simply return 0.If the sum of all three queues are equal return anyone sum.
For other conditions,finding the queue with maximum sum and removing its front element







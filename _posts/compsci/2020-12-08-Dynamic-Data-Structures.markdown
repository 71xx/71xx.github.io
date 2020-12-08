---
layout: single
title:  "Dynamic Data Structures"
date:   2020-12-08 15:00:23 +0100
categories: compsci
tags: code
excerpt: Dynamic Data Structures Overview
---

# Collections

An unordered list of unknown size that is dynamically growing/shrinking.

## Java Equivalents

 * ArrayList
 * LinkedList
 * Stacks
 * Queues
 * Trees

## IB Collection Operations

{% highlight java linenos %}

.addItem(Data)
.resetNext()
.hasNext()
.getNext()
.isEmpty()

{% endhighlight %}


## IB Example Usage

{% highlight java linenos %}

NAMES = new Collection() 				//make a new empty collection
NAME = "" 							//declare NAME
loop while NAME <> "quit" 				//loop until “quit” is entered
	input NAME 						//accept NAME
	if NAME <> "quit" then 				//if “quit” not entered
		if NAMES.contains(NAME) then 	//if list contains NAME
			output NAME , " returned"	//print message returned
			NAMES.remove(NAME)			//remove it from NAMES
		Else
			output NAME , " is leaving"   //if list does not contain NAME
			NAMES.addItem(NAME)		//add NAME to NAMES
		end if
	end if
end loop	//Loop ends here

output "The following students left and did not return" 
NAMES.resetNext()						//START AT FIRST ITEM
loop while NAMES.hasNext() 				//AS LONG AS ITEMS EXIST
	output NAMES.getNext() 				//PRINT VALUES IN EACH ITEM
end loop

{% endhighlight %}


# Abstract Data Structures

An Abstract Data Structure/Type in CS is where a data type is defined by its behavior (semantics) from the point of view of a user of the data, specifically in terms of possible values, possible operations on data of this type, and the behavior of these operations. This contrasts with data structures, which are concrete representations of data, and are the point of view of an implementer, not a user.

## Examples of ADT's

 * STACKS a structure that follows a first in/last out and last in/first out approach to process data/information.
 * QUEUES a structure that follows a first in/first out and last in/last out approach to process data/information.
 * LINKED LISTS a structure that creates packets of data/information linked together with pointers (links in memory that connect to locations). One way/two way/cyclical traversal.
 * TREES a structure that replicates an upside down tree with a root and left/right nodes that branch out going to different areas. 
 * Lists, dictionaries, tuples, arrays, collections, sets, etc are all other examples.


# Stacks

## IB Operations

 * PUSH( )	Add a new item to TOP of the stack. Increment TOP.
 * PEEK( ) Check element in TOP.
 * POP( ) Remove element in TOP.
 * ISEMPTY( ) Check if stack is empty - boolean.
 * STACK OVERFLOW - Pushing an element into a full stack.
 * STACK UNDERFLOW - Trying to pop an element from an empty stack.

## Java Example

{% highlight java linenos %}

import java.util.Stack;

Stack<String> stackOfCards = new Stack<>();

stackOfCards.push("Jack");
stackOfCards.push("Queen");
stackOfCards.push("King");
stackOfCards.push("Ace");

stackOfCards.pop();	//current TOP
stackOfCards.pop();	//current TOP

System.out.println(stackOfCards);
System.out.println(stackOfCards.peek());

{% endhighlight %}


# Queues

## IB Operations

 * ENQUEUE - Adding a new element to the REAR of a queue. If it is the first or only element then it is both FRONT and REAR of the queue. Every new element is the new REAR of the queue.
 * DEQUEUE - Removing an element from the FRONT of the queue. Elements are shifted so that the item next to FRONT is the new FRONT.
 * PEEK - Returns the element in the FRONT of a queue. If the queue is empty it returns NULL.
 * QUEUE OVERFLOW/UNDERFLOW - Attempting to enqueue an item to a full Queue produces an overflow. Attempting to dequeue from an empty Queue produces an underflow. 

## Types of Queues

 * Linear
 * Circular
 * Priority

## Linear Queue Java Example

{% highlight java linenos %}

import java.util.LinkedList;
import java.util.Queue;
Queue<Integer> q = new LinkedList<>();
//make an object/instance of type Queue

q.add(“Jan”);
q.add(“Feb”);
q.add(“Mar”);
q.add(“Apr”);
System.out.println(q);	//print all elements

q.remove();
q.remove();

System.out.println(q);	//print all elements

{% endhighlight %}


# Circular Queues

A circular queue is a data structure where the front of the queue is decremented with every dequeue so that there are empty spaces in front of it. Once rear hits max size, the enqueue loops/circles back to the front to fill up the empty slots.

## Pseudocode Examples

### Adding an Elelemt

{% highlight java linenos %}

//ARRAY IMPLEMENT PSEUDOCODE FOR QUEUE MAX SIZE OF 7

FRONT = -1, REAR = -1		//EMPTY QUEUE
MAX = 7			//MAX ELEMENTS ALLOWED
AVAILABLE = TRUE

FUNCTION ENQUEUE (ITEM)
       IF REAR+1 == FRONT THEN		//IF CIRCULAR
            PRINT QUEUE OVERFLOW!
            AVAILABLE = FALSE		//NO MORE ENTRIES
       IF FRONT == 0 AND REAR = MAX-1 THEN
           PRINT QUEUE OVERFLOW!	//IF LINEAR
           AVAILABLE = FALSE		//NO MORE ENTRIES
      IF FRONT == -1 THEN		
           FRONT = 0			//IF QUEUE EMPTY
           REAR = 0
      ELSE IF REAR == MAX -1 THEN        //IF REAR NEEDS LOOPING BACK
                     REAR = 0			//MEANS FRONT IS ELSEWHERE
                ELSE
                      REAR = REAR +1		//NO CHANGE. JUST ADD.
IF AVAILABLE == TRUE THEN      	//CHECK AVAILABLE
     QUEUE[REAR] = ITEM 		//ADD IT

{% endhighlight %}

### Removing an Element

{% highlight java linenos %}

//ARRAY IMPLEMENT PSEUDOCODE FOR QUEUE MAX SIZE OF 7

FRONT = -1, REAR = -1		//EMPTY QUEUE
MAX = 7			//MAX ELEMENTS ALLOWED
AVAILABLE = TRUE
FUNCTION DEQUEUE ()
      IF FRONT == -1 THEN
         PRINT QUEUE UNDERFLOW!
     IF FRONT == REAR THEN
           FRONT  = -1
           REAR = -1
    ELSE IF FRONT == MAX-1 THEN
                  FRONT = 0
              ELSE
                   FRONT = FRONT + 1

{% endhighlight %}

### Printing a Queue

{% highlight java linenos %}

//ARRAY IMPLEMENT PSEUDOCODE FOR QUEUE MAX SIZE OF 7

FRONT = -1, REAR = -1		//EMPTY QUEUE
MAX = 7			//MAX ELEMENTS ALLOWED
AVAILABLE = TRUE
FUNCTION DISPLAY()
        FRONTPOS = FRONT, REARPOS = REAR
        IF FRONT == -1 THEN
             PRINT “QUEUE EMPTY!”
        ELSE IF FRONTPOS <= REARPOS THEN
                     LOOP FRONTPOS FROM FRONTPOS TO REARPOS
                                 PRINT QUEUE[FRONTPOS]
	        END LOOP
                  ELSE LOOP FRONTPOS FROM FRONTPOS TO MAX -1
                                     PRINT QUEUE[FRONTPOS]
                            ENDLOOP
                            FRONTPOS = 0
                             LOOP FRONTPOS FROM FRONTPOS TO REARPOS
                                        PRINT QUEUE[FRONTPOS]

{% endhighlight %}


## Java Implementation

{% highlight java linenos %}

import java.util.Random;
import java.util.Scanner;

public class Activity {
	public static int front = -1;
	public static int rear = -1;
	public static int max = 7;
	public static String[] queue = new String[8];
	public static Scanner scanner = new Scanner(System.in);
	public static Random rand = new Random();
	
	public static boolean avaliable = true;
	
	private static void enqueue(String x) {
		if (((rear + 1) == front) || (front == 0 && rear == (max-1))) {
			System.out.println("Queue Overflow!");
			avaliable = false;
		} 
		
		if (front == -1) {
			front = 0;
			rear = 0;
		} else if (rear == (max - 1)) {
			rear = 0;
		} else {
			rear = rear + 1;
		}
		//System.out.println(avaliable); // Debug line
		if (avaliable) {
			queue[rear] = x;
		}
	}
	
	private static void dequeue() {
		System.out.print(queue[front]);
		if (front == -1) {
			System.out.println("Queue Underflow!");
		} 
		
		if (front == rear) {
			front = -1;
			rear = -1;
		} else if (front == (max - 1)) {
			front = 0;
		} else {
			front++;
		}
		
		
	}
	
	private static void display() {
		int frontpos  = front;
		int rearpos = rear;
		if (front == -1) {
			System.out.println("Queue Empty!");
		} else if (frontpos <= rearpos) {
			for (int i = frontpos; i <= rearpos; i++) {
				System.out.print(queue[i] + ", ");
			}
		} else {
			for (int i = frontpos; i <= (max - 1); i++) {
				System.out.print(queue[i] + ", ");
			}
			frontpos = 0;
			for (int i = frontpos; i <= rearpos; i++) {
				System.out.print(queue[i] + ", ");
			}
		}
	}
	
	private static void question() {
		System.out.println("Do you have a question about a Current account or a Savings Account: Please Enter C or S: ");
		String input = scanner.next();
		if (input.equals("C")) {
			String token = "C-" + Integer.toString(rand.nextInt(200));
			enqueue(token);
		} else if (input.equals("S")) {
			String token = "S-" + Integer.toString(rand.nextInt(200));
			enqueue(token);
		} else {
			System.out.println("Incorrent Input");
		}
	}

	private static void teller() {
		System.out.println("");
		System.out.print("Can customer: ");
		dequeue();
		System.out.print(", Please come to the teller counter.");
		System.out.println();
		System.out.print("Next customers: ");
		display();
	}
	
	public static void main(String[] args) {
		int i = 4;
		int count = 0;
		while (count < i) {
			count++;
			question();	
		}
		
		int c = 0;
		while (c < (i-2)) {
			teller();
			c++;
		}
		
	}
	
	
}


{% endhighlight %}
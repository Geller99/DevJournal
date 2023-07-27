## Daily Dev Journal

Wednesday, the 26th July Learnings...

## Today's Dev Target

- Cover Recursive Backtracking Algorithms
- Implement Basic Linked Lists
- Implement Auth using AWS CDK in Golang for Tailz App
- Start Reading Bluesky Codebase
- Read more Go with Tests -> https://quii.gitbook.io/learn-go-with-tests/go-fundamentals/hello-world



## Recursive Backtracking

Today it finally clicked! 

- Path : in traversing a decision tree, we have to decide where we want to go...add that choice to path []
- Selection : once we decide, our chosen path will have options, we gotta decide again where we want to go...
- Terminal condition : once we reach the end of THAT leaf, our function terminates and backtracks to the previous function in recursive loop...

so If my tree consists of 1, 2, 3

I pick 1, that's added to my path [1]
step 2 .I can select 2 or 3
if I pick 2, path is now [1,2]
meaning I can only pick 3 after... path becomes [1,2,3]

Terminal condition hits...function call ends, prints current path and backtracks to step 2
then it picks 3 
path becomes [1,3]
meaning I end up at [1,3,2] as my path
hit another terminal condition and backtrack all the way back to 1...

and it just keeps happening recursively...


## Singly Linked Lists

A linear collection of data elements -> each element points to the next...nodes form a sequence, each node contains data and a reference to the next

This structure allows for efficient insertion or removal of elements but linear access...

`` Head -> val| -> val |-> tail |-> null `` - or sumn like that LOL...you get the point

here's basic JS and Golang implementations

```JS
class Node {
  constructor(val) {
    this.val = val;
    this.next = null;
  }
}

class SinglyLinkedList {
  constructor() {
    this.length = 0;
    this.head = null;
    this.tail = null;
  }

```

```Go

type Node struct {
    data interface{}
    next *Node
}

type LinkedList struct {
    head *Node
}

```
I don't quite understand Golang pointers just yet so I used chatGPT to write this...


## Feature Development -> Setting up Auth in Tailz

So, I've been following Andrew Brown's Cloud Engineering Bootcamp...and week 3 is implementing decentralized auth with AWS Cognito user pools

I elect to use Golang since...well, it's sexy and JavaScript is bad engineering...so here's how I followed along

- So far, I've setup the AWS amplify user auth pools via the AWS Console (yuck...), cli is next as andrew teaches it
- experimented with next js new page and api routing structures
- setup amplify config and some barebones components...



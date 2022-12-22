A queue is a useful data structure in programming. It is similar to the ticket queue outside a cinema hall, where the first person entering the queue is the first person who gets the ticket.

Queue follows the **First In First Out (FIFO)** rule - the item that goes in first is the item that comes out first.

![[queue.png]]

In the above image, since 1 was kept in the queue before 2, it is the first to be removed from the queue as well. It follows the #FIFO rule.

In programming terms, putting items in the queue is called **enqueue**, and removing items from the queue is called **dequeue**.

## Basic Operations of Queue

A queue is an object (an abstract data structure - ADT) that allows the following operations:

- **Enqueue**: Add an element to the end of the queue
- **Dequeue**: Remove an element from the front of the queue
- **IsEmpty**: Check if the queue is empty
- **IsFull**: Check if the queue is full
- **Peek**: Get the value of the front of the queue without removing it

## Working of Queue

Queue operations work as follows:

-   two pointers FRONT and REAR
-   FRONT track the first element of the queue
-   REAR track the last element of the queue
-   initially, set value of FRONT and REAR to -1

### Enqueue Operation

-   check if the queue is full
-   for the first element, set the value of FRONT to 0
-   increase the REAR index by 1
-   add the new element in the position pointed to by REAR

### Dequeue Operation

-   check if the queue is empty
-   return the value pointed by FRONT
-   increase the FRONT index by 1
-   for the last element, reset the values of FRONT and REAR to -1

![[queue-2.png]]

## Queue Implementations in Golang

We usually use arrays to implement queues.

```go
package main

import (
	"fmt"
)

type Event struct {
	Name  string
	Body  string
	Index int
}

const queueLimit = 4

func main() {
	var queue []Event
	indexes := []int{1, 2, 3, 4, 5}

	for _, index := range indexes {
		queue = Enqueue(queue, Event{
			Name:  "Queue Event",
			Body:  "Hello world",
			Index: index,
		})
	}

	fmt.Println("BEFORE DEQUEUE")
	fmt.Println(queue)
	queue = Dequeue(queue)
	fmt.Println("AFTER DEQUEUE")
	fmt.Println(queue)
	Peek(queue)
}

func Enqueue(queue []Event, event Event) []Event {
	queue = append(queue, event)
	fmt.Println("new event enqueued ", event.Index)
	return queue
}

func Dequeue(queue []Event) []Event {
	element := queue[0]
	fmt.Println("an event dequeued: ", element.Index)
	return queue[:len(queue)-1]
}

func Peek(queue []Event) Event {
	element := queue[len(queue)-1]
	fmt.Println("an event peeked: ", element.Index)
	return element
}
```

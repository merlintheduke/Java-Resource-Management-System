# Resource Management System

This was a group project for my Data Structures course. The program simulates how a fixed budget can be distributed across several university departments based on the amount of funding each department has already received.

Each department has a list of requested items. The program reads those requests from text files, decides which department should be processed next, purchases items that fit within the remaining budget, and prints a summary of what each department received.

## How It Works

Departments start with a priority of `0`. A `PriorityQueue` is used so that the department with the lowest amount of funding received is processed first.

When an item is purchased:

- the item's cost is added to the department's priority
- the item is moved to the department's received-items queue
- the cost is subtracted from the remaining budget
- the department is added back to the priority queue if it still has requests to process

Items that cost more than the remaining budget are moved to a separate queue for items that could not be purchased.

If a department has received all of its requested items and money is still available, the program can assign up to $1,000 as a scholarship.

## Data Structures Used

- `PriorityQueue<Department>` - determines which department receives funding next
- `Queue<Item>` / `LinkedList<Item>` - stores requested, received, and unpurchased items
- `ArrayList<Department>` - keeps track of every department for the final summary
- `ArrayList<String>` - stores formatted purchase output
- `Comparable<Department>` - defines department ordering inside the priority queue

## Other Concepts Used

- Object-oriented programming
- File input with `Scanner`
- Custom `Department` and `Item` classes
- Exception handling
- Budget allocation logic
- Sorting by priority
- Multiple test cases and edge cases

## Project Files

```text
BigDataProject-master/
├── Driver.java
├── ResourceManagement.java
├── TestCase1/
│   ├── Department-Chemistry.txt
│   ├── Department-ComputerScience.txt
│   ├── Department-Mathematics.txt
│   └── Department-PhysicsAndAstronomy.txt
└── TestCase2/
    ├── Department-DeptA.txt
    ├── Department-DeptB.txt
    ├── Department-DeptC.txt
    ├── Department-DeptD.txt
    ├── Department-DeptE.txt
    ├── Department-DeptF.txt
    └── Department-DeptG.txt
```

`Driver.java` runs the provided test cases with different budget amounts.

`ResourceManagement.java` contains the budget allocation algorithm along with the `Department` and `Item` classes.

## Running the Project

Make sure Java is installed, then run these commands from the project folder:

```bash
javac Driver.java ResourceManagement.java
java Driver
```

The program will run three tests, including a normal budget, a very small budget, and a second set of department data.

## Team

This project was completed by:

- Joshua Guzman
- Santiago Yuriar
- Dawson Merriman
- Matthew McCabe
- Patrick Tilotta

## Course

Data Structures - Group Project

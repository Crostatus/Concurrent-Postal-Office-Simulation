# Concurrent Postal Office Simulation

## Project Overview

This project is a **concurrent simulation of a postal office system** implemented in Java.  
It models the behavior of customers entering a post office, waiting in different service rooms, and being served by multiple service counters using **Java concurrency utilities**.

The application was developed as an academic assignment to demonstrate the correct use of **threads, synchronization mechanisms, and executor services**.

---

## Technical Description

The simulation is built on top of Java's `java.util.concurrent` package and focuses on:

- Managing multiple customer threads concurrently
- Coordinating access to shared resources
- Simulating real-world service delays
- Graceful startup and shutdown of concurrent components

Each customer is represented as an independent thread, while the postal office manages service counters using a thread pool.

---

## Architecture Overview

### Core Components

- **PostalOffice**
  - Central coordination class
  - Manages service counters using an `ExecutorService`
  - Controls access to waiting rooms and service logic

- **Customer**
  - Represents a single customer as a runnable task
  - Simulates arrival time, service time, and completion

- **CustomerGenerator**
  - Responsible for dynamically generating customers
  - Controls arrival rate and customer distribution across rooms

- **Main**
  - Application entry point
  - Initializes the postal office and starts the simulation

---

## Concurrency Model

- Customers are implemented as concurrent tasks
- Service counters are managed through a fixed thread pool
- Shared data structures use thread-safe collections such as:
  - `CopyOnWriteArrayList`
- Synchronization is enforced to prevent race conditions
- Blocking and waiting behavior simulates real queueing systems

---

## Simulation Flow

1. The application starts and initializes the postal office.
2. The customer generator creates customers at runtime.
3. Customers enter the system and wait in designated rooms.
4. Available service counters process customers concurrently.
5. Once served, customers leave the system.
6. The simulation terminates gracefully after completion.

---

## Source Code Structure

- **Main.java**  
  Application entry point. Initializes and starts the simulation.

- **PostalOffice.java**  
  Core logic of the postal office, including thread pool management and service coordination.

- **customer.java**  
  Represents customer behavior and lifecycle.

- **customerGenerator.java**  
  Generates customers dynamically and controls system load.

---

## Compilation and Execution

Compile all source files:

```bash
javac *.java
```

Run the simulation:

```bash
java Main
```

---

## Key Concepts Demonstrated

- Java multithreading
- ExecutorService and thread pools
- Thread-safe collections
- Synchronization and shared resource management
- Simulation of real-world concurrent systems

---

## Intended Audience

This project is intended for:

- Students studying operating systems or concurrent programming
- Developers learning Java concurrency
- Academic demonstrations of multithreaded system design

---

## Notes

This is a simulation project and does not aim to model a real postal office with complete accuracy.  
Its primary goal is to demonstrate correct and effective use of Java concurrency mechanisms.

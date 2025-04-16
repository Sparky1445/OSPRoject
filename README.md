# OSPRoject
A dynamic load balancer for a multiprocessor system is a key component in ensuring efficient resource utilization, optimal performance, and system scalability. Let’s break it down and then go into how it works, the design considerations, and some implementation strategies.

🔄 What is a Dynamic Load Balancer?
In the context of a multiprocessor system (like multi-core CPUs or systems with multiple CPUs), a dynamic load balancer is responsible for distributing tasks or processes across processors at runtime, depending on the current system load.

💡 Why "Dynamic"?
Unlike static load balancing, which assigns tasks at compile-time or launch-time, dynamic load balancing adapts during execution. This is crucial when:

Tasks have unpredictable execution times

The system has heterogeneous processors

There’s variability in input data or workloads

Some processors become overloaded or underutilized

🧠 Key Goals of Dynamic Load Balancing
Maximize processor utilization

Minimize task waiting and execution time

Avoid processor idling

Balance the workload fairly among all processors

Support scalability and fault tolerance

⚙️ How It Works
Monitoring: The system tracks processor usage, task queue lengths, execution times, etc.

Decision Making: The load balancer decides whether to migrate tasks based on current metrics.

Task Migration: Tasks may be paused, moved, and resumed on another processor.

Feedback Loop: The system continuously updates decisions as loads change.

🧱 Design Models
Here are common strategies for dynamic load balancing:

1. Centralized Load Balancing
A single load balancer makes global decisions.

Simple but can become a bottleneck.

2. Distributed Load Balancing
Each processor makes local decisions or collaborates with neighbors.

Scalable and avoids a single point of failure.

3. Hierarchical Load Balancing
A tree or layered structure of controllers.

Balances between centralized control and distributed execution.

🔄 Task Migration Techniques
Preemptive migration: Running tasks can be moved.

Non-preemptive migration: Only newly scheduled tasks are migrated.

Need to consider task dependencies, data locality, and communication cost.


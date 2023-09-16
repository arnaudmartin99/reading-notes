# Concurrency
Decoupling of what gets done from when it gets done:
- to improve application structure by separating concerns
- to improve performance when wait time can be shared between multiple threads
## Defense principles
- Separate concurrency-related code from other code to respect Single Responsibility Principle
- Partition data into independent subsets than can be operated on by independent threads
## Execution models
### Producer-Consumer
Bound resource is a queue.
Producers write in the queue when signaled by the consumer that there is free space.
Consumers read in the queue when signaled by the producer that there is work.
### Readers-Writers
A shared resource is often read fastly by readers and occasionnally updated slowly by writers.
Challenge is to find the balance between:
- throughput (letting readers read without being blocked)
- freshness of information (letting writers write the updated information)
### Dining Philosophers-
- A philosopher thinks when he is not hungry
- An hungry philosopher tries to pick up a fork from each side of his plate, eventually waiting until both are available.
- He puts them both back when he has eaten and starts thinking again
## Shutdown code is hard
## Testing threaded code
- Treat spurious system failures as candidate threading issues
- Make nonthreaded code work
- Make threaded code pluggable: vary number of threads, real or test doubles, speed, number of iterations
- Make threaded code tunable: allow changing while system is running, consider self-tuning based on throughput and system utilization
- Run with more threads than processors
- Run on different platforms
- Instrument your code to force failures (wait, sleep, yield, priority) by hand (but you have to find where to put it) or automatically with jiggling strategies (no results on Google)
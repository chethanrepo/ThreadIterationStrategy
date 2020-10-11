# ThreadIterationStrategy 

[![published](https://static.production.devnetcloud.com/codeexchange/assets/images/devnet-published.svg)](https://developer.cisco.com/codeexchange/github/repo/chethanrepo/ThreadIterationStrategy)

![alt text](https://github.com/chethanrepo/ThreadIterationStrategy/blob/master/docs/process_ring_of_threads.jpg)

  It is just a implementation to solve a general requirement like Iterating through set of threads and pass the status/task from one thread to another in a ring fashion. If there is requirement to iterate through all the nodes in a given cluster and the status of the each node is tracked this most efficient thread / node iteration strategy can be reused.
  
  
 # How to run the code
  $ git clone https://github.com/chethanrepo/ThreadIterationStrategy.git
  
  $ cd ThreadIterationStrategy
  
  $ java com/process/test/ProcessRing 10 5 
  
** Note: You can try verious inputs range (int) with two args[] **

# Benchmarking Analysis

* *The jvm version(32 bit or 64 bit), memory & data that is being processed has the control over number of threads being created inside jvm. My system had 64bit jvm, single core processor and 8GB RAM, I was able to create upto 100000 (1 lakhs thread) with almost 94% of memory. The single round trip with 100000 threads took 19 secs,(100% cpu usage in the beginning), that means I can have 100k threads without any issue provided message size is less. The number of round trip should not be problem when we have a sufficient memory to create threds, 16GB ram we can have 200k threads. In order to increase the number of threads in the jvm, you need to increase memory.  I have attached screenshot when 50k was the input, you can see 50k + threads  under threads section in the screenshot.
* *

![alt text](https://github.com/chethanrepo/ThreadIterationStrategy/blob/master/docs/process_ring_of_threads_output.jpg)

  

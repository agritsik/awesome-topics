
### Executor Framework
- ExecutorService, Future, Callable, Runnable *:books: "Java concurrency in practice" [review](https://github.com/agritsik/book-notes/blob/master/concurrency-in-practice.md#chapter-6-task-execution)*

### Synchronizers
A synchronizer is any object that coordinates the control flow of threads based on its state:
- `CountDownLatch` - the number of calls
- `CyclicBarrier` - the number of threads *:books: "OCP / Managing Concurrent Processes"*
- `Semaphore` - the number of concurrent threads that are using a resource

> :point_right: CountDownLatch vs CyclicBarrier. Latches are for waiting for events; barriers are for waiting for other threads [stack](https://stackoverflow.com/questions/4168772/java-concurrency-countdown-latch-vs-cyclic-barrier)

> :point_right: CountDownLatch vs CyclicBarrier. For simple use cases - services starting etc... a CountdownLatch is fine. A CyclicBarrier is useful for more complex co-ordination tasks. An example of such a thing would be parallel computation - where multiple subtasks are involved in the computation - kind of like MapReduce. [stack](https://stackoverflow.com/questions/4168772/java-concurrency-countdown-latch-vs-cyclic-barrier)

> :point_right: CountDownLatch vs Semaphore. Use Semaphore to control thread access to resource. Use CountDownLatch to wait for completion of all threads [stack](https://stackoverflow.com/a/33624654)

### Extra
- `Fork/Join Framework` - recursive problems E.g. divide and conquer problems  *:books: "OCP / Managing Concurrent Processes"*
- CompletableFuture

### Identifying Threading Problems
Deadlock, starvation, and livelock are three threading problems that can occur and result in threads never completing their task. Deadlock occurs when two or more threads are blocked forever. Starvation occurs when
a single thread is perpetually denied access to a shared resource. Livelock is a form of starvation where two or more threads are active but conceptually blocked forever. Finally, race conditions occur when two threads execute at the same time, resulting in an unexpected outcome.
*:books: "OCP / Identifying Threading Problems*

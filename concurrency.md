# Generic concepts
### [What's the difference between a Future and a Promise?](https://stackoverflow.com/questions/14541975/whats-the-difference-between-a-future-and-a-promise)
- **Futures** and **Promises** are pretty similar concepts, the difference is that a future is *a read-only container for a result that does not yet exist*, while a promise can be written (normally only once).	
- The Java 8 `CompletableFuture` and the Guava `SettableFuture` can be thought of as promises


# Python approach generators/coroutines/tasks
### [What can you use Python generator functions for?](https://stackoverflow.com/questions/102535/what-can-you-use-python-generator-functions-for)
- You can think of **generators** as returning multiple items, as if they return a list, but instead of returning them all at once they return them one-by-one, and the generator function is paused until the nextitem is requested. 
- **generators** are *good for calculating large sets of results* 
- another use for generators (that is really the same) is to replace callbacks with iteration

### [Difference between coroutine and future/task in Python 3.5?](https://stackoverflow.com/questions/34753401/difference-between-coroutine-and-future-task-in-python-3-5)
- A **coroutine** is a generator function that can both yield values and accept values from the outside. The benefit of using a coroutine is that we can pause the execution of a function and resume it later. In case of a network operation, it makes sense to pause the execution of a function while we're waiting for the response. We can use the time to run some other functions.
- A **future** is like the **Promise** objects from Javascript. It is like a placeholder for a value that will be materialized in the future.

### [Coroutines and Tasks](https://docs.python.org/3/library/asyncio-task.html)
- `Coroutines` declared with the async/await syntax is the preferred way of writing asyncio applications.
- There are three main types of awaitable objects: coroutines, Tasks, and Futures.
- `Tasks` are used to schedule coroutines concurrently.
- A `Future` is a special low-level awaitable object that represents an eventual result of an asynchronous operation.


# JS promises and async/await
### [What is the difference between JavaScript promises and async await?](https://stackoverflow.com/questions/34401389/what-is-the-difference-between-javascript-promises-and-async-await)
- `async/await` simply gives you a synchronous feel to asynchronous code. It's a very elegant form of syntactic sugar.
- The first things you have to understand that `async/await` syntax is just syntactic sugar which is meant to augment promises. In fact the return value of an async function is a promise.
- `async/await` syntax gives us the possibility of writing asynchronous in a synchronous manner.




# C++ concepts
### [What are coroutines in C++20?](https://stackoverflow.com/questions/43503656/what-are-coroutines-in-c20)

- The specific implementation of Coroutines in C++ is a bit interesting. At its most basic level, it adds a few keywords to C++: `co_return` `co_await` `co_yield`. A function becomes a coroutine by having one of those in its body.
- The simplest coroutine is a generator. `co_yield` suspends the functions execution, stores that state in the `generator<int>`
- `co_await` meanwhile lets you splice one coroutine onto another.

### async vs promise vs package_tasks [1](https://stackoverflow.com/a/24164631), [2](https://stackoverflow.com/a/11020645)
- In the words of [futures.state] a `std::future` is *an asynchronous return object* ("an object that reads results from a shared state") and a `std::promise` is *an asynchronous provider* ("an object that provides a result to a shared state")
- *The asynchronous provider* is what initially creates the shared state that a future refers to. `std::promise` is one type of asynchronous provider, `std::packaged_task` is another, and the internal detail of `std::async` is another
- Use `std::async` only for simple things, e.g. to make some call non-blocking.
- Use `std::promise` when you need more control over the future.

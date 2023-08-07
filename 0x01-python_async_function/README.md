# 0x01. Python - Async

This project contains 5 tasks related to asynchronous programming in Python.

## Tasks

### 0. The basics of async

This task covers the basics of asynchronous programming in Python. It includes:

- An explanation of asynchronous vs synchronous execution
- Examples of blocking and non-blocking code
- Using `async` and `await` keywords
- Creating coroutines with `async def`
- Running asynchronous code with `asyncio.run()`

See [0-basic_async_syntax.py](0-basic_async_syntax.py) for examples.

### 1. Async Comprehensions

This task explores how to use asynchronous comprehensions in Python. It covers:

- `async for` loops to iterate over asynchronous iterators
- `async with` blocks for asynchronous context managers
- `async comprehension` for creating asynchronous generator expressions

See [1-async_comprehension.py](1-async_comprehension.py) for examples.

### 2. Run time for four parallel comprehensions

This task measures the runtime for four different asynchronous comprehensions executed in parallel. The comprehensions generate 10 random numbers using the `random` module.

See [2-measure_runtime.py](2-measure_runtime.py) for the implementation and timing measurements.

### 3. Tasks

This task demonstrates using the `asyncio.Task` class to schedule coroutine execution. It includes:

- Creating tasks from coroutines 
- Running tasks concurrently with `asyncio.gather()`
- Handling exceptions from tasks

See [3-tasks.py](3-tasks.py) for examples.

### 4. Tasks

This task explores scheduling tasks with asyncio and tracking their state. It covers:

- Task states: pending, done, cancelled
- Calling `task.cancel()` to cancel a task
- Using `asyncio.as_completed()` to process tasks as they complete

See [4-tasks.py](4-tasks.py) for implementation details.

## Resources

- [Async IO in Python: A Complete Walkthrough](https://realpython.com/async-io-python/)
- [asyncio - Asynchronous I/O](https://docs.python.org/3/library/asyncio.html)

## Tasks To Complete

+ [x] 0. **The basics of async**<br/>[0-basic_async_syntax.py](0-basic_async_syntax.py) contains an asynchronous coroutine that takes in an integer argument (`max_delay`, with a default value of 10) named `wait_random` that waits for a random delay between 0 and `max_delay` (included and float value) seconds and eventually returns it. The `random` module should be used.

+ [x] 1. **Let's execute multiple coroutines at the same time with async**<br/>[1-concurrent_coroutines.py](1-concurrent_coroutines.py) contains a script that meets the following requirements:
  + Import `wait_random` from the previous python file that you’ve written and write an async routine called `wait_n` that takes in 2 int arguments (in this order): `n` and `max_delay`. You will spawn wait_random n times with the specified `max_delay`.
  + `wait_n` should return the list of all the delays (float values). The list of the delays should be in ascending order without using `sort()` because of concurrency.

+ [x] 2. **Measure the runtime**<br/>[2-measure_runtime.py](2-measure_runtime.py) contains a script that meets the following requirements:
  + From the previous file, import `wait_n` into [2-measure_runtime.py](2-measure_runtime.py).
  + Create a `measure_time` function with integers `n` and `max_delay` as arguments that measures the total execution time for `wait_n(n, max_delay)`, and returns `total_time / n`. Your function should return a float.
  + Use the `time` module to measure an approximate elapsed time.

+ [x] 3. **Tasks**<br/>[3-tasks.py](3-tasks.py) contains a script that meets the following requirements:
  + Import `wait_random` from [0-basic_async_syntax](0-basic_async_syntax).
  + Write a function (do not create an async function, use the regular function syntax to do this) `task_wait_random` that takes an integer `max_delay` and returns a `asyncio.Task`.

+ [x] 4. **Tasks**<br/>[4-tasks.py](4-tasks.py) contains a script that meets the following requirements:
  + Take the code from `wait_n` and alter it into a new function `task_wait_n`. The code is nearly identical to `wait_n` except `task_wait_random` is being called.


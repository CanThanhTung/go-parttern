<h1 align="center">Go Patterns</h1>
<h3 align="center">
  <img src="assets/images/BATMAN_GOPHER.png" height="350px">
</h3>
<h1 align="center"></h1>

Tổng hợp các design & application patterns cho Go language.

### Creational Patterns

|                      Pattern                       | Description                                                                           | Status |
|:--------------------------------------------------:|:--------------------------------------------------------------------------------------|:------:|
|        [Singleton](creational/singleton.md)        | Hạn chế khởi tạo một type của một Object                                              |   ✔️    |
|          [Builder](creational/builder.md)          | Build một object phức tạp từ những simple objects                                     |   ✔️    |
|   [Factory Method](creational/factory-method.md)   | Trì hoãn việc khởi tạo một Object thành một function chuyên biệt để tạo các instances |   ✔️    |
|        [Prototype](creational/prototype.md)        | Tạo các objects từ việc sao chép một đối tượng hiện có                                |   ✔️    |
| [Abstract Factory](creational/abstract-factory.md) | Cung cấp một interface để tạo families của releated objects hoặc dependent objects    |   ✔️    |
|      [Object Pool](creational/object-pool.md)      | Khởi tạo và duy trì một nhóm các objects cùng loại                                    |   ✔️    |
|              [Dependency Injection]()              | Truyền dependency vào các objects hoặc framework khác                                 |   ✖️    |

### Structural Patterns

|    Pattern    | Description | Status |
|:-------------:|:-------------|:------:|
| [Composte]()  |             |        |
|  [Adapter]()  |             |        |
|  [Bridge]()   |             |        |
|   [Proxy]()   |             |        |
|  [Facade]()   |             |        |
| [Decorator]() |             |        |
| [Flyweight]() |             |        |

### Behavioral Patterns

|           Pattern           | Description | Status |
|:---------------------------:|:-------------|:------:|
|        [Strategy]()         |             |        |
| [Chain of Responsibility]() |             |        |
|         [Command]()         |             |        |
|        [Template]()         |             |        |
|         [Memento]()         |             |        |
|       [Interpreter]()       |             |        |
|         [Visitor]()         |             |        |
|          [State]()          |             |        |
|        [Mediator]()         |             |        |
|            []()             |             |        |

## Synchronization Patterns

|                           Pattern                            | Description                                                                                        | Status |
|:------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------|:------:|
| [Condition Variable](/synchronization/condition_variable.md) | Provides a mechanism for threads to temporarily give up access in order to wait for some condition |   ✖️    |
|           [Lock/Mutex](/synchronization/mutex.md)            | Enforces mutual exclusion limit on a resource to gain exclusive access                             |   ✖️    |
|            [Monitor](/synchronization/monitor.md)            | Combination of mutex and condition variable patterns                                               |   ✖️    |
|    [Read-Write Lock](/synchronization/read_write_lock.md)    | Allows parallel read access, but only exclusive access on write operations to a resource           |   ✖️    |
|          [Semaphore](/synchronization/semaphore.md)          | Allows controlling access to a common resource                                                     |   ✔️    |

## Concurrency Patterns

|                          Pattern                           | Description                                                                                                                                    | Status |
|:----------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------------------------------------------|:------:|
|            [N-Barrier](/concurrency/barrier.md)            | Prevents a process from proceeding until all N processes reach to the barrier                                                                  |   ✖️    |
| [Bounded Parallelism](/concurrency/bounded_parallelism.md) | Completes large number of independent tasks with resource limits                                                                               |   ✔️    |
|           [Broadcast](/concurrency/broadcast.md)           | Transfers a message to all recipients simultaneously                                                                                           |   ✖️    |
|          [Coroutines](/concurrency/coroutine.md)           | Subroutines that allow suspending and resuming execution at certain locations                                                                  |   ✖️    |
|          [Generators](/concurrency/generator.md)           | Yields a sequence of values one at a time                                                                                                      |   ✔️    |
|             [Reactor](/concurrency/reactor.md)             | Demultiplexes service requests delivered concurrently to a service handler and dispatches them syncronously to the associated request handlers |   ✖️    |
|         [Parallelism](/concurrency/parallelism.md)         | Completes large number of independent tasks                                                                                                    |   ✔️    |
|   [Producer Consumer](/concurrency/producer_consumer.md)   | Separates tasks from task executions                                                                                                           |   ✖️    |

## Messaging Patterns

|                       Pattern                        | Description                                                                               | Status |
|:----------------------------------------------------:|:------------------------------------------------------------------------------------------|:------:|
|            [Fan-In](/messaging/fan_in.md)            | Funnels tasks to a work sink (e.g. server)                                                |   ✔️    |
|           [Fan-Out](/messaging/fan_out.md)           | Distributes tasks among workers (e.g. producer)                                           |   ✔️    |
| [Futures & Promises](/messaging/futures_promises.md) | Acts as a place-holder of a result that is initially unknown for synchronization purposes |   ✖️    |
| [Publish/Subscribe](/messaging/publish_subscribe.md) | Passes information to a collection of recipients who subscribed to a topic                |   ✔️    |
|        [Push & Pull](/messaging/push_pull.md)        | Distributes messages to multiple workers, arranged in a pipeline                          |   ✖️    |

## Stability Patterns

|                     Pattern                      | Description                                                                                                                                   | Status |
|:------------------------------------------------:|:----------------------------------------------------------------------------------------------------------------------------------------------|:------:|
|       [Bulkheads](/stability/bulkhead.md)        | Enforces a principle of failure containment (i.e. prevents cascading failures)                                                                |   ✖️    |
| [Circuit-Breaker](/stability/circuit-breaker.md) | Stops the flow of the requests when requests are likely to fail                                                                               |   ✔️    |
|        [Deadline](/stability/deadline.md)        | Allows clients to stop waiting for a response once the probability of response becomes low (e.g. after waiting 10 seconds for a page refresh) |   ✖️    |
|       [Fail-Fast](/stability/fail_fast.md)       | Checks the availability of required resources at the start of a request and fails if the requirements are not satisfied                       |   ✖️    |
|     [Handshaking](/stability/handshaking.md)     | Asks a component if it can take any more load, if it can't, the request is declined                                                           |   ✖️    |
|    [Steady-State](/stability/steady_state.md)    | For every service that accumulates a resource, some other service must recycle that resource                                                  |   ✖️    |

## Profiling Patterns

|                 Pattern                  | Description                             | Status |
|:----------------------------------------:|:----------------------------------------|:------:|
| [Timing Functions](/profiling/timing.md) | Wraps a function and logs the execution |   ✔️    |

## Idioms

|                      Pattern                       | Description                                                           | Status |
|:--------------------------------------------------:|:----------------------------------------------------------------------|:------:|
| [Functional Options](/idiom/functional-options.md) | Allows creating clean APIs with sane defaults and idiomatic overrides |   ✔️    |

## Anti-Patterns

|                          Pattern                           | Description                                                                                         | Status |
|:----------------------------------------------------------:|:----------------------------------------------------------------------------------------------------|:------:|
| [Cascading Failures](/anti-patterns/cascading_failures.md) | A failure in a system of interconnected parts in which the failure of a part causes a domino effect |   ✖️    |

#Full-stack Developer Interview Questions and Answers

This repo contains a number of full-stack developer interview questions that can be used when vetting potential candidates.

## <a name='toc'>Table of Contents</a>

  1. [General Questions](#general)
  1. [Architecture](#architecture)
  1. [WEB](#web)
  1. [SQL](#sql)
  1. [NoSQL](#nosql)
  1. [Networking](#networking)s
  1. [Scalability](#scalability)
  1. [Load balancing](#load-balancing)
  1. [Transcations](#transcations)
  1. [Concurrency](#concurrency)
  1. [Distributed](#distributed)
  1. [Cache](#cache)
  1. [Operating system](#os)
  1. [Java](#java)
  1. [Javascript](#javascript)
  1. [Python](#python)
  1. [C++](#cpp)
  1. [Code writing](#code)
  1. [Agile, Scrum, XP](#agile)
  1. [Git](#git)
  1. [QA](#qa)
  1. [Algorithms](#algorithms)
  1. [UML](#uml)
  1. [Other](#other)
  1. [Machine learning](#machine-learning)
  1. [Cryptography](#cryptography)

####[[⬆]](#toc) <a name='general'>General Questions:</a>
* What is *polymorphism*? (Variable of type Shape could refer to an object of type Square, Circle... Ability of a function to handle objects of many types)
* What is *encapsulation* (Packing of data and functions into a single component)
* What is *inversion of control*? (A design in which custom-written portions of a computer program receive the flow of control from a generic, reusable library)
* What is tail recursion? (A tail call is a subroutine call performed as the final action of a procedure)
* What is *virtual function*?
* What is *virtual method table*?
* What is *dynamic binding*?(Actual method implementation invoked is determined at run time based on the class of the object, not the type of the variable or expression)
* How does *garbage collector* work? (Mark and sweep: mark: traverse object graph starting from root objects, sweep: garbage collect unmarked objects. Optimizations: young/old generations, incremental mark and sweep)
* What is *semantic versioning*?
* What is *Blue-green Deployment*, *Canary release*?
* What is *A/B testing*?
* What is stub and mock? (A stub is a test double with preprogrammed behavior. Mocks are stubs with preprogrammed expectations.)

####[[⬆]](#toc) <a name='architecture'>Architecture:</a>
* *Design principles*. (SOLID, DRY, KISS, YAGNI, convention over configuration, separation of concerns, principle of least knowledge, tourist principle, single source of truth, single version of the truth)
* Benefits of *separation of concerns* (inversed)
  * Adding new features will take an order of magnitude longer
  * They’re impossible to optimize
  * They’re extremely difficult to test
  * Fixing and debugging can be a nightmare (fixing something in one place can lead to something else breaking that seems completely unrelated).

|Rule|Description|
|:--|:--|
|Single responsibility principle|A class should have one and only one task/responsibility. If class is performing more than one task, it leads to confusion.|
|Open/closed principle|The developers should focus more on extending the software entities rather than modifying them.|
|Liskov substitution principle|It should be possible to substitute the derived class with base class.|
|Interface segregation principle|It’s like Single Responsibility Principle but applicable to interfaces. Each interface should be responsible for a specific task. The developers should need to implement methods which he/she doesn’t need.|
|Dependency inversion principle|Depend upon Abstractions- but not on concretions. This means that each module should be separated from other using an abstract layer which binds them together.|

* *Design patterns*. (Creational:Builder,Object Pool,Factory Method,Signleton,Multiton,Prototype,Abstract Factory.Structural:Adapter,Bridge,Composite,Decorator,Facade,Flyweight,Proxy.Behavioral:Chain of Responsibility,Command,Interpreter,Iterator,Mediator,Memento,Observer,State,Strategy,Template Method,Visitor.)
* *Integration patterns*, SOA patterns.
* 3-tier architecture? (Presentation tier, Application tier, Data tier)
* 3-layer architecture? (DAO (Repository), Business (Service) layer, Controller)
* What is REST?
* What is *idempotent* operation? (The PUT and DELETE methods are referred to as idempotent, meaning that the operation will produce the same result no matter how many times it is repeated)
* What is *nullipotent* operation? (GET method is a safe method (or nullipotent), meaning that calling it produces no side-effects)
* Naked objects, Restful objects.
* What is *aspect-oriented programming*?
* Why do you need *application server*?
* *Inheritance* vs *Composition*.(inheritance - is-a relationship, whether clients will want to use the subclass type as a superclass type).
* *Multiple inheritance problem*.
* What is *uniform access principle*?(client code should not be affected by a decision to implement an attribute as a field or method)
* Advantages of using *modules*. (reuse, decoupling, namespace)

####[[⬆]](#toc) <a name='web'>WEB:</a>
* WEB security vulnerabilities (XSS, CSRF, session fixation, SQL injection, man-in-the-middle, buffer overflow)
* CSRF prevention. (CSRF-token)
* What is *JSONP*, *CORS*? (A communication technique used in JavaScript programs running in web browsers to request data from a server in a different domain, something prohibited by typical web browsers because of the same-origin policy)
* HTTPS negotiation steps.
* What is HTTP Strict Transport Security (HSTS)? (Prevents Man in the Middle attacks)
* Browser-server communication methods: WebSocket, EventSource, Comet(Polling, Long-Polling, Streaming)
* What is *character encoding*?
* What is *role-based access controll* and *access control list*?
* What is session and persistent cookies, sessionStorage and localStorage?
* How to implement *remember-me*? (http://jaspan.com/improved_persistent_login_cookie_best_practice)
* Authentication using cookies, JWT (JSON Web Tokens).

####[[⬆]](#toc) <a name='sql'>SQL:</a>
* *SQL join types* (inner join, left/right outer join, full outer join, cross join)
* *SQL normal forms* (1.The domain of each attribute contains only atomic values, and the value of each attribute contains only a single value from that domain. 2.No non-prime attribute in the table is functionally dependent on a proper subset of any candidate key. 3.Every non-prime attribute is non-transitively dependent on every candidate key in the table. BCNF.Every non-trivial functional dependency in the table is a dependency on a superkey.)
* *Isolation levels* and Anomalies (Read Uncommitted, Read Committed, Repeatable Read, Serializable

|Isolation_level\Anomaly|Lost_update (because of rollback)|Dirty_read|Non_repeatable_reads second_lost_update|Phantoms|Write_skew|
|:---------------|:-------:|:-------:|:-------:|:-------:|:-------:|
|Read Uncommitted|-        |may occur|may occur|may occur|may occur|
|Read Committed  |-        |-        |may occur|may occur|may occur|
|Repeatable Read |-        |-        |-        |may occur|may occur|
|Repeatable Read |-        |-        |-        |may occur|may occur|
|Snapshot        |-        |-        |-        |-        |may occur|
|Serializable    |-        |-        |-        |-        |-        |

####[[⬆]](#toc) <a name='nosql'>NoSQL:</a>
* Types of NoSQL databases?
  * Document Stores (MongoDB, Couchbase)
  * Key-Value Stores (Redis, Volgemort)
  * Column Stores (Cassandra)
  * Graph Stores (Neo4j, Giraph)

####[[⬆]](#toc) <a name='networking'>Networking:</a>
* OSI model (Physical, Data link, Network, Transport, Session, Presentation, Application)
* Multithreading vs select
* Swith, hub, router.
* TCP congestion.

####[[⬆]](#toc) <a name='scalability'>Scalability:</a>
* Horizontal and vertical scaling.
* How to scale database? (Data partitioning, sharding, replication(master-slave, master-master)).
* What is *synchronous multimaster replication*? (Each server can accept write requests, and modified data is transmitted from the original server to every other server before each transaction commits)
* What is *synchronous multimaster replication*? (Each server works independently, and periodically communicates with the other servers to identify conflicting transactions. The conflicts can be resolved by users or conflict resolution rules)
* *Denormalization*.
* When to use messaging queue?
* Hadoop basics.
* storing sessions in Redis.
* MongoDB, Redis.

####[[⬆]](#toc) <a name='load-balancing'>Load balancing:</a>
* What is *cloud computing*? (Cloud computing platform is a fully automated server platform that allows users to purchase, remotely create, dynamically scale, and administer system)
* sticky/non-sticky sessions

####[[⬆]](#toc) <a name='transactions'>Transactions:</a>
* What ACID?
* What is 2-phase, 3-phase commit?
* What is pessimistic/optimistic locking?

####[[⬆]](#toc) <a name='distributed'>Distributed:</a>
* What is *CAP theorem*? (it is impossible for a distributed computer system to simultaneously provide all three of the following guarantees: *consistency*, *availability*, *partition tolerance*) ![CAP theorem](http://guide.couchdb.org/draft/consistency/01.png "CAP theorem")
* What is *map-reduce*? (Word count example)
* *Sharding counters*.
* Herlihy’s consensus hierarchy. Every shared object can be assigned a consensus number, which is the maximum number of processes for which the object can solve wait-free consensus in an asynchronous system.
```
1 Read-write registers
2 Test-and-set, swap, fetch-and-add, queue, stack
⋮ ⋮
∞ Augmented queue, compare-and-swap, sticky byte
```

####[[⬆]](#toc) <a name='cache'>Cache:</a>
* What is *write-through* and *write-behind* caching? (write-through (synchronous), write-behind (asynchronous))
* HTTP cache options?

####[[⬆]](#toc) <a name='concurrency'>Concurrency:</a>
* What is *deadlock*, *livelock*? (Deadlock is a situation in which two or more competing actions are each waiting for the other to finish, and thus neither ever does. A livelock is similar to a deadlock, except that the states of the processes involved in the livelock constantly change with regard to one another, none progressing.)
* Deadlock avoidance. (prevention, detection, avoidance (Mutex hierarchy), and recovery)
* What is *starvation*? ()
* What is *race condition*? (Behavior of software system where the output is dependent on the sequence or timing of other uncontrollable events)
* What is *happens-before* relation?
* What is *thread contention*? (Contention is simply when two threads try to access either the same resource or related resources in such a way that at least one of the contending threads runs more slowly than it would if the other thread(s) were not running). Contention occurs when multiple threads try to acquire a lock at the same time
* What is a *thread-safe function*? (Can be safely invoked by multiple threads at the same time)
* Publish/Subscripe code
* What is *2-phase locking*? (Growing phase, shrinking phase. Guarantees serializablity for transactions, doesn't prevent deadlock).
* What is the difference between *thread* and *process*? (Threads (of the same process) run in a shared memory space, while processes run in separate memory spaces)
* What is *false sharing*, *cache pollution*, *cache miss*, *thread affinity*, *speculative execution*, *ABA-problem*?
* What is *lock-free* and *wait-free* algorithm?
* What is *sequential consistency*? (The result of any execution is the same as if the operations of all the processors were executed in some sequential order, and the operations of each individual processor appear in this sequence in the order specified by its program).
* What is *memory barrier*? (A memory barrier, also known as a membar, memory fence or fence instruction, is a type of barrier instruction that causes a CPU or compiler to enforce an ordering constraint on memory operations issued before and after the barrier instruction)
* Synchonization aids
  * CountDownLatch
  * Barrier
  * CyclicBarrier
  * Phaser
  * ReentrantLock
  * Exchanger
  * Semaphore
  * LinkedTransferQueue
* What is *data race*? (When a program contains two conflicting accesses that are not ordered by a happens-before relationship, it is said to contain a data race. Two accesses to (reads of or writes to) the same variable are said to be conflicting if at least one of the accesses is a write)
* Java *memory model*. (A program is correctly synchronized if and only if all sequentially consistent executions are free of data races. Correctly synchronized programs have sequentially consistent semantics. Causality requirement for incorrectly synchronized programs. https://dl.dropboxusercontent.com/u/1011627/journal.pdf)
* What is *monitor* in Java? (Each object in Java is associated with a monitor, which a thread can lock or unlock)
* What is *safe publication*?
* What is *wait*/*notify*?
* *Amdahl's law*? (Speedup = 1 / (1 - p + p / n))
* *Dining philosophers problem*.
* *Produces/consumer* problem.
* *Readers/writers* problem.
* *Consensus number*. Maximum number of threads for which objects of the class can solve consensus problem.

####[[⬆]](#toc) <a name='os'>Operating system:</a>
* What is *memory mapped* file and its benefits?
* *Interprocess communication* methods. (Pipes, Events, Mailboxes/Ports (can be implemented by using shared memory and semaphores), Direct Message Passing).
* *Virtual memory* organization.

####[[⬆]](#toc) <a name='java'>Java:</a>
* *WeakReference*, *SoftReference*, *PhantomReference*, *finalize()*, *ReferenceQueue*.
* How to correctly stop a thread? (Thread.interrupt())
* What is *Spring*? (Spring Framework is an application container for Java that supplies many useful features, such as Inversion of Control, Dependency Injection, abstract data access, transaction management, and more)
* What is *Hibernate* (Caches, lazy-loading)?
* How to write *benchmarks*? 
* What is OSGI? (Specification describes a modular system and a service platform for the Java programming language that implements a complete and dynamic component model. Each bundle has its own classpath. Dependency hell avoidance. META-INF/MANIFEST.MF contains OSGI-info)
* What is JMS?
* Serializable / Externalizable
* What is a *servlet* (versions of servlet api)?
* What is a *servlet filter*? How to implement *GZipFilter*? (ResponseWrapper)
* What is *generics* and PECS (producer extends and consumer super)?
* What is *DAO* (Data Access Object)? (DAO allows one to switch between technologies like JDBC, Hibernate, JPA or JDO fairly easily)
* What is the difference between <?> and <Object>?
* XML: SAX, DOM, StAX

####[[⬆]](#toc) <a name='javascript'>Javascript:</a>
* this keyword
* How *prototypes* work?
* inheritance 
* differences between == and === (http://dorey.github.io/JavaScript-Equality-Table/)
* closures
* What is *MVC*, *MVP*, *MVVM*?
* What is *promise*?
* What is event *bubbling* and *capturing*? (target.addEventListener(type, listener[, useCapture]))
* What is *AMD*(Asynchronous Module Design) and *CommonJS*?
* What is *jQuery*?

####[[⬆]](#toc) <a name='codewriting'>Codewriting:</a>
* Implement expression parser
* Implement quick sort
* Implement overflow resilient binary search
```java
// 000[1]11
public static int binarySearchFirstTrue(IntPredicate predicate, int fromInclusive, int toExclusive) {
    while (fromInclusive < toExclusive) {
        // see {@link com.google.common.math.IntMath#mean}
        int mid = (fromInclusive & toExclusive) + ((fromInclusive ^ toExclusive) >> 1);
        if (!predicate.test(mid))
            fromInclusive = mid + 1;
        else
            toExclusive = mid;
    }
    return toExclusive;
}
```
* Implement Longest increasing subsequence size
```java
public static int lisSize(int[] a) {
	int[] last = new int[a.length];
	Arrays.fill(last, Integer.MAX_VALUE);
	int len = 0;
	for (int v : a) {
		int pos = lower_bound(last, v);
		last[pos] = v;
		len = Math.max(len, pos + 1);
	}
	return len;
}
```

####[[⬆]](#toc) <a name='agile'>Agile:</a>
* What is Agile? ()
  * Individuals and interactions over Processes and tools
  * Working software over Comprehensive documentation
  * Customer collaboration over Contract negotiation
  * Responding to change over Following a plan
* What is Scrum? (Roles: product owner, development team, scrum master. Events: sprint, 
* What are the differences between Scrum and Waterfall? ( http://www.leanagiletraining.com/agile/waterfall-versus-scrum-how-do-they-compare/)
* What is XP? ()
* What is Lean, Kanban?

####[[⬆]](#toc) <a name='git'>Git:</a>
* *Git* workflow? (Master: production-ready state; Develop: latest delivered development changes for the next release; Feature Branches; Release Branches; Hotfixes) ![Git workflow](http://nvie.com/img/git-model@2x.png "Git workflow")

####[[⬆]](#toc) <a name='qa'>QA:</a>
* Unit tests advantages?
* Types of tests: acceptance testing, functional testing, smoke testing, regression testing, unit testing, integration testing, stress testing, (Load, Performance, Sanity, Stability, Security, Feature, Progression, Installation, Business).
* Differences between mock and stub?
* Selenium tests and webdriver.

####[[⬆]](#toc) <a name='algorithms'>Algorithms:</a>
* What is NP-completeness?

####[[⬆]](#toc) <a name='other'>Other:</a>
* How to find memory leak. (Memory snapshot diff).
* Profiling: sampling and instrumentation.
* Regular expressions. (Examples)
* XPath* 
* What are your goals to work in our company? (3 categories: professional, financial, social)
* What is *virtualization*? 
* What is total/partial order?

####[[⬆]](#toc) <a name='machine-learning'>Machine learning:</a>
* Bayes' theorem. P(A|B) = P(B|A)P(A)/P(B), P(B) = sum(P(Ai)P(B|Ai))

####[[⬆]](#toc) <a name='cryptography'>Cryptography:</a>
* What is *public key cryptography*?
* What is *public key certificate*?
* *RSA*
```
select 2 primes: p,q
n = p*q
phi(n) = (p-1)*(q-1)
select 1<e<phi(n), gcd(e,phi(n))=1
d=e^-1 mod phi(n)
(e,n) - public key
(d,n) - private key
c = m^e mod n
m = c^d mod n = m^(e*d) mod n = m^(e*d mod phi(n)) mod n = m
```

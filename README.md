#Full-stack Job Interview Questions and Answers

This repo contains a number of full-stack developer interview questions that can be used when vetting potential candidates.

## <a name='toc'>Table of Contents</a>

  1. [General Questions](#general)
  1. [WEB](#web)
  1. [SQL](#sql)
  1. [NoSQL](#nosql)
  1. [Networking](#networking)
  1. [Scalability](#scalability)
  1. [Concurrency](#concurrency)
  1. [Distributed](#distributed)
  1. [Operating system](#os)
  1. [Java](#java)
  1. [Javascript](#javascript)
  1. [Python](#python)
  1. [C++](#cpp)
  1. [Code writing](#code)
  1. [Agile, Scrum, XP](#agile)

####[[⬆]](#toc) <a name='general'>General Questions:</a>

* *Design principles*. (SOLID, DRY, KISS, YAGNI, convention over configuration, tourist principle)
* What is *polymorphism*? (Ability of a function to handle objects of many types)
* What is *encapsulation* (Packing of data and functions into a single component)
* What is *inversion of control*? (A design in which custom-written portions of a computer program receive the flow of control from a generic, reusable library)

####[[⬆]](#toc) <a name='web'>WEB:</a>

* WEB security vulnerabilities (XSS, CSRF, session fixation, SQL injection, man-in-the-middle, buffer overflow)
* CSRF prevention. (CSRF-token)
* What is *JSONP*? (A communication technique used in JavaScript programs running in web browsers to request data from a server in a different domain, something prohibited by typical web browsers because of the same-origin policy)
* HTTPS negotiation steps.

####[[⬆]](#toc) <a name='sql'>SQL:</a>

* *SQL join types* (inner join, left/right outer join, full outer join)
* *SQL normal forms*
* *Isolation levels* and Anomalies (Read Uncommitted, Read Committed, Repeatable Read, Serializable

|Isolation level \ Read phenomena|Dirty reads|Non-repeatable reads|Phantoms|
|:---------------|:-------:|:-------:|:-------:|
|Read Uncommitted|may occur|may occur|may occur|
|Read Committed  |-        |may occur|may occur|
|Repeatable Read |-        |-        |may occur|
|Serializable    |-        |-        |-        |

####[[⬆]](#networking) <a name='networking'>Networking:</a>
* OSI model (Physical, Data link, Network, Transport, Session, Presentation, Application)

####[[⬆]](#scalability) <a name='scalability'>Scalability:</a>
* sticky/non-sticky sessions
* Horizontal and vertical scaling

####[[⬆]](#distributed) <a name='general'>Distributed:</a>
* What is *CAP theorem*? (it is impossible for a distributed computer system to simultaneously provide all three of the following guarantees: *consistency*, *availability*, *partition tolerance*) ![CAP theorem](http://guide.couchdb.org/draft/consistency/01.png "CAP theorem")

####[[⬆]](#toc) <a name='concurrency'>Concurrency:</a>

* What is *race condition*? (Behavior of software system where the output is dependent on the sequence or timing of other uncontrollable events)
* What is *thread contention*? (Contention is simply when two threads try to access either the same resource or related resources in such a way that at least one of the contending threads runs more slowly than it would if the other thread(s) were not running)
* How to *avoid deadlock*? (Mutex hierarchy)
* What is a thread-safe function? (Can be safely invoked by multiple threads at the same time)

####[[⬆]](#toc) <a name='java'>Java:</a>

* WeakReference, SoftReference, PhantomReference
* What is *Spring*? (Spring Framework is an application container for Java that supplies many useful features, such as Inversion of Control, Dependency Injection, abstract data access, transaction management, and more)

####[[⬆]](#toc) <a name='javascript'>Javascript:</a>

* this keyword
* inheritance
* differences between == and ===
* closures

####[[⬆]](#toc) <a name='codewriting'>Codewriting:</a>

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

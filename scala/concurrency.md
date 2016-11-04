# A Hodgepodge Set of Concurrency Resources for Scala / AKKA

### Original article describing the Work Pulling Pattern with AKKA

[Akka Work Pulling Pattern to prevent mailbox overflow, throttle and distribute work](http://www.michaelpollmeier.com/akka-work-pulling-pattern)

### Excellent article describing the use of BalancingDispatcher to distribute work across a set of Actors

> First, take a quick look at the BalancingDispatcher. Essentially, it works by sharing a single Mailbox amongst all of its Actors. It doesn’t really “steal” work from its Actors; it just intelligently distributes that work by ensuring that the next message gets sent to an idle Actor, and if one isn’t available, then the message doesn’t get sent until that changes.

[Balancing Workload Across Nodes with AKKA 2](http://letitcrash.com/post/29044669086/balancing-workload-across-nodes-with-akka-2)


### Article by Manual Bernhardt about batch processing with AKKA

[Handful of AKKA Techniques](http://manuel.bernhardt.io/2014/04/23/a-handful-akka-techniques/)





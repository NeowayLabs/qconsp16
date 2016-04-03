# Top Performance Myths and Folklore

* Shared mutable state is evil
* Get better at doing simple things
* Have a good understand of TCP (TCP\_DELAY case)
* Use binary protocols (http2, protocol buffers, etc)
* Avoid copying stuff on memory defining good APIs (Golang excels on this :-)
* Use iterators (or Python generators for example) instead of lists
* Logs consumes a lot of resources, beware of that
* Use async log
* Records events as a high level entity not as an application log
* Records errors apart from application log (StatsD ?)
* Run profilers regularly


# Exercise failure at Netflix

* Vaccine metaphor: Inject bad stuff on the system to build resilience
* Run training drills when everything is ok. Calamity is not a good time for training.
* Always tries to degrade the service instead of going offline
* Sometimes you just cant degrade (video streaming for example)

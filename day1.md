# The future of your production environment is serverless


Lambda seems pretty magic to run stuff, already handles autoscaling.

Some cons:

* Lose too much control
* Dependency hell all over again (build zip with everything)
* Distance between prod/dev :-(
* Support to few languages only (no golang :-()


# The Spotify Playbook


## Struggles


### Deadlines

* Integrating with hardware vendors (add support to devices)
* Hard deadlines, defined on advance
* Put spotify on as much devices as possible generates too much WIP


### Assume people knows agile

* Just dont assume stuff :-)


## Wins

* Radical transparency (even on business stuff)
* Changes how the employee see the company
* Builds trust
* Empower developer
* Self organize
* Allow people to choose on what they want to work
* Continuous improvement :P


## Why different ?

* We use our product (dog food)
* Try to behave as a startup
* Internal open source model (everything is public within the company)
* Anyone can pull request on any project
* Favors people that take risks
* Counter intuitive bets (very different model than iTunes on start)
* Deliberate focus on culture (workshops, talks, constantly iterating)
* Train people on how to give feedback
* Celebrates failure (blog posts about it :-)
* Simple rules
* No projects/budgets/project managers
* Management happens within the team
* Team that goes around fixing flaky tests :-)
* Highly technical PO's
* Two hackweeks per year
* Humble leadership
* Flat consensus driven people (swedish)
* Hire globally
* Take away all excuse for you not succeed


## How?

* Trust your teams
* Serve your teams
* Empower your teams
* Then get out of their way :-)


# Microservices: aumentando a resiliencia na moip


* moip v2
* monolith saving all in my.sql
* need of high availability
* lack of orthogonality, generating reports made payment to stop working
* this is not awesome on black friday :-)
* microservices helped them get orthogonality
* better resilience, locks and outages are localized, not global
* incremental approach, one service at a time being extracted from the monolith
* easier to test


## Challenges

* Handling failures
* High latency (chatty APIs)
* Handling eventual consistency
* Use sampling comparing my.sql and elasticsearch to check for consistency
* monitoring: sentry
* easy to test is isolation, harder to test end to end
* monitoring: statsd, graphite, librato, ELK
* devops: infrastructure as code
* automate everything
* devs fazem deploy em PROD
* use containers to close dev <-> prod gap


## Questions

* How much time took the full migration ?


# Shopify at scale

Infrastructure and development platform


## Infrastructure

* Each shop is isolated from others (each one is a pod)
* It is NOT a Kubernetes pod
* They share the workers to avoid having to pre allocate resources
* Lua nginx module :D
* Proxy scheme like kubernetes :-), but on domain level


## Development


* Fallbacks: go to a degraded functionality, instead of breaking/exploding
* Orthogonality: One service cant bring everything down
* Make it easier to do the right thing, and hard to do the wrong one
* Resiliency matrix
* Talked a lot about the benefits of using a tool like toxyproxy
* Better than mocking since it acts on TCP level, uncovers lots of integration problems
* BuildKite, ShipIt
* No QA (code reviews + testing + incremental changes)
* No releases
* Devs deploy on first day
* 10m from merge to deploy
* Setting up development environment = one command
* Define load SLA
* Load test tool: Genghis
* Prove your load SLA


# Elixir: tolerancia a falhas para adultos


* Moore law is no longer a low
* We have to leverage machine paralelism
* Here enters the old and good Erlang machine
* Talks a lot about how it thinks that multithreading stinks
* Talks about how event loops also stinks (check out papers)
* Erlang is pretty old and robust to build concurrent systems
* Erlang has green threads, each green thread has its own independent garbage collector


## Elixir highlights

* Pattern matching (function call, assignments, everywhere, reminds me of prolog)
* Pipelining of function calls
* Purely functional language, with immutability
* Seems to have good tooling already


## Papers

* [The problem with threads](http://www.eecs.berkeley.edu/Pubs/TechRpts/2006/EECS-2006-1.pdf)
* [Why events are a bad idea](http://www.cs.berkeley.edu/~brewer/papers/threads-hotos-2003.pdf)

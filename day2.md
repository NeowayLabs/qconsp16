# Disponibilidade e confiança no Nubank


## Resilience

* For each service define a good load SLA
* Throttle services on failure (Circuit breakers)
* Everything is asynchronous through queues


## Architectural Concerns

* Complexity
* Harder to test (more moving parts)
* Async is harder to test (queues for example)
* Single point of failure (the queue broker)


## Monitoring

* Rienmann (http://riemann.io/)
* Correlate business and system information


## Traceability

* Where the failure happened on a distributed system ?
* Correlation ID (CID)


# Cloud security and usable protections from real-world

* If you need to ssh in a machine your monitoring is wrong
* Export data from machines, so you dont have to access them (logs and stats)
* Think about insight without access
* You cut a lot of attack space with that :-)


## 30 day project

No machine lives more than 30 days, which means:

* Good automation (or insanity)
* Knowledge sharing
* More prepared for disaster recovery


## Projects

* [Self service IAM](https://github.com/coinbase/self-service-iam)

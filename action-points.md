# Data pirates

* For each service define a good load SLA
* Throttle services on failure (check [go-resiliency](https://github.com/eapache/go-resiliency)
* Configure proper healthcheck on services (Kubernetes integration)
* Use toxyproxy project to automate tests on blackpearl connection problems
* Stress our entire new architecture with multiple failure modes and see if it cracks :-)

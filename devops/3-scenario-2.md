# Part 3 - Scenario 2: Memory Intensive Container

Somewhere in our fleet of containers there is a rogue agent that is using memory at an alarming rate.

Using either [Grafana](http://graphs.workshop.devops.beekeeper.rocks) or [Prometheus](http://metrics.workshop.devops.beekeeper.rocks), see if you can find the culprit.


## Tips
Try typing _memory_ in the query field and let the autocomplete help you find the _container_.

There will be a lot of noise as we record many metrics. You can filter the metrics by doing things like:
    
    
    metric_name{namespace!="",namespace!~".*-system", container_name!="POD"}

This will remove all metrics with no associated namespace or in a namespace reserved for system components.

Don't forget that `sum`, `rate` and `by` are your friends.

## Exercise

- Can you find the guilty namespace?

memory-leak
- Can you find the guilty pod?
memory-leak-59ff9fcfd5-4ds78 => memory-leak:python-processor

- What is interesting about the graph?

It is clearly a memory leak, it rises and falls again sharply - probably crashes.
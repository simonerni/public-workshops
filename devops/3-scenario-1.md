# Part 3 - Scenario 1: Find node with full disk

Somewhere in our fleet of containers there a node with a very full root mountpoint ("/")

Using either [Grafana](http://graphs.workshop.devops.beekeeper.rocks) or [Prometheus](http://metrics.workshop.devops.beekeeper.rocks), see if you can find the culprit.


## Tips
Try typing _node_ in the query field and let the autocomplete help you find the correct metric, play around with the time period to see if you are missing something.

## Exercise

- How much free disk space is left on the node?
around (8 GB)

- When did the high disk usage start?

Hmm. Hard to tell - maybe today around at 15:10, when the workshop started

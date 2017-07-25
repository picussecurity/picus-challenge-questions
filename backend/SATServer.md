# SAT Server

A boolean formula has this syntax:

```
b_prop ::= var | (b_prop OR b_prop) | (b_prop AND b_prop) | (NOT b_prop)
var    ::= lowercase strings
```

Implement a server that takes boolean formulae from clients and returns either a set of variable
assignments that makes the formula true, or "no solution".

Solving boolean formulae can take time, so the server should return a ticket to clients and clients
should check again later for the server's answer using the ticket.

Bonus: Server supports one more request. In this request client sends a boolean formula and a set of
substitutions. Server return “true” if the given substitution satisfies the formula, or “false”
otherwise. This mode is not asynchronous, e.g. server answers immediately.

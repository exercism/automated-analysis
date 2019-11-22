# Introduction to Representers

Representers have the single responsibility of taking a solution and returning a representation of it.

A _representation_ is an extraction of a solution to its essence with normalized names, comments, spacing, etc. but still uniquely identifying the approach taken. Two different ways of solving the same exercise must not have the same representation.

The most simple representer is one that just returns the solution's source code. However, as our goal is to have the same representation for solutions only differing in non-essential details, the representer should apply one or more [normalizations](./normalization.md).

Once we have a (normalized) representation for a solution, a team of vetted mentors will look at the solution and comment on it (if needed). These comments will then automatically be submitted to each new solution with the same representation. A notification will be sent for old solutions with a matching representation.

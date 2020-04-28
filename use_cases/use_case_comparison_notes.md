# Route data model use case comparison
Initial comparison between the route data model use cases from:
* [OGC API pilot](https://github.com/ogcincubator/route)
* [Transportation planning](Routes_TransportationPlanning_UseCase.md)

## Overview
Both models for routes are based on the assumption that a route is a linear path along the arcs of an underlying network of nodes, which are connected by arcs. This could also be multiple networks with shared nodes. Both models also have constructs to decompose a route into smaller segments.

The main differences are the result of the different use cases.

The OGC model has no connection between the route and the network elements used to create the route. The two main reasons are that a) route providers may not wish to share details of their underlying data and b) routes may come from many different route providers and clients should be able to process all of them in the same way.

The TPSO model has a close connection between the route and the underlying network, which is required for planning and simulation purposes. The use case also requires certain capabilities in the network model: representing changes in the network over time as well as separating the abstract network and the physical network, which includes details about physical aspects like directions, widths, etc.

## Summary Table

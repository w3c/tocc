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
| **TPSO Class** | **OGC Class** | **Similarities** | **Differences** |
| -- | -- | --- | --- |
| Route | Route Segment | can be composed into routes | TPSO doesn't distinguish between routes and route segments |
| NodePD | Waypoint | Indicate locations in a network <br> Mark beginning / end of routes | No notion of waypoint identity (the same waypoint at different times is a different waypoint?) <br> NodePD plays a role in defining the network as well whereas a Waypoint does not|
| TransportationComplex, <br> RoadSegment| RouteOverview| Representation of the physical route| The geometry is embedded in the definition of the RouteOverview whereas TransportationComplexes (e.g. road segments) are related to a location (Feature) that has a geometry.|
| Arc | RouteSegment | Describe part of a route| Arc describes only the network-specific information whereas RouteSegment includes route-specific data (e.g. duration)|
| Feature | Waypoint, <br> RouteOverview <br> RouteSegment | Describe a route’s (start and end) location| Feature is generic whereas the OGC concepts are route-specific with other attributes|

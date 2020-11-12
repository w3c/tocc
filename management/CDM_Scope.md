# City Data Model Scope

A city data model enables city software applications to share information, plan, coordinate, and execute city tasks, and support decision making, by providing a precise, unambiguous representation of information and knowledge commonly shared within and across city services. 

The city data model is stratified into three levels. The Foundation Level contains very general concepts such as time, location, and activity. The City Level contains concepts that  are common across multiple services such as households, services, and residents. The Service Level contains concepts commonly associated with a particular service but accessed by other services.  For example, a Transportation service may produce information, such as vehicular and transportation network data, that is accessed by other services.

The criterion for inclusion of concepts at the Foundation level are that they be independent of the city and service levels, but used by many of the concepts in these levels. The criterion for inclusion at the city level are that they be both read and updated by more than one service.  In other words the concepts are shared across multiple services. The criterion for inclusion at the service level is that the are "owned" by the service in the sense that they are instantiated and updated by the service, but can be read by other services. Concepts not used by other services are not part of the service level.

The scope is to simultaneously develop the three levels of the city data model, by analysing multiple services to guide what is included at each level.

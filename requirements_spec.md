# City Data Model / TOCC Collaboration Requirements

The purpose of this document is to identify the functionality required to support the standards coordination activities undertaken and designed by the TOCC.

## Goal
The goal of the TOCC is to coordinate and identify alignment between existing transportation-related standards. A key output of this work should be the emergence of a core model for the concepts that are shared across intersecting standards, as well as the identification for how the different standards intersect.

## Functional Requirements
To support collaboration for convergence on the core elements of a data model for transportation, the following functions are required:
1. Specification of use cases to provide context and motivate the need for elements of a standard.
2. Specify (parts of) standards - specifically data models - at the level of classes and properties.
3. Enable definition of classes and properties with DL and UML.
4. Enable specification of the relationship between model elements and use cases. 
5. Enable specification of relationships between classes and properties - within and between standards.
   * Relationships within a standard will typically be part of the (domain) model.
   * Relationships across standards will typically describe how the concepts are related.
6. Support for discussion on submitted content: use cases, definitions, and proposed relationships.
   * Question: One discussion thread per use case / class / property / definition / relationship or do we want multiple threads to separate discussion on separate topics?
   * Question: Do we need a capability to discuss topics that are not easily focussed on one element or do we then just pick the best guess?
7. Support navigation through and review of submitted content.
8. Support for some level of sanity checking for input.
9. Support for some level of user approval / membership control.
10. Support to enforce agreed-upon workflow (governance process).
11. Support for displaying where the different topics are in the process flow (e.g., using a kanban/project board or similar).
12. Publication of the core model of shared concepts.

## Non-functional Requirements
It is critical that the system and process be easy to use and participate in, in order to minimize barriers to participation and encourage quality contributions. To achieve this, the following characteristics are required:
1. Easy data input: multiple formats, linking to other sources, and an easy ability to reference/link to existing content (i.e. already defined terms) should be supported.
2. Clear data input guidance (e.g. with forms, etc). The nature of the input required should be clear to the user to avoid mistakes.
   * Question: I assume that it would also be ok, if this is not necessarily enforced (e.g., with the use of forms), but relies on broadly used practices? For example, data input could also be in something like Markdown based on templates (like GitHub supports for [issues](https://help.github.com/en/github/building-a-strong-community/configuring-issue-templates-for-your-repository))?
3. Clear process guidance. The process should be clear and enforced by the system to that users understand it and can contribute effectively.

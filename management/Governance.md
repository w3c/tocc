## Scope

This document defines how the content of the City Data Architecture is developed and managed.

The City Data Architecture defines data elements that are used within Smart City environments and provides context to this data by identifying:

- How the data is used to satisfy user needs
- How the logical data definitions are transformed to and from formats defined by interface specifications
- Metadata that specifies the semantics of the data and the rules for managing the data

Smart City environments are divided into multiple subdomains, such as transportation, health, governance, power, etc. The City Data Architecture is envisioned to document data that is shared across domains and within individual domain areas. It is recognized that data within a domain will likely only be of interest to those within that domain; as a result, the management structure is designed to accommodate the development of data definitions by those experts with a specific interest in the data out extensive bureaucratic overhead from other domains.

By adopting a model that establishes a common agreement on the semantics of data, various subdomains within a Smart City will be able to more easily share information with one another. The City Data Architecture does not attempt to define how to share this data (i.e., the syntax); it merely assists in integrating data from disparate protocols by defining common data semantics to which all protocol data can be mapped.

It is envisioned that existing protocols will define how to transform their data into the logical City Data Architecture format; by so doing, they will have clear transformation rule to share data with all other protocols that have defined transformation rules and data. Hopefully, new protocols will consider the content of the City Data Architecture prior to defining their own data and will be able to adopt formats that promote easy transformations.

The end result of the model will be to produce a data model that will facilitate data sharing among the many disparate systems that make up modern Smart Cities.

## Understanding the Model

While the primary goal of the City Data Architecture is to promote a common data model, learning the contents of a data model by itself is a bit like trying to understand a language by reading a dictionary. In practice, data models are most useful when presented in small chunks that can be directly related to a practical use of the data.

To promote comprehension, the City Data Architecture adopts a use-case approach to defining data. The use cases are defined within the Use Case View of the City Data Architecture using a standard template. Each use case identifies the data required by the use case and typically includes one or more class diagrams that depict the relationships among this data.

The Use Case View also includes hyperlinks into the Information View, which provides additional details about the data, including:

1. Detailed definitions of each data concept required by the use case
2. Diagrams depicting how this data relates to other data (e.g., data that might not be used by the specific use case)
3. Identification of specifications within the Specification View that define how the data is implemented in real-world interfaces
4. Links to outside resources that provides additional context for the data

The various parts of the City Data Architecture are summarized in Figure 1.

![](CDAOverview.png)

_Figure 1: City Data Architecture Overview_

## Contributing to the Model

The City Data Architecture is an open-source, collaborative product developed by and for the technical community that designs, develops, and maintains Smart City systems, including systems for any of the Smart City sub-areas, called domains.

### Approval Process

Submittals to the City Data Architecture can be made by any registered user of the cooperative environment. To register contact Mark Fox at the University of Toronto. Once registered, a user is able to select his or her domains of interest within the profile page of the website.

Registered users may submit:

- Proposals for any collaborative architecture element; these elements are fully documented and copyrighted as an integral part of the City Data Architecture
- Contributions for any catalogued architecture element; these elements remain copyrighted by their original source and the City Data Architecture might only include a reference to where the full definition can be found in the original source

All elements of the City Data Architecture, except for the External Specification elements, are collaborative elements. It is envisioned that External Specification elements will be submitted from multiple sources. Each source is likely to have its own copyright statement. If the source allows for reproduction of content, the submitter will be allowed to provide this content along with the copyright statement that applies to the content. Sources that do not allow for reproduction shall only be referenced using fair use of its content.

Submittals of collaborative elements follow the approval process described in Figure 2 and described below.

![](maturity.png)

_Figure 2: Maturity Levels of Model Elements_

An architectural element is initiated in the &quot;formulation&quot; state. Can the entry be viewed by others? Can others revise the content when in this state? Once the registered user has provided syntactically valid content for all mandatory fields for the element, the element will transition to the &quot;tentative&quot; state. Can the entry be viewed by others? Can others revise the content when in this state (or perhaps the originator can transfer ownership)? If others can see/edit, can they submit for review? Once the registered user is satisfied with the metadata entered for the architectural element in the &quot;tentative&quot; state, it may be submitted for review, whereupon it enters the &quot;proposed&quot; state. What happens if the user attempts to delete a mandatory item? Does the state revert to &quot;formulation&quot; or does the deletion fail (i.e., you allow change but not deletion)?

Upon each entry/re-entry into the &quot;proposed&quot; state, the revision number is incremented, and control of the element is passed to the appropriate domain data steward as defined by the domain and subdomain metadata for the element.

Version numbers shall be in the form of &quot;\&lt;major version\&gt;.\&lt;minor version\&gt;.\&lt;revision\&gt;-\&lt;state code\&gt;&quot;. Elements in the &quot;tentative&quot; state shall always be identified as version &quot;1.0.0-T&quot;; upon first entry into the &quot;proposed&quot; state, the element will be identified as version &quot;1.0.1-P&quot;.

The domain data steward will review the element to determine if the element is assigned to the proper domain and subdomain. At least once a month, each domain data steward shall provide a report to all other domain data stewards identifying the data concepts proposed within the domain and any recommendations to change these assigned domains. These reports shall be reviewed monthly by the domain data stewards. The domain data steward shall implement any change to the domain and subdomain as agreed to by a simple majority of the domain data stewards present.

Registered users can review and submit comments on any architectural element within the City Data Architecture with a state of &quot;proposed&quot; or above. Other registered users can respond to these comments. The preferred mechanism for submitting comments is to use the discussion forum on the architectural elements website page, but comments can also be verbally submitted during domain working group meetings. The domain data steward will guide these discussions towards resolution and make the changes that the working group agrees to. Each revision (or group of revisions performed in one action) to an architectural element will cause the element to be &quot;revised&quot; and re-enter the &quot;proposed&quot; state, whereupon the revision number is incremented.

Once the domain working group has completed its review of the element, it can either decide to reject the proposed element, whereupon it transitions to the &quot;closed&quot; state and is archived with the state code of &quot;R&quot;, or can accept the element, whereupon it transitions to the &quot;draft&quot; state. The state code for the &quot;draft&quot; state is &quot;D&quot; (e.g., a draft element might have a version number of &quot;1.0.13-D&quot;).

Comments received on elements in the &quot;draft&quot; state are handled in the same manner as with elements in the &quot;proposed&quot; state. If revisions are made, the element returns to the &quot;proposed&quot; state (whereupon the revision number is incremented) and may either remain there or may be elevated again by a new working group decision.

If an element in the &quot;draft&quot; state includes a reference to at least one specification model, it automatically transitions to the &quot;pendingApproval&quot; state, with the state code of &quot;pA&quot; (e.g., version number &quot;1.0.13-pA&quot;). Comments received on elements in the &quot;pendingApproval&quot; state are handled in the same manner as with elements in the &quot;proposed&quot; and &quot;draft&quot; states.

Once a quarter, the domain data steward shall provide a report to the domain working group that identifies elements that are in the &quot;pendingApproval&quot; state for the entire Smart City Architecture. Once a specific revision of an element has been in the pendingApproval state for at least 120 days without any comments or at least 180 days without any revisions, the working group may (but is not required) to promote the element to the &#39;approved&#39; state, with the state code of &quot;A&quot; (e.g., version number &quot;1.0.13-A&quot;). Comments received on elements in the &quot;approved&quot; state are handled in the same manner as with elements in the other states; however, upon exiting the &quot;approved&quot; state, the minor version number is incremented and the revision number is reset to zero. NOTE: The revision number is then incremented upon entering the &quot;proposed&quot; state, so the version number after &quot;1.0.13-A&quot; would be &quot;1.1.1-P&quot;.

The domain data steward will assess whether revised architectural elements are backward compatible with their previously approved versions. For elements that are not backward compatible, the domain data steward will increase the major version number to the first previously unused major version integer for the element; this act will automatically reset the minor revision number (e.g., &quot;1.1.1-P&quot; would likely become &quot;2.0.1-P&quot; unless a previous attempt to revise version &quot;1.0.13-A&quot; was unsuccessful – e.g., and resulted in &quot;2.0.10-R&quot; as an example – in which case, the version number would increment to the next unused major version – e.g., &quot;3.0.1-P&quot;).

The above should work pretty well, but we will have to consider how each correspondence rule might affect the revision process. For example, if I add a property to a class, does that count as a revision of the class? If I update a diagram to show the new element, does that affect every element that includes that diagram (or is the diagram its own separate element)?

### Preferred Sequence of Content

While contributions may be made in any order, the mandatory fields of elements are based on the general flow described in Figure 3.

![](process.png)

_Figure 3: Process for Adding Content_

The content of the City Data Architecture is intended to be based on use cases so that users of the architecture can understand the context in which data might be used by end systems. The use case is formally specified using the use case template as defined by the Use Case Specification Model Kind, which may include a use case diagram. The use case specification will eventually be supplemented with one or more Information Flow Class Diagrams but these might not be present upon initial submittal.

The use case specification includes the ability to link to external references to define the reference deployment architecture, which identifies the physical system components that exchange information to realize the use case and the descriptions of the flows between the components. This information can provide valuable context for how the use case is envisioned to be implemented, but it outside the scope of the City Data Architecture and the conventions used to document this information might vary by domain.

The next step in the process is to identify any existing specifications that have already defined data for this type of data or information flow. The goal of the City Data Architecture is to leverage existing efforts as much as possible, but there is recognition that in many cases, there are several existing standards that define the same core data. By identifying these various sources up front, we can gain a better understanding of where the entire industry is rather than basing our design off of a single effort.

Once we have identified various source specifications, we can begin the work of creating our City Data Model content. We start with defining the key terms (i.e., the classes within our model) and then continue to define the data elements (i.e., the properties of each class).

## Roadmap

The City Data Architecture is intended to specify the semantics of all data concepts that might be used within a Smart City environment, including data used within a single domain. This is a massive undertaking that will likely take decades to mature and will never be &quot;done&quot;. Managing such a large effort requires a management roadmap that identifies the major topics of current development and the major milestones along the way. This roadmap will be updated as the City Data Architecture matures and is highly dependent on the volunteer efforts from each domain.

The current roadmap focuses on activities to achieve the following major milestones in order or priority:

1. Defining the architecture framework for the City Data Architecture. This document will define the viewpoints, model kinds, and correspondence rules that will be used to document the City Data Architecture per ISO 42010. It will also clearly identify the fields that are deemed to be mandatory prior to elevating an element to the &quot;tentative&quot; state.
2. Defining the governance rules for the City Data Architecture as proposed by this document, which how content is contributed and approved for the architecture.
3. Developing prototype content to demonstrate how architectural elements should be captured within the City Data Architecture. The current intent is that this will focus on use cases related to routing (e.g., real-time navigational routing, pre-trip navigational routing, routing of public transport lines, etc.).
4. Developing specific domains based on volunteer activity. Interest has already been expressed for the following topics:
  1. Transportation planning
  2. Kerbside management
  3. Parking management
  4. Work zone management

## Support

How does one get support in contributing to the architecture?

## Credits

The City Data Model is managed and hosted by the World Wide Web Consortium (W3C), but it represents a collaborative effort of many partners, which currently includes:

- ISO/IEC JTC1 WG 11
- ISO TC 204
- ISO TC 211
- OGC
- W3C

## Copyright

The content of the City Data Architecture shall by copyrighted under the ??? License.
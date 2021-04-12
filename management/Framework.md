# City Data Model and Reference Architecture: Framework

## Scope of this document
This document defines the architectural framework of the City Data Model and Reference Architecture. This document is intended to be an [Evergreen Standard](Evergreen).

### Purpose of CDMRA

The purpose of the CDMRA is to:

1. assist experts in producing and building consensus around the definitions that are eventually captured in the city data model (CDM) portion of the CDMRA and
2. provide users of these data definitions the necessary context of the data so that they can fully appreciate the intent of the data.

These dual purposes are achieved by supplementing the CDM with the Use Case and Interface Specification Views, which provide justification and context for the data defined by the CDM.

The CDMRA formally defines the CDM; the other components of the CDMRA are only developed to the extent to support the needs of the CDM.

### Purpose of the CDM

The CDM enables city software applications to share information, plan, coordinate, and execute city tasks, and support decision making, by providing a precise, unambiguous representation of information and knowledge commonly shared within and across city services.

### Scope of services covered by the CDMRA (and CDM)

The CDMRA, and by inclusion the CDM, intends to provide a central reference for data definitions used within smart cities. However, it should be recognized that:

- smart cities encompass a huge number of potential services, including those for transport, health care, governance, power, etc.
- the CDMRA project is relatively new (starting in 2020)
- its content is dependent on the contributions of experts from the various areas of smart city services

As present, most of the work is focused on smart transport, including intelligent transport systems and transport planning, but the intent is to include all city services and experts from other service areas are encouraged to contribute.

In fact, the governance process envisioned by this document recognizes that the development of data definitions for any one smart city service often needs to consider the needs of other smart city services so that the data defined by one service can be reused by another. For example, a transport service might monitor the location of a vehicle, but a health care service might need access to that location information if a vehicle occupant has a health issue. If the two services are to be properly integrated, both the transport domain and the health care domain need to agree on how location should be defined, which requires experts from both domains to be involved in the definition of location data.

### Scope of technical specification

The CDMRA intends to define the semantics of city data to a level of detail such that it can be used as a reference for data transformations from one interface format to another. For example, it will define the meaning of data, the relationships among data, and the preferred units for data (or mechanisms for defining units of measure).

The CDM does not attempt to define representational form, encoding formats, or protocols used to exchange the data. However, before any element of the model is fully &quot;approved&quot;, at least one interface specification providing these rules must be identified and registered in the CDMRA. This ensures that the definitions provided in the model reflect real-world usage.

It is envisioned that data transformations will be defined to translate data from specific protocols into their corresponding data elements contained within the CDM. Such transformation rules will facilitate the unambiguous translation of data among different protocols and avoid mistakes in translations. The CDMRA collaboration environment makes provisions to store this type of information but this information is not currently the focus of the CDMRA development.

## Understanding the Model

While the primary goal of the CDMRA is to formally define the CDM, learning the contents of a data model by itself is a bit like trying to learn a language by reading a dictionary. In practice, data models are most useful when presented in small chunks that can be directly related to a practical use of the data.

To promote comprehension, the CDMRA adopts a use-case approach to defining data. The use cases are defined within the Use Case View of the CDMRA using a standard template. Each use case identifies the data required by the use case and typically includes one or more class diagrams that depict the relationships among this data.

The Use Case View also includes hyperlinks into the Information View, which provides additional details about the data, including:

1. Detailed definitions of each data concept required by the use case (the City Data Model)
2. Diagrams depicting how this data relates to other data (e.g., data that might not be used by the specific use case)
3. Links to each use case that uses each data element
4. Identification of interface specifications within the Interface View that define how the data is implemented in real-world interfaces
5. Links to outside resources that provide additional context for the data (e.g., external reference architectures)

The various parts of the CDMRA are summarized in Figure 1.

![](CDMRAOverview.png)

_Figure 1: City Data Model and Reference Architecture Overview_

## Terms and definitions

data

general term - we prefer data element or data instance to be precise\

data model

definition

data instance\

realization of a data element

data element

definition of a property of a class with a abstract syntax

information

text

knowledge

text

wisdom

text\

## Framework

The framework specification contained in this specification conforms to an *architecture framework* as specified in [ISO 42010](ISO42010). Specifically, the document identifies a set of *viewpoints*, each of which is designed to address a specific set of *concerns* held by *stakeholders*. The viewpoints are defined using *model kinds*, which specify modeling conventions to be used for specific presentations of the data. 

According to ISO/IEC/IEEE [ISO 42010](ISO42010), an architecture viewpoint establishes "the conventions for the construction, interpretation, and use of architecture views to frame specific system concerns."

An *architecture description* based on this framework will develop *models* conforming to the model kinds defined by this document and group the models into *views* that correspond to the viewpoints defined in this document. As multiple viewpoints might share similar concerns, the same model kinds and models can be referenced by multiple viewpoints and views.

The viewpoint specifications are based on the [Viewpoint Specification Template](Hilliard1). 

The Use Case Viewpoint specification has been developed in consideration of input based on [Hiiliard2](Hiiliard2), [Kruchten](Kruchten), and [IEEE2413](IEEE2413).

The Information Viewpoint specification was developed in consideration of the specifications defined in [Software Systems Architecture](Rozanski), the [Department of Defense Architecture Framework](DoDAF), [The Open Group Architecture Framework](TOGAF), and the [Zachman Framework](Zachman).

The Interface Specification Viewpoint was developed based on the needs of the CDMRA.

### Usage Viewpoint

#### Overview

The Usage Viewpoint defines the conventions for capturing how city data might be used to meet the needs of various system actors. 

#### Concerns and Stakeholders

Example stakeholders might include [Rozanski]:

-   Developers
-   System Administrators
-   Testers
-   Users

#### Concerns
The following table provides an overview of the staekholder concerns addressed by this viewpoint along with a specific reference to the model kind (and field) or correspondence rule that addresses the concern.

`Text presented as code indicates items that have not yet reached consensus.`

|Concern|Addressed by Model Kind|
|-------|-----------------------|
|What are the use cases that are driving the data definitions?|Use Case Specification: Name, Summary, Description, and Figures|
|Is the use case definition collaboratory or copyrighted elsewhere?|Use Case Specification: Use Case Licensing|
|What is the context of this use case?|Use Case Specification: Name (shown in structure), Description|
|Who are the participants for this use case?|Use Case Specification: Actors|
|What data needs to be exchanged among participants?|Use Case Specification: Information Requirements<br />`Use Case Specification: Required Classes`<br />`Use Case Specification: Required Object Properties`<br />`Use Case Specification: Required Data Properties`<br />`Unclear how the above can be traced meaningfully` `(i.e., class to property relationships)`<br />Use Case Specification: Figures|
|`What data needs to be generated/accessed` <br />`internally to the smart city system?`|`If we define internal flows, we need to define internal`<br /> `elements and this is no longer a use case specification - `<br />`but perhaps what we are trying to achieve is primarily `<br />`standardizing data among major system components. Thus, `<br />`perhaps we need at least a high-level deployment viewpoint `<br />`that at least identifies the major system components that `<br />`we will consider in our analysis. Actually, the best way `<br />`to handle this within the scope of our environment is to `<br />`define a separate use case where the boundary changes so `<br />`that one of the component systems is defined as an actor.`|
|What are the flow of events for each scenario associated with each use case?|Use Case Specification: Basic Flow of Events<br />Use Case Specification:Flow Exceptions|
|What are the outstanding issues with this use case?|Use Case Specification:Issues|
|What is the source of this use case?|Use Case Specification:Reference(s)|
|What standards/specifications exist related to this use case?|Use Case Specification:Specifications|
|How has this use case evolved over time?|Use Case Specification:Page History|
|What is the approval status of this use case?|Use Case Specification:Status|

#### Concerns not addressed

This viewpoint does not attempt to frame the following stakeholder
concerns:

- What non-participating stakeholders exist for this use case?

####Model Kinds

The usage viewpoint includes two defined model kinds:

- Use case specification model kind
- **Information flow class diagram model kind**

Each use case shall be associated with one use case specification model. Each use case specification model may include supplemental figures, which can include zero or more information flow class diagram models. Each information flow class diagram model depicts the information from the CDM that is used by the use case; information flow class diagram models are often associated with multiple use cases. 

`NOTE: Documenting as above implies that two use cases that use the same`
`information will each include the same information flow class diagram as` `static figures. As the CDM matures, these figures will not be automatically` `updated. As a result, they might become dated.`

Information flow class diagram models depict the content of the City Data Model; thus, the typical work flow is:

1. The use case specification is developed
2. A notional information flow class diagram is conceptualized (i.e., might not be shown within the CDMRA)
3. The notional information flow class diagram is harmonized with the existing content of the CDM (i.e., part of the Information View); this might entail adding new data elements to the CDM, revising existing data elements, and revising the notional information flow class diagram model to conform to the revised CDM
4. Developing a final information flow class diagram model 
5. `Linking (or with the revised flow, perhaps copying) the information flow` `class diagram model to the use case specification`

Thus, initial versions of a use case model are likely not to include an information flow class diagram model or might only include a notional diagram.  However, once fully specified, the use case model should provide `a link to the information flow class diagram model, which will be fully consistent` `with the content of the CDM.` The information flow class diagram model kind is a part of both the Use Case Viewpoint and the Information Viewpoint and is formally defined in the Information Viewpoint section. 


#### Use Case Model Kind

The use case model kind provides a template that is to be used to define all use cases defined within the Usage View. The template is defined as follows:

**Boldface text indicates items that have been approved but are not yet reflected in the online tool.** _Italicized text indicates items that equate to existing online tool fields where some minor change is still needed (e.g., name change of field)._ `Text presented as code indicates items that have not yet reached consensus.`

|Field|Description|Conformance|
|-----|-----------|-----------|
| _Use Case Name_ |Name of use case as a hierarchical field of the format<br /> \<Domain\>: \<Subdomains\>: \<Use Case\><br />The domain field should be one of the following strings: **????** <br />The subdomains field should indicate a hierarchical list of subdomains as defined by the domain.  |Mandatory|
| **Summary** |Short description (\<= 280 characters). <br />The summary should identify the goal and one or more value proposition(s) in the form **«[\<Verb\>] \<direct object\>»** <br />For example: <br />This use case describes how a user might plan a driving trip from a source to a destination. This use case focuses on ensuring the following user benefits: <ul><li>[Improve] travel efficiency</li><li>[Improve] driver expectations</li><li>[Reduce] driver confusion</li></ul>|Mandatory|
| _Description_ |A more extended description of the use case. The purpose of the CDMRA is to develop the data model, as such, the description does not need to provide full details, but it should provide sufficient context to provide insight into the data that needs to be exchanged and processed.|Mandatory|
| _Figures_ |An illustration that might assist the user in better understanding the scenario. The illustration should be explained by either the description or the flow of events.|Optional|
|Actors|Parties that directly interact with the system for this use case|Mandatory|
|Basic Flow of Events|The sequence of events that occur during the normal flow of this use case with any notes|Mandatory|
| **Flow Exceptions** |Highlighted alternative flow of events that reveal the need for additional data to be exchanged among the actors of the use case|Optional|
| **Information Requirements** |This is a very high-level description, for example, "origin location, destination location, and travel preferences". Details can be hashed out later and shown in the diagrams; this can be updated later to provide correspondence linkages to the defined data concepts in the Information View. While not technically required to define a use case, this field should be populated prior to beginning work on the data definitions|Optional|
|Required Classes|Links to CDM `Should this be linked with the following two so that we say something` `like "Vehicle.speed" with both Vehicle and speed linked to their` `respective attributes so that the reader understands that the` `"speed" attribute is describing "Vehicle"?.` Should eventually be populated once CDM contains data for use case.|Optional|
|Required Object Properties|Links to CDM. Should eventually be populated once CDM contains data for use case.|Optional|
|Required Data Properties|Links to CDM. Should eventually be populated once CDM contains data for use case.|Optional|
| **Issues** |Primarily to track issues during development `Perhaps link to github issues?`|Optional|
| **Reference(s)** |Source materials used to develop this use case|Optional|
|`Version`|`The date, version number, and status of the use case in the form` `YYYY-MM-DD #.#.#-S; See governance for details` `Do we need both version and status?`|Mandatory|
| **Status** |Approval status|Mandatory|
| **Specifications** |Link to reference architectures, standards and other resources that rely upon this use case definition|Optional|
| _License information_ |Indicate the owner and provide a reference to the copyright information|Mandatory|

##### `Operations for Use Case Models`

When initially creating a use case model, the following fields shall be populated, as a minimum, prior to considering the use case definition complete:

- Name
- Summary 
- Description
- Actors
- Basic flow of events
- Version
- Status
- License information

##### `Correspondence Rules for Use Case Models`

Each use case model shoulud eventually be linked to the CDM data concepts that are needed to implement the Information Requirements defined bty the use case. These linkages are stored within CDM by associating each required data concept to the use case(s) that use them.

#### `Operations for Naming Use Cases`

Use cases should be named so that users can easily search and find use cases within a long list. This document recommends using a standard list of subdomains for each domain. For example, in the case of the ITS domain, use cases should be categorized according to the services groupings defined in ISO 14813-1.

#### `Correspondence Rules for Usage Views`

The usage view includes the following correspondence rules with other views and resources:

- The domain and subdomain values used within each use case model should be selected from pre-defined lists
- Actors should be defined in a separately maintained list
- The source should cite a publicly available document
- The specicifications shall cite an entry in the specification view
- The information flow class diagram shall be a diagram showing only those elements from the Information View that are relevant to this use case
- The interaction diagram of the scenario model might also be contained within a deployment or similar view of another reference architecture

#### `Example`
|Field|Value|
|-----|-----------|
|Use Case Name|ITS: Traveller Information: Real-time route guidance and information: Dynamic in-vehicle route guidance using real-time information: Routing a vehicle between two known points|
|Summary|A traveler wants to identify options for travelling from an origin to a destination given a set of personal preferences and the likely duration of such a trip using different modes of travel.<ul><li>[Improve] transportation efficiency</li><li>[Improve] traveler expectations</li></ul>|
|Description|A traveler wishes to plan a trip from an origin to a destination and compare several options.  The trip may involve and/or compare multiple modes of transport. The traveler may define preferences up front and choose how to sort the options presented. The traveler might wish to refine the details of some or all of the trip legs prior to finalizing the selection. The proposed route might be visually displayed to the traveler, as in the illusrtation, to assist in selecting among the presented options.|
|Figures|![](TripIllustration.png)<br />_Figure 1: Route Options for Los Angeles Airport (LAX) to Hollywood Sign_<br />![Trip Planning Use Case](TripPlanningUseCase.png)<br />_Figure 2: Trip Planning Use Case_<br />![](TripPlanningSequence.png)<br />_Figure 3: Use case sequence diagram_|
|Actors|<ul><li>[Traveler](https://local.iteris.com/arc-it/html/physobjects/physobj64.html)</li><li>[`Traveler Support Equipment`](https://local.iteris.com/arc-it/html/physobjects/physobj72.html)</li><li>[`Personal Information Device`](https://local.iteris.com/arc-it/html/physobjects/physobj23.html)</li><li>[Transportation Information Center](https://local.iteris.com/arc-it/html/physobjects/physobj17.html)</li></ul>|
|Basic Flow of Events|<ol><li>Traveler signs into their account, if needed</li><li>Traveler inputs details of trip request through user interface</li><li>User interface optionally logs into user account at Traveler Information Center and/or provides user profile information</li><li>User interface device sends the specific trip request to a Transportation information Center</li><li>Transporation Information Center responds to the User Interface Decvice with a list of alternate trip plans</li><li>User interface presents the alternate trip plans to the traveler</li><li>The traveler optionally selects one of the trips and authorizes charges</li><li>The User Interface Device reserves the trip with the Transportation Information Center</li></ol>|
|Flow Exceptions|<ul><li>Traveler might revise preferences after seeing alternative trip plans.</li><li> Transportation Information Center might not be able to identify a viable route.</li></ul>|
|Information requirements|<ul><li>IN<ul><li>Origin</li><li>Destination</li><li>Traveler Preferences (optional)</li><li>Desired departure time (optional)</li><li>Desired arrival time (optional)</li></ul></li><li>OUT<ul><li>List of route alternatives</li></ul></li></ul>|
|Required Classes|<ul><li>[OGC:Route](http://citydata.utoronto.ca/index.php/Ogc:Route), [NavigationRoute](http://citydata.utoronto.ca/index.php/NavigationRoute)</li></ul>|
|Required Object Properties||
|Required Data Properties||
|Issues|The data for this use case has not been defined yet.|
|References|<ul><li>[ISO 14813-1:2015](https://www.iso.org/standard/57393.html) (defines subdomain/service)</li><li><span style="background:yellow">[ARC-IT 9.0: Infrastructure-Provided Trip Planning and Route Guidance](https://local.iteris.com/arc-it/html/servicepackages/sp163.html#tab-3) (sample physical view)</span></li></ul>|
|Version|2021-01-12 (0.0.3-D)|
|Status|draft|
|Specifications|<li>[SAE J2353](https://www.sae.org/standards/content/j2353_201906/) (defines data for traveler information) </li>|
|Licanese information|[W3C Document License](https://www.w3.org/Consortium/Legal/2015/doc-license)|

#### Notes
\<Any?\>

### Information Viewpoint

#### Overview

The Information Viewpoint frames how stakeholder concerns related to information will be addressed, especially those related to the structure, semantics, ownership, latency, and retention of information.

#### Stakeholders

The Information Viewpoint considers concerns from the following stakeholders:

1. Data custodians
2. Data stewards
3. Designers, developers, and integrators
4. System managers
5. Users, including
	1.  End users
	2.  Field support users
	3.  System operators
	4.  Administrative users
	5. Maintainers
	6. Testers
	7. Standardization bodies
	8. Privacy advocates

#### Concerns

The following table identifies the stakeholder concerns considered in the development of this viewpoint. Each concern is categorized into a generalized topic area and includes a reference to the model kind where the concern is addressed. 

`What data do we consider to be in scope of the CDMRA?`
`- Major business terms (i.e., object model classes); all, some, none?`
`- Data elements (i.e., class attributes); all, some, none?`
`- Associations (i.e., class associations); all, some, none?`
`- Metadata (i.e., details about data concepts); all, some, none?`

|Topic|Concern|Addressed by Model Kind|
-----|-------|-----------------------|
Data Definition|What are the definitions of the major business terms?|Vocabulary|
Data Definition|How do business terms relate to one another?|Ontology|
Data Definition|What does each data element mean?|Data Dictionary: Definition|
Data Definition|How does each data element relate to other data elements? (including dynamic metadata)|Logical Data Model|
Data Definition|What, if any, state behavior relationships are there for data and classes?|State Machine|
Data Definition|What is the representational form of the data within data exchanges? |Physical Data Model|
Data Definition|How can the information view be extended to support additional domain or implementation-specific data?|Operations on Views|
Data Definition|What are the key sources for the data definition?|Data Dictionary: |
Data Standardization|What functions use this data element?|Correspondence rule: users|
Data Quality|What are the constraints on data values?|Logical data model: Data element specification|
Data Integrity|How are inputs from multiple sources handled?|Logical data model: Class Model ??|
Data Availability|What data is required and under what conditions?|Correspondence rule|
Data Lifecycle|Who produces/writes the data?|Correspondence rule|
Data Lifecycle|Who consumes/reads the data?|Correspondence rule|
Data Conformance|What metadata must be supported and under what conditions?|Correspondence rule|
Data Conformance|What auditing trails are required?|Correspondence rule|
Data Evolution|How has the data model changed over time?|Correspondence rule|
Data Evolution|How does each data element relate to older versions?|Logical data model: Data element specification|
Data Evolution|What service was the data originally designed for?|Correspondence rule|
Data Evolution|What is the evolutionary history of the data element?|Correspondence rule|
Data Evolution|What is the status of the data definition?|Logical data model: Data element specification|
Data Evolution|When was the definition last modified?|Logical data model: Data element specification|
Data Evolution|What was the last change to the data definition?|Correspondence rule|



#### Concerns not addressed

This viewpoint does not attempt to frame the following stakeholder
concerns:

-   What operations can be supported for each data element or class?
-   How is data accessed/exchanged with internal and external systems?
-   How are access control rights are maintained (e.g., removing rights
    for a terminated employee)?
-   What are the physical infrastructure requirements (e.g., for data
    storage)?
-   What are the costs involved in deploying, operating and maintaining
    the data?
-   What potential legal liability is associated with maintaining data
    stores?
-   How are data sources located?
-   How are data ownership and access right conflicts resolved?
-   How does a user gain permission to access the data?
- What external policies and legislation needs to be considered for the
data? (e.g., GDPR)
- What information transfers use the data?
- Does the data represent sensitive information (e.g., personally
identifiable information)?
- What level of data access control is needed?
- How is data access controlled?
- What cybersecurity and data privacy standards apply? (NITS WP-692 Item
15)
- What are the data accuracy requirements?
- How is data quality captured (e.g., sensor issues, conflicts among
inputs, etc)?
- What measures are needed to detect and quash bad data?
- How are constraints on data values enforced (i.e., prevent buffer
overflow, invalid content, etc.)?
- How is bad or missing data reported?
- How is the data protected from unauthorized modification?
- How does a receiver validate that the information was produced by a
legitimate source? (e.g., a MAP message sent by an RSU)
- How quickly does the data age?
- How is the data kept up to date?
- How is outdated data flagged?
- How is data synchronized and conflicts resolved among multiple entities?
- What are the latency requirements for the data?
- Who last edited the data?
- When was the data last updated?
- Who has accessed the data?
- Who is responsible for data quality?
- Are there penalties for bad behavior (e.g., releasing data)? Who
decides/enforces? What are options?
- Where is the data stored (if at all)?
- What persistence requirements exist for the data?
- How is the data (and all copies) destroyed?
- What data must be supported by a device and under what conditions (e.g.,
for which services)?
- Does the data element need to be shared in an interoperable fashion? (or perhaps proprietary or out of scope)
- Does the data represent aggregated/fused data?
- Who has what rights to specific aggregated/fused data?
- What dynamic metadata exists regarding the employed analytic methods used to produce the aggregated/fused data?
- Can the algorithms and parameters used to aggregate/fuse the data be
controlled?
- Who owns the data?
- What rights does a user of the data have?
- What restrictions are there on the data (sharing, derived data, etc.)?
- What responsibilities does a data provider have?
- What responsibilities does a data consumer have?
- How are ownership and usage rights controlled, expressed, and exchanged?
- Does the data have safety-of-life implications?
- How is data transformed from one data exchange format into another?
- What known gaps/overlaps exist between the defined use cases and the existing data definitions?
- What interface standards include this data element?

These issues are left for domain, solution, or implementation-specific documentation.

#### Model Kinds

The Information Viewpoint consists of the following model kinds ([MK comment: I think we opted to omit some of these]):

-   Vocabulary Model Kind
-   Ontology Model Kind
-   Logical Data Model Kind
-   Data Dictionary Model Kind
-   State Machine Model Kind
-   Physical Data Model Kind

Model Kinds not included at present:

-   Data Ownership Model Kind
-   Information Lifecycle Model Kind
-   Timeliness and Latency Model Kind
-   Archive and Retention Model Kind

#### Vocabulary Model Kind

The Vocabulary Model Kind is used to provide formal definitions of key business terms. Formal definitions should be developed according to the principles defined in ISO 704. 

NOTE: This is roughly equivalent to IEEE 2413 semantic model kind

##### Conventions

The Vocabulary Model Kind is presented as a template providing the following static metadata for each entry.

-   Term
-   Definition

Optional static metadata for each entity and relationship includes\

-   Preferred Synonym(s)
-   Admitted Synonym(s)
-   Deprecated Synonym(s)
-   Note(s)
-   Example(s)

##### Operations

##### Correspondence Rules

##### Example



#### Ontology Model Kind\

The Ontology Model Kind is used to specify relationships among key business terms. It is roughly equivalent to IEEE 2413 semantic model kind.

##### Conventions\

The Ontology Model Kind is graphically represented using UML class diagrams and formally defined using RDF/XML (or perhaps we want to use the Functional-Style syntax defined in the OWL2 specification as it is more concise?). It is expected that there will be one (or perhaps a
small number of) RDF/XML file(s) while there will be a large number of ontology diagrams.

UML class diagrams should be limited to no more than 20 classes.

Define a UML class diagram profile

[MK comment: we also need to document the use of patterns as discussed at our last meeting (1/Apr/2021). Does this fit into the Information view? If so, is it part of the Ontology Model or something separate?]

##### Operations

##### Correspondence Rules


#### Logical Data Model Kind\

The Logical Data Model Kind is used to specify relationships among
entries contained within the LDD. \
 UML class diagram; three variations\

-   Class focus
-   Information flow focus (Information flow model kind of IEEE 2413)\
-   Component - Information flow focus

Attributes to be considered (somewhere)\

-   Does the data need to be stored with supplemental authentication
    information? E.g., an RSU might broadcast a MAP message to vehicles,
    but that MAP message must be signed by a mapping authority\

##### Conventions

Data element specification includes:\

-   Definition \
-   See ISO 14817-1\

##### Operations

##### Correspondence Rules
Each business entity shall trace to one entry within the Logical Data
Dictionary (LDD). The tool should default to having the link point to a
class in the Logical Data Dictionary having the identical name of the
business entity with the option to override this link to another class
or LDD entry.

#### Data Dictionary Model Kind\

The Data Dictionary Model Kind is used to specify static metadata about
data concepts. Data concepts include:

-   Class
-   Data object: characteristic of a class with an explicit value
    domain
-   Value domain: expression of the range of values that a
    characteristic can have
-   Information object: logical grouping of data elements that is useful
    for information storage or transfer

NOTE: A data object might be elemental in nature and represent a single
indivisible concept (e.g., Vehicle.speed:measure-mps), in which case it
is a data element. Alternatively, a data object might represent a
composition of information (e.g., Vehicle.position:GeoLocation3D, which
includes a latitude, longitude, and elevation), in which case it
represents an association role to another class.\

##### Conventions

Data concept specifications can include the following static metadata
based on type. Within the table, an "M" indicates that the metadata is
mandatory, an "O" indicates that it is optional, and a "N/A" indicates
that it is not applicable to the type of data concept. Metadata items
that are shown in italics indicate that the values represent
correspondences to another architectural element. Metadata options that
are shown with an optional plural name indicate that multiple instances
of the metadata item are allowed.\

|  Metadata|                     Class|   Data Object|   Value Domain|   Information Object|
|-----------------------------|--------|--------------|---------------|---------------------|
  Data Concept Type|            M|       M|             M|              M|
  ~~Identifier~~|                   M|       M|             M|              M|
  Version|                      M|       M|             M|              M|
  ~~Revision~~|                     M|       M|             M|              M|
  Name|                         M|       M|             M|              M|
  Definition|                   M|       M|             M|              M|
  Note(s)|                      O|       O|             O|              O|
  ~~Inspiration~~|                  O|       O|             O|              O|
  ~~Business Entity~~|              O|       N/A|            N/A|             N/A
  Generalized Class(es)|        O|       N/A|            N/A|             N/A
  ~~Abstract~~|                     M|       N/A|            N/A|             N/A
  Property(ies)|                O|       N/A|            O|              N/A
  State Machine|                O|       N/A|            N/A|             N/A
  Parent Class|                 N/A|      M|             N/A|             N/A
  Multiplicity|                 N/A|      M|             N/A|             N/A
  ~~Accuracy~~|                     N/A|      ?|             N/A|             N/A
  ~~Aging Rate~~|                    N/A|      ?|             N/A|             N/A
  ~~Value Domain~~|                  N/A|      M|             N/A|             N/A
  ~~Reverse Association Role~~|     N/A|      O|             N/A             N/A
  ~~Usage: service(s)~~|            N/A|      M|             N/A             M
  ~~Usage: external link(s)~~|      N/A|      O|             N/A             O|
  ~~Physical Representation(s)~~|   N/A|      O|             O|              N/A
  ~~Datatype~~|                      N/A|      N/A|            M|              N/A
  ~~Format~~|                        N/A|      N/A|            O|              N/A
  ~~Unit of Measure~~|               N/A|      N/A|            O|              N/A
  ~~Valid Value Rule~~|              N/A|      N/A|            O|              N/A
  Constraint                    N/A|      O|             O|              N/A
  ~~Precursor(s)~~|                  O|       O|             O|              N/A
  ~~Successor(s)~~|                  O|       O|             O|              N/A
  Data Elements(s)|             N/A |    N/A |          N/A |           M|
  Information Flow(s)|          N/A |    N/A |          N/A |           M|

##### Signer - metadata to be added for each information transfer(?)\

This identifies the physical object that has the authority to issue the
information object (i.e., which indicates who should sign the
information object).  \

##### Inspiration

Identifies the This includes both the identifier and name of a service
that uses the information as well as an assessment of how
safety-critical the information is.\

##### Usage: service

This includes both the identifier and name of a service that uses the
information as well as an assessment of how safety-critical the
information is.\

##### Usage: external link

This provides a link to an external resource that identifies an
architectural element that relies upon this information; it is coupled
with an assessment of how safety-critical the information is within the
context of that usage. Examples of external resources that might use
information defined within the information view include:\

-   A functional view process
-   A functional view data store\
-   A deployment view information flow (e.g., which might identify
    sources and sinks for the flow)\

##### Physical Representation\

This includes both the name of a corresponding data element contained in
a Physical Data Model coupled with a (preferably mathematical)
definition of how to transform the Physical Data Model data element into
the Logical Data Model data element.\

##### Operations



#### Information structure model kind

SysML Internal Block Diagram\
 IEEE 2413\

#### State Machine Model Kind

The State Machine Model Kind is used to specify the behavior of a class
as it transitions among various states.

##### Conventions

The state machine shall be defined using a UML State Machine diagram
accompanied by text explaining the bahavior of the class within each
state and the characteristics of each state transition. \

##### Operation

\

##### Correspondence Rules

\
 \

#### Physical Data Model

UML Class Diagram\
 Information flow based\

##### Conventions

##### Operations

##### Correspondence Rules

Each element of the PDM should trace to a element of the Logical Data
model with a justification for any transormation that needs to occur\

#### Data Ownership Model Kind

[[Rozanski]] provides the following \

RozanskiAndWoods-Architecture-Description-Template

If data is owned by more than one entity or part of the system, define
who owns which pieces of the data and explain how any resulting problems
will be handled.

In the example below, it can be seen that there are issues with entity 4
which can be updated by System D which is not the owner. The AD should
explain how this inconsistency will be managed.

**Entity**

**System A**

**System B**

**System C**

**System D**

**entity 1**

MASTER

r/o copy

reader

reader

**entity 2**

reader

MASTER

none

reader

**entity 3**

none

reader

MASTER

reader

**entity 4**

MASTER

none

none

reader\
 updater\
 deleter

#### Information Lifecycle Model Kind

#### Timeliness and Latency Model Kind\

If information needs to be copied around the system or is updated
regularly, explain how timeliness and latency requirements will be
addressed.\

#### Archive and Retention

Explain how will archive and retention requirements will be met by the
system.\

#### Operations on Views

#### Correspondence Rules

All information referenced in other views shall be consistent with the
content of the Information View.\

All information referenced in other views should be traced to elements
within the Information View. The "should" within this statement allows
for the preferred development process where use cases are defined prior
to developing the detailed data definitions. \

Primary\
 Information is produced by functions\
 Data (of Information) is consumed by the logical structure of functions
(per RA for Space Data Systems)\
 \
 Secondary\
 Enterprise, Functional, Physical, and Communication Viewpoints might
all reference data that might need to be stored in the system; when
these links are needed, there will be information flows in the Physical
View. We could include hyperlinks to these other views - but more likely
(esp. given the connection between two systems) the link from the Smart
City Data Model will be only to the Information Flows of remote
Communication Views and the local Use Case View.\

#### Examples

#### Notes

#### Sources


## A. References

### A.1 Normative references

**[DoDAF]** <br />
[Department of Defense Architecture Framework Version 2.02.](https://dodcio.defense.gov/Library/DoD-Architecture-Framework/) U.S. Department of Defense. Published. URL: https://dodcio.defense.gov/Library/DoD-Architecture-Framework/

**[Hiiliard2]** <br />
Reference not found.

**[Hilliard1]**
Reference not found.

**[IEEE2413]**
Reference not found.

**[ISO42010]** <br />
[Systems and software engineering — Architecture description.](https://www.iso.org/standard/50508.html) ISO/IEC/IEEE. Published. URL: https://www.iso.org/standard/50508.html

**[Kruchten]** <br />
Reference not found.

**[Rozanski]** <br />
[Software Systems Architecture - Second Edition: Working with Stakeholders Using Viewpoints and Perspectives.](https://www.viewpoints-and-perspectives.info/home/book/) Rozanski and Woods. Published. URL: https://www.viewpoints-and-perspectives.info/home/book/

**[TOGAF]** <br />
[TOGAF — The Open Group Architecture Framework, Version 8.1.1.](https://pubs.opengroup.org/architecture/togaf8-doc/arch/toc.html) The Open Group. Published. URL: https://pubs.opengroup.org/architecture/togaf8-doc/arch/toc.html

**[Zachman]** <br />
[Zachman Framework.](https://www.zachman.com/images/ZI_PIcs/ZF3.0.jpg) Published. URL: https://www.zachman.com/images/ZI_PIcs/ZF3.0.jpg

### A.2 Informative references

**[Evergreen]** <br />
[Evergreen Standards.](https://www.w3.org/wiki/Evergreen_Standards) W3C. Published. URL: https://www.w3.org/wiki/Evergreen_Standards

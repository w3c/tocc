# TOCC Modelling Conventions

__This is currently a draft under review__

## Logical Data Model
### Overview
The TOCC will use UML Class Diagrams as the primary graphical notation for documenting relationships among data concepts. The diagrams __and associated text?__ are informative in nature; the formal definition of each data concept is provided by the associated ~~text~~ __description logic__.  

The rules defined here are generally consistent with and an extension of the rules defined in ISO 14817-1:2015.

### General
All documentation and names shall be in English with a general preference for consistency with the following, except when such consistency is more likely to create ambiguities:

* Approved vocabulary of defined in ISO 14812
* British English

The UML standard provides a great deal of flexibility in how to present UML Class Diagrams; within the TOCC efforts diagrams should strive to follow the following rules.

### Naming Conventions
The following naming conventions are consistent with ISO 14817-1:2015.

```
Class names shall be in UpperCamelCase
```
All class names shall be in UpperCamelCase to promote readability while being distinct from attribute names and  elemental types.

```
Attribute names shall be in lowerCamelCase
```
All attribute names shall be in lowerCamelCase to promote readability while being distinct from class names and  elemental types.

```
Elemental type names shall be in lower-hyphenated-case
```
All elemental type names shall be in lower-hyphenated-case to promote readability while being distinct from class and attribute names.

Although represented in diagrams as classes, enumerations are considered elemental types and shall follow these naming conventions.

```
Elemental types shall start with one of the defined base terms
```

* binary 
* code
* date
* date-time
* duration
* identifier
* indicator
* image
* measure
* name
* number
* percent
* quantity
* rate
* sound
* text
* time
* video

```
Elemental types names shall identify a unique datatype
```
Elemental types shall follow the base term with additional text that further distinguishes the type and provides a unique reference to a defined datatype. For datatypes that are relatively unique to a particular standard or effort, it is recommended that the standard/effort is identified as a part of the name.

```
The name of any data element shall be constructed as 
<ClassName>.<attributeName>:<elemental-type-name>
```

```
The name of any association shall be constructed as 
<ClassName>.<attributeName>:<AssociatedClassName>
```


### Class Stereotypes
```
A class that is stereotyped shall indicate its stereotype on the class diagram.
```
Showing the class stereotypes on class diagrams assists the reader in understanding important characteristics about the displayed class. For example, an "enumeration" class implies something distinctly different than a normal class. 

```
Stereotypes should only be applied where needed
```
Per ISO 19501:2005: 
> A stereotype is, in effect, a new class of metamodel element that is introduced at modeling time. It represents a subclass of an existing metamodel element with the same form (attributes and relationships) but with a different intent. Generally a stereotype represents a usage distinction. A stereotyped element may have additional constraints on it from the base metamodel class. It may also have required tagged values that add information needed by elements with the stereotype. It is expected that code generators and other tools will treat stereotyped elements specially.
 
The following class stereotypes are defined for use within TOCC UML Logical Data Model Diagrams:

```
enumeration
```
An enumeration is depicted as a class but represents a value domain consisting of a number of alternative named values. The properties listed for the class actually represent the named alternative values.

In addition to the textually depicting the "enumeration" stereotype on the class, it is recommended to colour the class box in a green shade to further distinguish that the stereotype is applied.

```
choice
```
A choice is depicted as a class without any attributes and with multiple relationships of the same type (i.e., specializations or associations). The choice indicates that only one of the relationships are instantiated in any instance. 

In addition to the textually depicting the "choice" stereotype on the class, it is recommended to colour the class box in a purple shade to further distinguish that the stereotype is applied.

```
role
```
A role is depicted semantically similar to a class but represents a set of characteristics and responsibilities that a class might fulfill. For example, a ```Customer``` is a role that might be fulfilled by a ```Person``` or an ```Organization```.

In addition to the textually depicting the "choice" stereotype on the class, it is recommended to colour the class box in a gold shade to further distinguish that the stereotype is applied.

### Class Diagram settings
Attributes should be shown with name and type.
Attributes should not show visibility.

### Static Metadata
Every data concept defined within the model shall be formally defined with static metadata as defined in ISO 14817-1. Static metadata is data about data (concepts) that does not change (e.g., from instance to instance). Dynamic metadata, when needed, should be defined within the logical data model itself as the value of dynamic metadata can change from one instance to the next.

For example, every data element can be associated with a name and a definition. The name and definition are examples of metadata that is permanently defined for the data element and does not vary from one instance of a data element and another; these are two types of static metadata. By comparison, the type of sensor used to make a measurement is also metadata, but as the value of this meta will vary between different types of sensors, the metadata is considered dynamic and must be incorporated into the logical data model rather than in the documentation of the data element.

#### Class Metadata
For the purpose of the TOCC logical data model, the following static metadata shall be recorded for classes:

* Data concept type (i.e., shall always be "class")
* Name
* Definition
* Context (i.e., the package that contains the class)
* Abstract (i.e., a Boolean value indicating whether the class is abstract)

The following static metadata shall be recorded for classes when applicable:

* Superclass (i.e., the class's generalized class)

The following static metadata may optionally be defined for classes:

* Nominal version
* Historic name
* Uniform resource locator
* Source
* Remark
* Precursor
* Successor
* Synonym 

####Data Element Metadata
For the purpose of the TOCC logical data model, the following static metadata shall be recorded for data elements:

* Data concept type (i.e., shall always be "data element")
* Name (of attribute)
* Definition
* Parent class
* Multiplicity (i.e., how many instances of the attribute can exist for one instance of the class)
* Value Domain (i.e., a reference to another class or to an elemental type)

The following static metadata shall be recorded for data elements when applicable:

* Constraint (e.g., a range constrint on a more general value domain)

The following static metadata may optionally be defined for data elements:

* Nominal version
* Historic name
* Uniform resource locator
* Source
* Remark
* Precursor
* Successor
* Synonym

####Value Domain Metadata
For the purpose of the TOCC logical data model, the following static metadata shall be recorded for value domains:

* Data concept type (i.e., shall always be "value domain")
* Name
* Definition
* Context
* Datatype (an ASN.1 BuiltinType or ConstrainedType)

The following static metadata shall be recorded for value domains when applicable:

* Format (e.g., a date recorded in a text string might have a format of YYYYMMDD)
* Unit of measure (e.g., milliseconds)
* Valid value rule (e.g., If the month is January, the range of dates is 1 to 31)

The following static metadata may optionally be defined for value domains:

* Nominal version
* Historic name
* Uniform resource locator
* Source
* Remark
* Precursor
* Successor
* Synonym

####Association Metadata
For the purpose of the TOCC logical data model, the following static metadata shall be recorded for associations:

* Data concept type (i.e., shall always be "association")
* Name (role name of associated class)
* Definition
* Parent Class
* Multiplicity (i.e., how many instances of the attribute can exist for one instance of the class)
* Datatype (i.e., a reference to another class)

The following static metadata shall be recorded for value domains when applicable:

* Reverse role name

The following static metadata may optionally be defined for value domains:

* Nominal version
* Historic name
* Uniform resource locator
* Source
* Remark
* Precursor
* Successor
* Synonym


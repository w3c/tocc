## Use Case Template
The following table represents the composite of three distinct use case template inputs from:

* ISO/TR 25102:2008, a document by ISO/TC 204 (TC 204),
* SAE J2945 - 2017 (SAE)
* A draft template discussed within ISO/IEC JTC1 AG8 (JTC 1)

The three templates have been merged into this single template with each field mapped to the template(s) where it is defined.  

This is a work in progress that currently includes a first attempt at identifying fields that we might wish to omit from the W3C TOCC effort. Fields that are proposed for omission are shown with <del>strikeout text</del> and coupled with an explanation in the footnotes.

Once we agree on the list of ~allowed/defined~ fields, we should consider which should be considered mandatory and which optional.

| **Item** | **Description** |
| --- | --- | 
| **Id#** | SAE[^id] |
| <del>**Short Title**</del> | <del>SAE (Working title)</del>[^short_title] |
| **Name** | Formal name of the Case Study <br> AG8 (Case Study Name) <br> SAE (Formal Name) <br> TC 204|
| **Summary** | AG8 - Short summary of the case study (with a maximum of 280 char) <br> SAE (Short description)|
| **Description** | AG8 - Extended description of the case study (text, images, etc.) <br> SAE (contained in the body of standard rather than in table) <br>TC 204|
| **Goal** | SAE <br> TC 204<br>AG8[^goal] <br> Value Proposition(s)Bullet list with value proposition(s) of the Validation:<ul>   <li>«Value Proposition #1 in the form ["Verb"] "direct object"»</li>   <li>«Value Proposition #2 in the form ["Verb"] "direct object"»</li>   <li>«Value Proposition #3 in the form ["Verb"] "direct object"»</li>   <li>…</li>   </ul>   Examples:<ul>   <li>[Increase] Yield</li>   <li>[Reduce] Pesticide Use</li>   <li>[Improve] Water Quality</li>   <li>[Reduce] Scrap parts</li>   </ul>|
| **Business Rules** | TC 204 - i.e., as defined by stakeholders|
| **Stakeholders** | TC 204 |
| **Domain**|AG8 <br> SAE (Category) [^domain] |
| <del>**Infraastructure Roles**</del>|<del>SAE</del> [^roles]|
| <del>**Vehicle Roles**</del> | <del>SAE</del> [^roles]|
| <del>**Other Roles**</del> | <del>SAE</del> [^roles]|
| **Geographic Scope** | SAE - how large of an area an implementation of the use case affects [^geographic_scope] |
| **Technical Scope** | TC 204 - defines boundaries of the "system" |
| <del>**Relationship to other use cases**</del> | <del>TC 204</del>[^uc_relationships] |
| **Extensions** | TC 204 |
| **Inclusions** | TC 204 |
| <del>**Level**</del> | <del>TC 204 - typically for individual user but might be abstract business goal or sub-task user goal.</del>[^levels]|
| <del>**Abstraction Level**</del> | <del>TC 204 - Generalized or detailed.</del> [^levels]|
| <del>**Primary Actor**</del> | <del>TC 204</del> [^primary_actor] |
| **Actors** | SAE - entities that have input/output but no functionality defined <br> TC 204|
| **Illustrations** | SAE - sequence diargams, geograpic layout diagrams, etc[^illustrations] |
| **Assumptions**| SAE (Constraints) - i.e., constant constraints <br> TC 204|
| **Technology Constraints**| SAE (Constraints) <br> TC 204|
| **Triggers**| TC 204| 
| **Pre-conditions** | SAE - constraints to start but may change over time |
| **Event Flow <#>**| SAE <br> TC 204[^event_flow]|
| **Post-Conditions**| SAE - i.e., conditions expected after the flow <br> TC 204|
| **Exceptions**| TC 204 - highlighted, potential undesirable outcomes identifying positions within flow of events where they can occur|
| **Information Requirements** | SAE - identify data elements and quality |
| **Issues** | SAE - mainly used to document issues during development <br> TC 204|
| **References** | SAE - Any source material|
| **References to requirements** | TC 204 - shows relationships among requirements that might be defined in separate locations|
| **Version** | TC 204 |
| **Release** | TC 204 (Target System Release) <br> might want to show the release of the ontology that is expected to incorporate this use case|
| **Modification History** | AG 8 <br> TC 204 |
| **Approvals** | TC 204[^approvals] |
| **Application Notes** | TC 204 |
| <del>**DSRC TC Vetting**</del> | <del>SAE</del>[^vetting] |
| <del>**J2945 Tracking**</del> | <del>SAE</del>[^tracking] |
| <del>**Repository ID**</del> | <del>SAE</del>[^reporistory] |
| <del>**Verification**</del> | <del>TC 204</del>[^verification] |
| <del>**Test Cases**</del> | <del>TC 204</del>[^test_cases] |

##Use Case Validation <#>
ISO/IEC JTC1 AG8 defines validation concepts in a separate table; TC204 identifies validation as a single field (listed here as "description"); SAE does not include validation. As there are likely to be multiple validations of any use case, using a separately defined table might be useful.

| **Item** | **Description** |
| --- | --- | 
|Validation Name |AG8 - Name of the Validation|
|Summary (\*)	|AG8 - Short summary (with a maximum of 280 char) of the Validation|
|Description	|AG8 - Extended description of the Validation (text, images, etc.) <br> TC 204 (acceptance criteria)|
|Documentation	|AG8 - Assorted documentation related to the Validation|
|Image(s)	|AG8 - Photo gallery of the Validation|
|Website	|AG8 - The website of the Validation|
|Keywords	|AG8 - Set of keywords/tags that characterise the Validation|

##Use Case Deployment <#>[^deployment]
<del></del>

##Comments / Notes[^notes]
<del></del>

##Authorship[^authorship]
<del></del>

[^id]: While "id" is defined by SAE, it does not seem to be used by its various standards. However, this might be useful if we come up with a meaningful identification scheme

[^short_title]: While "short title" is defined by SAE, it does not seem to be used by its various standards. We should perhaps omit until we have a better justification and naming scheme.

[^goal]: Only AG 8 defines detailed rules for "goals", but they seem to be good ideas

[^domain]: If we keep "domain", we should define a formal list of domains

[^roles]: SAE defines fields for "roles" of the vehicles, infrastructure, and other items. The usage of this field seems inconsistent among different standards as either identifying "physical objects" (e.g., roadside device) or the actions performed by these physical objects (e.g., data reception, data provision, processing, etc). In either case, this seems to be an architecture issue rather than a use case issue. The W3C TOCC has indicated that the architecture content should be treated as the next step after the use case.

[^geographic_scope]: Not sure if this is useful or not

[^uc_relationships]: Use case relationships should generally be defined by the other two fields: extensions and inclusions.

[^levels]:  If we define a field for "levels", we should define clearer rules on how it should be used

[^primary_actor]: We probably don't need to pick a "primary" actor, just list all of them

[^illustrations]: We might want to define separate categories for the different types of illustrations

[^event_flow]: SAE identifies a primary flow and alternative flows; TC 204 allows multiple flows without identifying a "primary". Each flow is its own complex concept, which could be broken out into its own sub-table like we have for validation - each with its own set of post-conditions, etc.

[^approvals]: "Approvals" might be better named "endorsements" or something similar for our purposes.

[^vetting]: "Vetting" might be revised to "status" for our purposes once we develop governance rules on how things become accepted.

[^tracking]: "Tracking" does not seem to be needed for our use

[^reporistory]: "Repository" does not seem to be needed for our use

[^verification]: "Verification" seems to be out-of-scope for the W3C effort

[^test_cases]: "Test Cases" seems to be out-of-scope for the W3C effort

[^deployment]: ISO/IEC JTC1 AG8 defines additional tables describing deployments of the use case; neither TC204 nor SAE include this information. It is likely out of scope of the W3C effort so these table have been omitted from this report.

[^notes]: ISO/IEC JTC1 AG8 defines an additional table for additional notes about the Case Study. Examples might include: Concept (technical concept of the Case Study), Ambition (innovation potential related to the Case Study), Exploitation (how the results of the Case Study can be exploited), etc. However, these items can likely be adequately captured in the above table so this table has also been omitted from this report.

[^authorship]: ISO/IEC JTC1 AG8 defines an additional table for authorship, which includes a version history and dissemination level. The version history has been included in the main table above under "Modification History" and as all W3C material is intented to be public information, there does not seem to be a need for dissemination level.
# City Data Model Mediawiki To Do:

## Use Case page: 
* [DONE] Define an initial set of domains (and eventually, sub-domains)
-> Note: see Governance doc
* Decide whether to introduce an official version numbering system (in
addition to status and mediawiki documented versions)
* Add to pages to [Category:License](http://citydata.utoronto.ca/index.php/Category:License) as required (i.e. create new pages labelled as [[Category:License]] to capture additional types of licensing (e.g. content from ISO)

## Class page:
* [DONE] use dropdown list for "subclass of" and "has subclass" fields
* allow for "other" entry if possible
* [DONE] remove Domains of Interest fields
* [DONE] move Manchester syntax spec and annotations to end of template
* Can we populate rdfs:comment based on the content from the
Description (text definition) field?
* [DONE] test Manchester syntax spec to allow for arbitrary statements as
well (e.g. and, or ...)
* [DONE] add Interface Specification Requirements field (per class example)
* [TO DO] add CDM References field (per class example), to identify classes
	* Temporary solution: include a "What Links Here" list to show all references to the page.
	* A cleaner solution likely requires use of semantic mediawiki properties
	* Neither solution is capable of capturing references made with complex value statements (e.g. involving conjunctions, disjunctions, or nested property restrictions)
* [DONE] All pages: modify supplementary figures template/form to include Captions
	* Note: likely possible to embed figures into main structure of the forms/templates using the embedded template approach adopted for Manchester and annotations specification
* [DONE] Class diagram description
* State machine diagram description
* [DONE] need to fix Manchester specification and annotations specification format to enable repeating rows

## Object Property page:
* [DONE] Incorporate above additions/revisions for Object Property pages

## Data Property page:
* [DONE] Incorporate above additions/revisions for Data Property pages


## Other:
* set-up email for Mediawiki tasks (e.g. account confirmation)
* website security certificates
* update content/documentation (e.g. Main page, About,...) to reflect governance & framework documents
* delete all earlier versions of pages
* [DONE] share mediawiki set-up notes/documentation (sent e-mail to Mark Fox)
* [DONE] set-up access to EC2 instance (sent e-mail to Mark Fox)
* [DONE] create an Admin Guide page with pointers to the key templates/forms
	https://github.com/w3c/tocc/blob/master/management/Wiki%20Management%20Notes.md

# MOVED #

PAV ontology has [moved to Github](https://github.com/pav-ontology/pav)

See https://github.com/pav-ontology/pav

# Versions #

The latest version of the OWL ontology of PAV is always available from the **PAV namespace**:

| **Namespace** / **OWL** | **Documentation** |
|:------------------------|:------------------|
| http://purl.org/pav/    | http://purl.org/pav/html |

**Current version** (v2.3):

| **Namespace** | **versionIRI** / **OWL** | **Documentation** |
|:--------------|:-------------------------|:------------------|
| http://purl.org/pav/ | http://purl.org/pav/2.3  | http://purl.org/pav/2.3/html |

## Versioning ##

PAV follows the [Semantic versioning](http://semver.org/) rules. In particular, for say v2.1.0, we consider that:
  * The _major_ number (2.x.x) will increase if a change is breaking (such as removing or renaming a term). This will typically mean a new namespace.
  * The _minor_ number (x.1.x) will increase if a change is non-breaking, but adds new functionality (such as a new term or OWL import)
  * The _patch_ number (x.x.0) will increase if a change is a superficial bug-fix, such as changing typos or avoiding broken links.

Browse the [SVN tags](https://code.google.com/p/pav-ontology/source/browse/#svn%2Ftags) for individual patch releases.

## Example of import ##

Please note that the namespace is always http://purl.org/pav/ no matter which version of PAV 2.x is used.

```
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix pav: <http://purl.org/pav/> .
<> a owl:Ontology ;
    # Lock down import to minor version 2.3
    owl:imports <http://purl.org/pav/2.3> .
```


You may want to **owl:imports** either the namespace, http://purl.org/pav/, to always get the latest version (2.x.x), or a particular (minor or patch) versionIRI, as above, in order to lock down the version.

_Note that for compatibility reasons, http://purl.org/pav/ returns the OWL as RDF/XML, but with `Content-Type: application/xml` in order to present a human-readable version (by XSLT) for browsers accessing the namespace URI. Some OWL tools might not accept this media type, in such cases the versionIRI like http://purl.org/pav/2.1 should be used instead, which return the ontology with `Content-Type: application/rdf+xml`_


The versionIRI stated in the OWL files always return the latest patch version (ie. http://purl.org/pav/2.1 might serve 2.1.2) - the idea being that for most cases you would want patch updates.


## PAV ontology v2.3.1 (2014-08-28) ##

| **Namespace** | **OWL** | **Documentation** |
|:--------------|:--------|:------------------|
| http://purl.org/pav/ | http://purl.org/pav/2.3.1 | http://purl.org/pav/2.3.1/html |

Changes since v2.3.0:
  * Re-added owl:equivalentProperty to PAV 1.2 properties (which where unintentionally removed in 2.3.0)


## PAV ontology v2.3.0 (2014-08-22) ##

| **Namespace** | **OWL** | **Documentation** |
|:--------------|:--------|:------------------|
| http://purl.org/pav/ | http://purl.org/pav/2.3.0 | http://purl.org/pav/2.3.0/html |

Changes since v2.2.0:
  * Added more versioning properties: [pav:hasVersion](http://pav-ontology.googlecode.com/svn/branches/2.3/pav.html#http://purl.org/pav/hasVersion), [pav:hasCurrentVersion](http://pav-ontology.googlecode.com/svn/branches/2.3/pav.html#http://purl.org/pav/hasCurrentVersion), [pav:hasEarlierVersion](http://pav-ontology.googlecode.com/svn/branches/2.3/pav.html#http://purl.org/pav/hasEarlierVersion)
  * Subproperty relations to [prov:alternateOf](http://www.w3.org/TR/prov-o/#alternateOf), [prov:specializationOf](http://www.w3.org/TR/prov-o/#specializationOf), [prov:generalizationOf](#inverse-names-table.md), [dct:hasVersion](http://purl.org/dc/terms/hasVersion)
  * pav:previousVersion subproperty of pav:hasEarlierVersion
  * Ontology metadata adds owl:priorVersion and new contributors.
  * HTML: Updated [diagram](http://pav-ontology.googlecode.com/svn/tags/2.3.0/images/pav-overview.png) to show versioning


## PAV ontology v2.2.0 (2013-08-30) ##

| **Namespace** | **OWL** | **Documentation** |
|:--------------|:--------|:------------------|
| http://purl.org/pav/ | http://purl.org/pav/2.2.0 | http://purl.org/pav/2.2.0/html |

Changes since v2.1.2:
  * DC Terms subproperties introduced:
    * pav:authoredBy subproperty of dcterms:creator        (creation of content)
    * pav:createdBy subproperty of dcterms:creator         (creation of representation)
    * pav:contributedBy subproperty of dcterms:contributor (contribution of content)
    * Avoids OWL import of http://purl.org/dc/terms/ - instead includes property definitions of the above
    * Remaining properties still [mapped to DCTerms in SKOS](http://purl.org/pav/mapping/dcterms)
  * Description for date properties like pav:createdOn explain how to form an xsd:dateTime when time is  unknown
  * Descriptions have clarified intended functionality, e.g. [pav:authoredBy](http://pav-ontology.googlecode.com/svn/tags/2.2.0/pav.html#d4e149) indicate the **last** authoring date.
  * Examples in descriptions further clarify the distinction between creation of representation and  authoring of content.
  * added owl:isDefinedBy <http://purl.org/pav/> for PAV terms
  * HTML documentation includes hierarchy of referenced PROV and DCTerms superproperties, but not their  labels (making it clear that they are not defined by PAV), see for example [prov:wasRevisionOf](http://pav-ontology.googlecode.com/svn/tags/2.2.0/pav.html#d4e137)

## PAV ontology v2.1.2 (2013-08-16) ##

| **Namespace** | **OWL** | **Documentation** |
|:--------------|:--------|:------------------|
| http://purl.org/pav/ | http://purl.org/pav/2.1.2 | http://purl.org/pav/2.1.2/html |

Changes since v2.1.1:
  * Misspelling in [description of pav:createdBy](http://pav-ontology.googlecode.com/svn/tags/2.1.2/pav.html#d4e148) - dct:createdBy changed to dct:creator


## PAV ontology v2.1.1 (2013-03-26) ##

| **Namespace** | **OWL** | **Documentation** |
|:--------------|:--------|:------------------|
| http://purl.org/pav/ | http://purl.org/pav/2.1.1 | http://purl.org/pav/2.1.1/html |

Changes since v2.1.0:
  * Link to [overview diagram](http://pav-ontology.googlecode.com/svn/tags/2.1.1/images/pav-overview-755px.png)
  * Modified descriptions for [pav:importedFrom](http://pav-ontology.googlecode.com/svn/tags/2.1.1/pav.html#http://purl.org/pav/importedFrom) to clarify that the translated knowledge does not need to be complete
  * Elaborated pav:createdWith, pav:derivedFrom, pav:importedBy, pav:retrievedBy
  * A [SKOS](http://www.w3.org/TR/skos-primer/) mapping for: [dcterms](http://purl.org/pav/mapping/dcterms); uses  [PAV in SKOS](http://purl.org/pav/mapping/skos). This mapping is also described as a [VoID dataset](http://pav-ontology.googlecode.com/svn/trunk/mapping/dcterms-void.ttl).

## PAV ontology v2.1.0 (2013-02-27) ##

| **Namespace** | **OWL** | **Documentation** |
|:--------------|:--------|:------------------|
| http://purl.org/pav/ | http://purl.org/pav/2.1.0 | http://purl.org/pav/2.1.0/html |

Changes since v2.0:
  * Sub-property mapping to [PROV-O](http://www.w3.org/TR/prov-o/). Note that PROV-O is not imported by PAV, so you may import <http://www.w3.org/ns/prov#>, for instance to get the inferred domains and ranges from PROV.
  * Includes introduction about PAV ontology
  * Descriptions of properties are elaborated with examples and relationships to each other
  * Backward compatibility with PAV 1.2 terms indicated using owl:equivalentProperty (Note that the ontology itself is owl:incompatibleWith because several PAV 1 properties have changed names or are organized in a flatter hierarchy).
  * pav:curates marked as deprecated, use its inverse pav:curatedBy
  * owl:versionIRI does now does NOT end in a / - this is to avoid confusion between the versionIRI and the namespace (which stays unchanged).
  * [HTML representation](http://purl.org/pav/html) of ontology (made using [LODE](http://www.essepuntato.it/lode/))
  * OWL-file includes a little [XSLT stylesheet](http://pav-ontology.googlecode.com/svn/trunk/owl2html.xslt) so that accessing http://purl.org/pav/ in a browser will give links to the above HTML documentation
  * The individual URIs in the PAV namespace - like http://purl.org/pav/authoredBy - redirect to the OWL ontology

## PAV ontology v2.0 (2012-04-04) ##

| **Namespace** | **versionIRI** / **OWL** | **Documentation** |
|:--------------|:-------------------------|:------------------|
| http://purl.org/pav/ | http://purl.org/pav/2.0/ | http://purl.org/pav/2.0/html |

  * Initial release independent from SWAN
  * New namespace http://purl.org/pav/
  * Terms removed: acceptedOn, authors, contributors, curators, importedFirstOn, importedLastOn, importedWithId, lastUpdateBy, publishedBy, publishedOn, sourceFirstAccessedOn, submittedBy, submittedOn
  * Terms renamed:  importedFromSource->importedFrom, versionNumber->version
  * Terms added: authoredOn, contributedOn, createdAt, createdWith, curatedOn, curates, derivedFrom, lastRefreshedOn, providedBy, retrievedBy, retrievedFrom, retrievedOn, sourceAccessedBy

Note that during development of PAV 2.0, the ontology was split into three modules (with a common namespace): [provenance](http://purl.org/pav/provenance/2.0/) [authoring](http://purl.org/pav/authoring/2.0/) and [versioning](http://pav-ontology.googlecode.com/svn/trunk/pav-versioning.owl) - but these modules were later merged to the single PAV ontology. For backward compatibility, these module versionIRIs now simply import the whole PAV ontology.


## PAV Ontology v1.2 (2009-01-13) ##
| **Namespace** | **OWL** | **Documentation** |
|:--------------|:--------|:------------------|
| http://swan.mindinformatics.org/ontologies/1.2/pav/ | http://purl.org/pav/1.2/ | http://purl.org/pav/1.2/html |

  * PAV module from the [SWAN ontology](https://code.google.com/p/swan-ontology/) 1.2
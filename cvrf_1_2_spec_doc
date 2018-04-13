1. 1CSAF CVRF Model Tree Map

To assist navigating the topology of the CSAF CVRF version 1.2 document schema, a graphical tree rendering of the parent-child-grandchild relations among the elements under the single cvrf:cvrfdoc root is provided in the following diagram, where children and grandchildren (inside the prod and vuln namespaces) are displayed as they relate to the root element of a CSAF CVRF document:

Figure 1: **CSAF CVRF Document Root** (cvrf:cvrfdoc) with children and grandchildren.

Next a map of some abstract but specific and valid **CSAF CVRF Document** configuration emphasizing the topology of the elements from the cvrf namespace:

Figure 2: A topologically valid **CSAF CVRF Document Root** configuration.

Some decent coloring has been applied to above graph to balance visual hints with accessibility. The mathematical closed interval notation has been used to annotate the minimum and maximum occurrences of elements, where the infinity symbol (∞) translates to the term unbounded in XML lingo.

1. 2Document (Context) Schema Elements

« The nine top-level elements are defined in the cvrf XML schema file and if given MUST appear in the order listed below and as children of the cvrf:cvrfdoc single root element. » [CSAF-4-1]

These main constituents in sequence (Format is &quot; **Concept** : namespace:Element&quot;) are:

1. **Title** :                          cvrf:DocumentTitle
2. **Type** :                         cvrf:DocumentType
3. **Publisher** :                 cvrf:DocumentPublisher
4. **Tracking** :                 cvrf:DocumentTracking
5. **Notes** :                 cvrf:DocumentNotes
6. **Distribution** :                 cvrf:DocumentDistribution
7. **Aggregate Severity** :         cvrf:AggregateSeverity
8. **References** :                 cvrf:DocumentReferences
9. **Acknowledgements** :         cvrf:Acknowledgements

The remaining sub sections will describe the elements, requirements on them and state recommendations and examples.

1.
  1. 2.1Document

Element cvrf:cvrfdoc

« The cvrf:cvrfdoc element is the root element of a CSAF CVRF Document and MUST contain the following child elements cvrf:DocumentTitle, cvrf:DocumentType, cvrf:DocumentPublisher, and cvrf:DocumentTracking all exactly once and in that order. » [CSAF-4.1-1]

« Following these child elements it MUST contain the elements cvrf:DocumentNotes, cvrf:DocumentDistribution, cvrf:AggregateSeverity,     cvrf:DocumentReferences, cvrf:Acknowledgements, and prod:ProductTree all zero or once and in that order. » [CSAF-4.1-2]

« It MUST finally contain zero or more vuln:Vulnerability elements. » [CSAF-4.1-3]

1.
  1. 2.2Document Title

Element cvrf:DocumentTitle

« The cvrf:DocumentTitle element is required exactly once as first child of cvrf:cvrfdoc and its sole content MUST be a non-empty string. » [CSAF-4.2-1]

This string SHOULD be a definitive canonical name for the document, providing enough descriptive content to differentiate from other similar documents, ideally providing a unique &quot;handle&quot;.

Non-normative Comment:

While this elements value – often just named &quot;the title&quot; – is largely up to the document producer, common usage brings some recommendations:

The title should be succinct and promptly give the reader an idea of what is expected document content.

If the document producer also publishes a human-friendly document that hand-in-hand with a CSAF CVRF document, it is recommended that both documents use the same title.

It is further recommended to include the manufacturer name with any product names mentioned in the title.

Example 6:

&lt;DocumentTitle&gt;Cisco IPv6 Crafted Packet Vulnerability&lt;/DocumentTitle&gt;

Example 7:

&lt;DocumentTitle&gt;CERT Vulnerabilities in Kerberos 5 Implementation&lt;/DocumentTitle&gt;

Example 8:

&lt;DocumentTitle&gt;Cisco Content Services Switch 11000 Series DNS Negative Cache of Information  Denial-of-Service Vulnerability&lt;/DocumentTitle&gt;

Example 9:

&lt;DocumentTitle&gt;Symantec Brightmail AntiSpam Static Database Password&lt;/DocumentTitle&gt;

Example 10:

&lt;DocumentTitle&gt;HPSBUX02697 SSRT100591 rev.1 - HP-UX Running Java, Remote Unauthorized Access, Disclosure of Information, and Other Vulnerabilities&lt;/DocumentTitle&gt;

Example 11:

&lt;DocumentTitle&gt;Microsoft Vulnerability in the Microsoft Data Access Components (MDAC) Function Could Allow Code Execution&lt;/DocumentTitle&gt;

Example 12:

&lt;DocumentTitle&gt;
  Microsoft Vulnerability in Windows Explorer Could Allow
  Remote Code  Execution
&lt;/DocumentTitle&gt;

1.
  1. 2.3Document Type

Element cvrf:DocumentType

« The cvrf:DocumentType element is required exactly once inside cvrf:cvrfdoc and its sole content MUST be a non-empty string. » [CSAF-4.3-1]

Theelementcvrf:DocumentTypedefines a short canonical name, chosen by the document producer, which will inform the end user as to the type of document.

Non-normative comment:

This type label is expected to be aligned with the content conveyed: If it is a &quot;Security Advisory&quot;, it should be named so, likewise a pure &quot;Vulnerability Report&quot; (see following below examples).

Example 13:

&lt;DocumentType&gt;Vulnerability Report&lt;/DocumentType&gt;

Example 14:

&lt;DocumentType&gt;Security Advisory&lt;/DocumentType&gt;

Example 15:

&lt;DocumentType&gt;Security Notice&lt;/DocumentType&gt;

1.
  1. 2.4Document Publisher

Element cvrf:DocumentPublisher

« The cvrf:DocumentPublisher element is required exactly once inside cvrf:cvrfdoc, it MUST provide the Type attribute. » [CSAF-4.4-1]

It MAY provide the VendorID attribute.

It MAY contain zero or one cvrf:ContactDetails element and zero or one cvrf:IssuingAuthority element.

« These MUST appear in the order cvrf:ContactDetails and cvrf:IssuingAuthority If both child elements are given. » [CSAF-4.4-2]

Attribute Type

The value of Type is a token restricted by the set cvrf-common:PublisherEnumType defined in the common.xsd schema file and the values as given in section 2.2.2Note Type Model.

Attribute VendorID

The value of VendorID is a string that SHOULD represent a unique identifier (OID) that a vendor uses as issued by FIRST under the auspices of IETF.

Map of some valid **Document Publisher** element level configuration including the parent node ( **Root** ):

Figure 3: A topologically valid **Document Publisher** configuration.

Some decent coloring has been applied to above graph to balance visual hints with accessibility. The mathematical closed interval notation has been used to annotate the minimum and maximum occurrences of elements.

Non-normative comment:

At the time of this writing, OID issuance by FIRST is still a work in progress, thus some samples are provided below, that use OID&#39;s from other standard MIB&#39;s.

Example 16:

&lt;DocumentPublisher Type=&quot;Vendor&quot;/&gt;

Example 17: Cisco Systems Inc. OID in dot notation (cf. [http://oid-info.com/get/1.3.6.1.4.1.9](http://oid-info.com/get/1.3.6.1.4.1.9)):

&lt;DocumentPublisher Type=&quot;Vendor&quot; VendorID=&quot;1.3.6.1.4.1.9&quot;/&gt;

Example 18: Cisco Systems Inc. via OID-IRI notation (slash-separated Unicode labels from root of OID tree):

&lt;DocumentPublisher Type=&quot;Vendor&quot; VendorID=&quot; /ISO/Identified-Organization/6/1/4/1/9&quot;/&gt;

Example 19: Cisco Systems Inc. MIB entry in ASN.1:

&lt;DocumentPublisher Type=&quot;Vendor&quot; VendorID=&quot;{iso(1) identified-organization(3) dod(6) internet(1) private(4) enterprise(1) 9}&quot;/&gt;

1.
  1.
    1. 2.4.1Document Publisher – Contact Details

Element cvrf:ContactDetails

« The cvrf:ContactDetails element contains as its only content a non-empty string and MUST be present zero or one time inside cvrf:DocumentPublisher to convey author contact information such as address, phone number, or email. » [CSAF-4.4.1-1]

Example 20:

&lt;ContactDetails&gt;
  Name: Birgit Mustermensch\r\nOrganization: Internationale Sicherheit für Alle\r\n
  Phone Number: 004912345678901\r\nFax Number: 004912345678902\r\n
  Email Address: birgit.mustermensch@example.com
&lt;/ContactDetails&gt;

1.
  1.
    1. 2.4.2Document Publisher – Issuing Authority

Element cvrf:IssuingAuthority

« The cvrf:IssuingAuthority element contains as its only content a non-empty string and MUST be used zero or once inside cvrf:DocumentPublisher to store the name of the issuing party and their authority to release the document, in particular, the party&#39;s constituency and responsibilities or other obligations. » [CSAF-4.4.2-1]

Non-normative comment:

This element is expected to also include instructions for contacting the issuer.

Example 21:

&lt;IssuingAuthority&gt;

  The Juniper SIRT (Juniper Networks Security Incident Response Team) is the sole
  authority regarding vulnerabilities in any Juniper Networks products or services,
  and coordinates the handling of all aspects of such vulnerabilities from initial
  discovery or report through public announcements and any subsequent follow-on
  activities. Additional information is available at
  http://www.juniper.net/support/security/report\_vulnerability.html
&lt;/IssuingAuthority&gt;

1.
  1. 2.5Document Tracking

Element cvrf:DocumentTracking

« The cvrf:DocumentTracking element required exactly once inside the cvrf:cvrfdoc root element and MUST contain the elements cvrf:Identificaton, cvrf:Status, cvrf:Version, cvrf:RevisionHistory, cvrf:InitialReleaseDate, and cvrf:CurrentReleaseDate all exactly once and in that order. » [CSAF-4.5-1]

« Following these child elements MUST be zero or one element cvrf:Generator.
» [CSAF-4.5-2]

The element cvrf:DocumentTracking is a container designated to hold all management attributes necessary to track a CVRF document as a whole.

Following is the visual display of some valid **Document Tracking** configuration including the parent node cvrf:cvrfdoc (Document **Root** ):

Figure 4: A topologically valid **Document Tracking** configuration.

Some decent coloring has been applied to above graph to balance visual hints with accessibility. The mathematical closed interval notation has been used to annotate the minimum and maximum occurrences of elements, where the infinity symbol (∞) translates to the term unbounded in XML lingo.

1.
  1.
    1. 2.5.1Document Tracking – Identification

Element cvrf:Identification

« The cvrf:Identification element is required exactly once inside the element  cvrf:DocumentTracking and MUST contain the element cvrf:ID exactly once as first child. » [CSAF-4.5.1-1]

« Following this child element MUST be zero or more cvrf:Alias elements.
» [CSAF-4.5.1-2]

The Document Tracking element cvrf:Identification is a container that holds all the identifiers for the CVRF document.

1.
  1.
    1.
      1. 2.5.1.1Document Tracking – Identification – ID

Element cvrf:ID

« The crvf:ID element MUST appear exactly once inside cvrf:Identification and its content MUST be a non-empty string that represents a short, unique identifier that allows to refer to the document unambiguously in any context. » [CSAF-4.5.1.1-1]

Its value refers to the condition of the document with regard to completeness and the likelihood of future editions.

The ID is a simple label. It is a string data type to provide for a wide range of numbering values, types, and schemes.

Its value SHOULD be assigned and maintained by the original document issuing authority.

Non-normative comment:

It is recommended that the ID contains monotonically increasing integer value parts, or is increasing in such a predictable manner that it does not contribute toward confusion or misinterpretation of numbering.

Common practice places a fixed producer acronym, the 4-digit year and a sequence integer number separated by e.g. dashes (-). So, for a fictitious producer Vendorix represented by the acronym VDX, and a security advisory number 42 produced in the calendar year 2017 this might result in an ID value of: VDX-2017-42

Careful consideration is required to ensure that construction of the ID does not contribute to confusion or collision with other labels.

1.
  1.
    1.
      1. 2.5.1.2Document Tracking – Identification – Alias

Element cvrf:Alias

« The crvf:Alias element MUST appear zero or more times inside cvrf:Identification. » [CSAF-4.5.1.2-1]

« If given every instance MUST contain a non-empty string that represents a distinct optional alternative ID used to refer to the document. » [CSAF-4.5.1.2-2]

Non-normative comment:

Many vendors have one or more alternative or secondary IDs for documents and the Alias presents an interface to publish those alongside the primary ID.

1.
  1.
    1. 2.5.2Document Tracking – Status

Element cvrf:Status

« The crvf:Status element MUST appear exactly once in cvrf:DocumentTracking and its sole content MUST be a valid representative of the Status model documented in section 2.2.8Status Type Model. » [CSAF-4.5.2-1]

Its value refers to the condition of the document with regard to completeness and the likelihood of future editions.

Non-normative comment:

Issuing parties are strongly recommended to set Status to &quot;Draft&quot; when initiating a new document and to implement procedures to ensure that the status is changed to the appropriate value before the document is released.

1.
  1.
    1. 2.5.3Document Tracking – Version

Element cvrf:Version

« The crvf:Version element MUST appear exactly once in cvrf:DocumentTracking and its sole content MUST be a valid representative of the Version model documented in section 2.2.9Version Type Model. » [CSAF-4.5.3-1]

Example 22: Only major and minor version numbers stated:

&lt;Version&gt;1.0&lt;/Version&gt;

Example 23: Major (1), minor (2) and patch (3) version numbers given:

&lt;Version&gt;1.2.3&lt;/Version&gt;

Example 24: Build number 9876 appended to version triple (1.0.0):

&lt;Version&gt;1.0.0.9876&lt;/Version&gt;

1.
  1.
    1. 2.5.4Document Tracking – Revision History

Element cvrf:RevisionHistory

« The cvrf:RevisionHistory element MUST be present exactly once inside cvrf:DocumentTracking, and MUST contain one or more cvrf:Revision elements. » [CSAF-4.5.4-1]

For every version or revision of the CSAF CVRF document, including the initial version it SHOULD hold matching cvrf:Revision elements.

1.
  1.
    1.
      1. 2.5.4.1Document Tracking – Revision History – Revision

Element cvrf:Revision

« The cvrf:Revision element MUST appear one or more times inside the element  cvrf:RevisionHistory, and every instance MUST contain the elements cvrf:Number, cvrf:Date, and cvrf:Description all exactly once and in that order. » [CSAF-4.5.4.1-1]

The cvrf:Revision element contains all the information elements required to track the evolution of a CSAF CVRF document.

Non-normative comment:

Each change to a CSAF CVRF document should only be noteworthy, if accompanied by Number, Date, and Description information to be stored inside the child elements.

1.
  1.
    1.
      1.
        1. 2.5.4.1.1Document Tracking – Revision History – Revision – Number

Element cvrf:Number

« The crvf:Number element MUST appear exactly once in cvrf:Revision and its sole content MUST be a valid representative of the Version model documented in section 2.2.9 Version Type Model. » [CSAF-4.5.4.1.1-1]

Its value SHOULD contain the numeric version of the document.

The most recent cvrf:Number elements value should always match the value of the cvrf:Version element.

Minor revisions SHOULD be used for less-significant changes (for example, 1.0.0.0 to 1.0.0.1). Major, actionable changes SHOULD lead to a major increase of the version number (for example, 1.0 to 2.0).

Non-normative comment:

Examples of major or actionable changes include:

 • Any change to severity or impact

• The announcement of additional vulnerabilities

• The announcement of additional vulnerable products

• A significant change in remediation status

1.
  1.
    1.
      1.
        1. 2.5.4.1.2Document Tracking – Revision History – Revision – Date

Element cvrf:Date

« Theelementcvrf:DateMUST appear exactly once in cvrf:Revision and SHOULD record the date the revision was made and MUST be valid representative of the Date and Time model documented in section2.2.1Date and Time. » [CSAF-4.5.4.1.2-1]

1.
  1.
    1.
      1.
        1. 2.5.4.1.3Document Tracking – Revision History – Revision – Description

Element cvrf:Description

« Theelementcvrf:DescriptionMUST appear exactly once in cvrf:Revision and SHOULD hold a single non-empty string representing a short description of the changes. » [CSAF-4.5.4.1.3-1]

Non-normative comment:

It can describe the conditions that prompted the change or be a short list of the items changed.

Example 25:

&lt;RevisionHistory&gt;
  &lt;Revision&gt;
    &lt;Number&gt;1&lt;/Number&gt;
    &lt;Date&gt;2011-11-26T00:00:00+00:00&lt;/Date&gt;
    &lt;Description&gt;initial public release&lt;/Description&gt;
  &lt;/Revision&gt;
&lt;/RevisionHistory&gt;

1.
  1.
    1. 2.5.5Document Tracking – Initial Release Date

Element cvrf:InitialReleaseDate

« Theelementcvrf:InitialReleaseDateMUST appear exactly once inside cvrf:DocumentTracking and SHOULD record the date that the document was initially released by the issuing party and MUST be valid representative of the Date and Time model documented in section2.2.1Date and Time. » [CSAF-4.5.5-1]

Example 26:

&lt;InitialReleaseDate&gt;2011-11-26T00:00:00+00:00&lt;/InitialReleaseDate&gt;

1.
  1.
    1. 2.5.6Document Tracking – Current Release Date

Element cvrf:CurrentReleaseDate

« Theelementcvrf:CurrentReleaseDateMUST appear exactly once inside cvrf:DocumentTracking, SHOULD be the current date that the document was released by the issuing party, and MUST be a valid representative of the Date and Time model documented in section2.2.1Date and Time. » [CSAF-4.5.6-1]

Example 27:

&lt;CurrentReleaseDate&gt;2011-11-26T00:00:00+00:00&lt;/CurrentReleaseDate&gt;

1.
  1.
    1. 2.5.7Document Tracking – Generator

Element cvrf:Generator

« The cvrf:Generator element MUST appear zero or once in cvrf:DocumentTracking and MUST contain the elements cvrf:Engine and cvrf:Date all zero or once and in that order. » [CSAF-4.5.7-1]

It is a container to hold all elements related to the generation of the document. These items will reference when the document was actually created, including the date it was generated and the entity that generated it.

1.
  1.
    1.
      1. 2.5.7.1Document Tracking – Generator – Engine

Element cvrf:Engine

« The optional cvrf:Engine element if present MUST be in cvrf:Generator.
» [CSAF-4.5.7.1-1]

« Any instance MUST contain a non-empty string **.** » [CSAF-4.5.7.1-2]

This string SHOULD represent the name of the engine that generated the CSAF CVRF document, and MAY additionally refer to its version.

1.
  1.
    1.
      1. 2.5.7.2Document Tracking – Generator – Date

Element cvrf:Date

« Theelementcvrf:DateMUST appear zero or once in cvrf:Generator, SHOULD be the current date that the document was generated, and MUST be a valid representative of the Date and Time model documented in section2.2.1 Date and Time Model. » [CSAF-4.5.7.2-1]

Because documents are often generated internally by a document producer and exist for a nonzero amount of time before being released, this field MAY be different from the Initial Release Date.

Example 28: Generator entry with fictitious engine and date given as date time with offset:

&lt;Generator&gt;
  &lt;Engine&gt;Magical Mitigation Machinery, version 1.2.3.42&lt;/Engine&gt;
  &lt;Date&gt;2017-03-27T01:23:45+00:00&lt;/Date&gt;
&lt;/Generator&gt; 

Example 29: Generator entry for another fictitious engine and date stated for AEST time zone (UTC+10) via offset

&lt;Generator&gt;
  &lt;Engine&gt;AnotherSSLVulnAdvisor xsslcsaf 0.9.987&lt;/Engine&gt;
  &lt;Date&gt;2012-05-08T10:26:11+10:00&lt;/Date&gt;
&lt;/Generator&gt;

Example 30: Generator entry from existing vendor documentation and date given with time zone UTC (via Z token)

&lt;Generator&gt;
  &lt;Engine&gt;Red Hat rhsa-to-cvrf 1.0.1478&lt;/Engine&gt;
  &lt;Date&gt;2012-05-08T10:26:11Z&lt;/Date&gt;
&lt;/Generator&gt;

Example 31: Full Document tracking element sample (with generator entry from previous example)

&lt;DocumentTracking&gt;
  &lt;Identification&gt;&lt;ID&gt;RHSA-2010:0888&lt;/ID&gt;&lt;/Identification&gt;
  &lt;Status&gt;Final&lt;/Status&gt;
  &lt;Version&gt;1&lt;/Version&gt;
  &lt;RevisionHistory&gt;
     &lt;Revision&gt;
       &lt;Number&gt;1&lt;/Number&gt;
       &lt;Date&gt;2010-11-16T11:08:00Z&lt;/Date&gt;
       &lt;Description&gt;Current version&lt;/Description&gt;
     &lt;/Revision&gt;
  &lt;/RevisionHistory&gt;
  &lt;InitialReleaseDate&gt;2010-11-16T11:08:00Z&lt;/InitialReleaseDate&gt;
  &lt;CurrentReleaseDate&gt;2010-11-16T11:08:00Z&lt;/CurrentReleaseDate&gt;
  &lt;Generator&gt;
    &lt;Engine&gt;Red Hat rhsa-to-cvrf 1.0.1478&lt;/Engine&gt;
    &lt;Date&gt;2012-05-08T10:26:11Z&lt;/Date&gt;
  &lt;/Generator&gt;
&lt;/DocumentTracking&gt;

1.
  1. 2.6Document Notes

Element cvrf:DocumentNotes

« The cvrf:DocumentNotes element is an optional child of the document root element cvrf:cvrfdoc and if present MUST contain one or more cvrf:Note elements.
» [CSAF-4.6-1]

It holds all of the document-level **Note** elements.

Following is a visual display of **Document Notes** including the parent element ( **Document root** ) in some valid configuration:

Figure 5: A topologically valid **Document Notes** configuration.

Again, some decent coloring has been applied to above graph to balance visual hints with accessibility. The mathematical closed interval notation has been used to annotate the minimum and maximum occurrences of elements, where the infinity symbol (∞) translates to the term unbounded in XML lingo.

The node carrying an ellipsis (…) shall hint at possible further **Note** elements.

1.
  1.
    1. 2.6.1Document Notes – Note

Element cvrf:Note

« The cvrf:Note element MUST occur one or more times inside the cvrf:DocumentNotes element. » [CSAF-4.6.1-1]

« Any instance MUST contain a non-empty string representing a **Note.** » [CSAF-4.6.1-2]

« It MUST provide a Type and an Ordinal. » [CSAF-4.6.1-3]

It MAY provide Title and Audience attributes.

The element cvrf:Note is a place to put all manner of text blobs related to the document as a whole. For further details cf. section 2.2.2Note Type Model.

Attribute Title

The optional Title attributes value is a string, that SHOULD not be empty, and the value SHOULD be aligned with the annotations described in section 2.2.2Note Type Model .

Attribute Audience

The optional Audience attributes value is a string, that SHOULD not be empty, and the value SHOULD be aligned with the annotations described in section 2.2.2Note Type Model .

Attribute Type

« The required Type attribute MUST be a string with a valid enumeration value of the Note Type model as defined in section 2.2.2Note Type Model . » [CSAF-4.6.1-4]

Attribute Ordinal

« The required Ordinal attribute MUST hold a **Positive Integer**. » [CSAF-4.6.1-5]

In addition to its domain the attribute value represents a mandatory, locally significant value used to track notes inside a CSAF CVRF document at the root (document) level.

Every Ordinal that tracks a cvrf:Note inside the cvrf:Notes is completely independent from an Ordinal tracking a Note in a different namespace e.g. inside vuln:Notes.

It is provided to uniquely identify a Note. There should be exactly one of these values per every cvrf:Note inside the cvrf:Notes container element.

The ascendingly ordered set of all such Ordinal values SHOULD be identical to the subset of Positive Integers smaller or equal to the length of the set.

Non-normative comment:

For example, when Type is &quot;General&quot;, Title is &quot;executive summary&quot;, and Audience is &quot;executives&quot;, the note is a high-level overview designed for consumption by C-level decision makers. It should be brief and devoid of any technical details and jargon.

On the other hand, when Type is &quot;Details&quot;, Title is &quot;technical summary&quot;, and Audience is &quot;operational management and system administrators&quot;, the note will be more detailed in nature and will contain more operational information.

Example 32: A cvrf:Note with all attributes provided and adhering to value convention for Ordinal:

&lt;DocumentNotes&gt;
  &lt;Note Type=&quot;General&quot; Ordinal=&quot;1&quot; Title=&quot;Details&quot; Audience=&quot;All&quot;&gt;
    These are some details about a CVRF document intended for
    all stakeholders.
  &lt;/Note&gt;
&lt;/DocumentNotes&gt;

1.
  1. 2.7Document Distribution

Element cvrf:DocumentDistribution

« The cvrf:DocumentDistribution element MUST be present zero times or once as a child of cvrf:cvrfdoc and its value MUST be a non-empty string. » [CSAF-4.7-1]

It should contain details about constraints, if any, for sharing the CSAF CVRF document with additional recipients.

These constraints MAY include instructions on how to reproduce, share, copy, or otherwise distribute the document.

Example 33:

&lt;DocumentDistribution xml:lang=&quot;de&quot;&gt;
  Urheberrechtlich geschützt, 2017, Fiktive GmbH.
  Keine Weitergabe ohne vorherige schriftliche Zustimmung;
  Anzufragen via E-Mail unter cert@fg.example.com
  Quelle für dieses Dokument: https://fg.example.com/sa/fg-sa-2017-123
&lt;/DocumentDistribution&gt;

Example 34:

&lt;DocumentDistribution xml:lang=&quot;en&quot;&gt;
  Copyright © 2016 Previous Year Again, Inc. All rights reserved.
&lt;/DocumentDistribution&gt;

1.
  1. 2.8Aggregate Severity

Element cvrf:AggregateSeverity

« The optional cvrf:AggregateSeverity element if present MUST be in cvrf:cvrfdoc.
» [CSAF-4.8-1]

« Any instance MUST contain a non-empty string. » [CSAF-4.8-2]

It MAY provide a Namespace attribute.

The element cvrf:AggregateSeverity is a vehicle that is provided by the document producer to convey the urgency and criticality with which the one or more vulnerabilities reported should be addressed.

It is a document-level metric and applied to the document as a whole — not any specific vulnerability. The range of values in this field is defined according to the document producer&#39;s policies and procedures.

Attribute Namespace

The optional Namespace attribute&#39;s value SHOULD be a URL (xs:anyURI) pointing to the namespace so referenced.

Non-normative comment:

These values can be understood only in the context of the document producer&#39;s stated practices. Therefore, the values may vary widely depending on the source of the document. The field is independent of—and in addition to—any other standard metric for determining the impact or severity of a given vulnerability (such as CVSS).

Example 35:

&lt;AggregateSeverity Namespace=&quot;https://example.com/se/c/&quot;&gt;Important&lt;/AggregateSeverity&gt;

1.
  1. 2.9Document References

Element cvrf:DocumentReferences

« The optional cvrf:DocumentReferences element if present MUST occur as if appended to the position that a cvrf:AggregateSeverity element will take inside the cvrf:cvrfdoc root element. » [CSAF-4.9-1]

« If present, cvrf:DocumentReferences MUST contain [1, ∞] instances of the element  cvrf:DocumentReference **.** » [CSAF-4.9-2]

The cvrf:DocumentReferences element is a container that SHOULD provide a place in its children cvrf:DocumentReference elements to include references to any conferences, papers, advisories, and other resources that are related and considered to be of value to the document consumer.

1.
  1.
    1. 2.9.1Document References – Reference

Element cvrf:Reference

« The cvrf:Reference element MUST occur one or more times inside the element cvrf:References. » [CSAF-4.9.1-1]

« Any instance MUST contain the elements cvrf:URL and cvrf:Description all exactly once and in that order **.** » [CSAF-4.9.1-2]

« It MUST provide either a Type attribute or a default will be taken instead. » [CSAF-4.9.1-3]

The element cvrf:Reference refers to resources related to the overall CSAF CVRF document. These may include a plaintext or HTML version of the advisory or other related documentation, such as white papers or mitigation documentation.

Attribute Type

« The required Type attribute is if not present understood per default as the enumeration value External or if given MUST be a string with a valid enumeration value of the Reference Type model as defined in section 2.2.7Reference Type Model. » [CSAF-4.9.1-4]

The Type attribute denotes the type of the document reference relative to the given document and as described in section 2.2.7Reference Type Model.

1.
  1.
    1.
      1. 2.9.1.1Document References – Reference – URL

Element cvrf:URL

« The cvrf:URL element MUST be present exactly once in cvrf:Reference and its content SHOULD be the fixed URL (xs:anyURI) or location of reference. » [CSAF-4.9.1.1-1]

1.
  1.
    1.
      1. 2.9.1.2Document References – Reference – Description

Element cvrf:Description

« The cvrf:Description element MUST occur exactly once in cvrf:Reference.
» [CSAF-4.9.1.2-1]

« Any instance MUST contain a non-empty string representing the description of the related document **.** » [CSAF-4.9.1.2-2]

Non-normative comment:

This can be a descriptive title or the name of the referenced artifact.

Example 36:

&lt;References&gt;
  &lt;Reference Type=&quot;External&quot;&gt;
    &lt;URL&gt;http://example.com/bar/&lt;/URL&gt;
    &lt;Description xml:lang=&quot;fr&quot;&gt;C&#39;est un test de référence&lt;/Description&gt;
  &lt;/Reference&gt;
&lt;/References&gt;

1.
  1. 2.10Acknowledgements

Element cvrf:Acknowledgements

« The optional cvrf:Acknowledgements element if present MUST be in cvrf:cvrfdoc.
» [CSAF-4.10-1]

« An instance MUST contain one or more cvrf:Acknowledgement elements **.**
» [CSAF-4.10-2]

The cvrf:Acknowledgements element is a container that SHOULD provide a place in the children cvrf:Acknowledgement elements to note recognition of external parties.

Following is a visual representation of some valid **Document Acknowledgements** configuration including the parent node cvrf:cvrfdoc ( **Document**** Root**) — again with the node labeled {…} indicating further possible**Acknowledgement** subtrees:

Figure 6: A topologically valid **Document Acknowledgements** configuration.

Non-normative comment:

This is the direct cvrf:cvrfdoc child element. For a sample display of the **Acknowledgements** container of a Vulnerability element cf. section 6.15).

1.
  1.
    1. 2.10.1Acknowledgements – Acknowledgement

Element cvrf:Acknowledgement

« The cvrf:Acknowledgement element MUST occur one or more times inside the cvrf:Acknowledgements element. » [CSAF-4.10.1-1]

« Any instance MUST contain elements cvrf:Name [0, ∞], cvrf:Organization [0, ∞], cvrf:Description [0, 1], and cvrf:URL [0, ∞] with the given **Cardinality Ranges** and in that order **.** » [CSAF-4.10.1-2]

The element cvrf:Acknowledgement contains recognition of external parties that reported noncritical/low- severity security issues or provided information, observations, or suggestions that contributed to improved security or improved documentation in future releases of the document producer&#39;s products. This may also contain recognition to external parties that contributed toward producing this document.

1.
  1.
    1.
      1. 2.10.1.1Acknowledgements – Acknowledgement – Name

Element cvrf:Name

« The cvrf:Name element MUST occur zero or more times in cvrf:Acknowledgement.
» [CSAF-4.10.1.1-1]

« Any instance MUST contain a non-empty string, that SHOULD contain the name of the party being acknowledged **.** » [CSAF-4.10.1.1-2]

1.
  1.
    1.
      1. 2.10.1.2Acknowledgements – Acknowledgement – Organization

Element cvrf:Organization

« The cvrf:Organization element MUST be present zero or more times inside any cvrf:Acknowledgement element. » [CSAF-4.10.1.2-1]

«Any instance MUST contain a non-empty string, that SHOULD contain the organization of the party or if cvrf:Name is omitted, the organization itself that is being acknowledged representing the description of the related document **.** » [CSAF-4.10.1.2-2]

1.
  1.
    1.
      1. 2.10.1.3Acknowledgements – Acknowledgement – Description

Element cvrf:Description

« The cvrf:Description element MUST be present zero or one time inside any cvrf:Acknowledgement element. » [CSAF-4.10.1.3-1]

« Any instance MUST contain a non-empty string, that SHOULD represent any contextual details the document producers wish to make known about the acknowledgment or acknowledged parties **.** » [CSAF-4.10.1.3-2]

If attributing to multiple organizations, each contributor should be grouped with that Organization within a single Acknowledgment container.

Non-normative comment:

An Organization-specific acknowledgment may be added within each Acknowledgment container using the Description element. If an overall general or aggregate acknowledgment is to be added, an Acknowledgment container that contains a single Description element may be used.

1.
  1.
    1.
      1. 2.10.1.4Acknowledgements – Acknowledgement – URL

Element cvrf:URL

« The cvrf:URL element MUST be contained zero or more times per any cvrf:Acknowledgement element and its content SHOULD give the optional URL (xs:anyURI) to the person, place, or thing being acknowledged. » [CSAF-4.10.1.4-1]

Example 37:

&lt;Acknowledgments&gt;
  &lt;Acknowledgment&gt;
    &lt;Name&gt;Johann Sebastian Bach&lt;/Name&gt;
    &lt;Organization&gt;Security Fugue LLC&lt;/Organization&gt;
    &lt;Description&gt;First analysis of Coordinated Multi-Stream Attack (CMSA)&lt;/Description&gt;
    &lt;URL&gt;https://secure-fugue.example.com/team/~jsb&lt;/URL&gt;
  &lt;/Acknowledgment&gt;
&lt;/Acknowledgments&gt;  

1. 3Product Tree Schema Elements

Product information in CSAF CVRF is modeled as zero or one top-level Product Tree element instance of prod:ProductTree (defined in the product tree schema file within the prod namespace).

« The following 4 second-level elements are and MUST appear in the order listed if given as elements of the top-level element Product Tree:

1. **Branch** :                  prod:Branch
2. **Full Product Name:**         prod:FullProductName
3. **Relationship** :                prod:Relationship
4. **Product Groups** :        prod:ProductGroups

» [CSAF-5-1]

The remaining sub sections will describe the above 5 first and second level elements together with their children and grandchildren, constraints on them as well as state recommendations and examples.

To avoid duplication of data and accommodate for the many possible complex relationships among real world products, the 4 above named elements maybe nested deeply (e.g. a **Branch** of a **Branch**...) or are clearly useful in many places like the **Full Product Name**.

The sub sections introducing **Branch, Relationship** , and **Product Groups** try to further offer such topological usage information to aid the reader in creating or navigating the graph that can be spanned by instances of a **Product Tree**.

1.
  1. 3.1Product Tree

Element prod:ProductTree

« The optional prod:ProductTree element MUST occur with cardinality [0, 1] as child of cvrf:cvrfdoc. » [CSAF-5.1-1]

« If given, the instance MUST contain prod:Branch [0, ∞], prod:FullProductName [0, ∞], prod:FullProductName [0, ∞], prod:ProductGroups [0, 1], elements with noted cardinalities and in that order. » [CSAF-5.1-2]

The optional elementprod:ProductTreeis a container for all fully qualified product names that can be referenced elsewhere in the document.

References to be named specifically when describing the products that are affected by a vulnerability using the **Product Statuses** , **Vulnerability**  **Threats** , **Vulnerability**** CVSS Score Sets **, and** Vulnerability ****Remediation** containers.

The **Product Tree** can have as many branches as needed, but every endpoint of the tree must be terminated with a **Full Product Name** element, which represents a product that can be referenced elsewhere.

 Example 38:

&lt;prod:ProductTree&gt;
  &lt;prod:Branch Name=&quot;Vendorix&quot; Type=&quot;Vendor&quot;&gt;
    &lt;prod:Branch Name=&quot;... Appliances&quot; Type=&quot;Product Name&quot;&gt;
      &lt;prod:Branch Name=&quot;1.0&quot; Type=&quot;Product Version&quot;&gt;
        &lt;prod:Branch Name=&quot;.0&quot; Type=&quot;Service Pack&quot;&gt;
          &lt;prod:FullProductName ProductID=&quot;CVRFPID-223152&quot;&gt;
            ... AppY 1.0.0
          &lt;/prod:FullProductName&gt;
        &lt;/prod:Branch&gt;
        &lt;prod:Branch Name=&quot;(2)&quot; Type=&quot;Service Pack&quot;&gt;
          &lt;prod:FullProductName ProductID=&quot;CVRFPID-223153&quot;&gt;
            ... AppY 1.0(2)
          &lt;/prod:FullProductName&gt;
        &lt;/prod:Branch&gt;
      &lt;/prod:Branch&gt;
      &lt;prod:Branch Name=&quot;1.1&quot; Type=&quot;Product Version&quot;&gt;
        &lt;prod:Branch Name=&quot;.0&quot; Type=&quot;Service Pack&quot;&gt;
          &lt;prod:FullProductName ProductID=&quot;CVRFPID-223155&quot;&gt;
            ... AppY 1.1.0
          &lt;/prod:FullProductName&gt;
        &lt;/prod:Branch&gt;
        &lt;prod:Branch Name=&quot;(1)&quot; Type=&quot;Service Pack&quot;&gt;
          &lt;prod:FullProductName ProductID=&quot;CVRFPID-223156&quot;&gt;
            ... AppY 1.1(1)
          &lt;/prod:FullProductName&gt;
        &lt;/prod:Branch&gt;
      &lt;/prod:Branch&gt;
    &lt;/prod:Branch&gt;
  &lt;/prod:Branch&gt;
&lt;/prod:ProductTree&gt; 

Map of **Product Tree** including the parent node ( **Document** ) in some valid configuration spanning multiple sub trees:

Figure 7: A topologically valid **Product Tree** configuration.

Again, some decent coloring has been applied to above graph to balance visual hints with accessibility. The mathematical closed interval notation has been used to annotate the minimum and maximum occurrences of elements, where the infinity symbol (∞) translates to the term unbounded in XML lingo.

The pale gray color of the **Full Product Name** representative nodes shall indicate that they are more used like labels all over the topology. The nodes carrying an ellipsis (…) shall hint at possible further deep nesting of the sub trees where they are attached.

1.
  1.
    1. 3.1.1Product Tree – Branch

Element prod:Branch

« The optional prod:Branch choice element MUST occur with cardinality [0, ∞] inside the prod:ProductTree element or nested inside other prod:Branch instances.
» [CSAF-5.1.1-1]

« An instance MUST contain either a prod:Branch or a prod:FullProductName element.
» [CSAF-5.1.1-2]

The prod:FullProductName element has no children (is thus always a terminating or leaf element) while a prod:Branch can either contain further children or terminate its tree branch.

Attribute Name

The mandatory Nameattributeof the **Branch** element and its relation to the equally required Type attribute are documented in section 2.2.3Product Branch Type Model.

Attribute Type

The required Typeattributeof the **Branch** element is documented in section 2.2.3Product Branch Type Model.

Non-normative comment:

A choice element behaves as a regular container that can have different child elements, but with the difference that only exactly one child element can be chosen. It is similar in concept to the &quot;union&quot; programming construct in which one variable can have one of several different predefined data types.

 

Example 39: Nesting of **Branches** in a **Branch** subtree:

&lt;prod:Branch Type=&quot;Vendor&quot; Name=&quot;Microsoft&quot;&gt;
  &lt;prod:Branch Type=&quot;Product Family&quot; Name=&quot;Windows&quot;&gt;
    &lt;prod:Branch Type=&quot;Product Name&quot; Name=&quot;Vista&quot;&gt;
      &lt;prod:Branch Type=&quot;Service Pack&quot; Name=&quot;1&quot;&gt;
        &lt;prod:FullProductName ProductID=&quot;CVRFPID-0001&quot;&gt;
          Microsoft Windows Vista Service Pack 1
        &lt;/prod:FullProductName&gt;
      &lt;/prod:Branch&gt;
      &lt;prod:Branch Type=&quot;Service Pack&quot; Name=&quot;2&quot;&gt;
        &lt;prod:FullProductName ProductID=&quot;CVRFPID-0002&quot;&gt;
          Microsoft Windows Vista Service Pack 2
        &lt;/prod:FullProductName&gt;
      &lt;/prod:Branch&gt;
    &lt;/prod:Branch&gt;
  &lt;/prod:Branch&gt;
  &lt;prod:Branch Type=&quot;Product Family&quot; Name=&quot;Office&quot;&gt;
    &lt;prod:Branch Type=&quot;Product Name&quot; Name=&quot;Word 2010&quot;&gt;
      &lt;prod:Branch Type=&quot;Service Pack&quot; Name=&quot;0&quot;&gt;
        &lt;prod:Branch Type=&quot;Architecture&quot; Name=&quot;x86&quot;&gt;
          &lt;prod:FullProductName ProductID=&quot;CVRFPID-0003&quot;&gt;
            Microsoft Word 2010 (32-bit editions)
          &lt;/prod:FullProductName&gt;
        &lt;/prod:Branch&gt;
      &lt;/prod:Branch&gt;
    &lt;/prod:Branch&gt;
  &lt;/prod:Branch&gt;
&lt;/prod:Branch&gt;

A more visual display of the same structure from above example is shown in the figure below (Error! Reference source not found.).

Map of **Branch** sub tree from above example of nested Branches  including the parent node ( **Product Tree** left out in XML source code example) with some textual hints to map the topologies:

Figure 8: A topologically valid **Branch** configuration

1.
  1.
    1. 3.1.2Product Tree – Full Product Name

Element prod:FullProductName

« The prod:FullProductName element MUST be a child of cardinality [1, ∞] for all possible locations inside the product tree representation. » [CSAF-5.1.2-1]

This elements instances have multiple possible parent elements: prod:ProductTree, prod:Releationship, and prod:Branch.

The prod:FullProductNameelements define the endpoints of the **Product Tree** and occur either directly at the root level, at the branch level, or as the result of a relationship between two products.

The value of a **Full Product Name** element should be the product&#39;s full canonical name, including version number and other attributes, as it would be used in a human-friendly document.

Attribute ProductID

The ProductIDattribute is a token required to identify a **Full Product Name** so that it can be referred to from other parts in the document.

There is no predefined or required format for the ProductIDas long as it uniquely identifies a product in the context of the current document.

Attribute CPE

The (Common Platform Enumeration) CPE attribute refers to a method for naming platforms external to CSAF CVRF.

« The CPE attribute if present MUST have a value, that is a valid cpe-lang:namePattern as defined in the external specification [CPE23\_N] and related schemas. » [CSAF-5.1.2-2]

Non-normative comment:

Examples for ProductID values include incremental integers or Globally Unique Identifiers (GUIDs).

The structure for CPE as required for a valid CSAF CVRF document is described in its specification documents ([CPE23\_N] et al.).

In short: The CPEcan be either an integer (if there exists a known entry for the platform in question) or a candidate string from the vendor if no commonly registered entry yet exists (at the NIST CPE registry site).

Example 40:

&lt;FullProductName ProductID=&quot;CVRFPID-0004&quot;&gt;
  Microsoft Host Integration Server 2006 Service Pack 1
&lt;/FullProductName&gt;

Example 41:

&lt;FullProductName ProductID=&quot;CVRFPID-0005&quot;&gt;
  Microsoft Office 2008 for Mac 12.3.1 Update
&lt;/FullProductName&gt;

1.
  1.
    1. 3.1.3Product Tree – Relationship

Element prod:Relationship

« The prod:Relationship element MUST be present with cardinality [0, ∞] in prod:Tree and if given MUST contain one or more prod:FullProductName instances. » [CSAF-5.1.3-1]

The prod:Relationshipelement establishes a link between two existing **Full Product Name** elements, allowing the document producer to define a combination of two products that form a new **Full Product Name** entry.

As a **Relationship** connects two existing products with each other, there need to be at least two **Full Product Name** entries present in the **Product Tree** before a Relationship element can be created.

**Relationship** elements live at the root of a **Product Tree** , and they have three mandatory attributes: ProductReferenceand RelatesToProductReferenceeach contain the ProductIDtoken for the two products that will form the relationship, and the RelationTypeattribute defines how the products are related.

Attribute ProductReference

The required ProductReference attribute contains the ProductIDtoken of one of the two products that will form the relationship. For directed relationships the producer SHOULD associate correctly.

Attribute RelationType

The allowed values of the required RelationType attributeare of an enumeration type and as defined in 2.2.4 Product Relationship Type Model.

Attribute RelatesToProductReference

The required RelatesToProductReference attributecontains the ProductIDtoken of the other of the two products that will form the relationship. Again: For directed relationships the producer SHOULD associate correctly.

Non-normative comment:

The situation where a need for declaring a Relationship arises, is given when a product is e.g. vulnerable only when installed together with another, or to describe operating system components.

Example 42:

The first product is defined as:  

&lt;FullProductName ProductID=&quot;CVRFPID-0007&quot;&gt;
  Active Directory Lightweight Directory Service
&lt;/FullProductName&gt;

And the second product is defined as:

&lt;FullProductName ProductID=&quot;CVRFPID-0008&quot;&gt;
  Windows Vista Service Pack 2
&lt;/FullProductName&gt;

And the relationship can then be defined as:

&lt;Relationship ProductReference=&quot;CVRFPID-0007&quot;
 RelationType=&quot;Optional Component Of&quot;
 RelatesToProductReference=&quot;CVRFPID-0008&quot;&gt;
  &lt;FullProductName ProductID=&quot;CVRFPID-0009&gt;
    Active Directory Lightweight Directory Service as an optional component of
    Windows Vista Service Pack 2
  &lt;/FullProductName&gt;
&lt;/Relationship&gt;

Example 43:

In another example, the first product is defined as:

&lt;FullProductName ProductID=&quot;CVRFPID-0010&quot;&gt;
  Cisco AnyConnect Secure Mobility Client 2.3.185
&lt;/FullProductName&gt;

And the second product is defined as:

&lt;FullProductName ProductID=&quot;CVRFPID-0011&quot;&gt;Microsoft Windows&lt;/FullProductName&gt;

And the relationship can then be defined as:

&lt;Relationship ProductReference=&quot;CVRFPID-0010&quot; RelationType=&quot;Installed On&quot;
 RelatesToProductReference=&quot;CVRFPID-0011&quot;&gt;
  &lt;FullProductName ProductID=&quot;CVRFPID-0012&gt;
    Cisco AnyConnect Secure Mobility Client 2.3.185 when installed on
    Microsoft Windows
  &lt;/FullProductName&gt;
&lt;/Relationship&gt;

1.
  1.
    1. 3.1.4Product Tree – Product Groups

Element prod:ProductGroups

« The prod:ProductGroups element MUST be present zero or one time inside a given prod:ProductTree element and if present MUST contain one or more prod:Group elements. » [CSAF-5.1.4-1]

The element prod:ProductGroupsis a container, that defines whether **Full Product Name** elements in the product tree will be grouped into logical groups.

If groups are defined, products can be referred to using the GroupID attribute in many other parts of the document, rather than repeatedly having to list all members individually.

Whether groups are defined or not, the ability to reference each product individually in other parts of the document is not affected. In fact, the creator of a document can choose to use either direct product references or group references.

Non-normative comment:

Given that a single product can be a member of more than one group, some areas of the CSAF CVRF document may prohibit product references by group to avoid ambiguity.

Example 44:

We create two groups, CVRFGID-0001 and CVRFGID-0002. Both groups have four members, and ProductIDCVRFPID-0001 is a member of both groups:  

&lt;ProductGroups&gt;
  &lt;Group GroupID=&quot;CVRFGID-0001&quot;&gt;
    &lt;ProductID&gt;CVRFPID-0001&lt;/ProductID&gt;
    &lt;ProductID&gt;CVRFPID-0002&lt;/ProductID&gt;
    &lt;ProductID&gt;CVRFPID-0003&lt;/ProductID&gt;
    &lt;ProductID&gt;CVRFPID-0004&lt;/ProductID&gt;
  &lt;/Group&gt;
  &lt;Group GroupID=&quot;CVRFGID-0002&quot;&gt;
    &lt;ProductID&gt;CVRFPID-0001&lt;/ProductID&gt;
    &lt;ProductID&gt;CVRFPID-0010&lt;/ProductID&gt;
    &lt;ProductID&gt;CVRFPID-0011&lt;/ProductID&gt;
    &lt;ProductID&gt;CVRFPID-0099&lt;/ProductID&gt;
  &lt;/Group&gt;
&lt;/ProductGroups&gt;

A visual map of some fictitious sample **Product Groups** sub tree including the parent node ( **Product Tree** ) with the node labeled {…} indicating further possible **Group** subtrees is depicted below.

Figure 9: A topologically valid **Product Groups** configuration



1.
  1.
    1.
      1. 3.1.4.1Product Tree – Product Groups – Group

Element prod:Group

« The prod:Group element MUST be present one or more times as child of the optional prod:ProductGroups element and MUST contain zero or one prod:Description and 2 or more prod:ProductID elements and in that order. » [CSAF-5.1.4.1-1]

The element prod:Groupis a container, that defines a new logical group of products that can then be referred to in other parts of the document to address a group of products with a single identifier.

**Group** members are defined by adding one **Product ID** element for every member of the group.

Attribute GroupID

The GroupIDattribute is required to identify a **Group** so that it can be referred to from other parts in the document.

There is no predefined or required format for the GroupIDas long as it uniquely identifies a group in the context of the current document.

Non-normative comment:

Examples for GroupIDattribute values include incrementing integers or GUIDs.

1.
  1.
    1.
      1.
        1. 3.1.4.1.1Product Tree – Product Groups – Group – Description

Element prod:Description

« The prod:Description element MUST be present zero or one time in prod:Group and if given is a short, optional description of the group. » [CSAF-5.1.4.1.1-1]

Example 45:

&lt;ProductGroups&gt;
  &lt;Group GroupID=&quot;CVRFGID-0001&quot;&gt;
    &lt;Description&gt;The x64 versions of the operating system.&lt;/Description&gt;
    &lt;ProductID&gt;CVRFPID-0001&lt;/ProductID&gt;
    &lt;ProductID&gt;CVRFPID-0002&lt;/ProductID&gt;
    &lt;ProductID&gt;CVRFPID-0003&lt;/ProductID&gt;
    &lt;ProductID&gt;CVRFPID-0004&lt;/ProductID&gt;
  &lt;/Group&gt;
&lt;/ProductGroups&gt;

1.
  1.
    1.
      1.
        1. 3.1.4.1.2Product Tree – Product Groups – Group – Product ID

Element prod:ProductID

« The prod:ProductID element MUST be present 2 or more times in prod:Group elements and every instance defines a member of a group by referring to the unique ProductIDattribute of a **Full Product Name** element. » [CSAF-5.1.4.1.2-1]

Example 46:

If the two products &quot;Microsoft Windows Vista Service Pack 1&quot; and &quot;Microsoft Windows Vista Service Pack 2&quot; have been defined in the product tree as follows:

&lt;FullProductName ProductID=&quot;CVRFPID-0001&quot;&gt;
  Microsoft Windows Vista Service Pack 1
&lt;/FullProductName&gt;
&lt;FullProductName ProductID=&quot;CVRFPID-0002&quot;&gt;
  Microsoft Windows Vista Service Pack 2
&lt;/FullProductName&gt;

They can both be made a member of the same group with Group ID &quot;GRP-0001&quot;:

&lt;ProductGroups&gt;
  &lt;Group GroupID=&quot;GRP-0001&quot;&gt;
    &lt;ProductID&gt;CVRFPID-0001&lt;/ProductID&gt;
    &lt;ProductID&gt;CVRFPID-0002&lt;/ProductID&gt;
  &lt;/Group&gt;
&lt;/ProductGroups&gt;

Later in the document, both products can be referenced together using the Group ID:

&lt;Remediations&gt;
  &lt;Remediation Type=&quot;Vendor Fix&quot;&gt;
    &lt;Description&gt;Security Update for Windows Vista&lt;/Description&gt;
    &lt;GroupID&gt;GRP-0001&lt;/GroupID&gt;
  &lt;/Remediation&gt;
&lt;/Remediations&gt;

The ability to reference both products individually will also be maintained (and in some cases required):

&lt;Remediations&gt;
  &lt;Remediation Type=&quot;Vendor Fix&quot;&gt;
    &lt;Description&gt;Security Update for Windows Vista&lt;/Description&gt;
    &lt;ProductID&gt;CVRFPID-0001&lt;/ProductID&gt;
    &lt;ProductID&gt;CVRFPID-0002&lt;/ProductID&gt;
  &lt;/Remediation&gt;
&lt;/Remediations&gt;

1. 4Vulnerability Schema Elements

Vulnerability information in CSAF CVRF is modeled as zero or more top-level Vulnerability element instances of vuln:Vulnerability (defined in the vulnerability schema file within the vuln namespace).

« The following listed 14 second-level elements MUST appear in the order listed if given as elements of the top-level element Vulnerability:

1. **Title** :                          vuln:Title
2. **ID** :                         vuln:ID
3. **Notes** :                         vuln:Notes
4. **Discovery Date** :        vuln:DiscoveryDate
5. **Release Date** :                 vuln:ReleaseDate
6. **Involvements** :         vuln:Involvements
7. **CVE** :                         vuln:CVE
8. **CWE** :                         vuln:CWE
9. **Product Statuses** :         vuln:ProductStatuses
10. **Threats** :                 vuln:Threats
11. **CVSS Score Sets** :         vuln:CVSSScoreSets
12. **Remediations** :         vuln:Remediations
13. **References** :                 vuln:References
14. **Acknowledgements** :         vuln:Acknowledgements

» [CSAF-6-1]

The remaining sub sections will describe the above 15 first and second level elements together with their children and grandchildren, constraints on them as well as state recommendations and examples.

1.
  1. 4.1Vulnerability

Element vuln:Vulnerability

« The vuln:Vulnerability element MUST be present zero more times in cvrf:cvrfdoc and MUST contain the following child elements vuln:Title [0, 1], vuln:ID [0, 1], vuln:Notes [0, 1], vuln:DiscoveryDate [0, 1], vuln:ReleaseDate [0, 1], vuln:Involvements [0, 1], vuln:CVE [0, 1], vuln:CWE [0, ∞], vuln:ProductStatuses [0, 1], vuln:Threats [0, 1], vuln:CVSSScoreSets [0, 1], vuln:Remediation [0, 1], vuln:References [0, 1], and vuln:Acknowledgments [0, 1] as per given cardinalities and in that order. » [CSAF-6.1-1]

The optional elementvuln:Vulnerabilityis a container for the aggregation of all fields that are related to a single vulnerability in the document.

The cardinality allows to describe zero, one, or many vulnerabilities in a single CSAF CVRF document.

Attribute Ordinal

« The required attribute Ordinalis a locally significant value used to track vulnerabilities inside a CSAF CVRF document that MUST be an integer in the interval [1, ∞]. » [CSAF-6.1-2]

It is provided to enable specific vulnerabilities to be referenced from elsewhere in the document (or even outside the namespace of a document provided that a unique **Document Title** and **Revision** information are provided).

There SHOULD be one of these values for every **Vulnerability** container in a document, and it is recommended that Ordinalshould be instantiated as a monotonically increasing counter, indexed from 1.

Example 47:

&lt;Vulnerability Ordinal=&quot;1&quot;
 xmlns=&quot;http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/vuln&quot;&gt;
 &lt;!-- ... All children optional, ; sample valid, albeit otherwise useless --&gt;
&lt;/Vulnerability&gt;

A visual map of **Vulnerability** element including the parent node ( **Document** ) in some valid configuration spanning multiple sub trees is given below.

Figure 10: A topologically valid **Vulnerability** configuration.

As before, some decent coloring has been applied to above graph as usual to balance visual hints with accessibility. Also, the mathematical closed interval notation has been used to annotate the minimum and maximum occurrences of elements, where the infinity symbol (∞) translates to the term unbounded in XML lingo.

The nodes carrying an ellipsis (…) here are to be read combined with the rounded edge rectangles, as the latter list the represented leaf elements that did not well fit into the picture.

1.
  1. 4.2Vulnerability – Title

Element vuln:Title

« The vuln:Title element MUST be present zero or one time in vuln:Vulnerability and if present gives the document producer the ability to apply a canonical name or title to the vulnerability. » [CSAF-6.2-1]

To avoid confusion, it is recommended that, if employed, this element commensurately match the nomenclature used by any numbering or cataloging systems references elsewhere, such as the **Document Title** or **CVE.**

Example 48:

&lt;Title&gt;February 2011 TelePresence Vulnerability Bundle&lt;/Title&gt;

1.
  1. 4.3Vulnerability – ID

Element vuln:ID

« The vuln:ID element MUST be present zero or one time in vuln:Vulnerability and if present gives the document producer a place to publish a unique label or tracking ID for the vulnerability (if such information exists). » [CSAF-6.3-1]

The value domain for vuln:ID elements is further documented in section 2.2.14 Vulnerability ID Type Model.

The attribute SystemName is required.

Attribute SystemName

The required attribute SystemNameindicates the name of the vulnerability tracking or numbering system that this **ID** comes from.

Every **ID** value SHOULD have exactly one SystemName.

Non-normative comment:

It is helpful if document producers use unique and consistent system names.

Example 49:

&lt;Vulnerability&gt;
  &lt;ID SystemName=&quot;Cisco Bug ID&quot;&gt;CSCso66472&lt;/ID&gt;
&lt;/Vulnerability&gt;

1.
  1. 4.4Vulnerability – Notes

Element vuln:Notes

« The vuln:Notes element MUST be present zero or one time in vuln:Vulnerability and if present contain one or more vuln:Note elements.
» [CSAF-6.4-1]

The elementvuln:Notesis a container that holds all vulnerability-level **Note** elements.

1.
  1.
    1. 4.4.1Vulnerability – Notes – Note

Element vuln:Note

« The vuln:Note element MUST be present one or more times in vuln:Notes and is a place to put all manner of text blobs related to the vulnerability. » [CSAF-6.4.1-1]

Text should be limited to talking about the impacts, vectors, or caveats of this node and should not contain details to other vulnerabilities in the document. It is, however, acceptable to refer to a vulnerability that is not in the document for the purposes of pointing out a regression.

The vuln:Note element has four attributes, two of them are required: Type and Ordinal.

Titleand Audienceare the two optional attributes to give human readers context around what they are about to read.

Akin to the **Document Notes** element, the note SHOULD contain a compartmentalized textual discussion constrained by its Typeattribute.

Attribute Type

« The value of the attribute TypeMUST be one of the enumeration values as described in section 2.2.2 Note Type Model. » [CSAF-6.4.1-2]

Attribute Ordinal

Ordinalis a mandatory, locally significant value used to track notes inside a CVRF document at the vulnerability level.

It is provided to uniquely identify a **Note**.

There should be one of these values for every **Note** inside **Vulnerability Notes** and it is recommended that OrdinalSHOULD be instantiated as a monotonically increasing counter, indexed from 1.

Every Ordinalthat tracks a **Note** inside **Vulnerability Notes** is completely independent from any Ordinaltracking a **Note** inside **Document Notes**.

Attribute Title

The optional attribute TitleSHOULD be a concise description of what is contained in the text.

Attribute Audience

The optional attribute Audience SHOULD indicate who is intended to read it.

Example 50:

&lt;vuln:Notes&gt;
  &lt;vuln:Note Type=&quot;General&quot; Ordinal=&quot;1&quot; Title=&quot;Details&quot; Audience=&quot;All&quot;&gt;
    These are some details about a vulnerability intended for
    all stakeholders.
  &lt;/vuln:Note&gt;
&lt;/vuln:Notes&gt;

1.
  1. 4.5Vulnerability – Discovery Date

Element vuln:DiscoveryDate

« The vuln:DiscoveryDate element MUST be present zero or one time inside any  vuln:Vulnerability instance element and if given holds the date and time the vulnerability was originally discovered. » [CSAF-6.5-1]

All date like values in CSAF CVRF require a date and a time (cf. section 2.2.1Date and Time).

Example 51:

&lt;DiscoveryDate&gt;2010-11-03T00:00:00Z&lt;/DiscoveryDate&gt;

1.
  1. 4.6Vulnerability – Release Date

Element vuln:ReleaseDate

« The vuln:ReleaseDate element MUST be present zero or one time inside any vuln:Vulnerability instance element and if given holds the date and time the vulnerability was originally released into the wild. » [CSAF-6.6-1]

All date like values in CSAF CVRF require a date and a time (cf. section 2.2.1Date and Time).

Example 52:

&lt;ReleaseDate&gt;2010-11-16T00:00:00Z&lt;/ReleaseDate&gt;

1.
  1. 4.7Vulnerability – Involvements

Element vuln:Involvements

« The vuln:Involvements MUST be present zero or one time inside any vuln:Vulnerability element and if present contain one or more vuln:Involvement elements. » [CSAF-6.7-1]

The optional elementvuln:Involvementsis a container that holds one or more **Involvement** containers, which allow the document producers (or third parties) to comment on their level of involvement in the vulnerability identification, scoping, and remediation process.

Matching the possibly multiple **Involvements** containers, multiple parties can comment on their levels of involvement.

1.
  1.
    1. 4.7.1Vulnerability – Involvements – Involvement

Element vuln:Involvement

« The vuln:Involvment element MUST be present one or more times in vuln:Involvements and MUST contain zero or one vuln:Description elements. » [CSAF-6.7.1-1]

Theelementvuln:Involvement is a container, thatallows the document producers to comment on their level of Involvement (or engagement) in the vulnerability identification, scoping, and remediation process.

The two attributes Party and Status are both required.

Attribute Party

The attribute Partyindicates the type of the producer issuing the status.

It is identical to the **Document Publisher** attribute Type.

Most of the time, both attributes will be the same because document producers will issue an **Involvement** status on their own behalf.

However, if the document producer wants to issue a status on behalf of a third party and use a different type from that used in **Document Publisher** , that use is allowed by the schema.

If this is the case, **Description** should contain additional context regarding what is going on.

« The value of the attribute PartyMUST be as defined in section 2.2.6 Publisher Type Model.
» [CSAF-6.7.1-2]

Attribute Status

« The attribute Statusindicates the level of involvement of (the) Party and the enumeration value MUST be as defined in section 2.2.15 Vulnerability Involvement Type Model.
» [CSAF-6.7.1-3]

1.
  1.
    1.
      1. 4.7.1.1Vulnerability – Involvements – Involvement – Description

Element vuln:Description

« The vuln:Description element MUST occur zero or one time in vuln:Involvment and if present contains a string value, that represents a thorough human-readable discussion of the **Involvement**. » [CSAF-6.7.1.1-1]

Example 53:

&lt;Involvements&gt;
  &lt;Involvement Party=&quot;Vendor&quot; Status=&quot;In Progress&quot;&gt;
    &lt;Description&gt;
      Cisco acknowledges that the IronPort Email Security Appliances (ESA)
      and Cisco IronPort Security Management Appliances (SMA) contain a
      vulnerability that may allow a remote, unauthenticated attacker to
      execute arbitrary code with elevated privileges.
      A Mitigation is available.
    &lt;/Description&gt;
  &lt;/Involvement&gt;
&lt;/Involvements&gt;

Example 54:

&lt;Involvements&gt;
  &lt;Involvement Party=&quot;Researcher&quot; Status=&quot;Contact Attempted&quot;&gt;
    &lt;Description&gt;
      We emailed the vendor on February 14, 2012 when the vulnerability was
      first discovered by our team.
    &lt;/Description&gt;
  &lt;/Involvement&gt;
&lt;/Involvements&gt;

Example 55:

&lt;Involvements&gt;
  &lt;Involvement Party=&quot;Vendor&quot; Status=&quot;Completed&quot;&gt;&lt;/Involvement&gt;
&lt;/Involvements&gt;

1.
  1. 4.8Vulnerability – CVE

Element vuln:CVE

« The vuln:CVE element MUST be present zero or one time in any vuln:Vulnerability and if present its value holds the MITRE standard Common Vulnerabilities and Exposures (CVE) tracking number for the vulnerability and this value MUST match the pattern documented in section 2.2.10 Vulnerability CVE Type Model. » [CSAF-6.8-1]

Non-normative comment:

CVE is a standard for vulnerability naming that provides improved tracking of vulnerabilities over time across different reporting sources. More information about CVE domain values can be found in section 2.2.10 Vulnerability CVE Type Model.

Example 56:

&lt;CVE&gt;CVE-2010-3864&lt;/CVE&gt;

1.
  1. 4.9Vulnerability – CWE

Element vuln:CWE

« The vuln:CWE element MUST be present zero or one time in any vuln:Vulnerability and if present it contains the MITRE standard Common Weakness Enumeration (CWE) and this value MUST match the pattern documented in section 2.2.13 Vulnerability CWE Type Model. » [CSAF-6.9-1]

Non-normative comment:

The CWE domain value type is described in section 2.2.13 Vulnerability CWE Type Model.

Example 57:

&lt;CWE ID=&quot;CWE-601&quot;&gt;URL Redirection to Untrusted Site (&#39;Open Redirect&#39;)&lt;/CWE&gt; 

Example 58:

&lt;CWE ID=&quot;CWE-602&quot;&gt;Client-Side Enforcement of Server-Side Security&lt;/CWE&gt; 

1.
  1. 4.10Vulnerability – Product Statuses

Element vuln:ProductStatuses

« The vuln:ProductStatuses element MUST be present zero or one time in any vuln:Vulnerability and if present it MUST contain one or more vuln:Status elements which contain a subset of products chosen from **Product Tree**. » [CSAF-6.10-1]

Every affected (and unaffected) product relating to the vulnerability is referenced here, inside one or more **Status** containers.

There is a constraint in place to prevent a single product from being assigned two different (conflicting) **Status** elements within the scope of **Vulnerability**.

Likewise, a **Status** child container cannot be tied to a **Product Group** due to the fact that a single product can be a member of more than one product group.

Non-normative comment:

Without this constraint, it would be possible to assign conflicting status information to one and the same product.

1.
  1.
    1. 4.10.1Vulnerability – Product Statuses – Status

Element vuln:Status

« The vuln:Status element MUST be present with cardinality [1, ∞] in vuln:ProductStatuses and MUST contain one or more vuln:ProductID elements. » [CSAF-6.10.1-1]

Attribute Type

The allowed values of the Typeattribute of a vuln:Status element are documented in section 2.2.16 Vulnerability Product Affected Status Type Model. Theelementvuln:Status contains one or more products as chosen from the **Product Tree** , and defines the status of this product in the mandatory _Status_ attribute.

 

1.
  1.
    1.
      1. 4.10.1.1Vulnerability – Product Statuses – Status – Product ID

Element vuln:ProductID

« The vuln:ProductID element MUST be present one or more times inside a vuln:Status element and defines a product as having the status defined in the parent element&#39;s Typeattribute. » [CSAF-6.10.1.1-1]

The reference is made via value by using the unique ProductIDattribute of a **Full Product Name** element that is defined in the **Product Tree**.

« A single **Product ID** MUST not be assigned more than one status type within the same **Vulnerability**. » [CSAF-6.10.1.1-2]

Example 59:

The three products &quot;Microsoft Windows Vista (RTM)&quot;, &quot;Microsoft Windows Vista Service Pack 1&quot;, and &quot;Microsoft Windows Vista Service Pack 2&quot; have been defined in the product tree as follows:  

&lt;ProductTree&gt;
  &lt;FullProductName ProductID=&quot;CVRFPID-0000&quot;&gt;
    Microsoft Windows Vista (RTM)
  &lt;/FullProductName&gt;
  &lt;FullProductName ProductID=&quot;CVRFPID-0001&quot;&gt;
    Microsoft Windows Vista Service Pack 1
  &lt;/FullProductName&gt;
  &lt;FullProductName ProductID=&quot;CVRFPID-0002&quot;&gt;
    Microsoft Windows Vista Service Pack 2
  &lt;/FullProductName&gt;
&lt;/ProductTree&gt;

If Windows Vista RTM and Service Pack 1 are known to be affected, and Service Pack 2 is known not to be affected, it can be documented as follows:

&lt;Vulnerability Ordinal=&quot;1&quot;&gt;
  &lt;Product Statuses&gt;
    &lt;Status Type=&quot;KnownAffected&quot;&gt;
      &lt;ProductID&gt;CVRFPID-0000&lt;/ProductID&gt;
      &lt;ProductID&gt;CVRFPID-0001&lt;/ProductID&gt;
    &lt;/Status&gt;
    &lt;Status Type=&quot;KnownNotAffected&quot;&gt;
      &lt;ProductID&gt;CVRFPID-0002&lt;/ProductID&gt;
    &lt;/Status&gt;
  &lt;/Product Statuses&gt;
&lt;/Vulnerability&gt;

1.
  1. 4.11Vulnerability – Threats

Element vuln:Threats

« The vuln:Threats element MUST be present zero or one time inside any vuln:Vulnerability and if present it MUST contain one or more vuln:Threat elements which contain information about a vulnerability that can change with time. » [CSAF-6.11-1]

Non-normative comment:

Threat information about a vulnerability that can change with time is also called &quot;vulnerability kinetics&quot;.

A visual map of some valid **Threats** configuration including the parent node ( **Vulnerability** ) — again with the node labeled {…} indicating further possible **Threat** subtrees follows below.

Figure 11: A topologically valid **Threats** configuration.

1.
  1.
    1. 4.11.1Vulnerability – Threats – Threat

Element vuln:Threat

« The vuln:Threat element MUST be present with cardinality [1, ∞] as in vuln:Threats and MUST contain exactly one vuln:Description element and zero or more vuln:ProductID and vuln:GroupID elements and in that order. » [CSAF-6.11.1-1]

Theelementvuln:Threat contains the vulnerability kinetic information. This information can change as the vulnerability ages and new information becomes available.

The attribute Type is required and categorizes the threat according to the rules in section 2.2.18 Vulnerability Threat Type Model.

A **Threat** container is tied to one or more specific products by referencing these products using either the **Product ID** or **Group ID** child elements.

If the **Threat** is meant to be general or nonspecific for all products, the **Product ID** and **Group ID** child elements SHOULD be omitted.

Attribute Type

The allowed enumerated values for the Type attribute are documented in section 2.2.18 Vulnerability Threat Type Model.

Attribute Date

The Dateattribute is optional, but if given it must contain a date time value as documented in section 2.2.1Date and Time.

1.
  1.
    1.
      1. 4.11.1.1Vulnerability – Threats – Threat – Description

Element vuln:Description

« The vuln:Description element MUST be present exactly once in vuln:Threat and the string content represents a thorough human-readable discussion of the **Threat**. » [CSAF-6.11.1.1-1]

Example 60: Impact: 

&lt;Threat Type=&quot;Impact&quot;&gt;
  &lt;Description&gt;complete compromise of the integrity of affected machines &lt;/Description&gt;
&lt;/Threat&gt;

Example 61: Exploit Status:

&lt;Threat Type=&quot;Exploit Status&quot;&gt;
  &lt;Description&gt;none&lt;/Description&gt;
  &lt;Date&gt;2011-11-26T00:00:00+00:00&lt;/Date&gt;
  &lt;ProductID&gt;CVRFPID-0000&lt;/ProductID&gt;
&lt;/Threat&gt;

Example 62: Exploit Status without Product ID:

&lt;Threat Type=&quot;Exploit Status&quot;&gt;
  &lt;Description&gt;proof of concept&lt;/Description&gt;
  &lt;/Date&gt;2011-11-26T00:00:00+00:00&lt;/Date&gt;
&lt;/Threat&gt;

Example 63: Target Set:

&lt;Threat Type=&quot;Target Set&quot;&gt;
  &lt;Description&gt;Financial Institutions&lt;/Description&gt;
&lt;/Threat&gt;

Example 64: Target Set variation of content:

&lt;Threat Type=&quot;Target Set&quot;&gt;
  &lt;Description&gt;US Government Agencies&lt;/Description&gt;
&lt;/Threat&gt;

Example 65: Target Set with another variation of content:

&lt;Threat Type=&quot;Target Set&quot;&gt;
  &lt;Description&gt;All versions of BIND&lt;/Description&gt;
&lt;/Threat&gt;

1.
  1.
    1.
      1. 4.11.1.2Vulnerability – Threats – Threat – Product ID

Element vuln:ProductID

« The vuln:ProductID element MUST be present with the cardinality [0, ∞] in vuln:Threat element and if given represents a reference by value to the related product via the unique ProductID attribute of the matching **Full Product Name** element.
» [CSAF-6.11.1.2-1]

If a **Threat** applies to more than one Product, either additional **Product ID** elements or **Group ID** elements (replacing/combining those) SHOULD be added.

1.
  1.
    1.
      1. 4.11.1.3Vulnerability – Threats – Threat – Group ID

Element vuln:GroupID

« The vuln:GroupID element MUST be present with the cardinality [0, ∞] in a vuln:Threat element and if given represents a reference by value to the related products via the unique GroupIDattribute of a **Group** element that is defined in the **Product Tree**. » [CSAF-6.11.1.3-1]

If the **Threat** pertains to several products that have been logically grouped into a **Product Group** optional elementvuln:GroupIDrepresents a reference to that group of products.

If a **Threat** applies to more than one group of products, multiple **Group ID** elements are added accordingly.

1.
  1. 4.12Vulnerability – CVSS Score Sets

Element vuln:CVSSScoreSets

« The vuln:CVSSScoreSets element MUST present zero or one time per and inside any vuln:Vulnerability and holds one or more of the vuln:ScoreSetV2 (deprecated) orvuln:ScoreSetV3 (preferred) container elements and in that order if instances of both are present. » [CSAF-6.12-1]

A visual map of some valid **CVSS Score Sets** configuration including the parent node ( **Vulnerability** ) — again the node with label {…} indicates further possible **Score Set V3** (preferred) or **Score Set V2** (deprecated) subtrees is shown below:

Figure 12  A topologically valid **CVSS Score Sets** configuration.



1.
  1.
    1. 4.12.1Vulnerability – CVSS Score Sets – Score Set V2

Element vuln:ScoreSetV2

« The vuln:ScoreSetV2 element MUST be present with cardinality [0, ∞] inside vuln:CVSSScoreSets and if given, every instance MUST hold at least exactly one vuln:BaseScoreV2 element. » [CSAF-6.12.1-1]

« Any vuln:ScoreSetV2 instance MAY additionally provide the further children: vuln:TemporalScoreV2 [0, 1], vuln:EnvironmentalScoreV2 [0, 1], vuln:VectorV2 [0, 1], vuln:ProductID [0, ∞] and in that order. » [CSAF-6.12.1-2]

If a value of the temporal or environmental score is set to &quot;not defined&quot;, the corresponding elements SHOULD be omitted.

The allowed values for the children of the vuln:ScoreSetV2 element are documented in section 2.2.11 Vulnerability CVSS Version 2 Type Model.

Non-normative comment:

If given, instances hold the actual CVSS version 2 metrics [CVSS2]

See also section 2.2.11 Vulnerability CVSS Version 2 Type Model for further information and constraints on the values of the containers components.

A **Score Set V2** container can be tied to one or more specific products by referencing these products using the **Product ID** child element. If the **Score Set V2** is meant to be applied for all products, the _Product ID_ attribute should be omitted.

Note there is a constraint in place to prevent having a single product assigned to two different score sets within the scope of a **Vulnerability**. Likewise, a **Score Set V2** cannot be tied to a **Product Group** due to the fact that a single product can be a member of more than one product group. Without this constraint, it would be possible to assign conflicting base score information to one and the same product.

1.
  1.
    1.
      1. 4.12.1.1Vulnerability – CVSS Score Sets – Score Set V2 – Base Score V2

Element vuln:BaseScoreV2

« The vuln:BaseScoreV2 element MUST be present exactly once inside every vuln:ScoreSetV2 and contains the numeric value of the computed CVSS version 2 base score.
» [CSAF-6.12.1.1-1]

The finite set of allowed values the vuln:BaseScoreV2 element is documented in section 2.2.11 Vulnerability CVSS Version 2 Type Model.

1.
  1.
    1.
      1. 4.12.1.2Vulnerability – CVSS Score Sets – Score Set V2 – Temporal Score V2

Element vuln:TemporalScoreV2

« The vuln:TemporalScoreV2 element MUST be present zero or one time inside any vuln:ScoreSetV2 and if given contains the numeric value of the computed CVSS version 2 temporal score. » [CSAF-6.12.1.2-1]

The finite set of allowed values for the vuln:TemporalScoreV2 element is documented in section 2.2.11 Vulnerability CVSS Version 2 Type Model.

1.
  1.
    1.
      1. 4.12.1.3Vulnerability – CVSS Score Sets – Score Set V2 – Environmental ScoreV2

Element vuln:EnvironmentalScoreV2

« The vuln:EnvironmentalScoreV2element MUST be present zero or one time inside any vuln:ScoreSetV2 and if given contains the numeric value of the computed CVSS version 2 environmental score. » [CSAF-6.12.1.3-1]

The finite set of allowed values for the vuln:EnvironmentalScoreV2 element are documented in section 2.2.11 Vulnerability CVSS Version 2 Type Model.

Non-normative comment:

This metric is typically reserved for use by the end user and is specific to the environment in which the affected product is deployed. See also section 2.2.11 Vulnerability CVSS Version 2 Type Model for further information and constraints on this element.

1.
  1.
    1.
      1. 4.12.1.4Vulnerability – CVSS Score Sets – Score Set V2 – Vector V2

Element vuln:VectorV2

« The vuln:VectorV2 element MUST be present zero or one time inside any vuln:ScoreSetV2 and if present contains the official string notation that displays all the values used to compute the CVSS version 2 base, temporal, and environmental scores. » [CSAF-6.12.1.4-1]

The allowed values for the vuln:VectorV3 element are documented in section 2.2.11 Vulnerability CVSS Version 2 Type Model.

Example 66:

&lt;VectorV2&gt;AV:N/AC:L/Au:N/C:P/I:P/A:C/E:P/RL:O/RC:C/CDP:H/TD:M/CR:H/IR:H/AR:H&lt;VectorV2&gt;

1.
  1.
    1.
      1. 4.12.1.5Vulnerability – CVSS Score Sets – Score Set V2 – Product ID

Element vuln:ProductID

« The vuln:ProductID element MUST be present with cardinality [0, ∞| inside any vuln:ScoreSetV2 element and per instance value references to unique ProductIDattributes of **Full Product Name** elements defined in the **Product Tree** are noted.
» [CSAF-6.12.1.5-1]

If a **Score Set V2** applies to more than one product, you can add multiple **Product ID** elements as references accordingly.

Any single **Product ID** is to be assigned to exactly none or one **Score Set V2** within the same **Vulnerability**.

1.
  1.
    1. 4.12.2Vulnerability – CVSS Score Sets – Score Set V3

Element vuln:ScoreSetV3

« The vuln:ScoreSetV3 element MUST be present with cardinality [0, ∞] inside vuln:CVSSScoreSets and if given, every instance MUST hold at least exactly one vuln:BaseScoreV3 element. » [CSAF-6.12.2-1]

« Any vuln:ScoreSetV3 instance MAY additionally provide the further children: vuln:TemporalScoreV3 [0, 1], vuln:EnvironmentalScoreV3 [0, 1], vuln:VectorV3 [0, 1], vuln:ProductID [0, ∞] and in that order. » [CSAF-6.12.2-2]

If a value of the temporal or environmental score is set to &quot;not defined&quot;, the corresponding elements SHOULD be omitted.

The allowed values for the children of the vuln:ScoreSetV3 element are documented in section 2.2.12 Vulnerability CVSS Version 3 Type Model.

Non-normative comment:

If given, instances hold the actual CVSS version 3 metrics [CVSS3].

See also section 2.2.12 Vulnerability CVSS Version 3 Type Model for further information and constraints on the values of the containers components.

A **Score Set V3** container can be tied to one or more specific products by referencing these products using the **Product ID** child element. If the **Score Set V3** is meant to be applied for all products, the _Product ID_ attribute should be omitted.

Note there is a constraint in place to prevent having a single product assigned to two different score sets within the scope of a **Vulnerability**. Likewise, a **Score Set V2** cannot be tied to a **Product Group** due to the fact that a single product can be a member of more than one product group. Without this constraint, it would be possible to assign conflicting base score information to one and the same product.

1.
  1.
    1.
      1. 4.12.2.1Vulnerability – CVSS Score Sets – Score Set V3 – Base Score V3

Element vuln:BaseScoreV3

« The vuln:BaseScoreV3 element MUST be present exactly once inside every vuln:ScoreSetV3 and contains the numeric value of the computed CVSS version 3 base score. » [CSAF-6.12.2.1-1]

The finite set of allowed values for the vuln:BaseScoreV3 element is documented in section 2.2.12 Vulnerability CVSS Version 3 Type Model.

1.
  1.
    1.
      1. 4.12.2.2Vulnerability – CVSS Score Sets – Score Set V3 – Temporal Score V3

Element vuln:TemporalScoreV3

« The vuln:TemporalScoreV3 element MUST be present zero or one time inside any vuln:ScoreSetV3 and if given contains the numeric value of the computed CVSS version 3 temporal score. » [CSAF-6.12.2.2-1]

The finite set of allowed values for the vuln:TemporalScoreV3 element is documented in section 2.2.12 Vulnerability CVSS Version 3 Type Model.

1.
  1.
    1.
      1. 4.12.2.3Vulnerability – CVSS Score Sets – Score Set V3 – Environmental ScoreV3

Element vuln:EnvironmentalScoreV3

« The vuln:EnvironmentalScoreV3element MUST be present zero or one time inside any vuln:ScoreSetV3 and if given contains the numeric value of the computed CVSS version 3 environmental score. » [CSAF-6.12.2.3-1]

The finite set of allowed values for the vuln:EnvironmentalScoreV3 element are documented in section 2.2.12 Vulnerability CVSS Version 3 Type Model.

Non-normative comment:

This metric is typically reserved for use by the end user and is specific to the environment in which the affected product is deployed. See also section 2.2.12 Vulnerability CVSS Version 3 Type Model for further information and constraints on this element.

1.
  1.
    1.
      1. 4.12.2.4Vulnerability – CVSS Score Sets – Score Set V3 – Vector V3

Element vuln:VectorV3

« The vuln:VectorV3 element MUST be present zero or one time inside any vuln:ScoreSetV3 and if present contains the official string notation that displays all the values used to compute the CVSS version 3 base, temporal, and environmental scores. » [CSAF-6.12.2.4-1]

The allowed values for the vuln:VectorV3 element are documented in section 2.2.12 Vulnerability CVSS Version 3 Type Model.

Example 67:

&lt;VectorV3&gt;CVSS:3.0/AV:N/AC:L/PR:H/UI:N/S:U/C:L/I:L/A:N&lt;VectorV3&gt;

Example 68:

&lt;VectorV3&gt;CVSS:3.0/S:U/AV:N/AC:L/PR:H/UI:N/C:L/I:L/A:N/E:F/RL:X&lt;VectorV3&gt;

1.
  1.
    1.
      1. 4.12.2.5Vulnerability – CVSS Score Sets – Score Set V3 – Product ID

Element vuln:ProductID

« The vuln:ProductID element MUST be present with cardinality [0, ∞| inside any vuln:ScoreSetV3 element and per instance value references to unique ProductIDattributes of **Full Product Name** elements defined in the **Product Tree** are noted.
» [CSAF-6.12.2.5-1]

If a **Score Set V3** applies to more than one product, you can add multiple **Product ID** elements as references accordingly.

Any single **Product ID** is to be assigned to exactly none or one **Score Set V3** within the same **Vulnerability**.

1.
  1. 4.13Vulnerability – Remediations

Element vuln:Remediations

« The vuln:Remediations element MUST be present with cardinality [0, 1] inside vuln:Vulnerability and it holds [1, ∞] vuln:Remediation child elements.
» [CSAF-6.13-1]

These **Remediation** containers will have details on how to remediate a vulnerability.

Visual display of a map of some valid **Remediations** configuration including the parent node ( **Vulnerability** ) — again with the node labeled {…} indicating further possible **Remediation** subtrees — follows below.

Figure 13: A topologically valid **Remediations** configuration.



1.
  1.
    1. 4.13.1Vulnerability – Remediations – Remediation

Element vuln:Remediation

« The vuln:Remediation element MUST be present with cardinality [1, ∞] in vuln:Remediations and MUST contain the following child elements vuln:Description [1, 1], vuln:Entitlement [0, ∞], vuln:URL [0, 1], vuln:ProductID [0, ∞], and vuln:GroupID [0, ∞] in that order. » [CSAF-6.13.1-1]

The elementvuln:Remediationis a container that holds specific details on how to handle (and presumably, fix) a vulnerability.

A **Remediation** container can be tied to one or more specific products by referencing these products using either the **Product ID** or **Group ID** child elements.

If the **Remediation** is meant to be general or nonspecific for all products, the **Product ID** and **Group ID** child elements should be omitted.

Optionally, **Remediation** can contain information and constraints about how to obtain fixes via the **Entitlement** element.

Attribute Type

The allowed values for the required Type attribute are documented in section 2.2.17 Vulnerability Remediation Type Model.

1.
  1.
    1.
      1. 4.13.1.1Vulnerability – Remediations – Remediation – Description

Element vuln:Description

« The vuln:Description element MUST be present exactly once in vuln:Remediation and it contains a thorough human-readable discussion of the **Remediation**.
» [CSAF-6.13.1.1-1]

1.
  1.
    1.
      1. 4.13.1.2Vulnerability – Remediations – Remediation – Entitlement

Element vuln:Entitlement

« The vuln:Entitlement element MUST be present with cardinality [0, ∞] inside vuln:Remediation and it contains any possible vendor-defined constraints for obtaining fixed software or hardware that fully resolves the vulnerability. » [CSAF-6.13.1.2-1]

Non-normative comment:

This element will often contain information about service contracts or service-level agreements that is directed toward customers of large vendors.

Example 69:

&lt;Entitlement&gt;
  Cisco customers with service contracts that entitle them to regular software updates
  should obtain security fixes through their usual update channels, generally from the
  Cisco website. Cisco recommends contacting the TAC only with specific and imminent
  problems or questions.\r\nAs a special customer service, and to improve the overall
  security of the Internet, Cisco may offer customers free of charge software updates to
  address security problems. If Cisco has offered a free software update to address a
  specific issue, noncontract customers who are eligible for the update may obtain it by
  contacting the Cisco TAC using any of the means described in the Contact Summary
  section of this document. To verify their entitlement, individuals who contact the TAC
  should have available the URL of the Cisco document that is offering the
  upgrade.\r\nAll aspects of this process are subject to change without notice and on a
  case-by-case basis. No particular level of response is guaranteed for any specific
  issue or class of issues.
&lt;/Entitlement&gt;

1.
  1.
    1.
      1. 4.13.1.3Vulnerability – Remediations – Remediation – URL

Element vuln:URL

« The vuln:URL element MUST be present with cardinality [0, 1] in vuln:Remediation and it contains the URL to the **Remediation**. » [CSAF-6.13.1.3-1]

1.
  1.
    1.
      1. 4.13.1.4Vulnerability – Remediations – Remediation – Product ID

Element vuln:ProductID

« The vuln:ProductID element MUST be present with cardinality [0, ∞] inside vuln:Remediation and the content of the instances are tokens that are references to products through the value of a **Full Product Name**&#39;s ProductID attribute.
» [CSAF-6.13.1.4-1]

If the **Remediation** pertains to a specific product, a vuln:ProductIDrepresents the reference to that product.

The reference is made using the unique ProductIDattribute of a **Full Product Name** element that is defined in the **Product Tree**.

If a **Remediation** applies to more than one Product, multiple **Product ID** elements SHOULD be added accordingly, or the **Group ID** element (see below) instead.

Example 70:

&lt;Remediation Type=&quot;Vendor Fix&quot;&gt;
  &lt;Description&gt;
    this is an official fix for Test Product and here are the details...
  &lt;/Description&gt;
  &lt;URL&gt;http://foo.example.com/bar/&lt;/URL&gt;
  &lt;Product ID&gt;CVRFPID-0000&lt;/Product ID&gt;
&lt;/Remediation&gt;

1.
  1.
    1.
      1. 4.13.1.5Vulnerability – Remediations – Remediation – Group ID

Element vuln:GroupID

« The vuln:GroupID element MUST be present with cardinality [0, ∞] inside vuln:Remediation and the content of the instances are tokens that are references to groups of products. » [CSAF-6.13.1.5-1]

If the **Remediation** pertains to several products that have been logically grouped into a **Product Group** , a vuln:GroupID element can be added to reference that group of products. The reference is made using the unique GroupIDattribute of a **Group** element that is defined in the **Product Tree**.

If a **Remediation** applies to more than one group of products, one can add multiple **Group ID** elements accordingly.

1.
  1. 4.14Vulnerability – References

Element vuln:References

« The vuln:References element MUST be present with cardinality [0, 1] inside vuln:Vulnerability parent at last position or before any Acknowledgements if these exist. » [CSAF-6.14-1]

Theoptionalelementvuln:Referencesis a container that SHOULD include citations to any conferences, papers, advisories, and other resources that are specific to the vulnerability section and considered to be of value to the document consumer.

« If present, the vuln:References MUST contain [1, ∞] vuln:Reference child element instances. » [CSAF-6.14-2]

A visual map of some valid **References** configuration including the parent node ( **Vulnerability** ) — again with the node labeled {…} indicating further possible **Reference** subtrees is provided below:

Figure 14: A topologically valid **Vulnerability**** References** configuration.

1.
  1.
    1. 4.14.1Vulnerability – References – Reference

Element vuln:Reference

« The vuln:Reference element MUST be present with cardinality [1, ∞] inside vuln:References and every instance MUST have exactly one vuln:URL and onevuln:Description child element and in that order. » [CSAF-6.14.1-1]

Theelementvuln:Referencecontains a description of a related document specific to a vulnerability section of a CVRF document.

Attribute Type

« The Attribute Type if not present is taken to be the enumeration value External and if present MUST be one of the values documented in section 2.2.7 Reference Type Model. » [CSAF-6.14.1-2]

This attributes value denotes the type of the document reference relative to the CSAF CVRF document itself

Non-normative comment:

This may include a plaintext or HTML version of the advisory or other related documentation, such as white papers or mitigation documentation.

1.
  1.
    1.
      1. 4.14.1.1Vulnerability – References – Reference – URL

Element vuln:URL

« The vuln:URL element MUST be present exactly once in vuln:Reference and contains the fixed URL or location of the reference. » [CSAF-6.14.1.1-1]

1.
  1.
    1.
      1. 4.14.1.2Vulnerability – References – Reference – Description

Element vuln:Description

« The vuln:Description MUST be present exactly once in vuln:Reference and holds a descriptive title or name of the reference. » [CSAF-6.14.1.2-1]

Example 71:

&lt;References&gt;
  &lt;Reference Type=&quot;External&quot;&gt;
    &lt;URL&gt;http://foo.foo/bar/&lt;/URL&gt;
    &lt;Description xml:lang=&quot;fr&quot;&gt;C&#39;est un test de référence&lt;/Description&gt;
  &lt;/Reference&gt;
&lt;/References&gt;

1.
  1. 4.15Vulnerability – Acknowledgements

Element vuln:Acknowledgements

« The vuln:Acknowledgements element MUST be present with cardinality [0, 1] inside vuln:Vulnerability element and MUST contain one or more vuln:Acknowledgement child elements, which in turn either contain(s) recognition of external parties or is empty. » [CSAF-6.15-1]

Non-normative comment:

This **Acknowledgments** container is different from the one at the document level because it is specifically related to the vulnerability in context **.**

Following is a map of a valid **Acknowledgements** configuration including the parent node ( **Vulnerability** ) — again with the node labeled {…} indicating further possible **Acknowledgement** subtrees:

Figure 15: A topologically valid **Vulnerability**** Acknowledgements** configuration.



1.
  1.
    1. 4.15.1Vulnerability – Acknowledgements – Acknowledgement

Element vuln:Acknowledgement

« The vuln:Acknowledgement element MUST be present with cardinality [1, ∞] inside vuln:Acknowledgments and MUST contain the following child elements vuln:Name [0, ∞] times, vuln:Organization [0, ∞] times, vuln:Description [0, 1] times, and vuln:URL [0, ∞] times and in that order. » [CSAF-6.15.1-1]

Theelementvuln:Acknowledgementcontains recognition of external parties who were instrumental in the discovery of, reporting of, and response to the vulnerability. This element indicates collaboration with the security community in a positive fashion and is an important part of a notice or advisory.

Non-normative comment:

Care should be taken to ensure that individuals would like to be acknowledged before they are included.

External parties who have worked with the document producer may be recognized for their work. This should be applied liberally; if someone reports an issue and then discloses it publicly, that party might still be credited.

If the original discoverer is not concerned with recognition, or the issue was discovered internally by the document producer, this field can be omitted.

1.
  1.
    1.
      1. 4.15.1.1Vulnerability – Acknowledgements – Acknowledgement – Name

Element vuln:Name

« The vuln:Name MUST be present with cardinality [1, ∞] in vuln:Acknowledgment and every instance given contains the name of the party being acknowledged. » [CSAF-6.15.1.1-1]

1.
  1.
    1.
      1. 4.15.1.2Vulnerability – Acknowledgements – Acknowledgement – Organization

Element vuln:Organization

« The vuln:Organization MUST be present with cardinality [0, ∞] inside vuln:Acknowledgment. » [CSAF-6.15.1.2-1]

Theelementvuln:Organizationcontains the organization of the party or, if the Name is omitted, the organization itself that is being acknowledged.

1.
  1.
    1.
      1. 4.15.1.3Vulnerability – Acknowledgements – Acknowledgement – Description

Element vuln:Description

« The vuln:Description element MUST be present with cardinality [0, 1] inside vuln:Acknowledgment and if given contains any contextual details the document producers wish to make known about the acknowledgment or acknowledged parties. » [CSAF-6.15.1.3-1]

If attributing to multiple organizations, each contributor SHOULD be grouped with that **Organization** within a single **Acknowledgment** container.

An **Organization** -specific acknowledgment MAY be added within each **Acknowledgment** container by the **Description** element.

If an overall general or aggregate acknowledgment is to be added, an **Acknowledgment** container that contains a single **Description** element MAY be used.

1.
  1.
    1.
      1. 4.15.1.4Vulnerability – Acknowledgements – Acknowledgement – URL

Element vuln:URL

« The vuln:URL MUST be present with cardinality [0, ∞] inside vuln:Acknowledgment and every instance contains the URL or location of the reference to be acknowledged.
» [CSAF-6.15.1.4-1]

Example 72:Taking Isaac Newton, Jeanne D&#39;Arc, and Alan Turing as names for fictitious people, and Acme, as well as Things as such organizations and some vendor Vendorix:

&lt;Acknowledgments&gt;
  &lt;Acknowledgment&gt;
    &lt;Name&gt;Isaac Newton&lt;/Name&gt;
    &lt;Name&gt;Jeanne D&#39;Arc&lt;/Name&gt;
    &lt;Organization&gt;Acme&lt;/Organization&gt;
    &lt;URL&gt;http://acme.example.com/IsaacAndJeanne/&lt;/URL&gt;
  &lt;/Acknowledgment&gt;
  &lt;Acknowledgment&gt;
    &lt;Name&gt;Alan Turing&lt;/Name&gt;
    &lt;Organization&gt;Things&lt;/Organization&gt;
    &lt;Description&gt;
      Vendorix would like to thank Alan Turing from Things for reporting this issue.
    &lt;/Description&gt;
    &lt;URL&gt;http://things.example.com/JustAlan/&lt;/URL&gt;
  &lt;/Acknowledgment&gt;
  &lt;Acknowledgment&gt;
    &lt;Description&gt;
      Vendorix would like to thank the following researchers for their contributions to
      making this project more secure: Isaac Newton, Jeanne D&#39;Arc, Alan Turing
    &lt;/Description&gt;
    &lt;URL&gt;http://white-hats.example.com/AllOfThemAgain/&lt;/URL&gt;
  &lt;/Acknowledgment&gt;
&lt;/Acknowledgments&gt;

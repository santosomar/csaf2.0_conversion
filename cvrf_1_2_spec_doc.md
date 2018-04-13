CSAF CVRF Model Tree Map
========================

To assist navigating the topology of the CSAF CVRF version 1.2 document
schema, a graphical tree rendering of the parent-child-grandchild
relations among the elements under the single cvrf:cvrfdoc root is
provided in the following diagram, where children and grandchildren
(inside the prod and vuln namespaces) are displayed as they relate to
the root element of a CSAF CVRF document:

Figure : **CSAF CVRF Document Root** (cvrf:cvrfdoc) with children and
grandchildren.

Next a map of some abstract but specific and valid **CSAF CVRF
Document** configuration emphasizing the topology of the elements from
the cvrf namespace:

Figure : A topologically valid **CSAF CVRF Document Root**
configuration.

Some decent coloring has been applied to above graph to balance visual
hints with accessibility. The mathematical closed interval notation has
been used to annotate the minimum and maximum occurrences of elements,
where the infinity symbol (∞) translates to the term unbounded in XML
lingo.

Document (Context) Schema Elements
==================================

« The nine top-level elements are defined in the cvrf XML schema file
and if given MUST appear in the order listed below and as children of
the cvrf:cvrfdoc single root element. » \[CSAF-4-1\]

These main constituents in sequence (Format is "**Concept**:
namespace:Element") are:

1.  **Title**: cvrf:DocumentTitle

2.  **Type**: cvrf:DocumentType

3.  **Publisher**: cvrf:DocumentPublisher

4.  **Tracking**: cvrf:DocumentTracking

5.  **Notes**: cvrf:DocumentNotes

6.  **Distribution**: cvrf:DocumentDistribution

7.  **Aggregate Severity**: cvrf:AggregateSeverity

8.  **References**: cvrf:DocumentReferences

9.  **Acknowledgements**: cvrf:Acknowledgements

The remaining sub sections will describe the elements, requirements on
them and state recommendations and examples.

Document
--------

Element cvrf:cvrfdoc

« The cvrf:cvrfdoc element is the root element of a CSAF CVRF Document
and MUST contain the following child elements cvrf:DocumentTitle,
cvrf:DocumentType, cvrf:DocumentPublisher, and cvrf:DocumentTracking all
exactly once and in that order. » \[CSAF-4.1-1\]

« Following these child elements it MUST contain the elements
cvrf:DocumentNotes, cvrf:DocumentDistribution, cvrf:AggregateSeverity,
cvrf:DocumentReferences, cvrf:Acknowledgements, and prod:ProductTree all
zero or once and in that order. » \[CSAF-4.1-2\]

« It MUST finally contain zero or more vuln:Vulnerability elements.
» \[CSAF-4.1-3\]

Document Title
--------------

Element cvrf:DocumentTitle

« The cvrf:DocumentTitle element is required exactly once as first child
of cvrf:cvrfdoc and its sole content MUST be a non-empty string.
» \[CSAF-4.2-1\]

This string SHOULD be a definitive canonical name for the document,
providing enough descriptive content to differentiate from other similar
documents, ideally providing a unique "handle".

Non-normative Comment:

While this elements value -- often just named "the title" -- is largely
up to the document producer, common usage brings some recommendations:

The title should be succinct and promptly give the reader an idea of
what is expected document content.

If the document producer also publishes a human-friendly document that
hand-in-hand with a CSAF CVRF document, it is recommended that both
documents use the same title.

It is further recommended to include the manufacturer name with any
product names mentioned in the title.

Example :

\<DocumentTitle\>Cisco IPv6 Crafted Packet
Vulnerability\</DocumentTitle\>

Example :

\<DocumentTitle\>CERT Vulnerabilities in Kerberos 5
Implementation\</DocumentTitle\>

Example :

\<DocumentTitle\>Cisco Content Services Switch 11000 Series DNS Negative
Cache of Information  Denial-of-Service Vulnerability\</DocumentTitle\>

Example :

\<DocumentTitle\>Symantec Brightmail AntiSpam Static Database
Password\</DocumentTitle\>

Example :

\<DocumentTitle\>HPSBUX02697 SSRT100591 rev.1 - HP-UX Running Java,
Remote Unauthorized Access, Disclosure of Information, and Other
Vulnerabilities\</DocumentTitle\>

Example :

\<DocumentTitle\>Microsoft Vulnerability in the Microsoft Data Access
Components (MDAC) Function Could Allow Code Execution\</DocumentTitle\>

Example :

\<DocumentTitle\>\
Microsoft Vulnerability in Windows Explorer Could Allow\
Remote Code  Execution\
\</DocumentTitle\>

Document Type
-------------

Element cvrf:DocumentType

« The cvrf:DocumentType element is required exactly once inside
cvrf:cvrfdoc and its sole content MUST be a non-empty string.
» \[CSAF-4.3-1\]

The element cvrf:DocumentType defines a short canonical name, chosen by
the document producer, which will inform the end user as to the type of
document.

Non-normative comment:

This type label is expected to be aligned with the content conveyed: If
it is a "Security Advisory", it should be named so, likewise a pure
"Vulnerability Report" (see following below examples).

Example :

\<DocumentType\>Vulnerability Report\</DocumentType\>

Example :

\<DocumentType\>Security Advisory\</DocumentType\>

Example :

\<DocumentType\>Security Notice\</DocumentType\>

Document Publisher
------------------

Element cvrf:DocumentPublisher

« The cvrf:DocumentPublisher element is required exactly once inside
cvrf:cvrfdoc, it MUST provide the Type attribute. » \[CSAF-4.4-1\]

It MAY provide the VendorID attribute.

It MAY contain zero or one cvrf:ContactDetails element and zero or one
cvrf:IssuingAuthority element.

« These MUST appear in the order cvrf:ContactDetails and
cvrf:IssuingAuthority If both child elements are given. » \[CSAF-4.4-2\]

##### Attribute Type {#attribute-type .MemberHeading}

The value of Type is a token restricted by the set
cvrf-common:PublisherEnumType defined in the common.xsd schema file and
the values as given in section 2.2.2 [Note Type
Model](#_Note_Type_Model).

##### Attribute VendorID {#attribute-vendorid .MemberHeading}

The value of VendorID is a string that SHOULD represent a unique
identifier (OID) that a vendor uses as issued by FIRST under the
auspices of IETF.

Map of some valid **Document Publisher** element level configuration
including the parent node (**Root**):

Figure : A topologically valid **Document Publisher** configuration.

Some decent coloring has been applied to above graph to balance visual
hints with accessibility. The mathematical closed interval notation has
been used to annotate the minimum and maximum occurrences of elements.

Non-normative comment:

At the time of this writing, OID issuance by FIRST is still a work in
progress, thus some samples are provided below, that use OID's from
other standard MIB's.

Example :

\<DocumentPublisher Type=\"Vendor\"/\>

Example : Cisco Systems Inc. OID in dot notation (cf.
<http://oid-info.com/get/1.3.6.1.4.1.9>):

\<DocumentPublisher Type=\"Vendor\" VendorID=\"1.3.6.1.4.1.9\"/\>

Example : Cisco Systems Inc. via OID-IRI notation (slash-separated
Unicode labels from root of OID tree):

\<DocumentPublisher Type=\"Vendor\" VendorID=\"
/ISO/Identified-Organization/6/1/4/1/9\"/\>

Example : Cisco Systems Inc. MIB entry in ASN.1:

\<DocumentPublisher Type=\"Vendor\" VendorID=\"{iso(1)
identified-organization(3) dod(6) internet(1) private(4) enterprise(1)
9}\"/\>

### Document Publisher -- Contact Details

Element cvrf:ContactDetails

« The cvrf:ContactDetails element contains as its only content a
non-empty string and MUST be present zero or one time inside
cvrf:DocumentPublisher to convey author contact information such as
address, phone number, or email. » \[CSAF-4.4.1-1\]

Example :

\<ContactDetails\>\
Name: Birgit Mustermensch\\r\\nOrganization: Internationale Sicherheit
für Alle\\r\\n\
Phone Number: 004912345678901\\r\\nFax Number: 004912345678902\\r\\n\
Email Address: birgit.mustermensch\@example.com\
\</ContactDetails\>

### Document Publisher -- Issuing Authority

Element cvrf:IssuingAuthority

« The cvrf:IssuingAuthority element contains as its only content a
non-empty string and MUST be used zero or once inside
cvrf:DocumentPublisher to store the name of the issuing party and their
authority to release the document, in particular, the party\'s
constituency and responsibilities or other obligations.
» \[CSAF-4.4.2-1\]

Non-normative comment:

This element is expected to also include instructions for contacting the
issuer.

Example :

\<IssuingAuthority\>

The Juniper SIRT (Juniper Networks Security Incident Response Team) is
the sole\
authority regarding vulnerabilities in any Juniper Networks products or
services,\
and coordinates the handling of all aspects of such vulnerabilities from
initial\
discovery or report through public announcements and any subsequent
follow-on\
activities. Additional information is available at\
http://www.juniper.net/support/security/report\_vulnerability.html\
\</IssuingAuthority\>

Document Tracking
-----------------

Element cvrf:DocumentTracking

« The cvrf:DocumentTracking element required exactly once inside the
cvrf:cvrfdoc root element and MUST contain the elements
cvrf:Identificaton, cvrf:Status, cvrf:Version, cvrf:RevisionHistory,
cvrf:InitialReleaseDate, and cvrf:CurrentReleaseDate all exactly once
and in that order. » \[CSAF-4.5-1\]

« Following these child elements MUST be zero or one element
cvrf:Generator.\
» \[CSAF-4.5-2\]

The element cvrf:DocumentTracking is a container designated to hold all
management attributes necessary to track a CVRF document as a whole.

Following is the visual display of some valid **Document Tracking**
configuration including the parent node cvrf:cvrfdoc (Document
**Root**):

Figure : A topologically valid **Document Tracking** configuration.

Some decent coloring has been applied to above graph to balance visual
hints with accessibility. The mathematical closed interval notation has
been used to annotate the minimum and maximum occurrences of elements,
where the infinity symbol (∞) translates to the term unbounded in XML
lingo.

### Document Tracking -- Identification

Element cvrf:Identification

« The cvrf:Identification element is required exactly once inside the
element cvrf:DocumentTracking and MUST contain the element cvrf:ID
exactly once as first child. » \[CSAF-4.5.1-1\]

« Following this child element MUST be zero or more cvrf:Alias
elements.\
» \[CSAF-4.5.1-2\]

The Document Tracking element cvrf:Identification is a container that
holds all the identifiers for the CVRF document.

#### Document Tracking -- Identification -- ID

Element cvrf:ID

« The crvf:ID element MUST appear exactly once inside
cvrf:Identification and its content MUST be a non-empty string that
represents a short, unique identifier that allows to refer to the
document unambiguously in any context. » \[CSAF-4.5.1.1-1\]

Its value refers to the condition of the document with regard to
completeness and the likelihood of future editions.

The ID is a simple label. It is a string data type to provide for a wide
range of numbering values, types, and schemes.

Its value SHOULD be assigned and maintained by the original document
issuing authority.

Non-normative comment:

It is recommended that the ID contains monotonically increasing integer
value parts, or is increasing in such a predictable manner that it does
not contribute toward confusion or misinterpretation of numbering.

Common practice places a fixed producer acronym, the 4-digit year and a
sequence integer number separated by e.g. dashes (-). So, for a
fictitious producer Vendorix represented by the acronym VDX, and a
security advisory number 42 produced in the calendar year 2017 this
might result in an ID value of: VDX-2017-42

Careful consideration is required to ensure that construction of the ID
does not contribute to confusion or collision with other labels.

#### Document Tracking -- Identification -- Alias

Element cvrf:Alias

« The crvf:Alias element MUST appear zero or more times inside
cvrf:Identification. » \[CSAF-4.5.1.2-1\]

« If given every instance MUST contain a non-empty string that
represents a distinct optional alternative ID used to refer to the
document. » \[CSAF-4.5.1.2-2\]

Non-normative comment:

Many vendors have one or more alternative or secondary IDs for documents
and the Alias presents an interface to publish those alongside the
primary ID.

### Document Tracking -- Status

Element cvrf:Status

« The crvf:Status element MUST appear exactly once in
cvrf:DocumentTracking and its sole content MUST be a valid
representative of the Status model documented in section 2.2.8 Status
Type Model. » \[CSAF-4.5.2-1\]

Its value refers to the condition of the document with regard to
completeness and the likelihood of future editions.

Non-normative comment:

Issuing parties are strongly recommended to set Status to "Draft" when
initiating a new document and to implement procedures to ensure that the
status is changed to the appropriate value before the document is
released.

### Document Tracking -- Version

Element cvrf:Version

« The crvf:Version element MUST appear exactly once in
cvrf:DocumentTracking and its sole content MUST be a valid
representative of the Version model documented in section 2.2.9 Version
Type Model. » \[CSAF-4.5.3-1\]

Example : Only major and minor version numbers stated:

\<Version\>1.0\</Version\>

Example : Major (1), minor (2) and patch (3) version numbers given:

\<Version\>1.2.3\</Version\>

Example : Build number 9876 appended to version triple (1.0.0):

\<Version\>1.0.0.9876\</Version\>

### Document Tracking -- Revision History

Element cvrf:RevisionHistory

« The cvrf:RevisionHistory element MUST be present exactly once inside
cvrf:DocumentTracking, and MUST contain one or more cvrf:Revision
elements. » \[CSAF-4.5.4-1\]

For every version or revision of the CSAF CVRF document, including the
initial version it SHOULD hold matching cvrf:Revision elements.

#### Document Tracking -- Revision History -- Revision

Element cvrf:Revision

« The cvrf:Revision element MUST appear one or more times inside the
element cvrf:RevisionHistory, and every instance MUST contain the
elements cvrf:Number, cvrf:Date, and cvrf:Description all exactly once
and in that order. » \[CSAF-4.5.4.1-1\]

The cvrf:Revision element contains all the information elements required
to track the evolution of a CSAF CVRF document.

Non-normative comment:

Each change to a CSAF CVRF document should only be noteworthy, if
accompanied by Number, Date, and Description information to be stored
inside the child elements.

##### Document Tracking -- Revision History -- Revision -- Number

Element cvrf:Number

« The crvf:Number element MUST appear exactly once in cvrf:Revision and
its sole content MUST be a valid representative of the Version model
documented in section 2.2.9 [Version Type Model](#_Version_Type_Model).
» \[CSAF-4.5.4.1.1-1\]

Its value SHOULD contain the numeric version of the document.

The most recent cvrf:Number elements value should always match the value
of the cvrf:Version element.

Minor revisions SHOULD be used for less-significant changes (for
example, 1.0.0.0 to 1.0.0.1). Major, actionable changes SHOULD lead to a
major increase of the version number (for example, 1.0 to 2.0).

Non-normative comment:

Examples of major or actionable changes include:

• Any change to severity or impact

• The announcement of additional vulnerabilities

• The announcement of additional vulnerable products

• A significant change in remediation status

##### Document Tracking -- Revision History -- Revision -- Date

Element cvrf:Date

« The element cvrf:Date MUST appear exactly once in cvrf:Revision and
SHOULD record the date the revision was made and MUST be valid
representative of the Date and Time model documented in section 2.2.1
[Date and Time](#_Date_and_Time_1). » \[CSAF-4.5.4.1.2-1\]

##### Document Tracking -- Revision History -- Revision -- Description

Element cvrf:Description

« The element cvrf:Description MUST appear exactly once in cvrf:Revision
and SHOULD hold a single non-empty string representing a short
description of the changes. » \[CSAF-4.5.4.1.3-1\]

Non-normative comment:

It can describe the conditions that prompted the change or be a short
list of the items changed.

Example :

\<RevisionHistory\>\
\<Revision\>\
\<Number\>1\</Number\>\
\<Date\>2011-11-26T00:00:00+00:00\</Date\>\
\<Description\>initial public release\</Description\>\
\</Revision\>\
\</RevisionHistory\>

### Document Tracking -- Initial Release Date

Element cvrf:InitialReleaseDate

« The element cvrf:InitialReleaseDate MUST appear exactly once inside
cvrf:DocumentTracking and SHOULD record the date that the document was
initially released by the issuing party and MUST be valid representative
of the Date and Time model documented in section 2.2.1 [Date and
Time](#_Date_and_Time_1). » \[CSAF-4.5.5-1\]

Example :

\<InitialReleaseDate\>2011-11-26T00:00:00+00:00\</InitialReleaseDate\>

### Document Tracking -- Current Release Date

Element cvrf:CurrentReleaseDate

« The element cvrf:CurrentReleaseDate MUST appear exactly once inside
cvrf:DocumentTracking, SHOULD be the current date that the document was
released by the issuing party, and MUST be a valid representative of the
Date and Time model documented in section 2.2.1 [Date and
Time](#_Date_and_Time_1). » \[CSAF-4.5.6-1\]

Example :

\<CurrentReleaseDate\>2011-11-26T00:00:00+00:00\</CurrentReleaseDate\>

### Document Tracking -- Generator

Element cvrf:Generator

« The cvrf:Generator element MUST appear zero or once in
cvrf:DocumentTracking and MUST contain the elements cvrf:Engine and
cvrf:Date all zero or once and in that order. » \[CSAF-4.5.7-1\]

It is a container to hold all elements related to the generation of the
document. These items will reference when the document was actually
created, including the date it was generated and the entity that
generated it.

#### Document Tracking -- Generator -- Engine

Element cvrf:Engine

« The optional cvrf:Engine element if present MUST be in
cvrf:Generator.\
» \[CSAF-4.5.7.1-1\]

« Any instance MUST contain a non-empty string**.** » \[CSAF-4.5.7.1-2\]

This string SHOULD represent the name of the engine that generated the
CSAF CVRF document, and MAY additionally refer to its version.

#### Document Tracking -- Generator -- Date

Element cvrf:Date

« The element cvrf:Date MUST appear zero or once in cvrf:Generator,
SHOULD be the current date that the document was generated, and MUST be
a valid representative of the Date and Time model documented in section
2.2.1 [Date and Time Model](#_Date_and_Time_2). » \[CSAF-4.5.7.2-1\]

Because documents are often generated internally by a document producer
and exist for a nonzero amount of time before being released, this field
MAY be different from the Initial Release Date.

Example : Generator entry with fictitious engine and date given as date
time with offset:

\<Generator\>\
\<Engine\>Magical Mitigation Machinery, version 1.2.3.42\</Engine\>\
\<Date\>2017-03-27T01:23:45+00:00\</Date\>\
\</Generator\> 

Example : Generator entry for another fictitious engine and date stated
for AEST time zone (UTC+10) via offset

\<Generator\>\
\<Engine\>AnotherSSLVulnAdvisor xsslcsaf 0.9.987\</Engine\>\
\<Date\>2012-05-08T10:26:11+10:00\</Date\>\
\</Generator\>

Example : Generator entry from existing vendor documentation and date
given with time zone UTC (via Z token)

\<Generator\>\
\<Engine\>Red Hat rhsa-to-cvrf 1.0.1478\</Engine\>\
\<Date\>2012-05-08T10:26:11Z\</Date\>\
\</Generator\>

Example : Full Document tracking element sample (with generator entry
from previous example)

\<DocumentTracking\>\
\<Identification\>\<ID\>RHSA-2010:0888\</ID\>\</Identification\>\
\<Status\>Final\</Status\>\
\<Version\>1\</Version\>\
\<RevisionHistory\>\
\<Revision\>\
\<Number\>1\</Number\>\
\<Date\>2010-11-16T11:08:00Z\</Date\>\
\<Description\>Current version\</Description\>\
\</Revision\>\
\</RevisionHistory\>\
\<InitialReleaseDate\>2010-11-16T11:08:00Z\</InitialReleaseDate\>\
\<CurrentReleaseDate\>2010-11-16T11:08:00Z\</CurrentReleaseDate\>\
\<Generator\>\
\<Engine\>Red Hat rhsa-to-cvrf 1.0.1478\</Engine\>\
\<Date\>2012-05-08T10:26:11Z\</Date\>\
\</Generator\>\
\</DocumentTracking\>

Document Notes
--------------

Element cvrf:DocumentNotes

« The cvrf:DocumentNotes element is an optional child of the document
root element cvrf:cvrfdoc and if present MUST contain one or more
cvrf:Note elements.\
» \[CSAF-4.6-1\]

It holds all of the document-level **Note** elements.

Following is a visual display of **Document Notes** including the parent
element (**Document root**) in some valid configuration:

Figure : A topologically valid **Document Notes** configuration.

Again, some decent coloring has been applied to above graph to balance
visual hints with accessibility. The mathematical closed interval
notation has been used to annotate the minimum and maximum occurrences
of elements, where the infinity symbol (∞) translates to the term
unbounded in XML lingo.

The node carrying an ellipsis (...) shall hint at possible further
**Note** elements.

### Document Notes -- Note

Element cvrf:Note

« The cvrf:Note element MUST occur one or more times inside the
cvrf:DocumentNotes element. » \[CSAF-4.6.1-1\]

« Any instance MUST contain a non-empty string representing a **Note.**
» \[CSAF-4.6.1-2\]

« It MUST provide a Type and an Ordinal. » \[CSAF-4.6.1-3\]

It MAY provide Title and Audience attributes.

The element cvrf:Note is a place to put all manner of text blobs related
to the document as a whole. For further details cf. section 2.2.2 [Note
Type Model](#_Note_Type_Model_1).

##### Attribute Title {#attribute-title .MemberHeading}

The optional Title attributes value is a string, that SHOULD not be
empty, and the value SHOULD be aligned with the annotations described in
section 2.2.2 Note Type Model .

##### Attribute Audience {#attribute-audience .MemberHeading}

The optional Audience attributes value is a string, that SHOULD not be
empty, and the value SHOULD be aligned with the annotations described in
section 2.2.2 Note Type Model .

##### Attribute Type {#attribute-type-1 .MemberHeading}

« The required Type attribute MUST be a string with a valid enumeration
value of the Note Type model as defined in section 2.2.2 Note Type Model
. » \[CSAF-4.6.1-4\]

##### Attribute Ordinal {#attribute-ordinal .MemberHeading}

« The required Ordinal attribute MUST hold a **Positive Integer**.
» \[CSAF-4.6.1-5\]

In addition to its domain the attribute value represents a mandatory,
locally significant value used to track notes inside a CSAF CVRF
document at the root (document) level.

Every Ordinal that tracks a cvrf:Note inside the cvrf:Notes is
completely independent from an Ordinal tracking a Note in a different
namespace e.g. inside vuln:Notes.

It is provided to uniquely identify a Note. There should be exactly one
of these values per every cvrf:Note inside the cvrf:Notes container
element.

The ascendingly ordered set of all such Ordinal values SHOULD be
identical to the subset of Positive Integers smaller or equal to the
length of the set.

Non-normative comment:

For example, when Type is "General", Title is "executive summary", and
Audience is "executives", the note is a high-level overview designed for
consumption by C-level decision makers. It should be brief and devoid of
any technical details and jargon.

On the other hand, when Type is "Details", Title is "technical summary",
and Audience is "operational management and system administrators", the
note will be more detailed in nature and will contain more operational
information.

Example : A cvrf:Note with all attributes provided and adhering to value
convention for Ordinal:

\<DocumentNotes\>\
\<Note Type=\"General\" Ordinal=\"1\" Title=\"Details\"
Audience=\"All\"\>\
These are some details about a CVRF document intended for\
all stakeholders.\
\</Note\>\
\</DocumentNotes\>

Document Distribution
---------------------

Element cvrf:DocumentDistribution

« The cvrf:DocumentDistribution element MUST be present zero times or
once as a child of cvrf:cvrfdoc and its value MUST be a non-empty
string. » \[CSAF-4.7-1\]

It should contain details about constraints, if any, for sharing the
CSAF CVRF document with additional recipients.

These constraints MAY include instructions on how to reproduce, share,
copy, or otherwise distribute the document.

Example 33:

\<DocumentDistribution xml:lang=\"de\"\>\
Urheberrechtlich geschützt, 2017, Fiktive GmbH.\
Keine Weitergabe ohne vorherige schriftliche Zustimmung;\
Anzufragen via E-Mail unter cert\@fg.example.com\
Quelle für dieses Dokument: https://fg.example.com/sa/fg-sa-2017-123\
\</DocumentDistribution\>

Example 34:

\<DocumentDistribution xml:lang=\"en\"\>\
Copyright © 2016 Previous Year Again, Inc. All rights reserved.\
\</DocumentDistribution\>

Aggregate Severity
------------------

Element cvrf:AggregateSeverity

« The optional cvrf:AggregateSeverity element if present MUST be in
cvrf:cvrfdoc.\
» \[CSAF-4.8-1\]

« Any instance MUST contain a non-empty string. » \[CSAF-4.8-2\]

It MAY provide a Namespace attribute.

The element cvrf:AggregateSeverity is a vehicle that is provided by the
document producer to convey the urgency and criticality with which the
one or more vulnerabilities reported should be addressed.

It is a document-level metric and applied to the document as a whole ---
not any specific vulnerability. The range of values in this field is
defined according to the document producer\'s policies and procedures.

##### Attribute Namespace {#attribute-namespace .MemberHeading}

The optional Namespace attribute's value SHOULD be a URL (xs:anyURI)
pointing to the namespace so referenced.

Non-normative comment:

These values can be understood only in the context of the document
producer\'s stated practices. Therefore, the values may vary widely
depending on the source of the document. The field is independent
of---and in addition to---any other standard metric for determining the
impact or severity of a given vulnerability (such as CVSS).

Example :

\<AggregateSeverity
Namespace=\"https://example.com/se/c/\"\>Important\</AggregateSeverity\>

Document References
-------------------

Element cvrf:DocumentReferences

« The optional cvrf:DocumentReferences element if present MUST occur as
if appended to the position that a cvrf:AggregateSeverity element will
take inside the cvrf:cvrfdoc root element. » \[CSAF-4.9-1\]

« If present, cvrf:DocumentReferences MUST contain \[1, ∞\] instances of
the element cvrf:DocumentReference**.** » \[CSAF-4.9-2\]

The cvrf:DocumentReferences element is a container that SHOULD provide a
place in its children cvrf:DocumentReference elements to include
references to any conferences, papers, advisories, and other resources
that are related and considered to be of value to the document consumer.

### Document References -- Reference

Element cvrf:Reference

« The cvrf:Reference element MUST occur one or more times inside the
element cvrf:References. » \[CSAF-4.9.1-1\]

« Any instance MUST contain the elements cvrf:URL and cvrf:Description
all exactly once and in that order**.** » \[CSAF-4.9.1-2\]

« It MUST provide either a Type attribute or a default will be taken
instead. » \[CSAF-4.9.1-3\]

The element cvrf:Reference refers to resources related to the overall
CSAF CVRF document. These may include a plaintext or HTML version of the
advisory or other related documentation, such as white papers or
mitigation documentation.

##### Attribute Type {#attribute-type-2 .MemberHeading}

« The required Type attribute is if not present understood per default
as the enumeration value External or if given MUST be a string with a
valid enumeration value of the Reference Type model as defined in
section 2.2.7 Reference Type Model. » \[CSAF-4.9.1-4\]

The Type attribute denotes the type of the document reference relative
to the given document and as described in section 2.2.7 [Reference Type
Model](#_Reference_Type_Model).

#### Document References -- Reference -- URL

Element cvrf:URL

« The cvrf:URL element MUST be present exactly once in cvrf:Reference
and its content SHOULD be the fixed URL (xs:anyURI) or location of
reference. » \[CSAF-4.9.1.1-1\]

#### Document References -- Reference -- Description

Element cvrf:Description

« The cvrf:Description element MUST occur exactly once in
cvrf:Reference.\
» \[CSAF-4.9.1.2-1\]

« Any instance MUST contain a non-empty string representing the
description of the related document**.** » \[CSAF-4.9.1.2-2\]

Non-normative comment:

This can be a descriptive title or the name of the referenced artifact.

Example :

\<References\>\
\<Reference Type=\"External\"\>\
\<URL\>http://example.com/bar/\</URL\>\
\<Description xml:lang=\"fr\"\>C\'est un test de
référence\</Description\>\
\</Reference\>\
\</References\>

Acknowledgements
----------------

Element cvrf:Acknowledgements

« The optional cvrf:Acknowledgements element if present MUST be in
cvrf:cvrfdoc.\
» \[CSAF-4.10-1\]

« An instance MUST contain one or more cvrf:Acknowledgement
elements**.**\
» \[CSAF-4.10-2\]

The cvrf:Acknowledgements element is a container that SHOULD provide a
place in the children cvrf:Acknowledgement elements to note recognition
of external parties.

Following is a visual representation of some valid **Document
Acknowledgements** configuration including the parent node cvrf:cvrfdoc
(**Document** **Root**) --- again with the node labeled {...} indicating
further possible **Acknowledgement** subtrees:

Figure : A topologically valid **Document Acknowledgements**
configuration.

Non-normative comment:

This is the direct cvrf:cvrfdoc child element. For a sample display of
the **Acknowledgements** container of a Vulnerability element
cf. section 6.15).

### Acknowledgements -- Acknowledgement

Element cvrf:Acknowledgement

« The cvrf:Acknowledgement element MUST occur one or more times inside
the cvrf:Acknowledgements element. » \[CSAF-4.10.1-1\]

« Any instance MUST contain elements cvrf:Name \[0, ∞\],
cvrf:Organization \[0, ∞\], cvrf:Description \[0, 1\], and cvrf:URL
\[0, ∞\] with the given **Cardinality Ranges** and in that order**.**
» \[CSAF-4.10.1-2\]

The element cvrf:Acknowledgement contains recognition of external
parties that reported noncritical/low- severity security issues or
provided information, observations, or suggestions that contributed to
improved security or improved documentation in future releases of the
document producer\'s products. This may also contain recognition to
external parties that contributed toward producing this document.

#### Acknowledgements -- Acknowledgement -- Name

Element cvrf:Name

« The cvrf:Name element MUST occur zero or more times in
cvrf:Acknowledgement.\
» \[CSAF-4.10.1.1-1\]

« Any instance MUST contain a non-empty string, that SHOULD contain the
name of the party being acknowledged**.** » \[CSAF-4.10.1.1-2\]

#### Acknowledgements -- Acknowledgement -- Organization

Element cvrf:Organization

« The cvrf:Organization element MUST be present zero or more times
inside any cvrf:Acknowledgement element. » \[CSAF-4.10.1.2-1\]

«Any instance MUST contain a non-empty string, that SHOULD contain the
organization of the party or if cvrf:Name is omitted, the organization
itself that is being acknowledged representing the description of the
related document**.** » \[CSAF-4.10.1.2-2\]

#### Acknowledgements -- Acknowledgement -- Description

Element cvrf:Description

« The cvrf:Description element MUST be present zero or one time inside
any cvrf:Acknowledgement element. » \[CSAF-4.10.1.3-1\]

« Any instance MUST contain a non-empty string, that SHOULD represent
any contextual details the document producers wish to make known about
the acknowledgment or acknowledged parties**.** » \[CSAF-4.10.1.3-2\]

If attributing to multiple organizations, each contributor should be
grouped with that Organization within a single Acknowledgment container.

Non-normative comment:

An Organization-specific acknowledgment may be added within each
Acknowledgment container using the Description element. If an overall
general or aggregate acknowledgment is to be added, an Acknowledgment
container that contains a single Description element may be used.

#### Acknowledgements -- Acknowledgement -- URL

Element cvrf:URL

« The cvrf:URL element MUST be contained zero or more times per any
cvrf:Acknowledgement element and its content SHOULD give the optional
URL (xs:anyURI) to the person, place, or thing being acknowledged.
» \[CSAF-4.10.1.4-1\]

Example :

\<Acknowledgments\>\
\<Acknowledgment\>\
\<Name\>Johann Sebastian Bach\</Name\>\
\<Organization\>Security Fugue LLC\</Organization\>\
\<Description\>First analysis of Coordinated Multi-Stream Attack
(CMSA)\</Description\>\
\<URL\>https://secure-fugue.example.com/team/\~jsb\</URL\>\
\</Acknowledgment\>\
\</Acknowledgments\>  

Product Tree Schema Elements
============================

Product information in CSAF CVRF is modeled as zero or one top-level
Product Tree element instance of prod:ProductTree (defined in the
product tree schema file within the prod namespace).

« The following 4 second-level elements are and MUST appear in the order
listed if given as elements of the top-level element Product Tree:

1.  **Branch**: prod:Branch

2.  **Full Product Name:** prod:FullProductName

3.  **Relationship**: prod:Relationship

4.  **Product Groups**: prod:ProductGroups

» \[CSAF-5-1\]

The remaining sub sections will describe the above 5 first and second
level elements together with their children and grandchildren,
constraints on them as well as state recommendations and examples.

To avoid duplication of data and accommodate for the many possible
complex relationships among real world products, the 4 above named
elements maybe nested deeply (e.g. a **Branch** of a **Branch** \...) or
are clearly useful in many places like the **Full Product Name**.

The sub sections introducing **Branch, Relationship**, and **Product
Groups** try to further offer such topological usage information to aid
the reader in creating or navigating the graph that can be spanned by
instances of a **Product Tree**.

Product Tree
------------

Element prod:ProductTree

« The optional prod:ProductTree element MUST occur with cardinality
\[0, 1\] as child of cvrf:cvrfdoc. » \[CSAF-5.1-1\]

« If given, the instance MUST contain prod:Branch \[0, ∞\],
prod:FullProductName \[0, ∞\], prod:FullProductName \[0, ∞\],
prod:ProductGroups \[0, 1\], elements with noted cardinalities and in
that order. » \[CSAF-5.1-2\]

The optional element prod:ProductTree is a container for all fully
qualified product names that can be referenced elsewhere in the
document.

References to be named specifically when describing the products that
are affected by a vulnerability using the **Product Statuses**,
**Vulnerability Threats**, **Vulnerability** **CVSS Score Sets**, and
**Vulnerability** **Remediation** containers.

The **Product Tree** can have as many branches as needed, but every
endpoint of the tree must be terminated with a **Full Product Name**
element, which represents a product that can be referenced elsewhere.

Example :

\<prod:ProductTree\>\
\<prod:Branch Name=\"Vendorix\" Type=\"Vendor\"\>\
\<prod:Branch Name=\"\... Appliances\" Type=\"Product Name\"\>\
\<prod:Branch Name=\"1.0\" Type=\"Product Version\"\>\
\<prod:Branch Name=\".0\" Type=\"Service Pack\"\>\
\<prod:FullProductName ProductID=\"CVRFPID-223152\"\>\
\... AppY 1.0.0\
\</prod:FullProductName\>\
\</prod:Branch\>\
\<prod:Branch Name=\"(2)\" Type=\"Service Pack\"\>\
\<prod:FullProductName ProductID=\"CVRFPID-223153\"\>\
\... AppY 1.0(2)\
\</prod:FullProductName\>\
\</prod:Branch\>\
\</prod:Branch\>\
\<prod:Branch Name=\"1.1\" Type=\"Product Version\"\>\
\<prod:Branch Name=\".0\" Type=\"Service Pack\"\>\
\<prod:FullProductName ProductID=\"CVRFPID-223155\"\>\
\... AppY 1.1.0\
\</prod:FullProductName\>\
\</prod:Branch\>\
\<prod:Branch Name=\"(1)\" Type=\"Service Pack\"\>\
\<prod:FullProductName ProductID=\"CVRFPID-223156\"\>\
\... AppY 1.1(1)\
\</prod:FullProductName\>\
\</prod:Branch\>\
\</prod:Branch\>\
\</prod:Branch\>\
\</prod:Branch\>\
\</prod:ProductTree\> 

Map of **Product Tree** including the parent node (**Document**) in some
valid configuration spanning multiple sub trees:

Figure : A topologically valid **Product Tree** configuration.

Again, some decent coloring has been applied to above graph to balance
visual hints with accessibility. The mathematical closed interval
notation has been used to annotate the minimum and maximum occurrences
of elements, where the infinity symbol (∞) translates to the term
unbounded in XML lingo.

The pale gray color of the **Full Product Name** representative nodes
shall indicate that they are more used like labels all over the
topology. The nodes carrying an ellipsis (...) shall hint at possible
further deep nesting of the sub trees where they are attached.

### Product Tree -- Branch

Element prod:Branch

« The optional prod:Branch choice element MUST occur with cardinality
\[0, ∞\] inside the prod:ProductTree element or nested inside other
prod:Branch instances.\
» \[CSAF-5.1.1-1\]

« An instance MUST contain either a prod:Branch or a
prod:FullProductName element.\
» \[CSAF-5.1.1-2\]

The prod:FullProductName element has no children (is thus always a
terminating or leaf element) while a prod:Branch can either contain
further children or terminate its tree branch.

##### Attribute Name {#attribute-name .MemberHeading}

The mandatory Name attribute of the **Branch** element and its relation
to the equally required Type attribute are documented in section 2.2.3
[Product Branch Type Model](#_Product_Branch_Type).

##### Attribute Type {#attribute-type-3 .MemberHeading}

The required Type attribute of the **Branch** element is documented in
section 2.2.3 [Product Branch Type Model](#_Product_Branch_Type).

Non-normative comment:

A choice element behaves as a regular container that can have different
child elements, but with the difference that only exactly one child
element can be chosen. It is similar in concept to the "union"
programming construct in which one variable can have one of several
different predefined data types.

 

Example : []{#exampleNestedBranches .anchor}Nesting of **Branches** in a
**Branch** subtree:

\<prod:Branch Type=\"Vendor\" Name=\"Microsoft\"\>\
\<prod:Branch Type=\"Product Family\" Name=\"Windows\"\>\
\<prod:Branch Type=\"Product Name\" Name=\"Vista\"\>\
\<prod:Branch Type=\"Service Pack\" Name=\"1\"\>\
\<prod:FullProductName ProductID=\"CVRFPID-0001\"\>\
Microsoft Windows Vista Service Pack 1\
\</prod:FullProductName\>\
\</prod:Branch\>\
\<prod:Branch Type=\"Service Pack\" Name=\"2\"\>\
\<prod:FullProductName ProductID=\"CVRFPID-0002\"\>\
Microsoft Windows Vista Service Pack 2\
\</prod:FullProductName\>\
\</prod:Branch\>\
\</prod:Branch\>\
\</prod:Branch\>\
\<prod:Branch Type=\"Product Family\" Name=\"Office\"\>\
\<prod:Branch Type=\"Product Name\" Name=\"Word 2010\"\>\
\<prod:Branch Type=\"Service Pack\" Name=\"0\"\>\
\<prod:Branch Type=\"Architecture\" Name=\"x86\"\>\
\<prod:FullProductName ProductID=\"CVRFPID-0003\"\>\
Microsoft Word 2010 (32-bit editions)\
\</prod:FullProductName\>\
\</prod:Branch\>\
\</prod:Branch\>\
\</prod:Branch\>\
\</prod:Branch\>\
\</prod:Branch\>

A more visual display of the same structure from [above
example](#exampleNestedBranches) is shown in the figure below (**Error!
Reference source not found.**).

Map of **Branch** sub tree from above [example of nested
Branches](#exampleNestedBranches) including the parent node (**Product
Tree** left out in XML source code example) with some textual hints to
map the topologies:

Figure : A topologically valid **Branch** configuration

### Product Tree -- Full Product Name

Element prod:FullProductName

« The prod:FullProductName element MUST be a child of cardinality \[1,
∞\] for all possible locations inside the product tree representation.
» \[CSAF-5.1.2-1\]

This elements instances have multiple possible parent elements:
prod:ProductTree, prod:Releationship, and prod:Branch.

The prod:FullProductName elements define the endpoints of the **Product
Tree** and occur either directly at the root level, at the branch level,
or as the result of a relationship between two products.

The value of a **Full Product Name** element should be the product's
full canonical name, including version number and other attributes, as
it would be used in a human-friendly document.

##### Attribute ProductID {#attribute-productid .MemberHeading}

The ProductID attribute is a token required to identify a **Full Product
Name** so that it can be referred to from other parts in the document.

There is no predefined or required format for the ProductID as long as
it uniquely identifies a product in the context of the current document.

##### Attribute CPE {#attribute-cpe .MemberHeading}

The (Common Platform Enumeration) CPE attribute refers to a method for
naming platforms external to CSAF CVRF.

« The CPE attribute if present MUST have a value, that is a valid
cpe-lang:namePattern as defined in the external specification
\[[CPE23\_N](#refCPE23_N)\] and related schemas. » \[CSAF-5.1.2-2\]

Non-normative comment:

Examples for ProductID values include incremental integers or Globally
Unique Identifiers (GUIDs).

The structure for CPE as required for a valid CSAF CVRF document is
described in its specification documents (\[[CPE23\_N](#refCPE23_N)\] et
al.).

In short: The CPE can be either an integer (if there exists a known
entry for the platform in question) or a candidate string from the
vendor if no commonly registered entry yet exists (at the NIST CPE
registry site).

Example :

\<FullProductName ProductID=\"CVRFPID-0004\"\>\
Microsoft Host Integration Server 2006 Service Pack 1\
\</FullProductName\>

Example :

\<FullProductName ProductID=\"CVRFPID-0005\"\>\
Microsoft Office 2008 for Mac 12.3.1 Update\
\</FullProductName\>

### Product Tree -- Relationship

Element prod:Relationship

« The prod:Relationship element MUST be present with cardinality \[0,
∞\] in prod:Tree and if given MUST contain one or more
prod:FullProductName instances. » \[CSAF-5.1.3-1\]

The prod:Relationship element establishes a link between two existing
**Full Product Name** elements, allowing the document producer to define
a combination of two products that form a new **Full Product Name**
entry.

As a **Relationship** connects two existing products with each other,
there need to be at least two **Full Product Name** entries present in
the **Product Tree** before a Relationship element can be created.

**Relationship** elements live at the root of a **Product Tree**, and
they have three mandatory attributes: ProductReference and
RelatesToProductReference each contain the ProductID token for the two
products that will form the relationship, and the RelationType attribute
defines how the products are related.

##### Attribute ProductReference {#attribute-productreference .MemberHeading}

The required ProductReference attribute contains the ProductID token of
one of the two products that will form the relationship. For directed
relationships the producer SHOULD associate correctly.

##### Attribute RelationType {#attribute-relationtype .MemberHeading}

The allowed values of the required RelationType attribute are of an
enumeration type and as defined in 2.2.4 [Product Relationship Type
Model](#_Product_Relationship_Type).

##### Attribute RelatesToProductReference {#attribute-relatestoproductreference .MemberHeading}

The required RelatesToProductReference attribute contains the ProductID
token of the other of the two products that will form the relationship.
Again: For directed relationships the producer SHOULD associate
correctly.

Non-normative comment:

The situation where a need for declaring a Relationship arises, is given
when a product is e.g. vulnerable only when installed together with
another, or to describe operating system components.

Example :

The first product is defined as:  

\<FullProductName ProductID=\"CVRFPID-0007\"\>\
Active Directory Lightweight Directory Service\
\</FullProductName\>

And the second product is defined as:

\<FullProductName ProductID=\"CVRFPID-0008\"\>\
Windows Vista Service Pack 2\
\</FullProductName\>

And the relationship can then be defined as:

\<Relationship ProductReference=\"CVRFPID-0007\"\
RelationType=\"Optional Component Of\"\
RelatesToProductReference=\"CVRFPID-0008\"\>\
\<FullProductName ProductID="CVRFPID-0009\>\
Active Directory Lightweight Directory Service as an optional component
of\
Windows Vista Service Pack 2\
\</FullProductName\>\
\</Relationship\>

Example :

In another example, the first product is defined as:

\<FullProductName ProductID=\"CVRFPID-0010\"\>\
Cisco AnyConnect Secure Mobility Client 2.3.185\
\</FullProductName\>

And the second product is defined as:

\<FullProductName ProductID=\"CVRFPID-0011\"\>Microsoft
Windows\</FullProductName\>

And the relationship can then be defined as:

\<Relationship ProductReference=\"CVRFPID-0010\"
RelationType=\"Installed On\"\
RelatesToProductReference=\"CVRFPID-0011\"\>\
\<FullProductName ProductID="CVRFPID-0012\>\
Cisco AnyConnect Secure Mobility Client 2.3.185 when installed on\
Microsoft Windows\
\</FullProductName\>\
\</Relationship\>

### Product Tree -- Product Groups

Element prod:ProductGroups

« The prod:ProductGroups element MUST be present zero or one time inside
a given prod:ProductTree element and if present MUST contain one or more
prod:Group elements. » \[CSAF-5.1.4-1\]

The element prod:ProductGroups is a container, that defines whether
**Full Product Name** elements in the product tree will be grouped into
logical groups.

If groups are defined, products can be referred to using the GroupID
attribute in many other parts of the document, rather than repeatedly
having to list all members individually.

Whether groups are defined or not, the ability to reference each product
individually in other parts of the document is not affected. In fact,
the creator of a document can choose to use either direct product
references or group references.

Non-normative comment:

Given that a single product can be a member of more than one group, some
areas of the CSAF CVRF document may prohibit product references by group
to avoid ambiguity.

Example :

We create two groups, CVRFGID-0001 and CVRFGID-0002. Both groups have
four members, and ProductID CVRFPID-0001 is a member of both groups:  

\<ProductGroups\>\
\<Group GroupID=\"CVRFGID-0001\"\>\
\<ProductID\>CVRFPID-0001\</ProductID\>\
\<ProductID\>CVRFPID-0002\</ProductID\>\
\<ProductID\>CVRFPID-0003\</ProductID\>\
\<ProductID\>CVRFPID-0004\</ProductID\>\
\</Group\>\
\<Group GroupID=\"CVRFGID-0002\"\>\
\<ProductID\>CVRFPID-0001\</ProductID\>\
\<ProductID\>CVRFPID-0010\</ProductID\>\
\<ProductID\>CVRFPID-0011\</ProductID\>\
\<ProductID\>CVRFPID-0099\</ProductID\>\
\</Group\>\
\</ProductGroups\>

A visual map of some fictitious sample **Product Groups** sub tree
including the parent node (**Product Tree**) with the node labeled {...}
indicating further possible **Group** subtrees is depicted below.

Figure : A topologically valid **Product Groups** configuration

#### Product Tree -- Product Groups -- Group

Element prod:Group

« The prod:Group element MUST be present one or more times as child of
the optional prod:ProductGroups element and MUST contain zero or one
prod:Description and 2 or more prod:ProductID elements and in that
order. » \[CSAF-5.1.4.1-1\]

The element prod:Group is a container, that defines a new logical group
of products that can then be referred to in other parts of the document
to address a group of products with a single identifier.

**Group** members are defined by adding one **Product ID** element for
every member of the group.

##### Attribute GroupID {#attribute-groupid .MemberHeading}

The GroupID attribute is required to identify a **Group** so that it can
be referred to from other parts in the document.

There is no predefined or required format for the GroupID as long as it
uniquely identifies a group in the context of the current document.

Non-normative comment:

Examples for GroupID attribute values include incrementing integers or
GUIDs.

##### Product Tree -- Product Groups -- Group -- Description

Element prod:Description

« The prod:Description element MUST be present zero or one time in
prod:Group and if given is a short, optional description of the group.
» \[CSAF-5.1.4.1.1-1\]

Example :

\<ProductGroups\>\
\<Group GroupID=\"CVRFGID-0001\"\>\
\<Description\>The x64 versions of the operating
system.\</Description\>\
\<ProductID\>CVRFPID-0001\</ProductID\>\
\<ProductID\>CVRFPID-0002\</ProductID\>\
\<ProductID\>CVRFPID-0003\</ProductID\>\
\<ProductID\>CVRFPID-0004\</ProductID\>\
\</Group\>\
\</ProductGroups\>

##### Product Tree -- Product Groups -- Group -- Product ID

Element prod:ProductID

« The prod:ProductID element MUST be present 2 or more times in
prod:Group elements and every instance defines a member of a group by
referring to the unique ProductID attribute of a **Full Product Name**
element. » \[CSAF-5.1.4.1.2-1\]

Example :

If the two products "Microsoft Windows Vista Service Pack 1" and
"Microsoft Windows Vista Service Pack 2" have been defined in the
product tree as follows:

\<FullProductName ProductID=\"CVRFPID-0001\"\>\
Microsoft Windows Vista Service Pack 1\
\</FullProductName\>\
\<FullProductName ProductID=\"CVRFPID-0002\"\>\
Microsoft Windows Vista Service Pack 2\
\</FullProductName\>

They can both be made a member of the same group with Group ID
"GRP-0001":

\<ProductGroups\>\
\<Group GroupID=\"GRP-0001\"\>\
\<ProductID\>CVRFPID-0001\</ProductID\>\
\<ProductID\>CVRFPID-0002\</ProductID\>\
\</Group\>\
\</ProductGroups\>

Later in the document, both products can be referenced together using
the Group ID:

\<Remediations\>\
\<Remediation Type=\"Vendor Fix\"\>\
\<Description\>Security Update for Windows Vista\</Description\>\
\<GroupID\>GRP-0001\</GroupID\>\
\</Remediation\>\
\</Remediations\>

The ability to reference both products individually will also be
maintained (and in some cases required):

\<Remediations\>\
\<Remediation Type=\"Vendor Fix\"\>\
\<Description\>Security Update for Windows Vista\</Description\>\
\<ProductID\>CVRFPID-0001\</ProductID\>\
\<ProductID\>CVRFPID-0002\</ProductID\>\
\</Remediation\>\
\</Remediations\>

Vulnerability Schema Elements
=============================

Vulnerability information in CSAF CVRF is modeled as zero or more
top-level Vulnerability element instances of vuln:Vulnerability (defined
in the vulnerability schema file within the vuln namespace).

« The following listed 14 second-level elements MUST appear in the order
listed if given as elements of the top-level element Vulnerability:

5.  **Title**: vuln:Title

6.  **ID**: vuln:ID

7.  **Notes**: vuln:Notes

8.  **Discovery Date**: vuln:DiscoveryDate

9.  **Release Date**: vuln:ReleaseDate

10. **Involvements**: vuln:Involvements

11. **CVE**: vuln:CVE

12. **CWE**: vuln:CWE

13. **Product Statuses**: vuln:ProductStatuses

14. **Threats**: vuln:Threats

15. **CVSS Score Sets**: vuln:CVSSScoreSets

16. **Remediations**: vuln:Remediations

17. **References**: vuln:References

18. **Acknowledgements**: vuln:Acknowledgements

» \[CSAF-6-1\]

The remaining sub sections will describe the above 15 first and second
level elements together with their children and grandchildren,
constraints on them as well as state recommendations and examples.

Vulnerability
-------------

Element vuln:Vulnerability

« The vuln:Vulnerability element MUST be present zero more times in
cvrf:cvrfdoc and MUST contain the following child elements vuln:Title
\[0, 1\], vuln:ID \[0, 1\], vuln:Notes \[0, 1\], vuln:DiscoveryDate
\[0, 1\], vuln:ReleaseDate \[0, 1\], vuln:Involvements \[0, 1\],
vuln:CVE \[0, 1\], vuln:CWE \[0, ∞\], vuln:ProductStatuses \[0, 1\],
vuln:Threats \[0, 1\], vuln:CVSSScoreSets \[0, 1\], vuln:Remediation
\[0, 1\], vuln:References \[0, 1\], and vuln:Acknowledgments \[0, 1\] as
per given cardinalities and in that order. » \[CSAF-6.1-1\]

The optional element vuln:Vulnerability is a container for the
aggregation of all fields that are related to a single vulnerability in
the document.

The cardinality allows to describe zero, one, or many vulnerabilities in
a single CSAF CVRF document.

##### Attribute Ordinal {#attribute-ordinal-1 .MemberHeading}

« The required attribute Ordinal is a locally significant value used to
track vulnerabilities inside a CSAF CVRF document that MUST be an
integer in the interval \[1, ∞\]. » \[CSAF-6.1-2\]

It is provided to enable specific vulnerabilities to be referenced from
elsewhere in the document (or even outside the namespace of a document
provided that a unique **Document Title** and **Revision** information
are provided).

There SHOULD be one of these values for every **Vulnerability**
container in a document, and it is recommended that Ordinal should be
instantiated as a monotonically increasing counter, indexed from 1.

Example :

\<Vulnerability Ordinal=\"1\"\
xmlns=\"http://docs.oasis-open.org/csaf/ns/csaf-cvrf/v1.2/vuln\"\>\
\<!\-- \... All children optional, ; sample valid, albeit otherwise
useless \--\>\
\</Vulnerability\>

A visual map of **Vulnerability** element including the parent node
(**Document**) in some valid configuration spanning multiple sub trees
is given below.

Figure : A topologically valid **Vulnerability** configuration.

As before, some decent coloring has been applied to above graph as usual
to balance visual hints with accessibility. Also, the mathematical
closed interval notation has been used to annotate the minimum and
maximum occurrences of elements, where the infinity symbol (∞)
translates to the term unbounded in XML lingo.

The nodes carrying an ellipsis (...) here are to be read combined with
the rounded edge rectangles, as the latter list the represented leaf
elements that did not well fit into the picture.

Vulnerability -- Title
----------------------

Element vuln:Title

« The vuln:Title element MUST be present zero or one time in
vuln:Vulnerability and if present gives the document producer the
ability to apply a canonical name or title to the vulnerability.
» \[CSAF-6.2-1\]

To avoid confusion, it is recommended that, if employed, this element
commensurately match the nomenclature used by any numbering or
cataloging systems references elsewhere, such as the **Document Title**
or **CVE.**

Example :

\<Title\>February 2011 TelePresence Vulnerability Bundle\</Title\>

Vulnerability -- ID
-------------------

Element vuln:ID

« The vuln:ID element MUST be present zero or one time in
vuln:Vulnerability and if present gives the document producer a place to
publish a unique label or tracking ID for the vulnerability (if such
information exists). » \[CSAF-6.3-1\]

The value domain for vuln:ID elements is further documented in section
2.2.14 [Vulnerability ID Type Model](#_Vulnerability_ID_Type).

The attribute SystemName is required.

##### Attribute SystemName {#attribute-systemname .MemberHeading}

The required attribute SystemName indicates the name of the
vulnerability tracking or numbering system that this **ID** comes from.

Every **ID** value SHOULD have exactly one SystemName.

Non-normative comment:

It is helpful if document producers use unique and consistent system
names.

Example :

\<Vulnerability\>\
\<ID SystemName=\"Cisco Bug ID\"\>CSCso66472\</ID\>\
\</Vulnerability\>

Vulnerability -- Notes
----------------------

Element vuln:Notes

« The vuln:Notes element MUST be present zero or one time in
vuln:Vulnerability and if present contain one or more vuln:Note
elements.\
» \[CSAF-6.4-1\]

The element vuln:Notes is a container that holds all vulnerability-level
**Note** elements.

### Vulnerability -- Notes -- Note

Element vuln:Note

« The vuln:Note element MUST be present one or more times in vuln:Notes
and is a place to put all manner of text blobs related to the
vulnerability. » \[CSAF-6.4.1-1\]

Text should be limited to talking about the impacts, vectors, or caveats
of this node and should not contain details to other vulnerabilities in
the document. It is, however, acceptable to refer to a vulnerability
that is not in the document for the purposes of pointing out a
regression.

The vuln:Note element has four attributes, two of them are required:
Type and Ordinal.

Title and Audience are the two optional attributes to give human readers
context around what they are about to read.

Akin to the **Document Notes** element, the note SHOULD contain a
compartmentalized textual discussion constrained by its Type attribute.

##### Attribute Type {#attribute-type-4 .MemberHeading}

« The value of the attribute Type MUST be one of the enumeration values
as described in section 2.2.2 [Note Type Model](#_Note_Type_Model_2).
» \[CSAF-6.4.1-2\]

##### Attribute Ordinal {#attribute-ordinal-2 .MemberHeading}

Ordinal is a mandatory, locally significant value used to track notes
inside a CVRF document at the vulnerability level.

It is provided to uniquely identify a **Note**.

There should be one of these values for every **Note** inside
**Vulnerability Notes** and it is recommended that Ordinal SHOULD be
instantiated as a monotonically increasing counter, indexed from 1.

Every Ordinal that tracks a **Note** inside **Vulnerability Notes** is
completely independent from any Ordinal tracking a **Note** inside
**Document Notes**.

##### Attribute Title {#attribute-title-1 .MemberHeading}

The optional attribute Title SHOULD be a concise description of what is
contained in the text.

##### Attribute Audience {#attribute-audience-1 .MemberHeading}

The optional attribute Audience SHOULD indicate who is intended to read
it.

Example :

\<vuln:Notes\>\
\<vuln:Note Type=\"General\" Ordinal=\"1\" Title=\"Details\"
Audience=\"All\"\>\
These are some details about a vulnerability intended for\
all stakeholders.\
\</vuln:Note\>\
\</vuln:Notes\>

Vulnerability -- Discovery Date
-------------------------------

Element vuln:DiscoveryDate

« The vuln:DiscoveryDate element MUST be present zero or one time inside
any vuln:Vulnerability instance element and if given holds the date and
time the vulnerability was originally discovered. » \[CSAF-6.5-1\]

All date like values in CSAF CVRF require a date and a time (cf. section
2.2.1 [Date and Time](#_Date_and_Time_1)).

Example :

\<DiscoveryDate\>2010-11-03T00:00:00Z\</DiscoveryDate\>

Vulnerability -- Release Date
-----------------------------

Element vuln:ReleaseDate

« The vuln:ReleaseDate element MUST be present zero or one time inside
any vuln:Vulnerability instance element and if given holds the date and
time the vulnerability was originally released into the wild.
» \[CSAF-6.6-1\]

All date like values in CSAF CVRF require a date and a time (cf. section
2.2.1 [Date and Time](#_Date_and_Time_1)).

Example :

\<ReleaseDate\>2010-11-16T00:00:00Z\</ReleaseDate\>

Vulnerability -- Involvements
-----------------------------

Element vuln:Involvements

« The vuln:Involvements MUST be present zero or one time inside any
vuln:Vulnerability element and if present contain one or more
vuln:Involvement elements. » \[CSAF-6.7-1\]

The optional element vuln:Involvements is a container that holds one or
more **Involvement** containers, which allow the document producers (or
third parties) to comment on their level of involvement in the
vulnerability identification, scoping, and remediation process.

Matching the possibly multiple **Involvements** containers, multiple
parties can comment on their levels of involvement.

### Vulnerability -- Involvements -- Involvement

Element vuln:Involvement

« The vuln:Involvment element MUST be present one or more times in
vuln:Involvements and MUST contain zero or one vuln:Description
elements. » \[CSAF-6.7.1-1\]

The element vuln:Involvement is a container, that allows the document
producers to comment on their level of Involvement (or engagement) in
the vulnerability identification, scoping, and remediation process.

The two attributes Party and Status are both required.

##### Attribute Party {#attribute-party .MemberHeading}

The attribute Party indicates the type of the producer issuing the
status.

It is identical to the **Document Publisher** attribute Type.

Most of the time, both attributes will be the same because document
producers will issue an **Involvement** status on their own behalf.

However, if the document producer wants to issue a status on behalf of a
third party and use a different type from that used in **Document
Publisher**, that use is allowed by the schema.

If this is the case, **Description** should contain additional context
regarding what is going on.

« The value of the attribute Party MUST be as defined in
section 2.2.6 [Publisher Type Model](#_Publisher_Type_Model).\
» \[CSAF-6.7.1-2\]

##### Attribute Status {#attribute-status .MemberHeading}

« The attribute Status indicates the level of involvement of (the) Party
and the enumeration value MUST be as defined in
section 2.2.15 [Vulnerability Involvement Type
Model](#_Vulnerability_Involvement_Type).\
» \[CSAF-6.7.1-3\]

#### Vulnerability -- Involvements -- Involvement -- Description

Element vuln:Description

« The vuln:Description element MUST occur zero or one time in
vuln:Involvment and if present contains a string value, that represents
a thorough human-readable discussion of the **Involvement**.
» \[CSAF-6.7.1.1-1\]

Example :

\<Involvements\>\
\<Involvement Party=\"Vendor\" Status=\"In Progress\"\>\
\<Description\>\
Cisco acknowledges that the IronPort Email Security Appliances (ESA)\
and Cisco IronPort Security Management Appliances (SMA) contain a\
vulnerability that may allow a remote, unauthenticated attacker to\
execute arbitrary code with elevated privileges.\
A Mitigation is available.\
\</Description\>\
\</Involvement\>\
\</Involvements\>

Example :

\<Involvements\>\
\<Involvement Party=\"Researcher\" Status=\"Contact Attempted\"\>\
\<Description\>\
We emailed the vendor on February 14, 2012 when the vulnerability was\
first discovered by our team.\
\</Description\>\
\</Involvement\>\
\</Involvements\>

Example :

\<Involvements\>\
\<Involvement Party=\"Vendor\" Status=\"Completed\"\>\</Involvement\>\
\</Involvements\>

Vulnerability -- CVE
--------------------

Element vuln:CVE

« The vuln:CVE element MUST be present zero or one time in any
vuln:Vulnerability and if present its value holds the MITRE standard
Common Vulnerabilities and Exposures (CVE) tracking number for the
vulnerability and this value MUST match the pattern documented in
section 2.2.10 [Vulnerability CVE Type Model](#_Vulnerability_CVE_Type).
» \[CSAF-6.8-1\]

Non-normative comment:

CVE is a standard for vulnerability naming that provides improved
tracking of vulnerabilities over time across different reporting
sources. More information about CVE domain values can be found in
section 2.2.10 [Vulnerability CVE Type Model](#_Vulnerability_CVE_Type).

Example :

\<CVE\>CVE-2010-3864\</CVE\>

Vulnerability -- CWE
--------------------

Element vuln:CWE

« The vuln:CWE element MUST be present zero or one time in any
vuln:Vulnerability and if present it contains the MITRE standard Common
Weakness Enumeration (CWE) and this value MUST match the pattern
documented in section 2.2.13 [Vulnerability CWE Type
Model](#_Vulnerability_CWE_Type). » \[CSAF-6.9-1\]

Non-normative comment:

The CWE domain value type is described in section 2.2.13 [Vulnerability
CWE Type Model](#_Vulnerability_CWE_Type).

Example :

\<CWE ID=\"CWE-601\"\>URL Redirection to Untrusted Site (\'Open
Redirect\')\</CWE\> 

Example :

\<CWE ID=\"CWE-602\"\>Client-Side Enforcement of Server-Side
Security\</CWE\> 

Vulnerability -- Product Statuses
---------------------------------

Element vuln:ProductStatuses

« The vuln:ProductStatuses element MUST be present zero or one time in
any vuln:Vulnerability and if present it MUST contain one or more
vuln:Status elements which contain a subset of products chosen from
**Product Tree**. » \[CSAF-6.10-1\]

Every affected (and unaffected) product relating to the vulnerability is
referenced here, inside one or more **Status** containers.

There is a constraint in place to prevent a single product from being
assigned two different (conflicting) **Status** elements within the
scope of **Vulnerability**.

Likewise, a **Status** child container cannot be tied to a **Product
Group** due to the fact that a single product can be a member of more
than one product group.

Non-normative comment:

Without this constraint, it would be possible to assign conflicting
status information to one and the same product.

### Vulnerability -- Product Statuses -- Status

Element vuln:Status

« The vuln:Status element MUST be present with cardinality \[1, ∞\] in
vuln:ProductStatuses and MUST contain one or more vuln:ProductID
elements. » \[CSAF-6.10.1-1\]

##### Attribute Type {#attribute-type-5 .MemberHeading}

The allowed values of the Type attribute of a vuln:Status element are
documented in section 2.2.16 [Vulnerability Product Affected Status Type
Model](#_Vulnerability_Product_Affected). The element vuln:Status
contains one or more products as chosen from the **Product Tree**, and
defines the status of this product in the mandatory *Status* attribute.

 

#### Vulnerability -- Product Statuses -- Status -- Product ID

Element vuln:ProductID

« The vuln:ProductID element MUST be present one or more times inside a
vuln:Status element and defines a product as having the status defined
in the parent element's Type attribute. » \[CSAF-6.10.1.1-1\]

The reference is made via value by using the unique ProductID attribute
of a **Full Product Name** element that is defined in the **Product
Tree**.

« A single **Product ID** MUST not be assigned more than one status type
within the same **Vulnerability**. » \[CSAF-6.10.1.1-2\]

Example :

The three products "Microsoft Windows Vista (RTM)", "Microsoft Windows
Vista Service Pack 1", and "Microsoft Windows Vista Service Pack 2" have
been defined in the product tree as follows:  

\<ProductTree\>\
\<FullProductName ProductID=\"CVRFPID-0000\"\>\
Microsoft Windows Vista (RTM)\
\</FullProductName\>\
\<FullProductName ProductID=\"CVRFPID-0001\"\>\
Microsoft Windows Vista Service Pack 1\
\</FullProductName\>\
\<FullProductName ProductID=\"CVRFPID-0002\"\>\
Microsoft Windows Vista Service Pack 2\
\</FullProductName\>\
\</ProductTree\>

If Windows Vista RTM and Service Pack 1 are known to be affected, and
Service Pack 2 is known not to be affected, it can be documented as
follows:

\<Vulnerability Ordinal=\"1\"\>\
\<Product Statuses\>\
\<Status Type=\"KnownAffected\"\>\
\<ProductID\>CVRFPID-0000\</ProductID\>\
\<ProductID\>CVRFPID-0001\</ProductID\>\
\</Status\>\
\<Status Type=\"KnownNotAffected\"\>\
\<ProductID\>CVRFPID-0002\</ProductID\>\
\</Status\>\
\</Product Statuses\>\
\</Vulnerability\>

Vulnerability -- Threats
------------------------

Element vuln:Threats

« The vuln:Threats element MUST be present zero or one time inside any
vuln:Vulnerability and if present it MUST contain one or more
vuln:Threat elements which contain information about a vulnerability
that can change with time. » \[CSAF-6.11-1\]

Non-normative comment:

Threat information about a vulnerability that can change with time is
also called "vulnerability kinetics".

A visual map of some valid **Threats** configuration including the
parent node (**Vulnerability**) --- again with the node labeled {...}
indicating further possible **Threat** subtrees follows below.

Figure : A topologically valid **Threats** configuration.

### Vulnerability -- Threats -- Threat

Element vuln:Threat

« The vuln:Threat element MUST be present with cardinality \[1, ∞\] as
in vuln:Threats and MUST contain exactly one vuln:Description element
and zero or more vuln:ProductID and vuln:GroupID elements and in that
order. » \[CSAF-6.11.1-1\]

The element vuln:Threat contains the vulnerability kinetic information.
This information can change as the vulnerability ages and new
information becomes available.

The attribute Type is required and categorizes the threat according to
the rules in section 2.2.18 [Vulnerability Threat Type
Model](#_Vulnerability_Threat_Type). 

A **Threat** container is tied to one or more specific products by
referencing these products using either the **Product ID** or **Group
ID** child elements.

If the **Threat** is meant to be general or nonspecific for all
products, the **Product ID** and **Group ID** child elements SHOULD be
omitted.

##### Attribute Type {#attribute-type-6 .MemberHeading}

The allowed enumerated values for the Type attribute are documented in
section 2.2.18 [Vulnerability Threat Type
Model](#_Vulnerability_Threat_Type).

##### Attribute Date {#attribute-date .MemberHeading}

The Date attribute is optional, but if given it must contain a date time
value as documented in section 2.2.1 [Date and Time](#_Date_and_Time_1).

#### Vulnerability -- Threats -- Threat -- Description

Element vuln:Description

« The vuln:Description element MUST be present exactly once in
vuln:Threat and the string content represents a thorough human-readable
discussion of the **Threat**. » \[CSAF-6.11.1.1-1\]

Example : Impact: 

\<Threat Type=\"Impact\"\>\
\<Description\>complete compromise of the integrity of affected machines
\</Description\>\
\</Threat\>

Example : Exploit Status:

\<Threat Type=\"Exploit Status\"\>\
\<Description\>none\</Description\>\
\<Date\>2011-11-26T00:00:00+00:00\</Date\>\
\<ProductID\>CVRFPID-0000\</ProductID\>\
\</Threat\>

Example : Exploit Status without Product ID:

\<Threat Type=\"Exploit Status\"\>\
\<Description\>proof of concept\</Description\>\
\</Date\>2011-11-26T00:00:00+00:00\</Date\>\
\</Threat\>

Example : Target Set:

\<Threat Type=\"Target Set\"\>\
\<Description\>Financial Institutions\</Description\>\
\</Threat\>

Example : Target Set variation of content:

\<Threat Type=\"Target Set\"\>\
\<Description\>US Government Agencies\</Description\>\
\</Threat\>

Example : Target Set with another variation of content:

\<Threat Type=\"Target Set\"\>\
\<Description\>All versions of BIND\</Description\>\
\</Threat\>

#### Vulnerability -- Threats -- Threat -- Product ID

Element vuln:ProductID

« The vuln:ProductID element MUST be present with the cardinality \[0,
∞\] in vuln:Threat element and if given represents a reference by value
to the related product via the unique ProductID attribute of the
matching **Full Product Name** element.\
» \[CSAF-6.11.1.2-1\]

If a **Threat** applies to more than one Product, either additional
**Product ID** elements or **Group ID** elements (replacing/combining
those) SHOULD be added.

#### Vulnerability -- Threats -- Threat -- Group ID

Element vuln:GroupID

« The vuln:GroupID element MUST be present with the cardinality \[0, ∞\]
in a vuln:Threat element and if given represents a reference by value to
the related products via the unique GroupID attribute of a **Group**
element that is defined in the **Product Tree**. » \[CSAF-6.11.1.3-1\]

If the **Threat** pertains to several products that have been logically
grouped into a **Product Group** optional element vuln:GroupID
represents a reference to that group of products.

If a **Threat** applies to more than one group of products, multiple
**Group ID** elements are added accordingly.

Vulnerability -- CVSS Score Sets
--------------------------------

Element vuln:CVSSScoreSets

« The vuln:CVSSScoreSets element MUST present zero or one time per and
inside any vuln:Vulnerability and holds one or more of the
vuln:ScoreSetV2 (deprecated) or vuln:ScoreSetV3 (preferred) container
elements and in that order if instances of both are present.
» \[CSAF-6.12-1\]

A visual map of some valid **CVSS Score Sets** configuration including
the parent node (**Vulnerability**) --- again the node with label {...}
indicates further possible **Score Set V3** (preferred) or ***Score Set
V2*** (deprecated) subtrees is shown below:

Figure A topologically valid **CVSS Score Sets** configuration.

### Vulnerability -- CVSS Score Sets -- Score Set V2

Element vuln:ScoreSetV2

« The vuln:ScoreSetV2 element MUST be present with cardinality \[0, ∞\]
inside vuln:CVSSScoreSets and if given, every instance MUST hold at
least exactly one vuln:BaseScoreV2 element. » \[CSAF-6.12.1-1\]

« Any vuln:ScoreSetV2 instance MAY additionally provide the further
children: vuln:TemporalScoreV2 \[0, 1\], vuln:EnvironmentalScoreV2 \[0,
1\], vuln:VectorV2 \[0, 1\], vuln:ProductID \[0, ∞\] and in that order.
» \[CSAF-6.12.1-2\]

If a value of the temporal or environmental score is set to "not
defined", the corresponding elements SHOULD be omitted.

The allowed values for the children of the vuln:ScoreSetV2 element are
documented in section 2.2.11 [Vulnerability CVSS Version 2 Type
Model](#_Vulnerability_CVSS_Version_2).

Non-normative comment:

If given, instances hold the actual CVSS version 2
metrics \[[CVSS2](#refCVSS2)\]

See also section 2.2.11 [Vulnerability CVSS Version 2 Type
Model](#_Vulnerability_CVSS_Version) for further information and
constraints on the values of the containers components.

A **Score Set V2** container can be tied to one or more specific
products by referencing these products using the **Product ID** child
element. If the **Score Set V2** is meant to be applied for all
products, the *Product ID* attribute should be omitted.

Note there is a constraint in place to prevent having a single product
assigned to two different score sets within the scope of a
**Vulnerability**. Likewise, a **Score Set V2** cannot be tied to a
**Product Group** due to the fact that a single product can be a member
of more than one product group. Without this constraint, it would be
possible to assign conflicting base score information to one and the
same product.

#### Vulnerability -- CVSS Score Sets -- Score Set V2 -- Base Score V2

Element vuln:BaseScoreV2

« The vuln:BaseScoreV2 element MUST be present exactly once inside every
vuln:ScoreSetV2 and contains the numeric value of the computed CVSS
version 2 base score.\
» \[CSAF-6.12.1.1-1\]

The finite set of allowed values the vuln:BaseScoreV2 element is
documented in section 2.2.11 [Vulnerability CVSS Version 2 Type
Model](#_Vulnerability_CVSS_Version_2).

#### Vulnerability -- CVSS Score Sets -- Score Set V2 -- Temporal Score V2

Element vuln:TemporalScoreV2

« The vuln:TemporalScoreV2 element MUST be present zero or one time
inside any vuln:ScoreSetV2 and if given contains the numeric value of
the computed CVSS version 2 temporal score. » \[CSAF-6.12.1.2-1\]

The finite set of allowed values for the vuln:TemporalScoreV2 element is
documented in section 2.2.11 [Vulnerability CVSS Version 2 Type
Model](#_Vulnerability_CVSS_Version_2).

#### Vulnerability -- CVSS Score Sets -- Score Set V2 -- Environmental ScoreV2

Element vuln:EnvironmentalScoreV2

« The vuln:EnvironmentalScoreV2 element MUST be present zero or one time
inside any vuln:ScoreSetV2 and if given contains the numeric value of
the computed CVSS version 2 environmental score. » \[CSAF-6.12.1.3-1\]

The finite set of allowed values for the vuln:EnvironmentalScoreV2
element are documented in section 2.2.11 [Vulnerability CVSS Version 2
Type Model](#_Vulnerability_CVSS_Version_2).

Non-normative comment:

This metric is typically reserved for use by the end user and is
specific to the environment in which the affected product is deployed.
See also section 2.2.11 [Vulnerability CVSS Version 2 Type
Model](#_Vulnerability_CVSS_Version) for further information and
constraints on this element.

#### Vulnerability -- CVSS Score Sets -- Score Set V2 -- Vector V2

Element vuln:VectorV2

« The vuln:VectorV2 element MUST be present zero or one time inside any
vuln:ScoreSetV2 and if present contains the official string notation
that displays all the values used to compute the CVSS version 2 base,
temporal, and environmental scores. » \[CSAF-6.12.1.4-1\]

The allowed values for the vuln:VectorV3 element are documented in
section 2.2.11 [Vulnerability CVSS Version 2 Type
Model](#_Vulnerability_CVSS_Version_2).

Example :

\<VectorV2\>AV:N/AC:L/Au:N/C:P/I:P/A:C/E:P/RL:O/RC:C/CDP:H/TD:M/CR:H/IR:H/AR:H\<VectorV2\>

#### Vulnerability -- CVSS Score Sets -- Score Set V2 -- Product ID

Element vuln:ProductID

« The vuln:ProductID element MUST be present with cardinality \[0, ∞\|
inside any vuln:ScoreSetV2 element and per instance value references to
unique ProductID attributes of **Full Product Name** elements defined in
the **Product Tree** are noted.\
» \[CSAF-6.12.1.5-1\]

If a **Score Set V2** applies to more than one product, you can add
multiple **Product ID** elements as references accordingly.

Any single **Product ID** is to be assigned to exactly none or one
**Score Set V2** within the same **Vulnerability**.

### Vulnerability -- CVSS Score Sets -- Score Set V3

Element vuln:ScoreSetV3

« The vuln:ScoreSetV3 element MUST be present with cardinality \[0, ∞\]
inside vuln:CVSSScoreSets and if given, every instance MUST hold at
least exactly one vuln:BaseScoreV3 element. » \[CSAF-6.12.2-1\]

« Any vuln:ScoreSetV3 instance MAY additionally provide the further
children: vuln:TemporalScoreV3 \[0, 1\], vuln:EnvironmentalScoreV3 \[0,
1\], vuln:VectorV3 \[0, 1\], vuln:ProductID \[0, ∞\] and in that order.
» \[CSAF-6.12.2-2\]

If a value of the temporal or environmental score is set to "not
defined", the corresponding elements SHOULD be omitted.

The allowed values for the children of the vuln:ScoreSetV3 element are
documented in section 2.2.12 [Vulnerability CVSS Version 3 Type
Model](#_Vulnerability_CVSS_Version_1).

Non-normative comment:

If given, instances hold the actual CVSS version 3
metrics \[[CVSS3](#refCVSS3)\].

See also section 2.2.12 [Vulnerability CVSS Version 3 Type
Model](#_Vulnerability_CVSS_Version_1) for further information and
constraints on the values of the containers components.

A **Score Set V3** container can be tied to one or more specific
products by referencing these products using the **Product ID** child
element. If the **Score Set V3** is meant to be applied for all
products, the *Product ID* attribute should be omitted.

Note there is a constraint in place to prevent having a single product
assigned to two different score sets within the scope of a
**Vulnerability**. Likewise, a **Score Set V2** cannot be tied to a
**Product Group** due to the fact that a single product can be a member
of more than one product group. Without this constraint, it would be
possible to assign conflicting base score information to one and the
same product.

#### Vulnerability -- CVSS Score Sets -- Score Set V3 -- Base Score V3

Element vuln:BaseScoreV3

« The vuln:BaseScoreV3 element MUST be present exactly once inside every
vuln:ScoreSetV3 and contains the numeric value of the computed CVSS
version 3 base score. » \[CSAF-6.12.2.1-1\]

The finite set of allowed values for the vuln:BaseScoreV3 element is
documented in section 2.2.12 [Vulnerability CVSS Version 3 Type
Model](#_Vulnerability_CVSS_Version_1).

#### Vulnerability -- CVSS Score Sets -- Score Set V3 -- Temporal Score V3

Element vuln:TemporalScoreV3

« The vuln:TemporalScoreV3 element MUST be present zero or one time
inside any vuln:ScoreSetV3 and if given contains the numeric value of
the computed CVSS version 3 temporal score. » \[CSAF-6.12.2.2-1\]

The finite set of allowed values for the vuln:TemporalScoreV3 element is
documented in section 2.2.12 [Vulnerability CVSS Version 3 Type
Model](#_Vulnerability_CVSS_Version_1).

#### Vulnerability -- CVSS Score Sets -- Score Set V3 -- Environmental ScoreV3

Element vuln:EnvironmentalScoreV3

« The vuln:EnvironmentalScoreV3 element MUST be present zero or one time
inside any vuln:ScoreSetV3 and if given contains the numeric value of
the computed CVSS version 3 environmental score. » \[CSAF-6.12.2.3-1\]

The finite set of allowed values for the vuln:EnvironmentalScoreV3
element are documented in section 2.2.12 [Vulnerability CVSS Version 3
Type Model](#_Vulnerability_CVSS_Version_1).

Non-normative comment:

This metric is typically reserved for use by the end user and is
specific to the environment in which the affected product is deployed.
See also section 2.2.12 [Vulnerability CVSS Version 3 Type
Model](#_Vulnerability_CVSS_Version_1) for further information and
constraints on this element.

#### Vulnerability -- CVSS Score Sets -- Score Set V3 -- Vector V3

Element vuln:VectorV3

« The vuln:VectorV3 element MUST be present zero or one time inside any
vuln:ScoreSetV3 and if present contains the official string notation
that displays all the values used to compute the CVSS version 3 base,
temporal, and environmental scores. » \[CSAF-6.12.2.4-1\]

The allowed values for the vuln:VectorV3 element are documented in
section 2.2.12 [Vulnerability CVSS Version 3 Type
Model](#_Vulnerability_CVSS_Version_1).

Example :

\<VectorV3\>CVSS:3.0/AV:N/AC:L/PR:H/UI:N/S:U/C:L/I:L/A:N\<VectorV3\>

Example :

\<VectorV3\>CVSS:3.0/S:U/AV:N/AC:L/PR:H/UI:N/C:L/I:L/A:N/E:F/RL:X\<VectorV3\>

#### Vulnerability -- CVSS Score Sets -- Score Set V3 -- Product ID

Element vuln:ProductID

« The vuln:ProductID element MUST be present with cardinality \[0, ∞\|
inside any vuln:ScoreSetV3 element and per instance value references to
unique ProductID attributes of **Full Product Name** elements defined in
the **Product Tree** are noted.\
» \[CSAF-6.12.2.5-1\]

If a **Score Set V3** applies to more than one product, you can add
multiple **Product ID** elements as references accordingly.

Any single **Product ID** is to be assigned to exactly none or one
**Score Set V3** within the same **Vulnerability**.

Vulnerability -- Remediations
-----------------------------

Element vuln:Remediations

« The vuln:Remediations element MUST be present with cardinality \[0,
1\] inside vuln:Vulnerability and it holds \[1, ∞\] vuln:Remediation
child elements.\
» \[CSAF-6.13-1\]

These **Remediation** containers will have details on how to remediate a
vulnerability.

Visual display of a map of some valid **Remediations** configuration
including the parent node (**Vulnerability**) --- again with the node
labeled {...} indicating further possible **Remediation** subtrees ---
follows below.

Figure : A topologically valid **Remediations** configuration.

### Vulnerability -- Remediations -- Remediation

Element vuln:Remediation

« The vuln:Remediation element MUST be present with cardinality \[1, ∞\]
in vuln:Remediations and MUST contain the following child elements
vuln:Description \[1, 1\], vuln:Entitlement \[0, ∞\], vuln:URL \[0, 1\],
vuln:ProductID \[0, ∞\], and vuln:GroupID \[0, ∞\] in that order.
» \[CSAF-6.13.1-1\]

The element vuln:Remediation is a container that holds specific details
on how to handle (and presumably, fix) a vulnerability.

A **Remediation** container can be tied to one or more specific products
by referencing these products using either the **Product ID** or **Group
ID** child elements.

If the **Remediation** is meant to be general or nonspecific for all
products, the **Product ID** and **Group ID** child elements should be
omitted.

Optionally, **Remediation** can contain information and constraints
about how to obtain fixes via the **Entitlement** element.

##### Attribute Type {#attribute-type-7 .MemberHeading}

The allowed values for the required Type attribute are documented in
section 2.2.17 [Vulnerability Remediation Type
Model](#_Vulnerability_Remediation_Type).

#### Vulnerability -- Remediations -- Remediation -- Description

Element vuln:Description

« The vuln:Description element MUST be present exactly once in
vuln:Remediation and it contains a thorough human-readable discussion of
the **Remediation**.\
» \[CSAF-6.13.1.1-1\]

#### Vulnerability -- Remediations -- Remediation -- Entitlement

Element vuln:Entitlement

« The vuln:Entitlement element MUST be present with cardinality \[0, ∞\]
inside vuln:Remediation and it contains any possible vendor-defined
constraints for obtaining fixed software or hardware that fully resolves
the vulnerability. » \[CSAF-6.13.1.2-1\]

Non-normative comment:

This element will often contain information about service contracts or
service-level agreements that is directed toward customers of large
vendors.

Example :

\<Entitlement\>\
Cisco customers with service contracts that entitle them to regular
software updates\
should obtain security fixes through their usual update channels,
generally from the\
Cisco website. Cisco recommends contacting the TAC only with specific
and imminent\
problems or questions.\\r\\nAs a special customer service, and to
improve the overall\
security of the Internet, Cisco may offer customers free of charge
software updates to\
address security problems. If Cisco has offered a free software update
to address a\
specific issue, noncontract customers who are eligible for the update
may obtain it by\
contacting the Cisco TAC using any of the means described in the Contact
Summary\
section of this document. To verify their entitlement, individuals who
contact the TAC\
should have available the URL of the Cisco document that is offering
the\
upgrade.\\r\\nAll aspects of this process are subject to change without
notice and on a\
case-by-case basis. No particular level of response is guaranteed for
any specific\
issue or class of issues.\
\</Entitlement\>

#### Vulnerability -- Remediations -- Remediation -- URL

Element vuln:URL

« The vuln:URL element MUST be present with cardinality \[0, 1\] in
vuln:Remediation and it contains the URL to the **Remediation**.
» \[CSAF-6.13.1.3-1\]

#### Vulnerability -- Remediations -- Remediation -- Product ID

Element vuln:ProductID

« The vuln:ProductID element MUST be present with cardinality \[0, ∞\]
inside vuln:Remediation and the content of the instances are tokens that
are references to products through the value of a **Full Product
Name**'s ProductID attribute.\
» \[CSAF-6.13.1.4-1\]

If the **Remediation** pertains to a specific product, a vuln:ProductID
represents the reference to that product.

The reference is made using the unique ProductID attribute of a **Full
Product Name** element that is defined in the **Product Tree**.

If a **Remediation** applies to more than one Product, multiple
**Product ID** elements SHOULD be added accordingly, or the **Group ID**
element (see below) instead.

Example :

\<Remediation Type=\"Vendor Fix\"\>\
\<Description\>\
this is an official fix for Test Product and here are the details\...\
\</Description\>\
\<URL\>http://foo.example.com/bar/\</URL\>\
\<Product ID\>CVRFPID-0000\</Product ID\>\
\</Remediation\>

#### Vulnerability -- Remediations -- Remediation -- Group ID

Element vuln:GroupID

« The vuln:GroupID element MUST be present with cardinality \[0, ∞\]
inside vuln:Remediation and the content of the instances are tokens that
are references to groups of products. » \[CSAF-6.13.1.5-1\]

If the **Remediation** pertains to several products that have been
logically grouped into a **Product Group**, a vuln:GroupID element can
be added to reference that group of products. The reference is made
using the unique GroupID attribute of a **Group** element that is
defined in the **Product Tree**.

If a **Remediation** applies to more than one group of products, one can
add multiple **Group ID** elements accordingly.

Vulnerability -- References
---------------------------

Element vuln:References

« The vuln:References element MUST be present with cardinality \[0, 1\]
inside vuln:Vulnerability parent at last position or before any
Acknowledgements if these exist. » \[CSAF-6.14-1\]

The optional element vuln:References is a container that SHOULD include
citations to any conferences, papers, advisories, and other resources
that are specific to the vulnerability section and considered to be of
value to the document consumer.

« If present, the vuln:References MUST contain \[1, ∞\] vuln:Reference
child element instances. » \[CSAF-6.14-2\]

A visual map of some valid **References** configuration including the
parent node (**Vulnerability**) --- again with the node labeled {...}
indicating further possible **Reference** subtrees is provided below:

Figure : A topologically valid **Vulnerability** **References**
configuration.

### Vulnerability -- References -- Reference

Element vuln:Reference

« The vuln:Reference element MUST be present with cardinality \[1, ∞\]
inside vuln:References and every instance MUST have exactly one vuln:URL
and one vuln:Description child element and in that order.
» \[CSAF-6.14.1-1\]

The element vuln:Reference contains a description of a related document
specific to a vulnerability section of a CVRF document.

##### Attribute Type {#attribute-type-8 .MemberHeading}

« The Attribute Type if not present is taken to be the enumeration value
External and if present MUST be one of the values documented in
section 2.2.7 [Reference Type Model](#_Reference_Type_Model_1).
» \[CSAF-6.14.1-2\]

This attributes value denotes the type of the document reference
relative to the CSAF CVRF document itself

Non-normative comment:

This may include a plaintext or HTML version of the advisory or other
related documentation, such as white papers or mitigation documentation.

#### Vulnerability -- References -- Reference -- URL

Element vuln:URL

« The vuln:URL element MUST be present exactly once in vuln:Reference
and contains the fixed URL or location of the reference.
» \[CSAF-6.14.1.1-1\]

#### Vulnerability -- References -- Reference -- Description

Element vuln:Description

« The vuln:Description MUST be present exactly once in vuln:Reference
and holds a descriptive title or name of the reference.
» \[CSAF-6.14.1.2-1\]

Example :

\<References\>\
\<Reference Type=\"External\"\>\
\<URL\>http://foo.foo/bar/\</URL\>\
\<Description xml:lang=\"fr\"\>C\'est un test de
référence\</Description\>\
\</Reference\>\
\</References\>

Vulnerability -- Acknowledgements
---------------------------------

Element vuln:Acknowledgements

« The vuln:Acknowledgements element MUST be present with cardinality
\[0, 1\] inside vuln:Vulnerability element and MUST contain one or more
vuln:Acknowledgement child elements, which in turn either contain(s)
recognition of external parties or is empty. » \[CSAF-6.15-1\]

Non-normative comment:

This **Acknowledgments** container is different from the one at the
document level because it is specifically related to the vulnerability
in context**.**

Following is a map of a valid **Acknowledgements** configuration
including the parent node (**Vulnerability**) --- again with the node
labeled {...} indicating further possible **Acknowledgement** subtrees:

Figure : A topologically valid **Vulnerability** **Acknowledgements**
configuration.

### Vulnerability -- Acknowledgements -- Acknowledgement

Element vuln:Acknowledgement

« The vuln:Acknowledgement element MUST be present with cardinality \[1,
∞\] inside vuln:Acknowledgments and MUST contain the following child
elements vuln:Name \[0, ∞\] times, vuln:Organization \[0, ∞\] times,
vuln:Description \[0, 1\] times, and vuln:URL \[0, ∞\] times and in that
order. » \[CSAF-6.15.1-1\]

The element vuln:Acknowledgement contains recognition of external
parties who were instrumental in the discovery of, reporting of, and
response to the vulnerability. This element indicates collaboration with
the security community in a positive fashion and is an important part of
a notice or advisory.

Non-normative comment:

Care should be taken to ensure that individuals would like to be
acknowledged before they are included.

External parties who have worked with the document producer may be
recognized for their work. This should be applied liberally; if someone
reports an issue and then discloses it publicly, that party might still
be credited.

If the original discoverer is not concerned with recognition, or the
issue was discovered internally by the document producer, this field can
be omitted.

#### Vulnerability -- Acknowledgements -- Acknowledgement -- Name

Element vuln:Name

« The vuln:Name MUST be present with cardinality \[1, ∞\] in
vuln:Acknowledgment and every instance given contains the name of the
party being acknowledged. » \[CSAF-6.15.1.1-1\]

#### Vulnerability -- Acknowledgements -- Acknowledgement -- Organization

Element vuln:Organization

« The vuln:Organization MUST be present with cardinality \[0, ∞\] inside
vuln:Acknowledgment. » \[CSAF-6.15.1.2-1\]

The element vuln:Organization contains the organization of the party or,
if the Name is omitted, the organization itself that is being
acknowledged.

#### Vulnerability -- Acknowledgements -- Acknowledgement -- Description

Element vuln:Description

« The vuln:Description element MUST be present with cardinality \[0, 1\]
inside vuln:Acknowledgment and if given contains any contextual details
the document producers wish to make known about the acknowledgment or
acknowledged parties. » \[CSAF-6.15.1.3-1\]

If attributing to multiple organizations, each contributor SHOULD be
grouped with that **Organization** within a single **Acknowledgment**
container.

An **Organization**-specific acknowledgment MAY be added within each
**Acknowledgment** container by the **Description** element.

If an overall general or aggregate acknowledgment is to be added, an
**Acknowledgment** container that contains a single **Description**
element MAY be used.

#### Vulnerability -- Acknowledgements -- Acknowledgement -- URL

Element vuln:URL

« The vuln:URL MUST be present with cardinality \[0, ∞\] inside
vuln:Acknowledgment and every instance contains the URL or location of
the reference to be acknowledged.\
» \[CSAF-6.15.1.4-1\]

Example :Taking Isaac Newton, Jeanne D'Arc, and Alan Turing as names for
fictitious people, and Acme, as well as Things as such organizations and
some vendor Vendorix:

\<Acknowledgments\>\
\<Acknowledgment\>\
\<Name\>Isaac Newton\</Name\>\
\<Name\>Jeanne D'Arc\</Name\>\
\<Organization\>Acme\</Organization\>\
\<URL\>http://acme.example.com/IsaacAndJeanne/\</URL\>\
\</Acknowledgment\>\
\<Acknowledgment\>\
\<Name\>Alan Turing\</Name\>\
\<Organization\>Things\</Organization\>\
\<Description\>\
Vendorix would like to thank Alan Turing from Things for reporting this
issue.\
\</Description\>\
\<URL\>http://things.example.com/JustAlan/\</URL\>\
\</Acknowledgment\>\
\<Acknowledgment\>\
\<Description\>\
Vendorix would like to thank the following researchers for their
contributions to\
making this project more secure: Isaac Newton, Jeanne D'Arc, Alan
Turing\
\</Description\>\
\<URL\>http://white-hats.example.com/AllOfThemAgain/\</URL\>\
\</Acknowledgment\>\
\</Acknowledgments\>

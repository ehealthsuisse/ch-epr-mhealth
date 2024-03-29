This section specifies Swiss national extensions to Mobile Care Services Discovery (mCSD).
mCSD is [published](https://profiles.ihe.net/ITI/mCSD/index.html) as an IHE ITI Trial Implementation profile.

### Scope

In the Swiss EPR, the mCSD profile ensures that different systems can search for healthcare organizations and/or
professionals.

### Use Cases

A primary system wants to search for healthcare organizations or professionals. It can perform an
[ITI-90](iti-90.html) request with search parameters to get a list of matched resources and retrieve a resource
with its identifier.
It offers an alternative to the HPD ITI-58 transaction, which is SOAP-based.

The _Request Care Services Updates_ [ITI-91] transaction is not used in this national extension.

### Actors and Transactions, Content Specifications

<div>
{%include mCSD_actor_diagram.svg %}
</div>
This figure shows the actors directly involved in the _Mobile Care Services Discovery_ Profile and the relevant 
transactions between them.

### Actor Options

The Swiss national extension does not implement the 'Location Distance Option'.

### Required Actor Grouping

This national extension enforces authentication and authorization for access control.
Therefore, actors of this profile must be grouped with actors of other profiles according to the following table:

| Actor                            | Required Grouping        | Optionality |
|----------------------------------|--------------------------|-------------|
| Care Services Selective Consumer | IUA Authorization Client | R           |
| Care Services Selective Supplier | IUA Resource Server      | R           |
{:class="table table-bordered"}

<figcaption ID="1">Table 1: Grouping of mCSD actors required by this national extension.</figcaption>

### Security Consideration

This national extension enforces authentication and authorization of access to the _Care Services Selective Supplier_
using the IUA profile with basic access token as described in [IUA](iti-71.html).

### Examples

The Swiss extension uses [examples from eHealthSuisse](https://ehealthsuisse.ihe-europe.net/test_data/CommunityAdd_A_B_xml.zip):
<img alt="LDAP examples"
     style="max-width:100%"
     src="assets/images/ehealthsuisse_HPD_Structure.png" />

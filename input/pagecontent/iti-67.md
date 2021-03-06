There are **no additional requirements** for the Swiss EPR extension for the for the Swiss EPR of the Find
Document References [ITI-67] transaction defined in the MHD Profile published in the IHE ITI Trial Implementation
“Mobile Access to Health Documents”.

### Scope

The Find Document References transaction is used to find DocumentReference Resources that
satisfy a set of parameters. It is equivalent to the FindDocuments and
FindDocumentsByReferenceId queries from the Registry Stored Query [ITI-18] transaction. The
result of the query is a FHIR Bundle containing DocumentReference Resources that match the
query parameters.

### Actor Roles

**Actor:** Document Consumer   
**Role:** Requests a list of DocumentReference Resources, matching the supplied set of criteria, from the Document Responder.   
**Actor:** Document Responder   
**Role:** Returns DocumentReference Resources that match the search criteria provided by the Document Consumer.   

### Referenced Standards

[Mobile access to Health Documents (MHD) With XDS on FHIR Rev. 3.1 – 2019-03-06](https://www.ihe.net/uploadedFiles/Documents/ITI/IHE_ITI_Suppl_MHD.pdf)   

This MHD Profile is based on Release 4 of the emerging [HL7® FHIR®](https://www.hl7.org/fhir/index.html) standard.

### Messages

{% include img.html img="MHD_ActorDiagram_ITI-67.plantuml.png" width="40%" %}

### Trigger Events

When the Document Consumer needs to discover DocumentReference Resources matching
various metadata parameters, it issues a Find Document References message. 

### Message Example

Find Document Reference **request**:
```
GET [base]/DocumentReference?patient.identifier=urn:oid:2.999|11111111 HTTP/1.1
Accept: application/fhir+json
```

See [Bundle example](Bundle-Bundle-FindDocumentReferences.html) (and the corresponding [profile](StructureDefinition-ch-mhd-comprehensive-documentreference-bundle.html)) as **response** to the Find Document Reference request.

### Security Consideration

TLS SHALL be used. This national extension enforces authentication and authorization of access to the
Patient Identity Manager using IUA profile with basic access token. Consequently
the Find Document References [ITI-67] request must authorize using the Incorporate Authorization Token
[ITI-72] transaction of the IUA profile.

### Metamodel overview


<div xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.w3.org/1999/xhtml ../../schema/fhir-xhtml.xsd" xmlns="http://www.w3.org/1999/xhtml">
<blockquote class="stu-note">
<strong><p> **** **** **** These materials are still being developed. **** **** **** </p> <p> This is not intended to be used until approved and balloted by the HL7 Belgium Community. </p> </strong>
</blockquote>
</div>

HL7 Belgium proposes that all specifications should support a consistent approach and interchangeable artifacts which support:
* Understanding
* Implementation
* Validation

While the "main deliverable" consists of a set of technical specifications, the HL7 community in Belgium pursuits a content structure that contains the following types of artifacts


{% include image.html img="./metamodel.png" title="HL7 Belgium Artifact Model" caption="HL7 Belgium artifact model" %}

#### Functional Module
This module contains the functional description - a non-technical insight on the intended functionality, the use cases and functional (business) services that are in scope of the specification. This is not a full functional analysis of the systems, onlt the analysis related to the data exchange needs. This module also contains the logical data models - a functional description of the data needed for each of the data exchanges. 
> Target users: Functional analysis, clinical experts, validation engineers

| Artifact | Function  | Type  | Required / Recommended | Example | 
|---|---|---|---|---|
| Use case  | A functional description of the use cases for data exchange | Free text | Mandatory | *GP submits prescription, Pharmacy retrieves it* |
| Service  | A business-oriented description of the data exchange services | Free text | Recommended | *Prescription submission* |
| Logical Data Model  | A business-oriented description of the data needed | Structured <br/>(FHIR artifact) | Required for each service | Prescription<br/>-  Patient(1..1) <br/>-  Prescriber (1..1) <br/>-  Medication (1..\*) <br/>- Posology (1..*) |


#### Vocabulary
The Vocabulary module contains the terminology specification - predefined or context-specific sets of values, which can be used throughout and across systems. Typically this relies on existing terminology systems like SNOMED CT, LOINC, etc. but can also consist of new code systems. The value sets can be associated with the  technical or functional specifications. For example, value sets like "status code" are related to the technical information (the functional analysts do not define those codes). Other codes are important to appear on the functional level, for example "civil states in Belgium" - in this case, the codes are defined at the functional level and must be taken by the technical implementation. The Naming Systems are artifacts used in the specification to point to the terminology sources.

| Artifact | Function  | Type  | Required / Recommended | Example | 
|---|---|---|---|---|
| Code System | Pointer to an existing set of coded values or declaration of a new set of codes | [CodeSystem](http://hl7.org/fhir/codesystem.html) | As needed | *SNOMED CT,<br/>LOINC* |
| Value Set  | A set of coded values to be used in a specific context | [VaueSet](http://hl7.org/fhir/valueset.html) | As needed | *Lab order codes (from LOINC)* |
| Naming System  | A namespace (typically a url) for unequivocally referring to a set of codes and identifiers | [NamingSystem](http://hl7.org/fhir/namingsystem.html) | As needed | http://snomed.info/sct<br/>http://loinc.org<br/>http://unitsofmeasure.org |

<br/>
<br/>

#### Technical Implementation
The Technical Implementation module presents the conformance artifacts that define the technical behaviour of FHIR: the actual profiles, the operations and parameters, demonstrative examples, etc.

| Artifact | Function  | Type  | Required / Recommended | Example | 
|---|---|---|---|---|
| Transaction | A formal definition of a technical exchange of information, usually with specific event and purpose | FHIR resource | Recommended | *M_T1:Submit_Prescription*<br/>*M_T2:Submit_Dispense* |
| Profile | A constrained or extended version of a FHIR resource <br/> The technical specification for the format of data exchange | [StructureDefinition](http://hl7.org/fhir/structuredefinition.html) | As needed<br/>(Normally required) | *BePatient* |
| Operation Definition  | A computable definition of an operation on the server | [OperationDefinition](http://hl7.org/fhir/operationdefinition.html) | As needed |*[base]/CodeSystem/$lookup* |
| Search parameter  | A parameter that can be used in searching resources | [SearchParameter](http://hl7.org/fhir/searchparameter.html) | As needed | http://hl7.org/fhir/search_filter.html |
| Example instance  | An example of a resource | Resource (any type) | Required<br/>(at least one example per profile) |  `{"resourceType" : "Patient",`<br/>` "id" : "patient1",`<br/>` "identifier" : [{...`<br/>` }` |
| Example Scenario  | A demonstrative sequence of activities and exchanges that demonstrate how the systems exchange data in one scenario | [ExampleScenario](http://hl7.org/fhir/examplescenario.html) | Required |  |

      
<br/>
<br/>

#### Support
The Support module serves implementers in the implementation and validation of the specification. It consists of test data, test scripts, and capability statements, which are computable specifications for the expected behaviour of a system.

| Artifact | Function  | Type  | Required / Recommended | Example | 
|---|---|---|---|---|
| Test Data | Test data (resources) which can be used to test the behaviour of the systems. | FHIR resource | Recommended |  |
| Test Scripts | A sequence of activities that provide a test for a given functionality (activity or sequence of activities)  | [TestScript](http://hl7.org/fhir/testscript.html) | As needed<br/>(Normally required) | *BePatient* |
| CapabilityStatement  | A formal definition of the capabilities defined in the specification which must be supported (and may be tested) by the systems implementing the specification.<br/>May be used to feed tools for validation and implementation (e.g. FHIR validator, openAPI) | [CapabilityStatement](http://hl7.org/fhir/capabilityStatement.html) | As needed | |

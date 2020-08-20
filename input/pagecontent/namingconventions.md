# Naming conventions

In general, the artifacts are named for what they mean, not for the base resources in FHIR.
For example, a Prescription profile would be named be-prescription instead of be-medicationrequest. 

This is because several FHIR resource types will have different core profiles for different purposes - for example medicationrequest can be used for prescriptions or administration orders.

## Filenames
* The filenames correspond to the artifact ids.
* The FHIR resource type (e.g. StructureDefinition) is not a part of the filename nor the id
* all conformance artefacts have a prefix `be-`
* for some artefact types, the name includes the type of artefact 
  
type | prefix
-----|-------
profile|  
model|model 
extension|ext
CodeSystem |cs
ValueSet |vs
NamingSystem | ns
TestScript |ts

examples:
* be-ns-nihdi

### Casing
`id`s are lowercase  
`Name`s are PascalCase or WikiCase

&nbsp; 

### Profiles: 
> Folder:     `input/profiles`   
> Resource id:   `be-xxyyzz`  
> Filename:   (same as id)  
> Resource name:   `BeXxYyZz`

where xxyyzz is the functional name of the functionality e.g. "medicationprescription"
xxyyzz = lowercase
XxYyZz = PascalCase or WikiCase (WikiCase preferred i.e. not ThisIsAProfile but ThisIsaProfile)

&nbsp;

### Extensions:
> Folder:     `input/extensions`   
> Resource id:   `be-ext-xxyyzz`  
> Filename:   (same as id)  
> Resource name:   `BeXxYyZz`


&nbsp; 

## Models:
> Folder:     `input/models`   
> Resource id:   `be-model-xxyyzz`  
> Filename:   (same as id)  
> Resource name:   `BeXxYyZz`


&nbsp; 



## Vocabulary

### CodeSystems
> Folder:     `input/vocabulary`   
> Resource id:   `be-cs-xxyyzz`  
> Filename:   (same as id)  
> Resource name:   `BeCSXxYyZz`

### ValueSets
> Folder:     `input/vocabulary`   
> Resource id:   `be-vs-xxyyzz`  
> Filename:   (same as id)  
> Resource name:   `BeVSXxYyZz`

### NamingSystems
> Folder:     `input/vocabulary`   
> Resource id:   `be-ns-xxyyzz`  
> Filename:   (same as id)  
> Resource name:   `BeNSXxYyZz`

&nbsp; 
## ExampleScenarios
> Folder:     `input/scenarios`   
> Resource id:   `be-examplescenario-xxyyzz`  
> Filename:   (same as id)  
> Resource name:   `BeXxYyZz`

## Transactions
TBD

## Examples
> Folder:     `input/examples`     or      `input/examples/<profile>`, where `<profile>` is the name of the profile (e.g. addiction), and not the type (condition)  
> Resource id:   `example-xxxxxxxx`  
> Filename:   (same as id)  
> Resource name:   `xxxxxxxx`

(where xxxxxxxx is the title for the example e.g. "simple prescription")

## Testing
TBD

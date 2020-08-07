# FHIR Profiling in Belgium

## Profile levels

HL7 FHIR profiling consists of adding constraints to the base profiles. The concepts behind profiling are described in http://build.fhir.org/conformance-module.  

FHIR Profiles can be stacked (i.e. several layers of additional constraints and extensions can be added one after the other). In HL7 Belgium, we use this to provide several layers of compatibility:
&nbsp;  
&nbsp;  

![profile layers](..\images\profile_layers.png)
&nbsp;  
&nbsp;  

1. **The foundation layer consists of the FHIR standard and standard terminology resources** - from HL7, SNOMED-CT, LOINC, etc.  
Based on these specifications, we have two types of Belgian standard specifications: Legal and Community
2. **Legal standard specifications**: These specifications profile the fundamental content of FHIR resources, which apply to all uses in the country. These specifications are (or will become) **legal (*de jure*) standards**. They are maintained and published by the federal eHealth Platform, and maintained according to a process also maintained by the federal eHealth Platform.   
Examples of federal profiles: BePatient, BePractitioner... - setting aspects like the use of NISS numbers, legal status, NIHDI numbers, etc.
3. **Community specifications**: These are community standards, maintained and published by HL7 Belgium and used as **accepted community (*de facto*) standards**. When possible, these specifications will be based upon the eHealth platform specifications; when this is not possible or not intended (for example when the HL7 Community wishes to develop a specification that is unrelated to the roadmap of the eHealth platform), the community standards are based in the base FHIR standard. Of course, Community standards can have a path to becoming Legal standards, by following the process specified by the eHealth platform.  

4. **Project-specific or vendor-specific constraints**: Projects should base themselves on the existing Belgian specifications (legal or community standards), and add their own constraints, extensions, remarks and examples. This layer is compatible with all the layers below it.  
Typical examples of these types of constraints are **vendor-specific profiles** or **project specifications**.  

&nbsp;  
&nbsp;

## Format and Publication

Preferrably, the constraints are published in the form of a FHIR Implementation Guide, with the resources also in simplifier.net.  
The use of Simplifier.net allows us to use a simple, accessible platform shared by many FHIR users around the globe.  
The use of the Implementation Guide allows the specifications to follow a common structure supported by the rest of the community, and to be validated in the publication process.

&nbsp;  
&nbsp;


## Resources

For more information on what is in an ImplementationGuide

Here are  can find here some resources for implementing your ImplementationGuides:


* HL7 maintains a sample IG with basic features: https://github.com/FHIR/sample-ig


* Empty ImplementationGuide with Belgian template  
Here is a empty IG with the basic structure: https://github.com/hl7-be/empty-ig  

* Empty ImplementationGuide with Belgian template  
Here is a empty IG with the basic structure: https://github.com/hl7-be/empty-ig  

Please see this page how to get started on your own ImplementationGuides.




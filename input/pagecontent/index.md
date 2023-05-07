<div class="alert alert-warning">

<b>Please note:</b>
<br/>
- The guidance does not form the basis for a completely described deployable service in and of itself but is the basis from which other FHIR implementation guides can be derived.
- This version of the EEBase Implementation Guide is currently under development and will be updated daily.
- Known issues currently being addressed have been listed below:  
  - Some of the URLs might not be resolvable yet, there may be a few broken links.
  - Some of the CodeSystems and ValueSets are still in development.
  - Subpages "People and Organizations" and "Profiling Guidelines" are still in development.
  - Official contacts and the list of contributors/reviewers will be added in the near future. Until then the main contact point for inquiries is <b>fhir@tehik.ee</b>.

</div>

### Introduction

The EEBase Implementation Guide covers a set of national base profiles, terminology components and guiding principles based on [FHIR®© version R5](http://hl7.org/fhir/R4/index.html). The switch from document-based data exchange to a more granular one will be realized as a transitional process. The development of this Implementation Guide should be considered the first step in helping event-based health data exchange to become a real-life scenario in Estonia.

This guide serves the purpose of simplifying the process of implementing FHIR and thus increasing interoperability and clinical data quality in the Estonian context by including the following components:
- FHIR resources tailored for local use, e.g. **base profiles**, whereas conformance requirements must support flags and binding strengths have been held to as minimum as possible to support [open-world modeling](https://informatiestandaarden.nictiz.nl/wiki/FHIR:V1.0_FHIR_Profiling_Guidelines_R4#Open_vs._closed_world_modeling);
- Ready-to-use **CodeSystems** and **ValueSets** developed for Estonian healthcare data exchange specifically;
- **Implementation and profiling guidance** to support a smooth transition from other standards to FHIR.

Even though the initial draft of the EEBase Implementation Guide was developed in March-October 2022 as part of project "Estonian National Health Information System support for event-based data exchange", it should be regarded as the intellectual property of a community of contributors and reviewers who have provided valuable input during the validation process of this guide. 


### Audience
This document aims to provide standardized clinical data components and instructional materials to both implementation guide author communities and vendor communities. Users of this guide are expected to be familiar with FHIR, at least to some degree, to find additional information from the [official specification page](http://hl7.org/fhir/) if needed. Implementation of, testing and offering feedback on this specification is highly encouraged. Readers of this guide are welcome to find the appropriate e-mail address on the [Contact Us](contact.html) page in case of questions, suggestions, information requests, or collaboration offers.


### Scope
From the perspective of future and current implementers, it is most logical to divide the content of the EEBase Implementation Guide into three parts by the function they serve:
- **FHIR profiles and extensions** suitable for use in the Estonian healthcare domain specifically. Each profile has its dedicated page for details on example use cases, usage instructions and descriptions of data items. For a general overview of all profiles and extensions in this guide, it is suggested to look at the [Profiles Index](artifacts.html) page, where one can find profiling guidelines developed and followed in the profiling process of EEBase. The profiling guidelines offer insight into the principles and best practices, which are especially valuable in the early stage of building profiles based on one's use cases. *Please note that EEBase profiles are intended as a starting point for utilizing the possibilities offered by FHIR for specific use cases, projects and/or services.* The profiles provided *should not be considered suitable for use straight out of the box but must be used as a base profile to derive additional profiles from*;
- **CodeSystems and ValueSets** specially developed for EEBase (this means that CodeSystems and ValueSets developed by HL7 are not included in this IG even when bound with data elements in EEBase profiles, as the latest documentation of these artefacts could be found on [FHIR’s webpage](http://hl7.org/fhir/terminologies-systems.html)). 
ConceptMaps from custom value sets developed for EEBase to HL7’s ’default’ value sets are also provided in case of implementers decide on using the ones provided by HL7. For maximum interoperability, it is encouraged to use stable identifiers (either a URI or OID) in profiles. For that purpose, the authors of this implementation guide have utilized the [NamingSystem](artifacts.html#terminology-naming-systems) resources. For more information on using terminology, see the Profiling Guidelines section on the [Profiles Index](artifacts.html) page and pages under the Terminology tab;
- **Policy** from general compliance principles to FHIR operations to be followed when implementing FHIR within your jurisdiction. For more information, see the [Policy Index](policy.html) page.


#### How to Read This Guide

This Guide is divided into several pages, which are listed at the top of each page in the menu bar.

- [Home](index.html): The home page provides the introduction and background for EEBase.
- [Policy](policy.html): The Policy page provides the set of rules for FHIR standard developers in Estonia.
  - [General](policy.html#general): <!-- siia lisada selgitus -->
  - [Conformance](policy.html#conformance): <!-- siia lisada selgitus -->
  - [Profiling](policy.html#profiling): <!-- siia lisada selgitus -->
  - [Versioning](policy.html#versioning): <!-- siia lisada selgitus -->
  - [Naming](policy.html#naming): <!-- siia lisada selgitus -->
  - [Resource identifiers](policy.html#resource-identifiers): <!-- siia lisada selgitus -->
  - [Publishing](policy.html#publishing): <!-- siia lisada selgitus -->
  - [Serialization](policy.html#serialization): <!-- siia lisada selgitus -->
  - [FHIR operations](policy.html#fhir-operations): <!-- siia lisada selgitus -->
<!--  - [General](policy.html#health-service): List of providers of National Health Services. -->
- Profiles and Extensions: The header for pages about Extensions and Profiles
  - The [Extension Library](artifacts.html#structures-extension-definitions), which have been defined for the EEBase.
  - The [Profiles](artifacts.html#structures-resource-profiles), which have been defined for the EEBase:
    - [EEBaseEncounter](StructureDefinition-ee-encounter.html)
    - [EEBaseEpisodeOfCare](StructureDefinition-ee-episode-of-care.html)
    - [EEBaseHealthcareService](StructureDefinition-ee-healthcare-service.html)
    - [EEBaseLocation](StructureDefinition-ee-location.html)
    - [EEBaseObservation](StructureDefinition-ee-observation.html)
    - [EEBaseOrganization](StructureDefinition-ee-organization.html)
    - [EEBasePatient](StructureDefinition-ee-patient.html)
    - [EEBasePractitioner](StructureDefinition-ee-practitioner.html)
    - [EEBasePractitionerRole](StructureDefinition-ee-practitioner-role.html)
    - [EEBaseRelatedPerson](StructureDefinition-ee-related-person.html)
- Terminology: This page lists all the Terminology assets defined as part of this Implementation Guide.
<!-- - [ConceptMaps](#): This is the list of all ConceptMaps necessary to guarantee interoperability for using EEBase and HL7 terminology resources. NB! Delete this line because IG does not contain concept maps. -->
  - [CodeSystems](artifacts.html#terminology-code-systems): This is the list of all CodeSystems defined for use within the EEBase.
  - [ValueSets](artifacts.html#terminology-value-sets): This is the list of all ValueSets defined for use within the EEBase.
  - [NamingSystems](artifacts.html#terminology-naming-systems): This is the list of all Namingsystems defined for use within the EEBase.
- [Download](download.html): List of downloads available.
- [Contact Us](contact.html): How to Contact the key parties associated with this implementation guide.


<!--button onclick="topFunction()" id="topButton" title="Back to top">top</button-->

<!-- <div class="alert alert-warning">

* Licensing and Publisher *

Copyright © 2022+ HL7 Estonia Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at http://www.apache.org/licenses/LICENSE-2.0 Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License. HL7® FHIR® standard Copyright © 2011+ HL7 The HL7® FHIR® standard is used under the FHIR license. You may obtain a copy of the FHIR license at https://www.hl7.org/fhir/license.html.

Developed and authored by HL7 Estonia Base Development Team and published by HL7 Estonia.

</div> -->
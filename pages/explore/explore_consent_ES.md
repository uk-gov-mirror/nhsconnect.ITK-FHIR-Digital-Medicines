---
title: Consent Section
keywords:  messaging, bundles
tags: [fhir,messaging]
sidebar: foundations_sidebar
permalink: explore_consent_ES.html
summary: "Gives information about the Consent section"
---

{% include custom/section.warnbanner.html %}

## Consent Section Content ##
The Consent section carries information about the consent details used. PRSB Elements should be formatted as subheadings in any HTML sent.


<table style="width:100%;max-width: 100%;">
	<thead>
		<tr>
			<th width="15%">Section</th>
			<th width="35%">Description</th>
			<th width="5%">Card.</th>
			<th width="5%">MRO*</th>
			<th width="40%">FHIR Target and Guidance</th>
		</tr>
	</thead>
 <tbody>
  <tr>
   <td>Consent details</td>
   <td>This acts as a container that holds all of the elements for each instance of a consent entry.</td>
   <td>0 to 1</td>
   <td>R</td>
	<td>Carried in the CodeableConcept of <b>Composition.section.code</b> FHIR element.</td>
  </tr>
		<tr>
			<th>PRSB Element</th>
			<th>Description</th>
			<th>Card.</th>
			<th>MRO*</th>
			<th>FHIR Target and Guidance</th>		
		</tr>
  <tr>
   <td>Consent for treatment record</td>
   <td>Whether consent has been obtained for the treatment. May include where record of consent is located or record of consent.</td>
   <td>0 to 1</td>
   <td>R</td>
   <td>This is a record of the person's consent to information sharing. Free text.</td>
  </tr>
  <tr>
   <td>Consent for information sharing</td>
   <td>
This is a record of consent for information sharing. Where consent has been not been obtained or sought, the reason why must be provided. Include best interests decision where person lacks capacity.</td>
   <td>0 to 1</td>
   <td>O</td>
   <td>Not required in Pharmacy to GP communication.</td>
  </tr>
  <tr>
   <td>Consent relating to child</td>
   <td>Consideration of age and competency, applying Gillick competency or Fraser guidelines. Record of person with parental responsibility or appointed guardian where child lacks competency. Record if there is disagreement between patient and parent.</td>
   <td>0 to 1</td>
   <td>R</td>
   <td>The consent record relating to a child. Free text.</td>
  </tr>
		<tr>
		<td colspan="5"><b>* M=Mandatory R=Required O=Optional</b></td>
		</tr>
 </tbody>
</table>


## Example Consent details Section ##

<script src="https://gist.github.com/IOPS-DEV/30f77837b93cf11cd3593ede69db8838.js"></script>

## Coded Resources ##

This text section should be linked to the following FHIR Resources to provide the textual information in a coded format.

- The Digital Medicines specification does not currently support coded consent details.
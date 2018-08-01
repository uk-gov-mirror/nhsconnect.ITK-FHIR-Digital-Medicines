---
title: Immunizations Section
keywords:  messaging, bundles
tags: [fhir,messaging]
sidebar: foundations_sidebar
permalink: explore_immunizations.html
summary: "Gives information about the Immunizations section"
---

{% include custom/section.warnbanner.html %}

## Immunizations Section Content ##
The Immunizations section carries information about the immunization administered. PRSB Elements should be formatted as subheadings in any HTML sent.


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
   <td>Immunizations section</td>
   <td>This acts as a container that holds all of the elements for each instance of an vaccination entry.</td>
   <td>1 only</td>
   <td>M</td>
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
   <td>Vaccine product</td>
   <td>Vaccine product administered.</td>
   <td>1 only</td>
   <td>M</td>
   <td>Choice of: <br>
• Text <br>
• Coded text (needs to be GS1 code mapped to DM+D) – constraint: MedicationName.  Any AMP/VMP/VTM/AMPP/VMPP subsets from the dm+d terminology. NHS dm+d AMP ::352201000001139 NHS dm+d AMPP ::352401000001135 NHS dm+d VMP ::352701000001133 NHS dm+d VMPP ::352301000001131 NHS dm+d VTM ::352601000001138. Constraint binding: [dm+d]subset=NHS_dm+d</td>
  </tr>
  <tr>
   <td>Vaccine procedure</td>
   <td>Vaccine product administered.</td>
   <td>1 only</td>
   <td>M</td>
   <td>955691000000108 | Seasonal influenza vaccination given by pharmacist (situation) |<br>
Note that 849211000000109 | seasonal influenza vaccination given by pharmacist (finding) | in the NHSE service specification was made inactive in April 2015 and was replaced by the concept above</td>
  </tr>
  <tr>
   <td>Manufacturer</td>
   <td>Name of vaccine manufacturer</td>
   <td>0 to 1</td>
   <td>R</td>
   <td>Derived from GS1 code/free text. If the manufacturer is captured as part of normal business flow then flow the data. If this can only be captured by manually entering the data onto the pharmacy system, treat as optional.</td>
  </tr>
  <tr>
   <td>Batch number</td>
   <td>The batch number of the vaccine product.</td>
   <td>0 to 1</td>
   <td>R</td>
   <td>Not required for Pharmacy to GP communication.</td>
  </tr>
  <tr>
   <td>Expiry date</td>
   <td>The date on which the vaccine will expire.</td>
   <td></td>
   <td></td>
   <td>Not required for Pharmacy to GP communication.</td>
  </tr>
 <tr>
   <td>Serialisation code</td>
   <td>FMD - a code that separately identifies two identical vaccines (by box1; box2 etc.)</td>
   <td></td>
   <td></td>
   <td>Not required for Pharmacy to GP communication.</td>
  </tr>
 <tr>
   <td>Site</td>
   <td>Body site vaccine was administered into.</td>
   <td>0 to 1</td>
   <td>R</td>
   <td>Choice of: <br>
 • Text <br>
 • Coded text – constraint: SiteOfMedicationAdministration. Any valid site for the administration of a medication. Constraint binding: [SNOMED-CT]subset= SiteOfMedicationAdministration. <br> The CodeableConcept.text can also be used.</td>
  </tr>
 <tr>
   <td>Route</td>
   <td>How vaccine entered the body.</td>
   <td>0 to 1</td>
   <td>R</td>
   <td>Coded text – constraint: NHS e-prescribing route of administration subset ID: 413001000001136 Original Id : 30201000001137 This is an extract from the SUBSET -BiAnnual-Drug-15.0.1-20130401: SnomedCT_GB1000001_20130401/Subsets/EPrescribing/NHS e-Prescribing route of administration subset. Constraint binding: [SNOMED-CT]subset=NHS e-Prescribing route of administration subset.<br> The CodeableConcept.text can also be used.</td>
  </tr>
 <tr>
   <td>Indication</td>
   <td>The clinical indication or reason for administering the vaccine.</td>
   <td>0 to 1</td>
   <td>O</td>
   <td>Coded text <br> The CodeableConcept.text can also be used where there is not a map onto the indication concepts listed.</td>
  </tr>
 <tr>
   <td>Dose amount</td>
   <td>Amount of vaccine administered.</td>
   <td>0 to 1</td>
   <td>R</td>
   <td>This will be free text. Coded units of measure (from DM+D) <br> Guidance on how to use the dose amount field will follow.</td>
  </tr>
 <tr>
   <td>Dose sequence</td>
   <td>Nominal position in a series of vaccines.</td>
   <td>0 to 1</td>
   <td>R</td>
   <td>Not required for Pharmacy to GP communication.</td>
  </tr>
 <tr>
   <td>Administered by</td>
   <td>The name of the person who administered the vaccine, preferably in a structured format.</td>
   <td>1 only</td>
   <td>M</td>
   <td>Send as structured name, the receiver can form free text if needed.</td>
  </tr>
 <tr>
   <td>Professional identifier</td>
   <td>Professional identifier & regulatory body of the person who administered the vaccine</td>
   <td>0 to 1</td>
   <td>R</td>
   <td>GPhC number of the pharmacist(default in from the log in, in the system).</td>
  </tr>
 <tr>
   <td>Administered by Role</td>
   <td></td>
   <td>0 to 1</td>
   <td>R</td>
   <td></td>
  </tr>
 <tr>
   <td>DateTime</td>
   <td>The date on which the vaccine was administered.</td>
   <td>0 to 1</td>
   <td>R</td>
   <td>The date as recorded by the pharmacy system.</td>
  </tr>
		<tr>
		<td colspan="5"><b>* M=Mandatory R=Required O=Optional</b></td>
		</tr>
 </tbody>
</table>


## Example Immunization Section ##

<script src="https://gist.github.com/IOPS-DEV/e3f8338cef252ede9812669198d2fa71.js"></script>

## Coded Resources ##

This text section should be linked to the following FHIR Resources to provide the textual information in a coded format.

- Immunization
 
See constructing clinical coded structures
---
title: Medications and Medical Devices Section
keywords:  messaging, sections
tags: [fhir,messaging,section]
sidebar: foundations_sidebar
permalink: explore_medication_dmirs.html
summary: "Gives information about the Medications and Medical Devices section"
---

{% include custom/section.warnbanner.html %}

## Medications and Medical Devices Section Content ##
The Medications and medical devices section carries information about the patient's medication. PRSB Elements should be formatted as subheadings in any HTML sent. For more information on constructing medication lists see [constructing clinical coded structures](build_medication_dispense_list.html).

| MEDICATIONS   AND MEDICAL DEVICES   |                                                                                                                                                                                                                                                                                                            |             |                                                                                                                                                                                                                                                                                                                                                                 |                                  |                                                                            |
|-------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|----------------------------------------------------------------------------|
| Data Item                           | Description                                                                                                                                                                                                                                                                                                | Cardinality | Values                                                                                                                                                                                                                                                                                                                                                          | Mandatory/required/     optional | FHIR Target                                                                |
| Supply type                         | A   description of the type of supply (e.g. emergency supply, over the counter   medication, patient group direction etc)                                                                                                                                                                                  | 0 TO 1      | Emergency   supply      ​Minor ailments scheme      ​Over the counter      ​Patient group direction      ​Prescription dispensing      ​Private prescription dispensing      ​Self declared                                                                                                                                                                           | Required                         | Composition.section.text                                                   |
| Medication name                     | May   be generic name or brand name (as appropriate).                                                                                                                                                                                                                                                      | 1 ONLY      | Choice   of           • Text     • Coded text (needs to be GS1 code mapped to DM+D)– constraint:   MedicationName. Any AMP/VMP/VTM/AMPP/VMPP subsets from the dm+d terminology.   NHS dm+d AMP ::352201000001139 NHS dm+d AMPP ::352401000001135 NHS dm+d VMP   ::352701000001133 NHS dm+d VMPP    ::352601000001138. Constraint binding: [dm+d]subset=NHS_dm+d | Mandatory                        | MedicationStatement.medication[x].     medicationReference.Medication.Name |
| Form                                | Eg   capsule, drops, tablet, lotion etc.                                                                                                                                                                                                                                                                   | 0 TO 1      | Choice   of           • Text           • Coded text – constraint:   DrugDoseForm. SNOMED CT CfH DoseForm termset. Any descendant of 421967003    drug dose form. Constraint binding: [SNOMED CT]subset=CfH DoseForm                                                                                                                                            | <font color="red">Optional</font>                         | MedicationStatement.medication[x].     medicationReference.Medication.form |
| Site                                | The   anatomical site at which the medication is to be used, including   laterality.                                                                                                                                                                                                                       | 0   TO 1    | Choice   of           • Text           • Coded text – constraint:   SiteOfMedicationAdministration. Any valid site for the administration of a   medication. Constraint binding: [SNOMED-CT]subset=   SiteOfMedicationAdministration                                                                                                                            | <font color="red">Optional</font>                         | MedicationStatement.dosage.site                                            |
| Indication                          | Reason   for medication being supplied, where known.                                                                                                                                                                                                                                                       | 0 TO 1      | This will be   free text or SNOMED CT subset                                                                                                                                                                                                                                                                                                                    | Required                         | Composition.section.text                                                   |
| Total amount of medication supplied | A   description of the total amount of medication supplied e.g 30 tablets, 100ml   etc.                                                                                                                                                                                                                    | 1 ONLY      | Recorded   in a structured format i.e. a unit (eg ml, tablet, etc.) and a value (eg 100,   1, 0.5 etc.) .                                                                                                                                                                                                                                                       | Required                         | Composition.section.text                                                   |
| Dose directions description         | A   single plain text phrase describing the entire medication dosage and   administration directions including dose quantity and medication frequency.   Comment, eg, “1 tablet at night or “2mg at 10pm”. This is the form of dosage   direction text normally available from UK GP Systems.              | 0 TO 1      | This   will be free text.                                                                                                                                                                                                                                                                                                                                       | <font color="red">Optional</font>                         | MedicationStatement.dosage.text                                            |
| Additional instructions             | Allows   for:     * requirements for adherence support, e.g., compliance aids, prompts and   packaging requirements                                          * additional information about specific person requirements, e.g., unable   to swallow tablets.medicines, e.g., where specific brand required | 0 TO MANY   | This   will be free text                                                                                                                                                                                                                                                                                                                                        | <font color="red">Optional</font>                         | Composition.section.text                                                   |
| Date/time                           | The   date/time on which the medication was supplied to the patient.                                                                                                                                                                                                                                       | 0 TO 1      | The   date/time as recorded by the pharmacy system.                                                                                                                                                                                                                                                                                                             | Required                         | MedicationStatement.effective                                              |

## Example Medications and Medical Devices Section ##

```
<!--<xml>-->
	<section>
		<title value="Medications and medical devices"/>
		<code>
			<coding>
				<system value="http://snomed.info/sct"/>
				<code value="933361000000108"/>
				<display value="Medications and medical devices"/>
			</coding>
		</code>
		<text>
		<status value="additional"/>
		<div xmlns="http://www.w3.org/1999/xhtml">
		<table width="100%">
			<tbody>
				<tr>
					<th>Supply type</th>
					<td>A description of the type of medication being supplied (e.g. emergency supply, over the counter medication, patient group direction etc.).</td>
				</tr>
				<tr>
					<th>Medication name</th>
					<td>BD Viva hypodermic insulin needles for pre-filled / reusable pen injectors screw on 5mm/31gauge (Becton, Dickinson UK Ltd)</td>
				</tr>
				<tr>
					<th>Form</th>
					<td>capsule</td>
				</tr>
				<tr>
					<th>Site</th>
					<td>"Mouth"</td>
				</tr>
				<tr>
					<th>Indication</th>
					<td>Reason for medication being prescribed, where known.</td>
				</tr>
				<tr>
					<th>Total amount of medication supplied</th>
					<td>30 tablets</td>
				</tr>
				<tr>
					<th>Dose directions description</th>
					<td>I tablet at night" or "20mg at 10pm"</td>
				</tr>
				<tr>
					<th>Additional instructions</th>
					<td>Allows for: <br> - requirements for adherence support, e.g., compliance aids, prompts and packaging requirements <br> - additional information about specific person requirements, e.g., unable to swallow tablets.medicines, e.g., where specific brand required</td>
				</tr>
				<tr>
					<th>Date/time</th>
					<td>The date/time on which the medication was supplied to the patient.</td>
				</tr>
			</tbody>
		</table>
		</div>
		</text>
		<!--reference to further information carried in the medication dispense list resource-->
		<entry>
			<reference value="urn:uuid:4bc7faea-5974-407a-b658-d6ed1d4c9187"/>
		</entry>
	</section>
<!--</xml>-->
```

## Coded Resources ##

This text section should be linked to the following FHIR Resources to provide the textual information in a coded format.

- List
- MedicationDispense
- Medication
 
See constructing clinical coded structures - [Medication Dispense List](build_medication_dispense_list.html)
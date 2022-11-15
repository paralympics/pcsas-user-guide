# Tools

These are the tools use to make batch updates/changes to athlete profiles. 

## Duplicate Control

The duplicate control functionality is used to generate PDF reports indicating possible duplicate
entries in PCSAS. The search is customisable and automatically restricted by user data access.
Additionally, a merging tool allows to easily remove duplicates by merging relevant information
to a single profile.

The search criteria are specified by the following fields:

| **Field**                                           | **Format**             | **Comments**                                         |
| --------------------------------------------------- | ---------------------- | ---------------------------------------------------- |
| **Sport**                                           |                        | Defaults to Para-Cycling                             |
| **Member Federation**                               | drop down [federation] |                                                      |
| <span class="table-header">Equality Criteria</span> |                        |                                                      |
| **Family Name (passport)**                          | tick box               | default selections if no other criteria are applied. |
| **Given Name (passport)**                           | tick box               | default selections if no other criteria are applied. |
| **National Federation**                             | tick box               |                                                      |
| **Gender**                                          | tick box               |                                                      |
| **Date of Birth**                                   | tick box               |                                                      |
| **Passport/ID Card No**                             | tick box               |                                                      |

The criteria work in conjunction – the search only returns items that are equal on all selected
criteria, within any possible restriction by NF and/or sport.

Clicking **Search** opens a new tab in the browser with a PDF of the matches. Except for sport, all
personal data which can be searched is also displayed here, along with the career status of the
athlete.

When duplicates are found, it is recommended to merge all data from one profile the other and
delete the obsolete entry to keep the system clean.

## Classification Mass Import

With the continuous growth of sports for people with an impairment, more and more athletes
are classified in a single panel whose outcome needs to be registered in PCSAS. For simple
classification changes, it might be time-consuming to follow the steps as described in 
[Classification Details](athletes/classification.md#classification-details) for each athlete one by one.

The classification mass import offers a method to massively change the basic values like class,
class status, date, year of review and potential limitations with just a few clicks.

<figure>
    <img src="_img/figures/4.6-classification-mass-import.png" alt="Classification Mass Import" class="screenshot" >
    <figcaption>Figure 4.6 - Classification Mass Import</figcaption>
</figure>

It is highly recommend reading the *Instructions* and downloading the Excel template from there.
Basically, this template must be precisely filled out with the relevant information like the Athlete
ID, class, class status, and date of classification, year of review, names or acronyms of
responsible classifier and the codes for class limitations.

### How To: Use the classification mass import.

1. Download the Excel template from the tab *Instructions* and fill it out according to the 
   instructions. The examples in the template might help to understand. Save the file.

2. Open the tab *File Import*, select the sport and browse for the saved template. Click **Import**.

3. The *Import Log* indicates any potential problem like an unknown athlete ID, wrong class 
   name, an incorrect date format and similar. When errors are detected, correct them, 
   save the file again and repeat step 2 until the import is completed and the tab *File Import Control* 
   appears, see Figure 4.7.

<figure>
    <img src="_img/figures/4.7-file-import-control.png" alt="File Import Control" class="screenshot" >
    <figcaption>Figure 4.7 - File Import Control</figcaption>
</figure>

4. The import does not immediately replace classification data. The control view shows one 
   athlete per row with his current (*Old*) classification and the data uploaded from the 
   template (*New*). Sports with several classes like athletics and swimming distinguishes 
   the potential replacement by class group (see [Sport Codes](application-settings/sport-codes.md)).

5. For each row, decide to (1) replace the current classification as stored in the database 
   with the new one uploaded from the template (by class group), (2) only to add the new 
   class, (3) to ignore the new class, necessary by errors, (4) to ignore the data for now. The 
   replacement (1) is set as default value.

6. Once the decisions are made, click **Apply Class Updates**. 

   > [!DANGER]
   > Now all changes are irreversibly applied to the PCSAS classification table!    

   Replaced classification is automatically moved to the history section, the new classes 
   appear under *Current Classification*, (see [Classification Details](athletes/classification.md#classification-details)).

7. When all data are processed, an import log shows the final processes. This import log 
   can be reviewed anytime later from the mass import search grid.

It is important to understand from the instructions above that the upload of the template with
data does not immediately change any classification values, but the user is obliged to review the
proposed replacements before the data in the classification section is affected.

> [!DANGER]
> The class updates process with click on *Apply Class Updates* is irreversible!
> This means that the old classification if replaced cannot be massively restored. 
> However, the user still has the option to perform the necessary adjustments for 
> each athlete individually. The import log acts as a helper to know which athletes 
> were affected and which classes were replaced or added.
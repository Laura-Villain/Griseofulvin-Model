### In vitro / physico-chemical Data <a id="invitro-and-physico-chemical-data"></a>

A literature search was performed to collect available information on physicochemical properties of griseofulvin. The obtained information from literature is summarized in the table below. 

| **Parameter**   | **Unit** | **Value** | Source                                     | **Description**                                 |
| :-------------- | -------- | --------- | ------------------------------------------ | ----------------------------------------------- |
| MW              | g/mol    |    352.77       | [PubChem 2025](#main-references)               | Molecular weight                                |
| pK<sub>a</sub>  |          |     2.18      | [Hansch 1995](#main-references)         | Acid dissociation constant                      |
| Solubility (pH) |      mg/l    |   8.82 (6.5)        | [Brinkmann-Trettenes 2014](#main-references)               | Aqueous Solubility   |

### Clinical Data  <a id="clinical-data"></a>

A literature search was performed to collect available clinical data on griseofulvin in healthy adults.

#### Model Building <a id="model-building"></a>

The following studies were used for model building (training data):

| **Dose [mg]** | **Dosing** | **PK data** |**Dataset**| **Reference** |
| --------------- | ------------------- | ----------------------- | ----------------- |----------------- |
| 99| iv bolus, single dose, fasted |plasma|training|[Rowland 1968](#5-references)| 
| 122| iv, single dose, fasted |plasma|training|[Rowland 1968](#5-references)| 
| 142| iv, single dose, fasted |plasma|training|[Rowland 1968](#5-references)| 
| 500| po, tab, po, tab, fasted state with meal administered at 3h post-dose |plasma|training|[Rowland 1968](#5-references)| 


#### Model Verification <a id="model-verification"></a>

The following studies were used for model verification:

| **Dose [mg]** | **Dosing** | **PK data** |**Dataset**| **Reference** |
| --------------- | ------------------- | ----------------------- | ----------------- |----------------- |
| 500| po, tab, po, tab, fasted state with meal administered at 4h post-dose |plasma|verification|[Malm-Erjefält 2015](#5-references)| 


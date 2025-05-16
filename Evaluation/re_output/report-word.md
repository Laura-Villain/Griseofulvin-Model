---
title: 'Building and evaluation of a PBPK model for Griseofulvin in healthy adults'
subtitle: ''
abstract: | 
	 
	 
	 
	 
	 
	 
	 
	 | Version                                         | x.x-OSPy.y                                                   |
	 | ----------------------------------------------- | ------------------------------------------------------------ |
	 | based on *Model Snapshot* and *Evaluation Plan* | https://github.com/Open-Systems-Pharmacology/Griseofulvin-Model/releases/tag/vx.x |
	 | OSP Version                                     | 11.3                                                          |
	 | Qualification Framework Version                 | 11.3                                                          |
	 
	 
	 
	 
	 
	 This evaluation report and the corresponding PK-Sim project file are filed at:
	 
	 https://github.com/Open-Systems-Pharmacology/OSP-PBPK-Model-Library/
	 
	 
	 `<w:br w:type="page"/>`{=openxml}
---





# Introduction`<w:bookmarkStart w:id="introduction" w:name="introduction"/><w:bookmarkEnd w:id="introduction"/>`{=openxml}


The presented model building and evaluation report describes the development of a PBPK model for griseofulvin in healthy adults.

Griseofulvin is an orally administered antifungal agent used to treat skin and nail infections. 
It acts by disrupting microtubule function, thereby inhibiting fungal cell division. 
The compound selectively accumulates in keratin-producing tissues, providing localized antifungal activity.

Griseofulvin exhibits variable oral absorption, with bioavailability influenced by formulation and food intake. 
Peak plasma concentrations are typically observed within 4 to 8 hours. 
After absorption, the drug distributes broadly into skin, liver, fat, and muscle. 
It is extensively metabolized in the liver, with elimination occurring through both urine and feces. 
The terminal half-life ranges from 9 to 24 hours.

The presented Griseofulvin PBPK model as well as the respective evaluation plan and evaluation report are provided open-source ([https://github.com/Open-Systems-Pharmacology/Griseofulvin-Model](https://github.com/Open-Systems-Pharmacology/Griseofulvin-Model)).







# Methods`<w:bookmarkStart w:id="methods" w:name="methods"/><w:bookmarkEnd w:id="methods"/>`{=openxml}





## Modeling Strategy`<w:bookmarkStart w:id="modeling-strategy" w:name="modeling-strategy"/><w:bookmarkEnd w:id="modeling-strategy"/>`{=openxml}


The general concept of building a PBPK model has previously been described by Kuepfer et al. ([Kuepfer 2016](#main-references)) Regarding the relevant anthropometric (height, weight) and physiological parameters (e.g. blood flows, organ volumes, binding protein concentrations, hematocrit, cardiac output) in adults was gathered from the literature and has been previously published ([PK-Sim Ontogeny Database Version 7.3](#main-references)). The information was incorporated into PK-Sim® and was used as default values for the simulations in adults.

The  applied activity and variability of plasma proteins and active processes that are integrated into PK-Sim® are described in the publicly available PK-Sim® Ontogeny Database Version 7.3 ([Schlender 2016](#main-references)) or otherwise referenced for the specific process.

First, a base mean model was built using clinical Phase I data including selected single dose studies with intravenous and oral applications (tablet) of Griseofulvin to find an appropriate structure to describe the pharmacokinetics in plasma. The mean PBPK model was developed using a typical European individual. 

Unknown parameters (see below) were identified using the Parameter Identification module provided in PK-Sim®. Structural model selection was mainly guided by visual inspection of the resulting description of data and biological plausibility.

Once the appropriate structural model was identified, additional parameters for tablet formulations were identified. 

The model was then verified by simulating:

- Oral administration of Griseofulvin in fasted then fed state

Details about input data (physicochemical, *in vitro* and clinical) can be found in  [Section 2.2](#methods-data).

Details about the structural model and its parameters can be found in  [Section 2.3](#model-parameters-and-assumptions).






## Data`<w:bookmarkStart w:id="methods-data" w:name="methods-data"/><w:bookmarkEnd w:id="methods-data"/>`{=openxml}


### In vitro / physico-chemical Data `<w:bookmarkStart w:id="invitro-and-physico-chemical-data" w:name="invitro-and-physico-chemical-data"/><w:bookmarkEnd w:id="invitro-and-physico-chemical-data"/>`{=openxml}

A literature search was performed to collect available information on physicochemical properties of dapagliflozin. The obtained information from literature is summarized in the table below. 

| **Parameter**   | **Unit** | **Value** | Source                                     | **Description**                                 |
| :-------------- | -------- | --------- | ------------------------------------------ | ----------------------------------------------- |
| MW              | g/mol    |    352.8       | [PubChem 2025](#main-references)               | Molecular weight                                |
| pK~a~  |          |     2.18      | [Hansch 1995](#main-references)         | Acid dissociation constant                      |
| Solubility (pH) |      mg/l    |   8.82 (6.5)        | [Brinkmann-Trettenes 2014](#main-references)               | Aqueous Solubility   |

### Clinical Data  `<w:bookmarkStart w:id="clinical-data" w:name="clinical-data"/><w:bookmarkEnd w:id="clinical-data"/>`{=openxml}

A literature search was performed to collect available clinical data on dapagliflozin in healthy adults.

#### Model Building `<w:bookmarkStart w:id="model-building" w:name="model-building"/><w:bookmarkEnd w:id="model-building"/>`{=openxml}

The following studies were used for model building (training data):

| **Dose [mg]** | **Dosing** | **PK data** |**Dataset**| **Reference** |
| --------------- | ------------------- | ----------------------- | ----------------- |----------------- |
| 99| iv |plasma|training|[Rowland 1968](#5-references)| 
| 122| iv |plasma|training|[Rowland 1968](#5-references)| 
| 142| iv |plasma|training|[Rowland 1968](#5-references)| 
| 500| po, tab, fasted then fed |plasma|training|[Rowland 1968](#5-references)| 


#### Model Verification `<w:bookmarkStart w:id="model-verification" w:name="model-verification"/><w:bookmarkEnd w:id="model-verification"/>`{=openxml}

The following studies were used for model verification:

| **Dose [mg]** | **Dosing** | **PK data** |**Dataset**| **Reference** |
| --------------- | ------------------- | ----------------------- | ----------------- |----------------- |
| 500| po, tab, fasted then fed |plasma|verification|[Malm-Erjefält 2015](#5-references)| 






## Model Parameters and Assumptions`<w:bookmarkStart w:id="model-parameters-and-assumptions" w:name="model-parameters-and-assumptions"/><w:bookmarkEnd w:id="model-parameters-and-assumptions"/>`{=openxml}


### Absorption `<w:bookmarkStart w:id="model-parameters-and-assumptions-absorption" w:name="model-parameters-and-assumptions-absorption"/><w:bookmarkEnd w:id="model-parameters-and-assumptions-absorption"/>`{=openxml}

The parameters values for `Intestinal permeability` and `Permeability P(intracellular->interstitial) Mucosa` were optimized based on clinical oral data, see [Section 2.3.4](#model-parameters-and-assumptions-identification), taking into account the fact that most of the absorption occurs in the duodenum. 
The measured solubility of Griseofulvin was taken from Product information from [Brinkmann-Trettenes 2014](#main-references) (see [Section 2.2.1](#invitro-and-physico-chemical-data)).

Tablet dissolution was modeled using an empirical Weibull dissolution approach, with the corresponding parameters estimated accordingly.

### Distribution `<w:bookmarkStart w:id="model-parameters-and-assumptions-distribution" w:name="model-parameters-and-assumptions-distribution"/><w:bookmarkEnd w:id="model-parameters-and-assumptions-distribution"/>`{=openxml}


After testing the available organ-plasma partition coefficient and cell permeability calculation methods built in PK-Sim, observed clinical data was best described by choosing the partition coefficient calculation by `Poulin and Theil` and cellular permeability calculation by `Charge dependant Schmitt`. 


### Metabolism and Elimination `<w:bookmarkStart w:id="model-parameters-and-assumptions-metabolism-and-elimination" w:name="model-parameters-and-assumptions-metabolism-and-elimination"/><w:bookmarkEnd w:id="model-parameters-and-assumptions-metabolism-and-elimination"/>`{=openxml}

A general hepatic clearance was implemented and the value for `Plasma Clearance` was optimized using the training dataset. 

### Automated Parameter Identification `<w:bookmarkStart w:id="model-parameters-and-assumptions-parameter-identification" w:name="model-parameters-and-assumptions-parameter-identification"/><w:bookmarkEnd w:id="model-parameters-and-assumptions-parameter-identification"/>`{=openxml}

This is the result of the final parameter identification.

| Model Parameter      | Optimized Value | Unit |
| -------------------- | --------------- | ---- |
| `Fraction unbound` |          0.20       |      |
| `Plasma Clearance` |        1.3         |      |ml/min/kg
| `Intestinal permeability` |     3E-3            | cm/min     |
| `Weibul Dissolution time` |        60         |  min    |
| `Weibul Dissolution shape` |        4.00         |   -   |
| `Permeability P(intracellular->interstitial) Mucosa (Duodenum)` |        5.0E-3         |   cm/min   |
| `Permeability P(intracellular->interstitial) Mucosa (large intestine)`  |        2E-03         |   cm/min   |
| `Permeability P(intracellular->interstitial) Mucosa (small intestine)`  |        1E-04         |   cm/min   |






# Results and Discussion`<w:bookmarkStart w:id="results-and-discussion" w:name="results-and-discussion"/><w:bookmarkEnd w:id="results-and-discussion"/>`{=openxml}


The PBPK model for Griseofulvin was developed and verified with clinical pharmacokinetic data.

The model was evaluated covering data from studies including in particular

* Intravenous Bolus
* Oral administration over fed and fasted states.

The model quantifies ...

The next sections show:

1. the final model parameters for the building blocks: [Section 3.1](#final-input-parameters).
2. the overall goodness of fit: [Section 3.2](#diagnostics-plots).
3. simulated vs. observed concentration-time profiles for the clinical studies used for model building and for model verification: [Section 3.3](#ct-profiles).






## Final input parameters`<w:bookmarkStart w:id="final-input-parameters" w:name="final-input-parameters"/><w:bookmarkEnd w:id="final-input-parameters"/>`{=openxml}


The compound parameter values of the final PBPK model are illustrated below.





### Compound: Griseofulvin

#### Parameters

Name                                       | Value          | Value Origin | Alternative | Default
------------------------------------------ | -------------- | ------------:| ----------- | -------
Solubility at reference pH                 | 8.82 mg/l      |              | Measurement | True   
Reference pH                               | 6.5            |              | Measurement | True   
Solubility at reference pH                 | 14 mg/l        |              | table       | False  
Reference pH                               | 7.4            |              | table       | False  
Solubility table                           | 8.82 mg/l      |              | table2      | False  
Lipophilicity                              | 2.18 Log Units |              | Measurement | True   
Fraction unbound (plasma, reference value) | 0.2            |              | Measurement | True   
Is small molecule                          | Yes            |              |             |        
Molecular weight                           | 352.767 g/mol  |              |             |        
Plasma protein binding partner             | Albumin        |              |             |        


#### Calculation methods

Name                    | Value          
----------------------- | ---------------
Partition coefficients  | PK-Sim Standard
Cellular permeabilities | PK-Sim Standard


#### Processes

##### Systemic Process: Total Hepatic Clearance-Hepatic_Clearance

Species: Human

###### Parameters

Name                          | Value          | Value Origin                                                                                                         
----------------------------- | -------------- | ---------------------------------------------------------------------------------------------------------------------
Fraction unbound (experiment) | 0.2            | Parameter Identification-Parameter Identification-Value updated from 'Parameter Identification 2' on 2025-04-10 14:24
Lipophilicity (experiment)    | 2.18 Log Units | Parameter Identification-Parameter Identification-Value updated from 'Parameter Identification 2' on 2025-04-10 14:24
Plasma clearance              | 1.3 ml/min/kg  | Parameter Identification-Parameter Identification-Value updated from 'Parameter Identification 1' on 2025-05-16 17:57







## Diagnostics Plots`<w:bookmarkStart w:id="diagnostics-plots" w:name="diagnostics-plots"/><w:bookmarkEnd w:id="diagnostics-plots"/>`{=openxml}


Below you find the goodness-of-fit visual diagnostic plots for the PBPK model performance of all data used presented in [Section 2.2.2](#clinical-data).

The first plot shows observed versus simulated plasma concentration, the second weighted residuals versus time. 



```{=openxml}
<w:br w:type="page"/>
```

`<w:bookmarkStart w:id="table-3-1" w:name="table-3-1"/><w:bookmarkEnd w:id="table-3-1"/>`{=openxml}

**Table 3-1: GMFE for Goodness of fit plot for concentration in plasma**


|Group                                                    |GMFE |
|:--------------------------------------------------------|:----|
|Griseofulvin Intravenous Administration (model building) |1.76 |
|Griseofulvin Oral Administration (model building)        |1.72 |
|Griseofulvin Oral Administration (model verification)    |1.91 |
|All                                                      |1.77 |


<br>
<br>


```{=openxml}
<w:br w:type="page"/>
```

`<w:bookmarkStart w:id="figure-3-1" w:name="figure-3-1"/><w:bookmarkEnd w:id="figure-3-1"/>`{=openxml}

![](images/006_section_results-and-discussion/008_section_diagnostics-plots/2_gof_plot_predictedVsObserved.png)



**Figure 3-1: Goodness of fit plot for concentration in plasma**


<br>
<br>


```{=openxml}
<w:br w:type="page"/>
```

`<w:bookmarkStart w:id="figure-3-2" w:name="figure-3-2"/><w:bookmarkEnd w:id="figure-3-2"/>`{=openxml}

![](images/006_section_results-and-discussion/008_section_diagnostics-plots/3_gof_plot_residualsOverTime.png)



**Figure 3-2: Goodness of fit plot for concentration in plasma**


<br>
<br>





## Concentration-Time Profiles`<w:bookmarkStart w:id="ct-profiles" w:name="ct-profiles"/><w:bookmarkEnd w:id="ct-profiles"/>`{=openxml}


Simulated versus observed concentration-time profiles of all data listed in [Section 2.2.2](#clinical-data) are presented below.



```{=openxml}
<w:br w:type="page"/>
```

`<w:bookmarkStart w:id="figure-3-3" w:name="figure-3-3"/><w:bookmarkEnd w:id="figure-3-3"/>`{=openxml}

![](images/006_section_results-and-discussion/009_section_ct-profiles/1_time_profile_plot_Griseofulvin_Malm_500_PO.png)



**Figure 3-3: Time Profile Analysis**


<br>
<br>


```{=openxml}
<w:br w:type="page"/>
```

`<w:bookmarkStart w:id="figure-3-4" w:name="figure-3-4"/><w:bookmarkEnd w:id="figure-3-4"/>`{=openxml}

![](images/006_section_results-and-discussion/009_section_ct-profiles/2_time_profile_plot_Griseofulvin_Rowland_122_IV.png)



**Figure 3-4: Time Profile Analysis**


<br>
<br>


```{=openxml}
<w:br w:type="page"/>
```

`<w:bookmarkStart w:id="figure-3-5" w:name="figure-3-5"/><w:bookmarkEnd w:id="figure-3-5"/>`{=openxml}

![](images/006_section_results-and-discussion/009_section_ct-profiles/3_time_profile_plot_Griseofulvin_Rowland_142_IV.png)



**Figure 3-5: Time Profile Analysis**


<br>
<br>


```{=openxml}
<w:br w:type="page"/>
```

`<w:bookmarkStart w:id="figure-3-6" w:name="figure-3-6"/><w:bookmarkEnd w:id="figure-3-6"/>`{=openxml}

![](images/006_section_results-and-discussion/009_section_ct-profiles/4_time_profile_plot_Griseofulvin_Rowland_99_IV.png)



**Figure 3-6: Time Profile Analysis**


<br>
<br>


```{=openxml}
<w:br w:type="page"/>
```

`<w:bookmarkStart w:id="figure-3-7" w:name="figure-3-7"/><w:bookmarkEnd w:id="figure-3-7"/>`{=openxml}

![](images/006_section_results-and-discussion/009_section_ct-profiles/5_time_profile_plot_Griseofulvin_Rowland_500_PO.png)



**Figure 3-7: Time Profile Analysis**


<br>
<br>





# Conclusion`<w:bookmarkStart w:id="conclusion" w:name="conclusion"/><w:bookmarkEnd w:id="conclusion"/>`{=openxml}


The herein presented PBPK model adequately describes the pharmacokinetics of Griseofulvin in adults.
A high variability in the pharmacokinetics of oral Griseofulvin was observed between patients in the clinical studies, making it difficult to find parameters that would fit well each subject. 
Such a variability needs to be taken into account for the simulation of the pharmacokinetics of Griseofulvin in patients.






# References`<w:bookmarkStart w:id="main-references" w:name="main-references"/><w:bookmarkEnd w:id="main-references"/>`{=openxml}


**Kuepfer 2016** Kuepfer L, Niederalt C, Wendl T, Schlender JF, Willmann S, Lippert J, Block M, Eissing T, Teutonico D. Applied Concepts in PBPK Modeling: How to Build a PBPK/PD Model.CPT Pharmacometrics Syst Pharmacol. 2016 Oct;5(10):516-531. doi: 10.1002/psp4.12134. Epub 2016 Oct 19. 	

**PK-Sim Ontogeny Database Version 7.3** ([https://github.com/Open-Systems-Pharmacology/OSPSuite.Documentation/blob/38cf71b384cfc25cfa0ce4d2f3addfd32757e13b/PK-Sim%20Ontogeny%20Database%20Version%207.3.pdf](https://github.com/Open-Systems-Pharmacology/OSPSuite.Documentation/blob/38cf71b384cfc25cfa0ce4d2f3addfd32757e13b/PK-Sim%20Ontogeny%20Database%20Version%207.3.pdf))	

**Schlender 2016** Schlender JF, Meyer M, Thelen K, Krauss M, Willmann S, Eissing T, Jaehde U. Development of a Whole-Body Physiologically Based Pharmacokinetic Approach to Assess the Pharmacokinetics of Drugs in Elderly Individuals. Clin Pharmacokinet. 2016 Dec;55(12):1573-1589. 	

**PubChem 2025** PubChem Compound Summary of Griseofulvin (2025). https://pubchem.ncbi.nlm.nih.gov/compound/Griseofulvin

**Hansch 1995** Hansch C, Hoekman D, Leo A, Zhang L, Li P. The expanding role of quantitative structure-activity relationships (QSAR) in toxicology. Toxicol Lett. 1995 Sep;79(1-3):45-53. doi: 10.1016/0378-4274(95)03356-p. PMID: 7570673.

**Brinkmann-Trettenes 2014** Brinkmann-Trettenes U, Bauer-Brandl A. Solid phospholipid nano-particles: investigations into formulation and dissolution properties of griseofulvin. Int J Pharm. 2014 Jun 5;467(1-2):42-7. doi: 10.1016/j.ijpharm.2014.03.023. Epub 2014 Mar 11. PMID: 24614583.

**Rowland 1968** Rowland M, Riegelman S, Epstein WL. Absorption kinetics of griseofulvin in man. J Pharm Sci. 1968 Jun;57(6):984-9. doi: 10.1002/jps.2600570613. PMID: 5671346.

**Malm-Erjefält 2015** Malm-Erjefält M, Ekblom M, Vouis J, Zdravkovic M, Lennernäs H. Effect on the Gastrointestinal Absorption of Drugs from Different Classes in the Biopharmaceutics Classification System, When Treating with Liraglutide. Mol Pharm. 2015 Nov 2;12(11):4166-73. doi: 10.1021/acs.molpharmaceut.5b00278. Epub 2015 Oct 12. PMID: 26426736.



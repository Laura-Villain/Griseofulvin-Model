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



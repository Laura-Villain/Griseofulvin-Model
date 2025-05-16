### Absorption <a id="model-parameters-and-assumptions-absorption"></a>

The parameters values for `Intestinal permeability` and `Permeability P(intracellular->interstitial) Mucosa` were optimized based on clinical oral data, see [Section 2.3.4](#model-parameters-and-assumptions-identification), taking into account the fact that most of the absorption occurs in the duodenum. 
The measured solubility of Griseofulvin was taken from Product information from [Brinkmann-Trettenes 2014](#main-references) (see [Section 2.2.1](#invitro-and-physico-chemical-data)).

Tablet dissolution was modeled using an empirical Weibull dissolution approach, with the corresponding parameters estimated accordingly.
### Distribution <a id="model-parameters-and-assumptions-distribution"></a>


After testing the available organ-plasma partition coefficient and cell permeability calculation methods built in PK-Sim, observed clinical data was best described by choosing the partition coefficient calculation by `Poulin and Theil` and cellular permeability calculation by `Charge dependant Scmitt normalized to PK-Sim`. 


### Metabolism and Elimination <a id="model-parameters-and-assumptions-metabolism-and-elimination"></a>

A general hepatic clearance was implemented and the value for `Plasma Clearance` was optimized using the training dataset. 

### Automated Parameter Identification <a id="model-parameters-and-assumptions-parameter-identification"></a>

This is the result of the final parameter identification.

| Model Parameter      | Optimized Value | Unit |
| -------------------- | --------------- | ---- |
| `Fraction unbound` |          0.20       |      |
| `Plasma Clearance` |        1.2         |      |ml/min/kg
| `Intestinal permeability` |     2.8E-3            | cm/min     |
| `Weibul Dissolution time` |        60         |  min    |
| `Weibul Dissolution shape` |        4.00         |   -   |
| `Permeability P(intracellular->interstitial) Mucosa (Duodenum)` |        6.0E-3         |   cm/min   |
| `Permeability P(intracellular->interstitial) Mucosa (large intestine)`  |        2E-03         |   cm/min   |
| `Permeability P(intracellular->interstitial) Mucosa (small intestine)`  |        1E-04         |   cm/min   |


# README for scripts and data associated with illustration of decision framework for multi-hazard resilient, sustainable buildings
2019-12-09, created by Madeleine Flint as part of the VT-RSB project, funded by NSF CMMI #1455466. Any opinions, findings, and conclusions or recommendations expressed in this material are those of the authors and do not necessarily reflect the views of the National Science Foundation.

This repository contains scripts and data related to an illustration of the use of a modular decision framework to support early design of a hypothetical mid-rise office building located in Charleston, SC. The scripts and data can be used to reproduce data and plots associated with a companion journal manuscript "A decision framework for early design of multi-hazard resilient sustainable buildings," submitted to Engineering Structures on Dec. 2, 2019. It is noted that some text included in this README is derived from an early manuscript draft. This repository should be cited as:

Flint, Madeleine M, Mohsen Zaker Esteghamati, and Yasaman Shahtaheri (2019) "Scripts and data associated with illlustration of decision framework for multi-hazard resilient, sustainable buildings", DesignSafe-CI.

A DOI will be provided by the NHERI Design Safe CyberInfrastructure upon publication.

## Table of Contents
- [Motivation and Overview](#motivation-and-overview)
- [Illustration Details](#illustration-details)
  * [M0: Decision framing](#m0--decision-framing)
  * [M1: SFLE (soil-foundation-lateral structure-envelope) system generator](#m1--sfle--soil-foundation-lateral-structure-envelope--system-generator)
  * [M2: probabilistic life-cycle performance assessment](#m2--probabilistic-life-cycle-performance-assessment)
  * [M3: reliability-based ranking and optimization of alternative configurations using a generalized preference system](#m3--reliability-based-ranking-and-optimization-of-alternative-configurations-using-a-generalized-preference-system)
- [Technologies](#technologies)
- [How to Use](#how-to-use)
  * [M0: Decision framing](#m0--decision-framing-1)
  * [M1: SFLE (soil-foundation-lateral structure-envelope) system generator](#m1--sfle--soil-foundation-lateral-structure-envelope--system-generator-1)
  * [M2: probabilistic life-cycle performance assessment (earthquake focus)](#m2--probabilistic-life-cycle-performance-assessment--earthquake-focus-)
  * [M3: reliability-based ranking and optimization of alternative configurations using a generalized preference system](#m3--reliability-based-ranking-and-optimization-of-alternative-configurations-using-a-generalized-preference-system-1)
- [Repository Contents](#repository-contents)
- [Credits and Sources](#credits-and-sources)
- [License](#license)

<!--small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small-->


## Motivation and Overview
Achieving holistic resilient and sustainable building design requires that hazards be considered in the context of the full building life-cycle. Current design methods adequately address individual issues related to resilient and sustainable building design but cannot account for the complexities and interconnectedness of hazards and operation. A proposed decision framework integrates previous research in performance-based assessment to identify optimal building **S**oil, **F**oundation, **L**ateral structural, and **E**nvelope (SFLE) systems during early design. 

![VT-RSB Decision Framework](https://github.com/flintm/rsb-illustration/raw/master/Figs/RSB_Framework.png "RSB Decision Framework overlaid on standard Decision Analysis cycle")

Three modules assess resilience and sustainability over a broad set of SFLE systems: 

* (M1) site-appropriate SFLE system generation 
* (M2) probabilistic life cycle performance assessment
* (M3) multi-objective reliability-based ranking and optimization of candidate systems. 

These modules are envisioned generically and can be adapted for different building types, hazards, and performance metrics. Initial development efforts focus on mid-rise commercial buildings exposed to earthquake hazard and assessed for safety, cost, and energy. An illustration explores design of a hypothetical office building in Charleston, South Carolina.


## Illustration Details
Mid-rise commercial buildings were selected as the case study for decision framework development. These buildings tend to be designed by integrated project teams, exhibit low regional variability, account for a significant portion of commercial building energy consumption, and are centers of economic and governmental functions. The illustration identifies an optimal SFLE system for a hypothetical four-story office building is located in Charleston, South Carolina, USA (32.7221, -79.9341). The building is on a 30x30ft grid, with 6 bays in the longitudinal and 3 bays in the transverse direction, for a total of 64,800 square feet of floor area.  The climate is Zone 3A (Warm-Humid) and energy use is cooling-dominated. The building is exposed to high seismic hazard (S<sub>DS</sub> = 0.75g with site class B/C boundary) with a design life of 50 years.

![RSB illustration building plan](https://github.com/flintm/rsb-illustration/raw/master/Figs/Building_Plans.png "Elevation and Plan view of VT-RSB Archetype")

### M0: Decision framing

#### 0.1 Selection of eligible soil-foundation-lateral structure-envelope subsystems
Definition of the building and eligible SFLE subsystems uses pre-existing taxonomies.

In the illustration, from a set of 2 soil modifications, 3 foundation subsystems, 11 lateral structural subsystems, and 32 envelope subsystems applicable to mid-rise commercial buildings from a [multi-hazard performance data repository](), the hypothetical developers were assumed to have excluded soil reinforcement and masonry or wood lateral systems. Mat foundation and a curtain wall envelope subsystems were pre-defined as the only eligible alternatives.
#### 0.2 Selection of triple-bottom-line (TBL) sustainability metrics
Selection of TBL decision metrics that fully describe SFLE system sustainability and resilience; framework development has included life-cycle and initial cost, initial cost, time-integrated loss of function, downtime, CO2, and operational and embodied energy.

The illustration selected 7 metrics modeled as random variables with pre-determined probabilistic distributions.

1. Drift at the Design Basis Event (DBE) earthquake spectral acceleration at the structure's first mode period (Sa), lognormally distributed with ln(median) and dispersion.
1. Drift at Maximum Considered Event (MCE) earthquake Sa, lognormally distributed with ln(median) and dispersion.
1. Collapse drift limit used to compute probability of collapse at MCE Sa, lognormally distributed with log(median) and dispersion.
1. Initial cost, normally distributed with mean and coefficient of variation (CV).
1. Life-cycle cost (LCC), normally distributed with mean and standard deviation; a function of initial cost, maintenance, earthquake losses, and operation energy.
1. Embodied energy, normally distributed with mean and CV.
1. Operational energy, normally distributed with mean and CV.

#### 0.3 Definition of performance range
Definition of a performance range uses targeted literature review and expert elicitation to  identify the “best” and “worst” performing (yet code-compliant) systems, which must cover a wide range of hazard performance and energy efficiency.

The illustration performance range definition implicitly assumed that the developer would accept a code-minimum building costing 9M USD. The lateral subsystem seismic performance is later characterized as 1.5x and 2x code minimum, whereas the envelope subsystem performance is defined over a range of window-wall ratio from 40% to 22%.

#### 0.4 Preference assessment and indifference curve development
In the [SIMPLE-Design framework](https://doi.org/10.1016/j.autcon.2018.08.022), assessment of preferences and indifference curve development evaluates decision-maker utilities with respect to conflicting decision criteria within the performance range. After identifying a preferred alternative, the decision-maker generates equal-utility configurations, allowing regression to create an indifference curve representing bi-criteria tradeoffs. 

The illustration's indifference curves and preference systems were directly generated assuming the archetypal/hypothetical values of three stakeholder groups: developer, potential owner, and potential occupant/community. While the developer desires low initial costs (maximum profit), low liability (code compliant-safety), and sustainability (future marketing potential), the owner is concerned with life-cycle costs and operational energy. The occupants/community are concerned with environmental performance [AIA2030+](https://architecture2030.org/2030_challenges/2030-challenge/) and enhanced seismic performance [REDi TM](https://www.arup.com/perspectives/publications/research/section/redi-rating-system). Constraints (building code safety regulations and initial cost) are combined with safety, cost, and energy tradeoffs. 

Ten limit state functions represented the constraints and preferences of the three stakeholder groups. The developer’s drift-related constraints were augmented by the probability of collapse at MCE (<0.10), initial cost (<9.0M USD), and tradeoffs between life cycle cost and embodied or operational energy. The future owners’ interest in reducing the risk of total loss (collapse) or life-cycle expense was captured through tradeoffs with initial costs. Occupant desire for business continuity and “green” building was expressed as tradeoffs between strict limits for transient drift (0.5% at DBE and 1% at MCE) and operational energy use (70% and 90% below US median for office building energy use intensity).

The combination of the limit states was created using a generalized system. In addition to the limit states explicit in building design codes (1 and 3) and low initial cost (4), either developer cost-energy tradeoffs (5, 6), or either owner tradeoff (7, 8) was required to be satisfied. This system results in 4 "cut sets": *C* = {*C*<sub>I</sub> = {1}, *C*<sub>II</sub> = {3}, *C*<sub>III</sub> = {4}, *C*<sub>IV</sub> = {5,6,7,8}}.

### M1: SFLE (soil-foundation-lateral structure-envelope) system generator
Given a building taxonomy, user-determined eligible SFLE subsystems, and decision constraints or preferences, M1 generates a set of feasible alternative SFLE system configurations through two divergent phases and one convergent phase: (1) SFLE subsystem combinatorial expansion to the initial option space; (2) SFLE compatibility checks to develop the reduced non-infeasible set; and (3) parameterization to cover a range of performance. Optionally, (4) preliminary performance data may be passed to M3 to identify a higher-performing set of feasible candidate systems.

In the illustration, non-infeasible subsystems consistent with the decision framing (M0.1) were: *S* = {*s*<sub>1</sub> = "soil densification"}, *F* = {*f*<sub>3</sub> = "mat foundation"}, a set of 9 options for the lateral system in *L*, and *E* = {*e*<sub>9</sub> = "curtain; ventilated cavity; masonry rain screen and backup wall"}.

Performance data from  [multi-hazard performance data repository]() was pulled and used to assess the structural (safety) performance of non-infeasible lateral systems. The drift is modeled as lognormally distributed (median and dispersion) for the maximum transient interstory drift ratio (IDR) at design basis event (DBE) and maximum considered event (MCE) earthquake spectral accelerations (where Sa is taken at the first mode elastic period of the structure). For each system, M1 computes the probability of the IDR exceeding the limit states of 0.01 for DBE and 0.07 for MCE events. These targets were set to prioritize high-performing systems (the DBE limit) while making sure that possibly high-performing systems were not excluded (the MCE limit). M1 then ranks the lateral alternatives assuming a series system reliability formulation with no correlation and full correlation between limit states.

Only 6 of 11 lateral systems were available from the repsitory data. Of these, the M1 results indicated that the following lateral subsystems should be considered in the M2 assessment: *L* = {*l*<sub>3</sub> = "steel buckling restrained braced frame", *l*<sub>2</sub> = "steel concentrically braced frame", *l*<sub>7</sub> = "reinforced concrete moment-resisting frame (MRF)", *l*<sub>6</sub> = "steel MRF"}. The soil and foundation performance parameters (degree of densification and foundation depth, respectively) were limited to values of 0 (where the PP values are made dimensionless over the performance range from M0.3), whereas the lateral subsystem had variable PPs that took on values of 0, 0.5, and 1. 

### M2: probabilistic life-cycle performance assessment
Whereas M1 generates and pares down a set of systems based on qualitative or semi-quantitative criteria, M2 evaluates each alternative system configuration in detail. The probabilistic, quantitative approach draws on many existing methods from “performance-based engineering” as it is defined in the natural hazards, energy modeling, and durability research communities. Cradle-to-gate economic, societal, and environmental impacts are characterized, followed by operational performance (i.e., energy use), maintenance, and performance during the range of possible natural hazard events. Simulations must be sufficiently detailed to capture the difference between code-minimum and higher-performing configurations of the same SFLE system.

In the illustration, M2 considered only two lateral subsystems in the "special" class, *l*<sub>6</sub> = "reinforced concrete MRF", and *l*<sub>7</sub> = "steel MRF", each of which had 9 variant configurations (described subsequently). The illustration focuses on seismic performance and operational energy, with 2 SFLE alternatives x 9 lateral configurations x 3 envelope configurations = 54 candidate alternative configurations requiring life-cycle performance assessment.

#### Initial characterization
##### "Base case" configurations (lateral PP value = 0; envelope PP value = 0.5)
The [RSMeans commercial construction square foot cost estimator](https://www.rsmeans.com/products/online/core.aspx) was used to estimate the initial cost using cost ratios for Charleston, SC. Besides foundation, soil, and envelope selection, no customization was performed. This estimate included the SFLE, gravity structural subsystem, finishes, services, and AEC fees. The structure and envelope/partitions accounted for approximately 14 and 18%, respectively, of the total cost. As a percentage of SFLE, and partitions, the structural system cost was 35% for concrete and 50% for steel.

| Cost (M-USD)  | Concrete MRF  | Steel MRF  |
| ------------- | ------------- | ------------- |
| foundation  | 0.20 |  0.20 |
| shell (envelope+structure)  |  2.01 | 1.99 |
| *lateral structure*  |  *0.23* |  *0.20* |
| *gravity structure*  |  *0.53* |  *0.47* |
| *envelope*  |  *1.25* |  *1.21* |
| interior  |  1.44 | 1.44 |
| services |  2.80 | 3.02 |
| SUBTOTAL |  6.46 | 6.66 |
| + AEC FEES  | 8.64 | 8.91  |


The embodied energy (EE) associated with cradle-to-gate + maintenance was estimated using [Athena Impact Estimator](http://www.athenasmi.org/our-software-data/impact-estimator/), with customized assemblies for foundation, structure (gravity + lateral), envelope (with window-wall ratio of 31%), and partition walls and assuming a 50-year lifetime. The structure accounted for a significant portion of embodied energy, at 60% for the concrete MRF and 40% for steel. At 6.7 TJ, the envelope and partition walls also contributed significantly to embodied energy (24-37%), motivating the inclusion of these drift-sensitive non-structural components in the seismic assessment.

| EE (TJ)  | Concrete MRF  | Steel MRF  |
| ------------- | ------------- | ------------- |
| foundation  | 4.98  | 4.98  |
| vertical structure  | 7.81 | 4.31  |
| floors  | 6.65 | 2.53  |
| fa&ccedil;ade  | 3.87  | 3.87 |
| roof  | 2.6  | 0.04 |
| partition walls  | 2.50  | 2.50 |
| TOTAL  | 28.41 | 18.23  |
| *lateral structure*  | *7.81* | *4.31*  |
| *gravity structure*  | *9.25* | *2.57*  |
| *envelope*  | *3.87* | *3.87*  |


##### Lateral configurations (PP values of 0.5, 1)
Three hypothetical lateral performance parameters (PPs, as well as their combination) were identified to isolate the effects of various design decisions on seismic performance: yield strength, pre-capping plastic ductility (from yield to maximum strength), and post-capping ductility (from maximum to zero residual strength). 

* Normalized yield strength (*F*<sub>*y*</sub>) relates to overstrength, assuming constant stiffness. While it is generally difficult to isolate strength and stiffness, increased performance may be achievable by increasing member dimensions or varying the steel yield strength.
* Increased pre-capping plastic ductility (*δ*<sub>*p*</sub>) can be achieved through more ductile detailing, and isolates the effect of ductility at low shaking levels. 
* Post-capping ductility (*δ*<sub>*pc*</sub>) isolates ductility at high shaking levels, although in reality changes to joint detailing would affect both pre- and post-capping ductility; reduced building weight would also improve global near-collapse performance. 
* Combined increase of yield strength and pre- and post-capping ductility serves as a test of sufficiency; i.e., if an individual PP produces structural response equivalent to that of the combined system then it must sufficiently describe the seismic performance.

Factored values of 1.5 and 2&times; the code-minimum parameter value were considered for each PP (and the combined case) to represent PP values of 0, 0.5, and 1. The cost/energy marginal impact required to increase performance was estimated as follows:

* *F*<sub>*y*</sub>: proportional (1:1) to the cost/energy of the laterally-designed structural subsystem, i.e., for concrete the MRF plus a portion of the flat-plate floor system, and just the MRF for steel.
* *δ*<sub>*p*</sub>: proportional (1:0.5) to the laterally-designed subsystem.
* *δ*<sub>*pc*</sub>: proportional (1:0.1) to the gravity system cost/energy.

|    | +Pre-Fee Cost | (M-USD)   | +Embodied Energy  | (TJ)  |
| ------------- | ------------- | ------------- | ------------- | ------------- |
|   | Concrete MRF  | Steel MRF  | Concrete MRF  | Steel MRF  |
| *lateral structure*  |  *0.23* |  *0.20* | *7.81* | *4.31*  |
| *gravity structure*  |  *0.53* |  *0.47* | *9.25* | *2.57*  |
| +0.5*F<sub>y</sub>*  | 0.11 | 0.10  | 3.95 | 2.16 |
| +1.0*F<sub>y</sub>*  | 0.23 |  0.20 | 7.81 | 4.31 |
| +0.5*δ<sub>p</sub>*  | 0.06 | 0.05  | 1.95 | 1.07 |
| +1.0*δ<sub>p</sub>*  | 0.11 |  0.10 | 3.91 | 2.16 |
| +0.5*δ<sub>pc</sub>*  | 0.03 | 0.02  | 0.46 | 0.13 |
| +1.0*δ<sub>pc</sub>* | 0.05 | 0.05  | 0.93 | 0.26 |

##### Envelope configurations (PP values 0 and 1)
The envelope system PP was defined as the window-to-wall ratio of the envelope system, and with code-minimum defined as 40%, high-performance as 22%, and the intermediate "base" value of 31%. The marginal cost to increase performance was estimated using the following assumptions:

* Including materials and installation, the window square foot cost is ~60 USD, whereas the brick fa&ccedil;ade costs ~30 USD.
* The windows are placed in horizontal bands, such that the relative height of brick and window can be calculated.
* Window:wall ratios of 0.40, 0.31, and 0.22 therefore cost ~42 USD/sf, ~40 USD/sf, and ~38 USD/sf.
* The cost ratio to decrease or increase envelope performance is &pm; 2/40 = 0.05.
* The original RSMeans envelope costs were adjusted using this ratio to obtain the marginal cost increase

To compute changes in embodied energy, new Athena models were developed specifying window:wall ratios of 0.40 and 0.22.

|    | +Cost (M-USD)   | +Embodied Energy (TJ)  |
| ------------- | ------------- | ------------- |
| w:w: 40%  |  0.05 | -0.14 |
| *w:w 31%*  |  *--* |  *--* |
| w:w: 22%  |  -0.05 | 0.14 | 



#### Operational energy performance
The energy performance was modeled using [OpenStudio](http://openstudio.net) with data from [EnergyPlus](http://energyplus.net), assuming an interior layout and use as shown.



#### Seismic performance
The seismic behavior was modeled in OpenSees as a nonlinear single-degree-of-freedom (SDOF) oscillator using response history analysis over a suite of 80 unscaled synthetic ground motions based on a geologically-consistent hazard mapping of South Carolina. The performance-based earthquake engineering (PBEE) assessment is based on that of the ["PEER framework"](http://dx.doi.org/10.1061/9780784412121.173), and requires hazard analysis, structural analysis, damage analysis, and loss analysis. In addition to standard uncertainty sources, the pre-defined collapse-drift limit was defined as random variable *X*<sub>3</sub>, such that the PBEE assessment was conducted over discretized values of the structure-specific drift distribution. Subsequent convolution of expected lifetime loss ratio (ELLR) conditional on collapse drift limit with the collapse probability distribution allows the consideration of drift limit uncertainty. A similar convolution was performed to determine the probability of collapse at MCE.

The base or "code-minimum" configuration lateral configurations were obtained by fitting monotonic backbone SDOF parameters to a nonlinear static "pushover" of a representative building from the literature; the fitted backbone was uniformly scaled by the ratio of design seismic hazard of the original pushovers (in California) to the Charleston site (scale factor was 0.46).

##### Hazard (intensity measure, IM)
The seismic hazard curve was obtained from the [USGS Unified Hazard Tool]() and used the 2014 dynamic-conterminous (v4.1.1) mapping at B/C boundary for soil shear wave velocity. The hazard curve values for PGA, Sa(0.2s), Sa(1s), and Sa(2s) were loaded. Interpolation in log-log space was used for both Sa values at other periods and to support finer discretization of Sa and 
mean annual frequency of exceedence values (&lambda;<sub>IM</sub>) to support later numerical convolution.

Additionally, a [geologically realistic probabilistic hazard mapping of South Carolina](http://www.magma.geos.vt.edu/vtso/anonftp/scdot/report-FWHA-SC-06-09.pdf) was used in M2. This hazard model is derived from 1247 site locations within and adjacent to South Carolina for four 50-year exceedance probabilities (2%, 5%, 7% and 10%). Similar to USGS national hazard maps, the hazard model incorporates uncertainty due alternative: source configuration; source models for large characteristic earthquakes in the coastal area of Charleston; and ground motion prediction models. However, the significant difference from the USGS national hazard maps lies in representing actual geological conditions of Charleston through treatment of wave propagation in the coastal plain sedimentary section and weathered southeastern US Piedmont rock outside of the coastal plain.

The Charleston hazard maps were combined with a [ground motion simulation package](http://www.magma.geos.vt.edu/vtso/anonftp/scdot/report-FWHA-SC-06-09.pdf) to develop a suite of 80 hazard-consistent synthetic ground motions (GMs). The synthetic ground motions were developed using a stochastic method, which combines the seismological description of ground motion’s amplitude spectrum from the site hazard model with an adjusted random phase spectrum. The ground motion’s spectrum comprises three components (source, path and site) and encompasses the physical process of earthquake and resultant wave propagation. The code develops ground motion time series by generating white noise for the given duration, which is windowed and transformed to the frequency domain, scaled by the ground motion spectrum, and finally transformed back to the time domain [using a standard procedure](http://dx.doi.org/10.1007/PL00012553). The simulation package requires input magnitude-distance (M-R) pairs, which were obtained using an inverse transform sampling from the USGS hazard deaggregation at each level, such that the number of pairs in each bin was proportional to that bin’s contribution to the hazard. One synthetic GM was generated using for each M-R pair and associated hazard level.

##### Structural response (engineering demand parameter, EDP)
A least-squares regression in log-log space was performed on the OpenSees roof drift-spectral acceleration results. The regression was used to define lognormal distributions for roof drift (RD) given Sa. The distribution mean (ln of the median) was defined by ln(med(RD)) = *b*<sub>0</sub> + *b*<sub>1</sub>ln(Sa), and the dispersion *&beta;*<sub>RD|Sa</sub> was obtained from the regression error. As expected, PPs their values had no effect on the elastic behavior of the structures. Changes to pre-capping ductility and post-capping ductility affected drifts at large Sa values, with post-capping ductility having a larger effect. The combination of all PP s produced results with trends that could not easily be decomposed into the individual PP contributions, indicating that no individual PP is sufficient.

A log-logistic distribution for collapse probability conditional on Sa was obtained using the applicable pre-defined collapse drift limit, RD<sub>C</sub>. Two concrete configurations had unacceptable collapse probabilities (>10%); three others, including the code-minimum configurations, were close to unacceptable performance (>9%). While no steel configuration was unacceptable, the steel code-minimum and one other configuration had high MCE collapse probabilities (>9%). 

##### Damage of structural and non-structural components (damage states, DS)
The EDP results were translated to global damage states using the Hazus-MH drift-related limit states for 'slight', 'moderate', 'extensive', and 'complete' damage. The resulting fragility curves indicated that the code-minimum steel structure would experience earlier onset of almost all structural damage states as compared to the concrete structure. Fragility curves were also developed for non-structural drift-sensitive components using Hazus-MH data. The collapse fragility was obtained from the log-logistic regression and assumed to be mutually exclusive to the sequential damages states DS<sub>1</sub> to  DS<sub>4</sub>. The hazard curve &lambda;<sub>IM</sub> was then convolved with the fragility curves to obtain the annual probability of being in each damage state.

##### Economic loss and embodied energy (decision variables, DV)
Structural and non-structural damage repair cost ratios ranged from 0.4 to 32.9% of the assumed initial building value; with collapse repair cost ratio was assumed 110%. The annual probability of being in each damage state was multiplied by its associated repair cost ratio and summed over non-collapse/structural, non-collapse/non-structural, and collapse contributions. The expected annual loss ratio (EALR) was computed by summing the expected annual loss ratio over the components.

The expected lifetime loss ratio (ELLR) was estimated by multiplying the EALR by the input building lifetime (assumed 50 years in the illustration). This approximation is [acceptable due to the very low rate](http://doi.wiley.com/10.1002/eqe.504) of seismic events of interest at the site.

#### Lifetime impact characterization
Random variables/decision metrics were defined as:

* *X*<sub>1</sub>: drift at Sa DBE (unitless); data from PBEE assessment.
* *X*<sub>2</sub>: drift at Sa MCE (unitless); data from PBEE assessment.
* *X*<sub>3</sub>: collapse drift limit (unitless); median = 1.5&times;[Hazus-MH 'complete' damage drift limit], dispersion = 0.1.
* *X*<sub>4</sub>: initial cost (M USD); mean values from RSMeans initial assessment, CV = 0.05.
* *X*<sub>5</sub>: life-cycle cost (M USD); mean value *&mu;*<sub>*X*5</sub> = E[*X*<sub>5</sub>] = E[*X*<sub>4</sub>]&times;(1+EMLR+ELLR) + 0.0028E[*X*<sub>7</sub>]; *&sigma;*<sub>*X*5</sub><sup>2</sup> = VAR[*X*<sub>5</sub>] = (1+ELMR+ELLR)<sup>2</sup>&times;VAR[*X*<sub>4</sub>] + 0.0028<sup>2</sup>&times;VAR[*X*<sub>7</sub>]; where ELMR is the expected lifetime maintenance cost ratio, set to 0.56 (1.5USD/square foot &times; 50 years), and ELLR is obtained from the PBEE assessment convolved with collapse limit uncertainty, and 0.0028 = $0.10/kWh commercial electricity rate over 50 years.
* *X*<sub>6</sub>: embodied energy (TJ); *&mu;*<sub>*X*6</sub> = E[*X*<sub>6</sub>] = E[initial construction & maintenance]&times;(1+ELLR), CV = 0.05; expected embodied energy of initial construction and maintenance estimated using the Athena Impact Estimator.
* *X*<sub>7</sub>: operational energy (TJ); mean obtained from OpenStudio initial assessment using EnergyPlus data and CV = 0.2.

Correlations between random variables in *X*-space (**R**<sub>***XX***</sub>) were obtained as follows:

* *X*<sub>1</sub>-*X*<sub>2</sub>: OpenSees analysis of drift at DBE and drift at MCE using ground motions scaled to the Sa values was used to empirically estimate the correlations; ground motions that required scale factors >4 for the concrete or steel MRF structure were omitted; 0.5 &leq; *&rho;*<sub>*X*<sub></sub>1,*X*<sub></sub>2</sub> &leq; 0.9.
* *X*<sub>1</sub>/*X*<sub>2</sub>-*X*<sub>3</sub>: Monte Carlo Simulation computed empirical correlations; no *X*<sub>1</sub> samples caused collapse so *&rho;*<sub>*X*1,*X*3</sub> = 0; -0.7 &leq; *&rho;*<sub>*X*2,*X*3</sub> &leq; 0.
* *X*<sub>1</sub>/*X*<sub>2</sub>/*X*<sub>3</sub>-*X*<sub>4</sub>/*X*<sub>5</sub>/*X*<sub>6</sub>/*X*<sub>7</sub>: assumed zero as uncertainty in structural performance is assumed to be independent of uncertainty in initial cost, life-cycle cost, embodied energy, and operational energy; manuscript Supplemental Material provides a more detailed explanation.
* *X*<sub>4</sub>-*X*<sub>5</sub>: using the definition of covariance and linear expression for E[*X*<sub>5</sub>], is equal to *&rho;*<sub>*X*4,*X*5</sub> =(1+EMLR+ELLR)*&sigma;*<sub>*X*4</sub>/*&sigma;*<sub>*X*5</sub>, where *&sigma;*<sub>*X*i</sub> is the standard deviation of random variable *X<sub>i</sub>*.
* *X*<sub>4</sub>-*X*<sub>6</sub>/*X*<sub>7</sub>: assumed zero; explanation provided in manuscript Supplemental Material.
* *X*<sub>5</sub>-*X*<sub>6</sub>: assumed zero; explanation provided in manuscript Supplemental Material.
* *X*<sub>5</sub>-*X*<sub>7</sub>: using the definition of covariance and linear expression for E[*X*<sub>5</sub>], *&rho;*<sub>*X*5,*X*7</sub> = 0.0028*&sigma;*<sub>*X*7</sub>/*&sigma;*<sub>*X*5</sub>.
* *X*<sub>6</sub>-*X*<sub>7</sub>: assumed zero (source of uncertainty in embodied energy is independent of uncertainty in operational energy).

### M3: reliability-based ranking and optimization of alternative configurations using a generalized preference system

M3 used a standard implementation of the First-Order Reliability Method (FORM). The Sources section provides reference material and the improved Hasofer-Lind-Rackwitz-Feissler algorithm. A Nataf distribution between the 7 random variables was assumed, with the *Z*-space correlation matrix **R**<sub>***ZZ***</sub> defined equal to **R**<sub>***XX***</sub>.

With the exception of the third limit state function, *g*<sub>3</sub>, all limit states were linear indifference curves with an intercept and 1 or 2 coefficients across the 7 random variables. There were 10 limit state functions across the 4 cut sets previously described.

The top-ranked system was the code-minimum steel MRF with high-performance envelope. The code-minimum concrete MRF system with high-performance envelope ranked 26th.

## Technologies
* MATLAB R2019a with: Statistics and Machine Learning Toolbox; Curve Fitting Toolbox
* R v3.5.2 with: jsonlite v1.6; fields v10.0; reshape2 v1.4.3; mvtnorm v1.10-11; ggplot2 v3.1.0
* [OpenSees](https://opensees.berkeley.edu/OpenSees/user/download.php) v2.4.5; [TCL/TK](https://www.tcl.tk/software/tcltk/8.5.tml) 8.5

## How to Use
Reproduction of the illustration requires performing the initial decision framing (M0), and then running the three modules. As M2 and M3 rely on OpenSees assessment as well as M0, the most practical implementation would be to (1) follow the M1 steps in R, (2) perform the OpenSees analysis from M2, (3) follow the M0, M2, and M3 steps, all of which are chunks in a single MATLAB script. The organization that follows is theoretical, rather than as-ran.

More generally, the illustration scripts may be modified to change assumptions related to impacts (e.g., correlations, coefficients of variation, distribution form), the PBEE assessment, or the limit state functions and preference system. The scripts were written such that it should be possible to add data for another SFLE system or configuration of interest with minor additional work.

### M0: Decision framing

#### Steps
Open MATLAB and navigate to the main repository folder. Ensure that the `/Data` and `/Figs` folders and subfolders are added to the MATLAB path. Then:

* Open `M2_M3_Main_Run_All.m`; this script is going to be run chunk-by-chunk. Time-consuming chunks will output their progress to the command line.
* Change `SAVE_FIG` to `true` if you would like MATLAB-format .fig files to be saved by the plotting functions. 
* Run **Chunks 2** and **3 **to create empty variables for error encoding and to set plotting controls (e.g., colors used for lateral PP configurations,`colors` ).
* Run **Chunk 4** to define the cell `g`of individual limit state functions using a coefficient matrix, `a`, and create the cell of gradients &nabla;<sub>**X**</sub>**g**:= `grad_g`.

#### Supported modifications 
`M2_M3_Main_Run_All.m`:

* Values in the coefficient matrix, `a` may be altered to reflect different constraints or preferences, or additional linear functions may be added.
* If nonlinear functions are of interest new code will be needed to define `g` and `grad_g`; the symbolic math toolbox will likely be of help.
* Additional random variables may be added, e.g., global warming potential, assuming that distributions are subsequently developed and their parameters are added.


### M1: SFLE (soil-foundation-lateral structure-envelope) system generator

#### Steps
Open R and navigate to the main repository folder. Then:

* Run `M1_SFLE_Generation.R` to:
	1. Create the set, `A` = `S`&times;`F`&times;`L`&times;`E`, which is the cartesian product of the subsystem sets, i.e., `S` = {s<sub>1</sub> = "densification", s<sub>2</sub> = "reinforcement"} and A<sub>1</sub> = (s<sub>1</sub>, f<sub>1</sub>, l<sub>1</sub>, e<sub>1</sub>}. A is stored in matrix format `m.A`.
	2. Create the set &Theta;:=`Theta`={&theta;}<sup>4</sup> of all of the possible performance parameter values for each subsystem. &Theta; is stored in matrix format in `m.Theta`.
	3. Identify the subscript numbers *k* and *&kappa;* associated with examples A<sub>*k,&kappa;*</sub> of interest as defined in `ex.A` and `ex.Theta`.
* Run `M1_hazard_interp.R` to:
	1. Load the USGS-produced json file `haz.File` (defaults to`Charleston.BCboundary.2014DynamicConterm.json`) for the seismic hazard curve.
	2. Interpolate the hazard curve at periods of interest in the M1 assessment as defined by `M1.lateral.systems.RData` and save the interpolated curve to `[haz.File].interp.txt`.
	3. Plot the original USGS points and interpolated surface.
* Run `M1_StructResponse.R` to analyze lateral systems obtained from `Data/M1_Fragility_IDA_Database.xlsx`) and subsequently hard-coded and written to `M1.lateral.systems.txt`. Drift distribution parameters, limit state failure probabilities, and the system failure probabilities are stored in `df.lat` and saved to `M1.lateral.systems.ranked.txt`.


#### Supported modifications

* `M1_SFLE_Generation.R`: 
	* additional subsystems may be added to `S`, `F`, `L`, or `E`.
	* a different discretization may be used for &theta;:=`theta`.
	* a new category of subsystem may be added, e.g., gravity structural or mechanical, with minor adjustments to the code to ensure that `A` contains all values of interest.
* `M1_hazard_interp.R`:
	* A different file `haz.File` in the standard USGS .json format may be provided to perform the M1 assessment at at a different site.
	* Different spectral acceleration periods may be analyzed by altering the `T` column in tab-delimited file `M1.lateral.systems.txt`.
* `M1_Struct_Response.R`:
	* Modify `df.lat` to analyze different data (hard-coded; or the code could be modified to load local data).
	* Change the limit state functions `g1` and `g2` (or add additional functions).
	* Change the preference system formulation or correlation assumed between limit states.

### M2: probabilistic life-cycle performance assessment (earthquake focus)

#### Cloud-based seismic analysis using OpenSees and nonlinear single-degree-of-freedom oscillator
The oscillator uses a hysteretic behavior defined using the Ibarra-Medina-Krawinkler backbone curve. 


##### Steps
Follow the instructions at https://opensees.berkeley.edu/ to download and install OpenSees (alternately, use in the cloud at https://www.designsafe-ci.org. Download and install TCL/TK to run the scripts used to set up the OpenSees analysis. Navigate to the folder containing `Main_Run.tcl`.
* Open `Main_Run.tcl` and modify line 13 to set the `structure` variable as `"Steel"` or `"Concrete"`.
* Source `Main_Run.tcl` to set the monotonic backbone parameters in `Dy_list`, `dc_list`, `du_list`, `Fy_list`, and `Fc_list`. Next, `Main_Run.tcl` will in turn source `Time_History.tcl` to perform the response history analysis of the SDOF system. `Time_History.tcl`:
	1. Reads ground  motions from `/GMfiles` based on `GM_list.tcl`.
	1. Sources `Nonlin_spring.tcl` to creates the nonlinear spring (zero-length element in OpenSees) with the Ibarra-Medina Krawinkler behavior (Clough material in OpenSees) using parameters defined by the user in the `Main_Run.tcl`.
	1. Sources `Analysis_Engine.tcl` to set up the analysis engine by defining required OpenSees and model parameters such as integrator type, analysis test rules, and algorithm.	
	1. Saves the results in `GMresults`, where the maximum value of drift response is recorded in `nonlinSDOF_disp.out`
* Import `nonlinSDOF_disp.out` into MATLAB and save .mat files consistent with the names provided in `M2_M3_Main_Run_All.m`. 

##### Supported modifications

* *SDOFs with different backbone curve parameters*: If the user requires to run the code for different SDOFs, the values in `Dy_list`, `dc_list`, `du_list`, `Fy_list`, `Fc_list` could be changed to match users' input. It should be noted that the displacement and force values should be normalized by building height and weight, respectively to minimize changes to the original code. In case users are only considering one single SDOF, lines 22 to 49 can be removed (except for damping ratio value as defined by `dampRatio` variable ), and the values of the aforementioned parameters can be directly assigned in lines 58 to 62 and limiting the for loop count to only one iteration at line 57.
* *SDOFs with different backbone curve shape*: The Clough material is used in OpenSees to simulate a trilinear backbone curve shape that drops to zero at ultimate displacement. However, other types of nonlinear behavior such as bilinear can be incorporated by changing lines 22-26 in `Nonlin_Spring.tcl`. 
* *Different GM set*: The code is developed to be versatile enough for new GM sets. The user only needs to provide the GM records in the `GMfiles` folder and changes the `Record_List.tcl` file. The `Record_List.tcl` includes two columns of data: the first column is the name of the GM records included in `GMfiles` and the second column provides the scale factors. Care should be given that synthetic GM records used in the paper were provided as single column dat files. Therefore, if a different format of GM records is used (such as the one provided in the PEER NGA dataset), users need to prepare a procedure to format the data as a single column of ground motion acceleration.


#### Performance assessment

##### Steps
After following all steps listed for M0 above, perform the following in `M2_M3_Main_Run_All.m`:

* Run **Chunk 1** to create hard-coded parameters for the analysis, such as the names of the systems analyzed `'conc'` and `'steel'`, initial cost and embodied energy impacts `c_init` and `e_init`, analysis lifetime `Years`, expected lifetime maintenance ratio `ELMR`, marginal cost coefficients for configurations with the beyond-code performance parameters for lateral and envelope subsystems `c_PP_l` and `c_PP_e`, and correlations between drifts (from additional OpenSees analyses), `r_x1_x2`.
* Run **Chunk 5** to loop over structure types and perform M2's performance-based earthquake engineering assessment using the OpenSees nonlinear response history analysis results for the structure of interest  and the subfunction `M2_PBEE_Simple.m`. Intermediate (e.g., fragility curves `fragSs`, conditional losses `EAL_C`) and final results are returned. _Note: this run does NOT include uncertainty in collapse drift limit, rather it is used to compute the drift distributions and to obtain intermediate data such as fragilities and disaggregated losses._
* Run **Chunk 6** to run or load data from sensitivity assessment of collapse probability and loss to collapse drift limit uncertainty. The subfunction `M2_Sensitivity_Collapse_Limit.m` has a long runtime, which is why loading the stored .mat files is advised. The subfunction:
	1. 	 Discretizes the collapse drift limit, using parameters `mu_RD_c` and `sigma_RD_c` defined in **Chunk 1** (`numFac` controls the number of discretizations and defaults to 50 values).
	1. Performs the PBEE assessment at each discretization of collapse drift limit using `M2_PBEE_Simple.m` and convolves the result for ELLR `ELLR_c` and probability of collapse at Sa MCE `P_c`.
	1. Uses MATLAB's `cftool` package to fit a two-peak Gaussian model to the discretized probability of collapse at Sa MCE given collapse drift; the fit objects are stored in cell `P_c_fit`.
	1. Analyses the correlation between X2 and X3 based on `COMPUTE_CORR`:
		* `disc`: uses the discretization of RD<sub>C</sub> and computes the Pearson correlation coefficient between RD<sub>C</sub> and &int;P(C|RD<sub>C</sub>)dF<sub>RD_C</sub>. This approach is stable but indirect, as observations of X2 are not used.
		* `MC`: uses 1-million Monte Carlo simulations for each alternative configuration, computing the percentage of drift observations from `f_RD_Sa_MCE` causing collapse and values  and then obtaining the correlation between that value (`P_c_k`) and the observations of collapse drift limit. This approach tends to produce `NaN` results. The user must also set the value of `COMPUTE_CORR_MC` in `M2_Sensitivity_Collapse_Limit.m` to `true` to repeat the analysis.
		* `load`: loads the rounded values from `drift_collapse_corr.mat`, i.e., `r_x1_x3` (assumed = 0) and `r_x2_x3`. 
	1. Creates plots of the two-peak Gaussian fit, correlations, and ELLR.
* Run **Chunk 7** to create probability distributions for all alternative configurations across random variables `fX` using a combination of data and distribution types hard-coded in **Chunk 1** (e.g., `CV`, `pds`), and results from Chunks 5 (e.g., `f_RD_Sa_DBE`) and 6 (e.g., `ELLR_c`). The implementation required a few error-reducing procedures:
	
	1. A numerical adjustment is applied when the correlation matrix `Rzz` is not positive-definite (is rank-deficient). An eigenvalue analysis identifies the non-positive eigenvalue and a small adjustment is applied to correlations with non-zero values in the associated eigenvector to reduce the correlation. I.e., if the eigenvalue analysis produced value &lambda; <sub>1</sub> = -0.2 and vector **x**<sub>1</sub> = [-0.5, 0.7, 0.5, 0, 0, 0, 0], then the correlations between Z<sub>1</sub>, Z<sub>2</sub>, and Z<sub>3</sub> would be adjusted. E.g., *&rho;*<sub>Z1,Z2</sub> = 0.9 - &epsilon;, *&rho;*<sub>Z1,Z3</sub> = 0 + 0, *&rho;*<sub>Z2,Z3</sub> = -0.7 + &epsilon;, where &epsilon; = 0.001 and is defined in Chunk 2 as `R_adj`. This numerical adjustment is repeated until `Rzz` became positive definite, up to a limit set in Chunk 2, and a record of the configurations requiring adjustment is created in `record_Rzz_err`.
	1. From trial and error, the initial guess `x0` used in M3's application of FORM is hard-coded for problematic configurations to support convergence; similarly, the step size control used in the improved-Hasofer-Lind-Rackwitz-Feissler algorithm `lambda` is set to an appropriate value.
* Run **Chunks 16, 17, 18**, and **19** to create plots.

##### Supported modifications
`M2_M3_Main_Run_All.m`:

* Alter assumptions for initial impacts (`c_init`, `e_init`) or marginal cost to improve performance (`c_PP_l`, `e_PP_l`, `c_PP_e`, `e_PP_e`), or building lifetime `Years`.
* Change the assumed distribution functional forms for the random variables in `pds` and `paramNames`.
* Change the discretization `numFac` or parameters `mu_RD_c` and `sigma_RD_c` associated with collapse drift limits (changing the fit type would occur in `M2_Sensitivity_Collapse_Limit.m`).
* Add new building configurations to `strucs`, i.e., `'BRB'` could be added as a third lateral structural system if all subsequent laterally-related variables are updated (e.g., `c_init` and `r_x1_x2` would get a third column),  and OpenSees data `Sa_BRB.mat` and `EDP_BRB.mat` are added to `/Data` and `M2_M3_Main_Run_All` and `M2_PBEE_Simple.m` are updated accordingly.


### M3: reliability-based ranking and optimization of alternative configurations using a generalized preference system

#### Steps

After following all steps listed for M2 above, perform the following in `M2_M3_Main_Run_All.m`:

* Run **Chunk 8** to analyze the candidate alternative configurations across all limit state functions. 
	* Limit states j&in;{1,2,4,...10} analyzed using `M3_FORM.m`, which:
		* Takes a cell of probability distribution objects for the marginal distributions of **X** (`fX`) and Matlab function objects for limit state function (`g`) and its gradient (`grad_g`), as well as correlation matrix `Rzz`, initial guess vector `x0`, and step size control scalar `lambda`.
		* Assumes a Nataf distribution between random variables
		* Sets tolerance limits for convergence (`eps_1` for |*h*(***u***)|; `eps_2` for *&beta;*<sup>(*k*+1)</sup> - *&beta;*<sup>(*k*)</sup>), a maximum number of iterations `it_max`, and a minimum step size control `lambda_min`.
		* Uses the improved-Hasofer-Lind-Rackwitz-Feissler algorithm to find the design point in standard multivariate normal space, `u_star` and the normal vector for the tangent hyperplane, `alpha`. During each iteration, the step size control `lambda` is automatically reduced if a `NaN` is found in `u(:,k+1)`. A warning is produced and the function returns if the max number of iterations or the minimum size of lambda are violated.
		* Optionally plots the reliability index obtained in each iteration to determine whether convergence has been achieved (controlled by `FLAG_PLOT`)
		* Returns the reliability index `beta_FORM` and other sensitivity results such as `gamma`.
	*  Limit state j=3 is treated differently due to its nonlinear limit state function and propensity for causing non-convergence. 
		*  `g{3}` is upated with the appropriate conditional collapse probability fit, and `grad_g{3}` is evaluated using symbolic differentiation. 
		*  *IF* the probability of collapse obtained in **Chunk 6** is larger than a tolerance set in **Chunk 2** (`pC_min`) *AND* a value in the fit for conditional collapse probability at Sa MCE is larger than the intercept term defined in **Chunk 4** (i.e., for j = 3, a<sub>0</sub> = 0.10), then `M3_FORM.m` is run as usual.
		*  *ELSE*, an alert is displayed, the configuration is recorded in `record_g3_err`, and the following values are set: 
		 
			```matlab
			pf = 0; 
			beta_FORM = 6;
			alpha = -inv(transpose(chol(Rzz)))*Rzz(:,3);
			u_star = [0;6;6;0;0;0;0].
			```
		
* Run **Chunk 9** to set up the cell of cut sets `C` making up the generalized system and estimate the probability of cut set failure `pF_cut1` (a parallel system) using a first-order approximation and the FORM results. Four cut sets are currently used, with only the fourth having multiple limit state functions.
* Run **Chunk 10** to:
	*  Compute the probabilities of the intersections of two, three, and four cut sets (`pF_cut2`,...) using the same first order estimate. As described for **Chunk 7**, adjustments are made to the correlation matrix between limit state surfaces, `R_UU`, if not positive definite and recorded in `record_R_UU_3_err` and `record_R_UU_4_err`. 
	*  Compute series failure probability `pF` across cut sets using the inclusion-exclusion principle (i.e., `pF = pF_cut1- pF_cut2 + pF_cut3 - pF_cut4`).

* Run **Chunk 11** to obtain the ranking of the alternative configurations `alt_rank` according to `pF_rank` and sample results for three hard-coded configurations of interest.
* **Run Chunk 12** to check error diagnostics and save workspace to `Flint_2019_M2_M3_all.mat`
* Run **Chunk 13** to perform a basic sensitivity assessment for three hard-coded configurations of interest, i.e., pull out `pF_ex1`, `R_UU_ex1`, .
* Run **Chunk 15** to create tables used in the manuscript (for input data and M2 and M3 results).
* Run **Chunks 20, 21**, and **22** to create plots of M3 results.

#### Supported modifications:
`M2_M3_Main_Run_All.m`:

* The cut sets may be modified but additional modification will be required in Chunk 10 if there are more than 4 cut sets.
* Change the examples used to create results tables in **Chunk 13**.

## Repository Contents
Scripts are named according to their module of application, M1, M2, or M3. Data (both input and output) is in the `/Data` folder, whereas plots are created in the `/Figs/figs` or `/Figs/eps` folders. The OpenSees structural analysis scripts are in the `/OpenSees` folder, with synthetic ground motions for Charleston in `/OpenSees/GMfiles`.

### Scripts
* `M1_Hazard_Interp.R`
* `M1_SFLE_Generation.R`
* `M1_Struct_Response.R`
* `M2_M3_Main_Run_All.m`
* `M2_PBEE_Simple.m`
* `M2_Plot_Backbones.m`
* `M2_Plot_EDP_IM.m`
* `M2_Plot_Fragility.m`
* `M2_Push2SDOF_concrete_normalized.m`
* `M2_Push2SDOF_steel.m`
* `M2_Sensitivity_Collapse_Limit.m`
* `M3_FORM.m`
* `M3_Plot_Hyperpolygon.m`
* `M3_Plot_pF_bar.R`

### Data
* `4story_concrete.csv`
* `4story_steel.csv`
* `Charleston.BCboundary.2014DynamicCoterm.json`
* `EDP_conc.mat`
* `EDP_steel.mat`
* `Flint_2019_M2_M3_all.mat`
* `M1_Fragility_IDA_Database.xlsx`
* `Sa_conc.mat`
* `Sa_steel.mat`
* `drift_collapse_corr_disc.mat`
* * `drift_collapse_corr_MC.mat`
* `drift_distributions.mat`
* `hazardInfo.mat`

### OpenSees
* `Analysis_Engine.tcl`                                  
* `Main_Run.tcl`
* `Nonlin_Spring.tcl `
* `ReadSMDFile.tcl`
* `Record_List.tcl`
* `Time_History.tcl `
* `/GMfiles/1.dat...80.dat`

## Credits and Sources
* M1: [Haseeb Tahir, MS Thesis (2016), Virginia Tech](http://hdl.handle.net/10919/71794)
* M1:[Seismic, Hurricane, and Tsunami Vulnerability Database and Pinch-Point Taxonomy for Mid-Rise Commercial Buildings Repository](https://doi.org/10.17603/ds2-09nn-ze82)
* M1/M2: [USGS Unified Hazard Tool](https://earthquake.usgs.gov/hazards/interactive/)
* M2: [Charleston, SC hazard and GM package](http://www.magma.geos.vt.edu/vtso/anonftp/scdot/report-FWHA-SC-06-09.pdf)
* M2: special moment-resisting frames from Blume Center Technical Reports: concrete from [Haselton and Deierlein (2007)](http://purl.stanford.edu/ny266sf1883); steel from [Lignos and Krawinkler (2012)](http://purl.stanford.edu/yg701cw5473)
* M3: [Engineering Design Reliability Handbook](http://dx.doi.org/10.1201/9780203483930) Ch. 14 on FORM (Der Kiureghian) and Ch. 15 on systems (Thoft-Christensen)


## License
* Scripts are licensed under [GNU GPL v3.0](https://www.gnu.org/licenses/gpl-3.0.en.html).
* Data under [ODC-By](https://opendatacommons.org/licenses/by/1-0/index.html).
* Other copyrightable material under [CC-BY-NC-SA](https://creativecommons.org/licenses/by-nc-sa/4.0/).

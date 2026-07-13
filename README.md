# capstone
Capstone Project for MS in Data Science on Math &amp; Literacy Growth in Mindsets! Program

# Math & Literacy Growth in the Mindsets!® Math Program

## Project Overview

This capstone project examines how students’ mathematical reasoning, literacy, and engagement developed during participation in a five-week Mindsets!® mathematics program. The program used real-world, entrepreneurship-based challenges intended to strengthen students’ problem-solving, communication, and mathematical reasoning.

The study followed students across three measurement periods:

* **Pre-program**
* **Interim**
* **Post-program**

The primary goal was to investigate how two mathematical practices—abstract reasoning and repeated reasoning—developed over time and how they were related to literacy and program engagement.

## Mathematical Practices

The analysis focused on two Standards for Mathematical Practice:

* **SMP2: Reason abstractly and quantitatively**
  Students interpret quantities, represent situations mathematically, and connect mathematical calculations back to their real-world meaning.

* **SMP8: Look for and express regularity in repeated reasoning**
  Students recognize repeated calculations or structures and use those patterns to develop more general mathematical strategies.

Although these practices are related, SMP2 emphasizes interpreting quantities and context, while SMP8 emphasizes identifying and generalizing patterns.

## Research Questions

The project investigated the following broader questions:

1. Does earlier SMP2 performance predict later SMP8 performance after accounting for students’ previous SMP8 scores, and does SMP8 similarly predict later SMP2?
2. Do SMP2 and SMP8 develop together over the course of the program?
3. Does literacy predict later mathematical reasoning, or does mathematical reasoning predict later literacy?
4. Does student engagement help explain relationships among literacy and mathematical reasoning?
5. Does literacy increase measurably during program participation?

## Data

The study used de-identified student-level data collected at the pre-program, interim, and post-program stages.

### Measures

| Domain                 | Measures                                  |
| ---------------------- | ----------------------------------------- |
| Mathematical reasoning | SMP2 and SMP8 percentages                 |
| Literacy               | Overall literacy percentage               |
| Engagement             | Completion rate and maximum stage reached |
| Time                   | Pre-program, interim, and post-program    |

### Analytic Samples

The available three-wave samples included:

* **107 students** with complete math data
* **241 students** with complete literacy data
* **305 students** with complete engagement data
* **103 students** in the matched three-wave, cross-domain sample

The matched sample included students who had usable data across math, literacy, and engagement measures at all three stages.

## Data Preparation

Major preprocessing steps included:

* Matching student records across the three measurement periods
* Checking duplicate and missing student identifiers
* Standardizing SMP2, SMP8, and literacy scores within each wave
* Retaining completion rate and maximum stage reached as the primary engagement measures
* Examining distributions, missingness, range restriction, and student movement across performance categories
* Creating matched analytic datasets for the longitudinal models

SMP8 scores showed restricted variation during the earlier waves. For this reason, rank-based correlations and transition patterns were also examined alongside traditional correlations.

## Statistical Methods

The project used several forms of structural equation modeling to evaluate longitudinal relationships.

### Cross-Lagged Panel Model

A three-wave cross-lagged panel model was used to test whether earlier SMP2 predicted later SMP8 beyond students’ previous SMP8 performance and whether the reverse pathway was also present.

The model included:

* Autoregressive paths within each construct
* Cross-lagged paths between SMP2 and SMP8
* Within-wave associations
* Pre-program, interim, and post-program measurements

### Latent Growth Curve Models

Latent growth curve models were used to examine average change and individual differences in change over the three program stages.

These models estimated:

* An **intercept**, representing students’ initial status
* A **slope**, representing change across the program
* Variance in initial performance
* Variance in rates of growth
* Relationships between starting performance and subsequent growth

### Tri-Domain Cross-Lagged Panel Model

A larger cross-lagged model included:

* SMP2
* SMP8
* Literacy

This model examined whether earlier literacy predicted later mathematical reasoning and whether earlier mathematical reasoning predicted later literacy.

### Engagement Mediation Model

A mediation model tested whether interim program engagement helped explain longitudinal relationships among literacy and mathematical reasoning.

In this analysis, mediation would mean that earlier academic performance predicted later engagement, which then predicted later academic performance.

### Estimation

The structural equation models were estimated in R using `lavaan`.

Key estimation settings included:

* Robust maximum likelihood estimation (MLR)
* Standardized coefficients for interpretation
* Model evaluation using CFI, TLI, RMSEA, SRMR, and chi-square statistics

The principal modeling environment used:

* R 4.5.2
* `lavaan` 0.6-21

Python notebooks were used for data preparation, exploratory analysis, tables, and visualization.

## Main Findings

### SMP2 and SMP8 Directionality

Earlier SMP2 performance predicted later SMP8 more strongly than earlier SMP8 predicted later SMP2.

The primary standardized estimates were approximately:

* **SMP2 → later SMP8: β = 0.38**
* **SMP8 → later SMP2: β = 0.14**

This pattern suggests that students’ ability to reason abstractly and quantitatively may support their later ability to recognize and generalize repeated mathematical reasoning.

These paths represent longitudinal associations and should not be interpreted as proof of causation.

### Literacy and Mathematical Reasoning

The tri-domain model generally produced larger pathways from earlier literacy to later mathematical reasoning than from earlier mathematical reasoning to later literacy.

Selected standardized estimates included:

| Transition                        | Literacy → Math | Math → Literacy |
| --------------------------------- | --------------: | --------------: |
| Pre → Interim, SMP2 relationship  |            0.53 |            0.11 |
| Pre → Interim, SMP8 relationship  |            0.47 |            0.03 |
| Interim → Post, SMP2 relationship |            0.35 |            0.12 |
| Interim → Post, SMP8 relationship |            0.19 |            0.10 |

These estimates suggest that literacy may provide an important foundation for understanding directions, interpreting mathematical situations, explaining reasoning, and engaging with contextualized mathematics tasks.

The estimates should be interpreted collectively and alongside their uncertainty, statistical significance, and overall model fit.

### Literacy Growth

Literacy scores showed substantial upward movement during the program, particularly between the interim and post-program stages.

The growth model also indicated meaningful differences among students in how much their literacy scores changed. Students did not all begin at the same level or follow the same growth pattern.

A negative association between initial literacy and literacy growth suggested that students who began with higher scores generally had less room to improve, while some students who began lower demonstrated larger gains.

### Engagement

Program engagement was highest during the interim stage, when many students had high completion rates and reached the maximum available stage. Engagement declined somewhat by the post-program measurement.

The engagement mediation model had weak overall model fit, with approximately:

* **CFI: 0.84–0.86**
* **RMSEA: approximately 0.18**

Because the model did not fit the data well, the results did not provide strong evidence that individual engagement explained the longitudinal relationships between literacy and mathematical reasoning.

This does not mean engagement was unimportant. Instead, the available engagement measures may not have captured the particular types of participation, persistence, collaboration, or cognitive effort responsible for differences in student outcomes.

## Interpretation

The project’s central finding is that mathematical practices appear to develop in a meaningful sequence rather than independently.

SMP2 may help students:

* Interpret quantities and relationships
* Move between context and mathematical notation
* Explain what calculations mean
* Evaluate whether an answer makes sense

These abilities may then help students recognize repeated structures and develop the generalized reasoning associated with SMP8.

The literacy findings also reinforce that contextualized mathematics is not separate from reading and communication. Students must understand instructions, identify relevant information, interpret real-world situations, and explain their reasoning. Literacy may therefore function as part of the mathematical problem-solving process rather than only as an outside academic skill.

## Limitations

Several limitations should be considered when interpreting the findings:

* The matched cross-domain sample contained 103 students.
* Students without complete data across all three waves were not included in the matched-panel models.
* The study did not include a comparison or control group.
* The program lasted approximately five weeks.
* Some variables, particularly early SMP8 and interim engagement, had restricted variation.
* Cross-lagged coefficients describe temporal associations but do not establish causal effects.
* The engagement measures captured platform activity rather than every form of behavioral, emotional, social, or cognitive engagement.
* Some structural models had less-than-ideal fit.
* Results come from one program implementation and may not generalize to all schools, grade levels, or instructional settings.


## Author

**Elizabeth**
M.S. Data Science Capstone Project
GitHub: [@mrsroboticguru](https://github.com/mrsroboticguru)

## Acknowledgments

This project was completed as part of a graduate data science capstone.

Special thanks to:

* The faculty and advisors at Boston College who provided statistical and methodological guidance
* The Mindsets! team and project partners
* My cohort peers
* My family

## License

The code and documentation are governed by the license included in this repository.

The project license does not grant permission to redistribute any student-level, proprietary, confidential, or otherwise restricted data used in the analysis.

## Disclaimer

Mindsets!® is the property of its respective owner. This independent academic analysis does not imply endorsement of every interpretation, conclusion, or methodological decision presented in this repository.

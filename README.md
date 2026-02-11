**Response to post-publication critique**: “Does multilingualism really protect against accelerated ageing? Some critical comments” (Jan Vanhove)

---

${\color{red}RED}$


This document constitutes a response to the post-publication commentary by Jan Vanhove on our recently published article in Nature Aging, “Multilingualism protects against accelerated aging in cross-sectional and longitudinal analyses of 27 European countries” (https://www.nature.com/articles/s43587-025-01000-2). The commentary was initially disseminated as a blog post (https://janhove.github.io/posts/2025-12-15-multilingualism-accelerated-ageing/) and subsequently released as a preprint (https://osf.io/preprints/psyarxiv/rmnv9_v1). For clarity and reproducibility, we structure our response around the preprint version, which provides a stable and citable record of the critiques, while also addressing additional points raised in the original blog post.

As detailed below, we (i) acknowledged <u>technical errors and minor reporting inconsistencies and demonstrate that none of these alter the overall results or their interpretation</u>; (ii) clarified why several of the commenter’s <u>critiques are inappropriate or flawed (including altering our analysis by averaging ~86,000 outcomes into 26 means)</u>; and (iii) conducted <u>extensive additional analyses </u> in direct response to specific criticisms, all of which <u>confirm the validity of the original findings</u>. Even when accounting for the identified errors, none of these issues affect the direction, magnitude, statistical significance, or interpretation of the original results. 

Below, we provide a concise synthesis of our responses, followed by detailed point-by-point replies to the post-publication commentary. All analysis code and scripts are made available to ensure full reproducibility. We appreciate the opportunity to address these issues transparently and constructively.

Agustín Ibáñez, Lucia Amoruso, and Hernán Hernández
on behalf of all co-authors.


## SYNTHESIS OF THE MAIN RESPONSES


<u>A) Technical errors and inconsistencies</u>: We recognize one technical error, namely (1) a country label mismatch that unintentionally excluded the Slovakia subsample from downstream epidemiological analyses, and three reporting errors: (2) an incorrect description of the number of predictors in the age model (fourteen reported in the pipeline figure while twelve were used in the original model); (3) a GDP labeling inconsistency (reported as per capita while total GDP was used as a covariate); and (4) six wording inconsistencies when referring to country-level exposures in the Results section (i.e., in specific passages, the expression “individuals speaking one language” was used instead of the correct term “monolingualism”). We fully recognize these issues and implemented re-analyses to assess their impact: 

1) Correcting the country mapping and reintegrating the Slovakia subsample produced equal or stronger associations than the originally reported (**responses 1.2**, **1.12**, and **1.13**).

2) Re-estimating the age model with all fourteen predictors with available data yielded virtually identical model performance, even with top predictors unchanged (**response 1.1**). 

3) Additional adjusted models using both total GDP and GDP per capita produced consistent results (**response 1.13**). 

4) Concerning wording errors, the manuscript makes clear across multiple sections that our multilingualism measure is aggregated, and we propose to correct these terminological errors accordingly (**response 1.6**). 

5) Multiple new analyses in response to specific methodological criticisms demonstrated the robustness of the original results (**responses 1.5**, **1.7**, **1.12**, **1.9**, **1.14**, and **1.11**). 

<u>As reported below, none of these corrections (or commenter’s methodological observations) alter the direction, magnitude, statistical significance, or interpretation of the findings originally reported. </u>



<u>B) Inappropriate and flawed critiques</u>: The commenter’s critiques include repeated methodological misunderstandings, inappropriate modification of the analytical framework, and problematic practices (**responses 1.5**, **1.7**, **1.9**, **1.11**, **1.14**, **2.3**, and **2.4**). These include (1) systematically <u>replacing the prespecified cross-level analytic framework with averaged country-level analyses of the outcomes, collapsing ~86,000 individual observations into 26 means</u>. This change fundamentally redefines the estimand, discards within-country variability, and substantially reduces statistical power, while simultaneously increasing susceptibility to ecological bias—yet nonetheless claiming to rely on the original data and code (**responses 1.14**, **2.3**, and **2.4**). Additional invalid critiques stem from (2) limited familiarity with standard aging-clock methodology (**responses 1.5**, and **4.1–4.4**), (3) misinterpretation of monotonic scaling transformations as affecting inference (**responses 1.7**, and **1.8**), and (4) confusion between complementary versus independent exposure definitions (**response 1.9**). Other objections are further weakened by (5) reliance on a priori but inadequate assumptions (**responses 1.11**, and **2.3**), (6) post hoc exploratory modeling choices (**responses 2.3**, and **2.4**), (7) underpowered regressions (**response 2.3**), and (8) incorrect assumptions about nesting, overdispersion, and calibration (**responses 1.11**, **1.14**, and **2.4**). Importantly, even under these altered analytic choices, the commenter’s own re-analyses reproduce the direction (and in some cases the magnitude) of the original effects (**responses 2.1**, and **2.2**). <u>Together, these critiques rest on flawed assumptions and inconsistencies. We address each point in detail and demonstrate that the central findings remain unchanged, even when evaluated under the reviewer’s alternative assumptions.</u>


## POINT BY POINT RESPONSES

### A. Section 1: Criticisms

#### **Comment 1.1: Missing factors** 
The article suggests that the accelerated ageing variable was derived from fourteen factors, but the data and code indicate that it is based on only twelve factors. 

“The dataset scripts/main/data/data.csv in the project’s repository contains 86,149 observations of 14 variables: the respondents’ country, age, sex, and scores and indicators of the following eleven biobehavioural factors: Education, Barthel, Diabetes, Hypertension, Heart_Disease, Physical_activity, Cognition, Well_being_domain, Sleep_problems, Audition_problems, and Vision_problems. The authors derived what they dubbed biobehavioral age gaps (“BAGs”) from this dataset in the notebook scripts/main_BAGs_computation.ipynb. If you look for the string vars_list in this notebook (12th code block), you will see that these eleven biobehavioural factors as well as the participants’ sex were used as predictors, for a total of twelve factors. However, the article (particularly Figure 1b) suggests that fourteen factors were used to derive the BAGs. The factors unhealthy weight and alcohol consumption are mentioned both in this Figure and in the article’s Methods section, but they are not present in the dataset and were not used when deriving the BAGs.”

${\color{red}**Response 1.1:** We thank the commenter for inspecting the released data and code and for identifying this discrepancy. We acknowledge this reporting error and confirm that the model was trained on twelve predictors, not fourteen, as shown in **Figure 1b** of the pipeline.}$

<span style="color:red;">The discrepancy originates from the reuse of the conceptual framework from our previous Nature Medicine study<sup>1</sup>, where alcohol consumption and unhealthy weight were available in a broader multinational sample. In the present European subsample, these two variables showed extensive missing data across countries and were therefore excluded to preserve sample size and cross-country comparability. The released code and data correctly reflect this twelve-predictor specification, but this aspect was not properly updated in the pipeline figure.</span> 

<span style="color:red;">**Re-analysis with 14 factors (including alcohol consumption and unhealthy weight)**. To evaluate whether exclusion of these two variables affected model performance, we conducted a sensitivity analysis in the European subsample with complete data on alcohol consumption and unhealthy weight (N = 39,639) ([Code-01-BBAGs_computation_extra-vars](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-01-BBAGs_computation_extra-vars.ipynb)). Re-estimating the model in this subsample yielded nearly identical predictive performance and predictor rankings compared to the published model (**Fig. 1**). In both cases, the strongest contributors remained functional ability, hearing impairment, education, hypertension, cognition, and heart disease, whereas alcohol consumption and unhealthy weight did not rank among the dominant predictors. These results indicate excluding these variables does not affect the age-prediction framework or downstream analyses. </span>

![FigureR2R_extra-var_model-comparison_A4](https://hackmd.io/_uploads/B1Mwgwtw-e.png)

<small><em><span style="color:red;">***Figure 1. Comparison of biobehavioral age models with 12 and 14 predictors.** (A) Biobehavioral age model reported in the published manuscript (N = 86,149) without unhealthy weight and alcohol consumption. (B) Extended model including unhealthy weight and alcohol consumption in a subsample with available data (N = 39,639). Across both models, R², F², and MDE remained unchanged, with comparable ranges in RMSE and MAE.*</em></small>



---


#### **Comment 1.2: Missing respondents and countries** 
The article claims that the evidence is based on data from 86,149 respondents in 27 European countries. However, the cross-sectional analyses are based on data from only 84,127 respondents in 26 countries; the longitudinal analyses are based on data from only 81,329 respondents. 

*“The Jupyter notebook main_BAGs_computation.ipynb does not actually output the BAGs. Instead, two new datasets are fed to the second round of analyses. The first of these new datasets is scripts/main/data/BAG_OR_cross.csv. It contains 84,127 observations of 21 variables, most of which contain country-level information. This dataset was used for the cross-sectional analyses carried out in the Jupyter notebook scripts/main/ORs_cross.ipynb. The second is scripts/main/data/BAG_or_long.csv, which contains 81,329 observations of 22 variables and was used for the longitudinal analyses carried out in the Jupyter notebook scripts/main/ORs_long.ipynb. The difference in sample sizes is not commented on anywhere. The difference between 86,149 (data.csv) and 84,127 (BAG_OR_cross.csv) is 2,022, which happens to be exactly the size of the Slovak sample. The supplementary Table 6 does not contain any information about Slovakia, but it does contain information about Serbia, which is not represented in data.csv. It would seem that an output file containing the BAGs was merged with a dataset containing country-level information. Slovakia may have been missing from the latter dataset. Neither the actual BAG computation and output nor the merging is documented in any of the notebooks, though.”*



**Response 1.2:** We thank the commenter for identifying this inconsistency.


<span style="color:red;">The reduced sample size observed in the downstream epidemiological analyses resulted from a country-label mapping error introduced during dataset integration. Specifically, BBAGs were computed using the correct participant-level dataset including Slovakia, whereas the country-level metadata file used for the association models omitted Slovakia and erroneously included Serbia. This mismatch led to the unintended exclusion of the Slovak subsample (N = 2,022) from the cross-sectional and longitudinal analyses. </span>

<span style="color:red;">**Re-analysis with Slovakia.** After correcting the country-label mapping, we re-ran all cross-sectional ([Code-02-cross-with-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-02-cross-with-slovakia.ipynb)) and longitudinal ([Code-03-long-with-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-03-long-with-slovakia.ipynb)) analyses using the full sample (N = 86,149). The updated results show preserved effect direction and statistical significance patterns, with even slightly stronger effect sizes across the main outcomes in both cross-sectional (Table 1) and longitudinal (Table 2) analyses. Thus, results with and without the missing country are comparable, do not invalidate the main findings or conclusions, and rule out any possibility of selective sample exclusion.</span>

<small><em><span style="color:red;">**Table 1. Comparison of cross-sectional odds ratios with and without Slovakia**. Odds ratios (ORs) reported in the original manuscript (excluding Slovakia, N = 84,127) are compared with those recalculated using the full sample including Slovakia (N = 86,149). Effect sizes and directions remain comparable across both samples.</span></em></small>


Reported cross-sectional results

| Predictor              | 95% CI       | OR   | z      | p value   |
| ---------------------- | ------------ | ---- | ------ | --------- |
| Monolingualism         | [1.98, 2.24] | 2.11 | 23.49  | p &lt; 1e-15 |
| 1 additional language  | [0.69, 0.81] | 0.75 | -7.24  | 4.41e-13  |
| 2 additional languages | [0.51, 0.59] | 0.54 | -16.01 | p &lt; 1e-15 |
| 3 additional languages | [0.62, 0.72] | 0.67 | -10.62 | p &lt; 1e-15 |
| Total (≥1 language)    | [0.45, 0.50] | 0.47 | -23.48 | p &lt; 1e-15 |

---

Cross-sectional results with Slovakia

| Predictor                  | 95% CI        | OR   | z      | p value   |
|---------------------------|--------------|------|--------|----------|
| Monolingualism            | [2.14, 2.42] | 2.27 | 25.99  | p &lt; 1e-15 |
| 1 additional language     | [0.76, 0.89] | 0.82 | -4.91  | 8.91e-07 |
| 2 additional languages    | [0.44, 0.51] | 0.48 | -19.72 | p &lt; 1e-15 |
| 3 additional languages    | [0.57, 0.66] | 0.61 | -12.87 | p &lt; 1e-15 |
| Total (≥1 language)       | [0.41, 0.47] | 0.44 | -25.98 | p &lt; 1e-15 |



<small><em><span style="color:red;">**Table 2. Comparison of longitudinal relative risks with and without Slovakia**. Relative risks (RRs) reported in the original manuscript (excluding Slovakia, N = 84,127) are compared with those recalculated using the full sample including Slovakia (N = 86,149). Effect sizes and directions remain comparable across both samples.</span></em></small>


Reported longitudinal results

| Predictor                  | 95% CI        | RR   | z      | p value   |
|---------------------------|--------------|------|--------|----------|
| Monolingualism            | [1.38, 1.48] | 1.43 | 20.36  | p &lt; 1e-15 |
| 1 additional language     | [0.86, 0.94] | 0.90 | -4.87  | 1.14e-06 |
| 2 additional languages    | [0.77, 0.82] | 0.80 | -12.28 | p &lt; 1e-15 |
| 3 additional languages    | [0.68, 0.75] | 0.71 | -13.11 | p &lt; 1e-15 |
| Total (≥1 language)       | [0.68, 0.72] | 0.70 | -20.38 | p &lt; 1e-15 |

---

Longitudinal results with Slovakia

| Predictor                  | 95% CI        | RR   | z      | p value   |
|---------------------------|--------------|------|--------|----------|
| Monolingualism            | [1.42, 1.52] | 1.47 | 22.36  | p &lt; 1e-15 |
| 1 additional language     | [0.90, 0.98] | 0.94 | -2.85  | 0.004    |
| 2 additional languages    | [0.73, 0.79] | 0.76 | -14.67 | p &lt; 1e-15 |
| 3 additional languages    | [0.63, 0.70] | 0.66 | -15.92 | p &lt; 1e-15 |
| Total (≥1 language)       | [0.66, 0.70] | 0.68 | -22.39 | p &lt; 1e-15 |





---


#### **Comment 1.3** 

“*An additional 2,798 observations are missing from BAG_OR_long.csv. I did not investigate this dataset further, and I will ignore the longitudinal analyses in this note.*”

<span style="color:red;">**Response 1.3:** As reported above, analyses including and excluding the Slovakia subsample yield comparable results and do not affect the main findings, ruling out any selective sample exclusion. Separately, missing data in specific covariates were handled as prespecified and do not materially affect the age-prediction framework or downstream analyses. A smaller sample only impacted a sensitivity analysis that included the Structural Equality exposome as an additional covariate. This reduction was caused by a dropna operation applied during the generation of these covariate-adjusted tables in the public GitHub scripts. Structural Equality data were not available for the baseline year (2007) for this subset of participants, leading to their automatic exclusion in this auxiliary analysis only. This issue does not affect the main longitudinal models or any analyses adjusted for other covariates </span>

   

---
 
#### **Comment 1.4: Unjustified causal claims** 

By their own admission in the discussion section, the authors cannot make any causal claims. But the title and abstract contain a bold causal claim. 

“*As the authors correctly point out in their discussion, their observational study does not allow them to establish any causal links between the degree of multilingualism in a country and the extent to which its inhabitants show signs of accelerated ageing. Unfortunately, they do not seem to have kept this insight in mind when they came up with the title (“Multilingualism protects. . . ”) and the abstract (“These results underscore the protective role of multilingualism. . . ”) that grabbed the media’s attention.*”

<span style="color:red;">**Response 1.4:** Our study, as explicitly recognized in the original publication, is observational and does not allow causal inference. The use of terms “protective” or “protects against” to describe associations with reduced risk is standard terminology in observational epidemiology and does not imply causality. This convention is widely used in observational studies reporting OR-, RR-, and HR-based associations<sup>2-5</sup>, group-based ANOVA designs<sup>6,7</sup>, and correlational analyses<sup>8</sup>, without these studies being interpreted as causal.</span>

<span style="color:red;">As also noted by the commenter, our manuscript explicitly states this limitation. In the **Discussion**, we clearly indicate that *“While this approach provides evidence of temporal precedence, it does not establish causality. Proper causal inference would require experimental, quasi-experimental or intervention-based designs, such as randomized controlled trials that explicitly manipulate multilingualism and directly assess its effects on aging clocks.”* We also specify this in the **Abstract** section: *“… country-level multilingualism served as an aggregate exposure …”* and this specific design is highlighted across multiples sections of the manuscript.</span> 

<span style="color:red;">Finally, the argument of attributing media coverage to title wording seems speculative and arbitrary. Identical terminology in article’s titles has been used in bilingualism and aging papers without generating comparable public attention (e.g., <sup>7,9-12</sup>). Moreover, media dissemination is not controlled by the authors and should not be used as a criterion for evaluating scientific framing.</span>

 

---
   
#### **Comment 1.5: Questionable construction of the outcome variable** 

The outcome variable (“BAGs”) is a dichotomised version of a continuous metric. Other aspects of its construction merit scrutiny, too, but will not be dealt with in this note. 

“*The study’s outcome variable was the presence or absence of ‘accelerated aging’. It is useful to spell out how this variable was constructed. First, the authors gathered data on individual ‘biobehavioural’ factors (see data.csv). These are based on self-reports and are fairly coarse. For example, the variable Hypertension is simply the yes/no response to whether a physician has ever told the respondent that their blood pressure was too high. The specific questions can be found in Amoruso et al.’s supplementary materials. Then, they used the dataset to fit a model with the respondents’ age as the outcome variable and all of these biobehavioural factors as predictors. The model itself is gradient boosting, but this is not especially important conceptually. What is important is that the model is able to pick up on nonlinearities and interactions. The model’s hyperparameters were estimated from the data, and a couple of different cross-validation techniques were used. In this note, I will focus on the leave one country out cross-validation, because I consider it the most appropriate. What this means is that 27 models predicting age from biobehavioural factors were fitted, with each leaving out the data from another country. Next, the models fitted were used to predict the age of the inhabitants of the country that was left out when fitting them. For instance, the Belgian respondents’ ages were predicted on the basis of the model fitted to the data from the respondents in the other 26 countries. Then, the authors computed, for each respondent,*

    GAP := predicted age - actual age
    
*that is, the negative model residuals. As the authors correctly point out, though, the predictive model will tend to underestimate the age of the oldest respondents and overestimate the age of the youngest respondents.
To account for this phenomenon, they fitted linear models with GAP as the outcome and the participants’ actual age as the predictor; let’s call the predicted values of this model the predicted GAP values. They then defined*
    
    corrected GAP := GAP - predicted GAP
    
*Finally, the authors defined the variable ‘biobehavioral age gap’ (BAG) as*


    
 
BAG := \begin{cases}
1, & \text{if corrected GAP} > 0, \\
0, & \text{otherwise.}
\end{cases}


    
*To summarise, the BAG values that serve as the outcome variable in the models testing for a multilingualism effect are themselves the dichotomised output of another statistical model whose input, in turn, is the input and the output of yet another statistical model. At the very least, the literal meaning of these BAG values is highly convoluted. Further, I do not see why the corrected GAPs had to be dichotomised in the first place, thereby losing the distinction between a corrected GAP of, say, half a year and one of 12 years. The authors write that these dichotomous variables were created because otherwise no odds ratios (and relative risks) could be computed. But this is hardly a satisfactory justification; it is a bit like scattering dust throughout your living room before vacuum cleaning it as otherwise there would be no dust to get rid of. Lastly, any given respondent’s BAG value does not just depend on this respondent’s biobehavioural data: both the model to compute their raw GAP value as well as the one to compute their corrected GAP value are based on the data from the respondents from all the other countries. Relatedly, about half of the respondents can be expected to have a positive GAP value.*”
    
    
<span style="color:red;">**Response 1.5:** Thank you for raising these points. Here, we respond step by step.</span>

<span style="color:red;">**1. The age-gap framework is not convoluted**. The construction of the outcome variable follows established practice in aging-clock research. The critique apparently reflects a misunderstanding or lack of familiarity with standard aging-clock methodology. The multi-stage procedure used in our study (age prediction → age-bias correction → derivation of age-gap metrics → downstream association analyses) represents a canonical architecture<sup>13-16</sup> adopted across brain, cognitive, epigenetic, and multi-omic aging clocks<sup>14,17-24</sup>. This framework is widely validated for quantifying individual deviations from normative aging trajectories and linking them to clinically relevant outcomes, including disease burden<sup>1,22,25-28</sup>, cognitive decline<sup>23,29,30</sup>, and mortality risk<sup>21,22,31</sup>.</span>

<span style="color:red;">In this context, age gap estimates necessarily depend on the population used for model training, as is the case for all biological-age frameworks<sup>13,14,17,19,24</sup>. This dependence reflects model learning rather than methodological bias and does not invalidate the use of age-gaps as a downstream phenotype. The model first learns population-level aging patterns and then quantifies how much each individual deviates from the expected age given their multivariate profile. Positive age gaps indicate an older-than-expected profile (accelerated aging), whereas negative age gaps indicate a younger-than-expected profile (delayed aging)<sup>14</sup>. The approximately symmetric distribution around zero is an expected property of residual-based aging metrics<sup>13,14,19,32</sup>.</span>

<span style="color:red;">**2. Outcome dichotomization**. Although continuous age gaps retain finer-grained information, discrete classifications derived from outputs are standard<sup>1,18,27,33-37</sup> in applied epidemiology to enable interpretable risk estimation and population-level contrasts (in this case, accelerated vs. non-accelerated aging). Large-scale studies routinely use binary formulations, distribution-based contrasts (e.g., highest vs. lowest quartiles or top vs. bottom 25%), and case–control definitions based on deviation thresholds (e.g., BAG > $\mu$ vs. $\leq \mu$ and BAG $\lt$ $-\mu$ vs. $\geq -\mu$, with $\mu$ ranging from 1 to 5 years)<sup>1,18,27,33-37.</sup>. In this context, dichotomization was a deliberate analytical choice to enable interpretable association testing and OR/RR estimation, not a methodological simplification.</span>

<span style="color:red;">**3. New analyses using continuous BBAG values**. To directly test whether dichotomization influenced the results, we computed Pearson and Spearman correlations between mean continuous BBAGs and country-level monolingualism proportion and generated stratified visualizations across exposure quartiles ([Code-05-Continuous_outcome-removing-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-05-Continuous_outcome.ipynb)).  A consistent positive association between higher monolingualism and greater accelerated aging was observed, with effect direction and magnitude comparable to those obtained in the binary outcome analyses (**Fig. 2**). Thus, the reported associations are not driven by the dichotomization step and remain robust across alternative outcome parameterizations.</span>

![FigureR2R-Continuous-plot](https://hackmd.io/_uploads/BySog_twbe.png)

<small><em><span style="color:red;">**Figure 2. Outcomes analyzed using continuous measures. Left panel**. Pearson and Spearman correlations between mean continuous biobehavioral age gaps (BBAGs) and country-level monolingualism proportion, showing a significant positive association. **Right panel**. Stratified visualization of continuous BBAG values across quartiles of country-level monolingualism, illustrating a monotonic increase in BBAGs with increasing monolingualism exposure.</em></small>
    

---

#### **Comment 1.6: Conflation of country-level and individual multilingualism** 
*The multilingual data that the authors used is situated at the country level, but the authors regularly frame their findings in terms of individual multilingualism*. 

“*The authors use country-level data on multilingualism, namely the estimated percentage of monolinguals in the country (the Mono variable in BAG_OR_cross.csv), the estimated percentage of people in the country who know exactly one additional language (One), those who know exactly two additional languages (Two), and those who know at least three additional languages (Three), always at the time of data collection. Throughout their article, though, they move back and forth between country-level and individual-level interpretations. For instance, they write*

&nbsp;&nbsp;&nbsp;&nbsp; “*In the cross-sectional analysis, monolinguals (that is, those speaking only their mother tongue) were 2.11 times more likely to experience accelerated aging (. . . ).” (p. 2341)*
    
and
    
&nbsp;&nbsp;&nbsp;&nbsp; “*Individuals speaking one additional language were 1.11 less likely to develop accelerated aging (. . . ), those speaking two additional languages were 1.25 times less likely (. . . ), and those speaking three or more additional languages were 1.41 less likely (. . . ).” (p. 2341)*

*In the discussion they point out that their data are situated at the country level, which limits their ability to draw conclusions about individual multilingualism. A cleaner and more consistent choice of wording in the title and throughout the article would have been preferable.*”

<span style="color:red;">**Response 1.6**: We acknowledge the wording errors in the results section (“monolinguals”, “multilinguals”, and “individuals speaking…”). This reflects a semantic error issue and not an analytical problem, as multilingualism is consistently defined and modeled as a country-level exposure throughout the manuscript. This is explicitly stated across all core sections, including:</span>

<span style="color:red;">**Abstract:**</span>

&nbsp;&nbsp;&nbsp;&nbsp; <span style="color:red;">*“… while country-level multilingualism served as an aggregate exposure …”*</span>

<span style="color:red;">**Introduction:**</span>

&nbsp;&nbsp;&nbsp;&nbsp; <span style="color:red;">*“Our approach leverages aggregate-level measures—such as multilingualism and exposome variables—as predictors and covariates of individual-level health outcomes, captured through biobehavioral age gaps (BAGs)”.*</span>

&nbsp;&nbsp;&nbsp;&nbsp; <span style="color:red;">*“Multilingualism was analyzed as an aggregate-level exposure—defined by the country-level percentage of individuals speaking only their mother tongue (monolinguals) or one, two, three or more additional foreign languages—with individual-level BAGs serving as the primary outcome.”*</span>

<span style="color:red;">**Results:**</span>

&nbsp;&nbsp;&nbsp;&nbsp; <span style="color:red;">*“(…) speaking one foreign language were 1.3 times less likely (OR = 0.77, 95% CI: 0.71–0.83), two foreign languages 1.96 times less likely (OR = 0.51, 95% CI: 0.47–0.55), and three or more foreign languages 1.56 times less likely (OR = 0.64, 95% CI: 0.59–0.69).”*</span>

&nbsp;&nbsp;&nbsp;&nbsp; <span style="color:red;">*“In the cross-sectional analysis, speaking three or more foreign languages lost the delayed aging effect after adjustments for immigration status. Similarly, in the longitudinal analysis, speaking one foreign language lost the reduced risk of developing accelerated aging when controlled for gender equality.”*</span>

&nbsp;&nbsp;&nbsp;&nbsp; <span style="color:red;">*“Results indicate that multilingualism is significantly associated with delayed aging, whereas monolingualism is linked to accelerated aging.”*</span>

<span style="color:red;">**Discussion:**</span>

&nbsp;&nbsp;&nbsp;&nbsp; <span style="color:red;">*“We show that multilingualism is associated with reduced BAGs at the population level among healthy individuals and predicts a lower risk of future accelerated aging.”*</span>

&nbsp;&nbsp;&nbsp;&nbsp; <span style="color:red;">*“(…) multilingualism was estimated from country-level data rather than individual-level language metrics, limiting our ability to link variability in specific experiential factors (for example, age of acquisition, proficiency level, amount of code-switching) to aging outcomes.”*</span>

&nbsp;&nbsp;&nbsp;&nbsp; <span style="color:red;">*“By showing that speaking multiple languages can serve as a population-wide protective factor against accelerated aging—despite varying linguistic, physical, social and sociopolitical factors—this study highlights an actionable avenue toward enhancing functional ability and cognitive resilience in aging populations.”*</span>

<span style="color:red;">**Methods:**</span>

&nbsp;&nbsp;&nbsp;&nbsp; <span style="color:red;">*“…we treated multilingualism as an aggregate-level exposure and individual BAGs as the outcome, evaluating whether country-level multilingual profiles were associated with lower (that is, younger) BAG values. Multilingual status was defined as the country-level percentage of monolinguals (those speaking only their mother tongue), individuals speaking one, two, three or more additional languages, and the overall proportion of individuals speaking at least one additional language. Country-level percentages of self-reported language skills were obtained from the European Statistical Office (Eurostat) database.”*</span>
    
 

---
   
#### **Comment 1.7: Meaningless odds ratios** 
The odds ratios reported in Amoruso et al.’s Table 1 are presented without any mention of how the data were coded. A closer look at the Jupyter notebooks reveals that they are essentially meaningless. 

“*Having established that the multilingualism data are situated at the country level, what are we to make of the odds ratio of 2.11 in the claim that monolinguals . . . were 2.11 times more likely to experience accelerated aging” (p. 2341)? The authors’ Python code (ORs_cross.ipynb, fourth and seventh code blocks) shows that they scaled the multilingualism data to a range from 0.05 to 0.95*:

scaler = MinMaxScaler((0.05, 0.95))
X_train_scaled = scaler.fit_transform(X_train)”

<span style="color:red;">**Response 1.7**: Thank you for raising this point. As documented in the analysis code, multilingualism predictors were linearly rescaled to the interval [0.05, 0.95] to improve numerical stability and comparability across exposome variables with heterogeneous scales, consistent with standard preprocessing practices in regression modeling workflows<sup>38-40</sup>; while avoiding boundary values (0 and 1) that can cause convergence and separation issues in logistic models<sup>41</sup>. Apparently, the commentator rests on an incorrect interpretation of the transformation. Being strictly monotonic, the transformation does not affect model fit, effect direction, rank ordering of observations, or statistical inference. It only changes the units in which coefficients and odds ratios are expressed.</span> 

<span style="color:red;">Below we provide additional analyses to demonstrate the adequacy of our approach.</span> 

<span style="color:red;">**Re-analysis of ORs following the suggestion of the commentator induces artificial inflation**. Our scaling choice yields conservative effect estimates. When multilingualism is instead modeled directly as a proportion in the [0–1] range as suggested by the commentator, the estimated odds ratio for monolingualism increases substantially (OR = 3.07; [Code-06-cross-removing-slovakia-proportions-scale](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-06-cross-removing-slovakia-proportions-scale.ipynb)). This difference reflects the baseline at the empirical minimum (0.0286), which inflates contrasts across the full unit interval. We deliberately avoided this parameterization to restrict inference to the observed data range and prevent artificial inflation of effect sizes.</span>

<span style="color:red;">**Re-analysis of robustness under alternative exposure parameterizations**. We re-estimated odds ratios using multiple binary operationalizations of monolingualism based on percentile-based cut-points (low: 5th–25th percentiles; high: 75th–95th percentiles), coding it as 0 if ≤ low_thr and 1 if > high_thr across all possible threshold pairs. Odds ratios were estimated using 10 repetitions per threshold pair, yielding an overall OR of 2.17 [1.78–2.56] based on 1,100 model fits per variable ([Code-07-cross-removing-slovakia-binarization](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-07-cross-removing-slovakia-binarization.ipynb)). This alternative operationalization yielded effect sizes and directions fully consistent with the original analysis. Similar robustness patterns were observed for the remaining linguistic predictors (One, Two, Three, and Total).</span>

![FigureR2R_OR_Binarization](https://hackmd.io/_uploads/HJutVdYPZx.png)


<small><em><span style="color:red;">**Figure 3. Sensitivity analysis across alternative dichotomizations of country-level language exposures.** Odds ratios (ORs) and 95% confidence intervals are shown for each exposure (Monolingualism, 1 additional language, 2 additional languages, 3 additional languages, and Total ≥1 language) under binary splits of the original continuous measure. For each exposure, the “low” group was defined using all thresholds spanning the 5th–25th percentiles and the “high” group using all thresholds spanning the 75th–95th percentiles; ORs were estimated for every low–high pairing within these ranges. For each low–high threshold pair, the estimation was repeated 10 times. Results are displayed for analyses excluding (top) and including (bottom) Slovakia.</span></em></small>
    
   

---
 
#### **Comment 1.8** 
“*The highest percentage of country-level monolingualism in data.csv is 63.2, the lowest was 2.86. So, with 𝑝 the percentage of monolinguals in a given country, the scaled monolingualism variable 𝑠(𝑝) becomes*
    
![imagen_2026-02-11_002331884](https://hackmd.io/_uploads/HJpNUOtvbe.png)

*What the odds ratio of 2.11 for monolingualism means, then, is that the model estimates that the inhabitants of a country with 6,655 monolinguals for every 10,000 inhabitants are 2.11 times more likely to have a BAG value of 1 compared to the inhabitants of a country with negative 49 monolinguals per 10,000 inhabitants. It would have been more sensible to set the baseline at 0% monolinguals or some other sensible value and have the odds ratio refer to a difference in monolingualism of, say, 1 or 10 percentage points.*”
    
<span style="color:red;">**Response 1.8:** Thanks for your comment. Our scaling procedure maps the minimum and maximum observed values of country-level monolingualism (2.86 and 63.2) to the bounds of the scaling interval (0.05 and 0.95). This intentionally restricts inference to the empirical data range and avoids extrapolation to hypothetical countries that are not present in the dataset<sup>42</sup>.</span>

<span style="color:red;">The negative values reported by the commenter (e.g., “−49 monolinguals per 10,000 inhabitants”) arise from applying the inverse transformation to boundary values (0 and 1) that we never used in model fitting. These values reflect artificial extrapolation beyond the observed data range and do not correspond to any population included in our analyses. Contrarily, the reported odds ratios in our study describe contrasts across the empirically observed range of the data.</span> 

<span style="color:red;">Alternative formulations based on fixed percentage-point increments simply change the reporting scale and do not correct any methodological issue, as the estimated ≈12% increase in odds is invariant to the scaling parameterization.</span>

    

---

#### **Comment 1.9:** 
“*The interpretation of the other odds ratios suffers from the same problem. Further, these other odds ratios are not too useful for an additional reason. Consider, for example, the following statement*:
    
&nbsp;&nbsp;&nbsp;&nbsp; “speaking [sic.] one foreign language were 1.3 less likely (. . . ).”(p. 2341)
    
*The highest percentage of speakers of exactly one additional language was 62.08; the lowest was 9.48. The same computation as above shows that this odds ratio has the following interpretation: According to the model, inhabitants of a country with 6,500 speakers of exactly one additional language per 10,000 inhabitants are 1.3 times less likely to show signs of accelerated ageing compared to the inhabitants of a country with only 656 speakers of exactly one additional language per 10,000 inhabitants. Crucially, a country with 6,500 speakers of exactly (not ‘at least’!) one additional language per 10,000 inhabitants is not necessarily more multilingual than a country with only 656 speakers of exactly one additional language per 10,000 inhabitants: In the 2016 data, for instance, Luxembourg only had 16.2% speakers of exactly one additional language compared to, say, Austria’s 49.6%. But Luxembourg had 72% speakers of at least three additional languages compared to Austria’s 13.4%.
The same remark applies to the analyses concerning the percentage of speakers of exactly two additional languages or of speakers of at least three additional languages. Further, the result that “individuals [sic.; the predictor does not capture individual multilingualism, JV] speaking at least one additional foreign language were 2.17 times less likely (. . . ) to experience accelerated aging” (p. 2341) is superfluous: if we already know the odds ratio for the degree of monolingualism, we also know the odds ratio for the degree of multilingualism: it must be the multiplicative inverse. Incidentally, the odds ratio reported in Amoruso et al.’s Table 1 differs slightly from the one in their running text.*”


<span style="color:red;">**Response 1.9**: We want to clarify that our odds ratios reflect associations with distinct, non-interchangeable country-level linguistic exposure dimensions (not a single multilingualism continuum). We also address the complementary interpretation of monolingualism and “at least one language,” and show through proficiency-based reanalyses that the findings are robust across alternative operationalizations of multilingual exposure.

<span style="color:red;">**Our analyses include multiple country-level linguistic exposure variables**:  Monolingualism, one additional language, two additional languages, and three or more additional languages were included, each capturing a distinct dimension of national language structure rather than a single unidimensional “degree of multilingualism”. The Luxembourg–Austria example illustrates this distinction. Luxembourg has a lower proportion of speakers of exactly one additional language than Austria, but a substantially higher proportion of speakers of three or more additional languages. These exposure variables therefore describe different population-level language profiles and are not interchangeable indicators of the same construct. Accordingly, the estimated odds ratios quantify how variation in each specific linguistic dimension relates to accelerated aging, rather than ranking countries along a “more versus less multilingual” continuum.</span>

<span style="color:red;">**Complementarity of exposure measures**: The proportion of speakers of at least one additional language is indeed mathematically complementary to monolingualism and therefore yields reciprocal odds ratios. This variable was included to provide symmetric interpretability and facilitate comparison. In contrast, the remaining linguistic predictors are not complements of monolingualism and capture independent distributional features of national language profiles.</span>

<span style="color:red;">**New analysis (associations generalize across alternative definitions of multilingual exposure)**. To directly assess whether the reported associations depend on a counting-based operationalization of multilingualism, we repeated both cross-sectional ([Code-08-cross-with-slovakia-proficiency](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-08-cross-with-slovakia-proficiency.ipynb)) and longitudinal ([Code-09-long-with-slovakia-proficiency](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-09-long-with-slovakia-proficiency.ipynb)) analyses using country-level foreign-language proficiency as the exposure. As shown in Fig. 4, higher proficiency was associated with lower odds and relative risks of accelerated aging. Thus, the observed associations generalize across alternative definitions of multilingual exposure and are not driven by a specific counting-based metric.</span>
    
![FigureR2R_OR_proficiency-forest-plot](https://hackmd.io/_uploads/r1tVduKwWx.png)

<small><em><span style="color:red;">**Figure 4. Sensitivity analyses using proficiency-based foreign language exposure**. Cross-sectional odds ratio (OR) and longitudinal relative risk (RR) for accelerated aging estimated using country-level foreign-language proficiency as exposure. Error bars indicate 95% confidence intervals. All analyses are reported including (N = 86,149) the Slovakia subsample.</span></em></small>
    
    

---

**Comment 1.10**: 
“*While the article contains quite a few graphs, none shows a data plot for the association between degree of mono/multilingualism versus prevalence of accelerated ageing. In principle, it would have been possible that the actual relationship between these two variables is markedly nonlinear in log-odds space1 <span style="color:red;">[**Commenter’s Footnote 1**</span>: “This turns out not to be the case. But this could not be established by just reading the article and inspecting the code and data.*”]

<span style="color:red;">**Response 1.10:** First, in **Footnote 1**, the commenter states that the proposed nonlinear relationship is indeed not present in our data, self-contradicting the concern raised in his main comment. The claim that this conclusion could not be obtained by inspecting the code and data is incorrect, as the commenter himself derived this result. Second, for transparency, we provide direct data visualizations of the association between country-level mono/multilingualism and the prevalence of accelerated aging (as shown in **response 1.5**). Visual inspection shows a monotonic positive association, with no evidence of pronounced nonlinear patterns (e.g., inflection points or U-shaped relationships). This is further confirmed by the near-identical Pearson (r = 0.58) and Spearman (ρ = 0.58) correlation coefficients, indicating that the association is not driven by nonlinear monotonic structure.</span>

    

---

**Comment 1.11**: 
“*Incidentally, for some reason or other, the notebook ORs_cross.ipynb does not actually fit the logistic regression models that the authors claim to have fitted: They fit log-linear regression models instead (fourth and seventh code blocks):*
    
*model = sm.GLM(y_train, X_train_scaled,
family=sm.families.Binomial(link=sm.families.links.log())).fit()*

*Moreover, for reasons unspecified, the data were split up into a training set and a test set, but the test set was never used for anything (fourth and seventh code blocks):*
    
*X_train, X_test, y_train, y_test = train_test_split(X_ols,
y_ols, test_size=0.2, random_state=42)*

*This is not mentioned anywhere in the article, either.”*

<span style="color:red;">**Response 1.11**: We believe that the commenter may have misunderstood the modeling framework and code, and we clarify below that the correct regression models were used and provide fully documented scripts and additional sensitivity analyses.</span>

<span style="color:red;">**Logistic regression**. Odds ratios in the cross-sectional analyses were estimated using standard logistic regression (logit link), whereas relative risks in the longitudinal analyses were estimated using binomial models with log link, following established practice<sup>43</sup>. We recognize this confusion may arise from the code that was uploaded to GitHub. We have now updated the more detailed scripts used in the manuscript ([Code-10-cross-removing-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-04-long-removing-slovakia.ipynb) and [Code-04-long-removing-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-04-long-removing-slovakia.ipynb)), which reproduce all reported results precisely. Therefore, there is no error in the models used for OR and RR estimation.</span>

<span style="color:red;">**Clarifying misconceptions about train–test splitting and calibration**. Odds ratios are derived from the fitted model parameters estimated on the training data, and do not depend on test-set predictions. The use of a data split avoids fitting the model on the full dataset and therefore constitutes a more stringent estimation strategy<sup>44</sup>. In addition, as we document in the manuscript, we performed model calibration analyses<sup>45</sup>, incorporating the Hosmer-Lemeshow goodness-of-fit test<sup>46</sup> and bootstrapped confidence intervals<sup>47</sup> to evaluate the reliability and robustness of the results. The calibration procedure involved 1,000 iterations.</span>

<span style="color:red;">**Analysis of seed and data-split validity**. To directly address the concern that the reported results depend on a specific random seed or split proportion (e.g., seed = 42, 80/20 split), we conducted a sensitivity analysis varying both parameters. We evaluated three commonly used training proportions (70/30, 80/20, and 90/10) and repeated each configuration across different random seeds (0–100) ([Code-11-cross_and_long-iter-seed-removing-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-11-cross_and_long-iter-seed-removing-slovakia.ipynb)). As shown in **Fig. 5**, the resulting odds ratios and relative risks replicate the results and show minimal variability across seeds and split proportions. This demonstrates that the reported effects are stable and not driven by a particular random-state choice or partition configuration.</span>
    
![FigureR2R_seed_test-size_variation_A4](https://hackmd.io/_uploads/Hk3r9_tw-e.png)

<small><em><span style="color:red;">**Figure 5. Stability of odds ratios and relative risks across random seeds and train–test split proportions.** Cross-sectional odds ratios (ORs, panel A) and longitudinal relative risks (RRs, panel B) estimated using three training-set proportions (70%, 80%, and 90%) and 101 random seeds (0–100). Boxplots summarize the distribution of effect estimates across seeds for each split configuration. Results show minimal variability across both random-state initialization and partition size, indicating that effect estimates are robust to data splitting and seed selection.</span></em></small>
    
 

---
   
#### **Comment 1.12: Insufficient confounder control**
    
Several confounders are controlled for in the analyses—but only one at a time. 

“*The authors write in the abstract that the multilingualism “[e]ffects persisted after adjusting for linguistic, physical, social and sociopolitical exposomes.” This is true but also easily misunderstood: They only controlled for one exposome at a time. Hence, it is possible that the mono/multilingualism variables acted as a proxy for some of the exposomes that weren’t considered in the analysis.*”

<span style="color:red;">**Response 1.12**: Thanks for this observation. We clarify here why the confounder strategy is sufficient.</span>

<span style="color:red;">**1. Broad confounder coverage.** No previous population-level study on multilingualism and aging has incorporated this breadth of macro-level covariates, including linguistic (institutional languages, stable languages, typological distance), social (GDP, gender equality, migration, structural equality), physical (air quality), and sociopolitical indicators (free political parties, inclusive suffrage, credible elections, local democracy), for a total of 12 covariates. This substantially extends confounder coverage relative to prior work.</span>

<span style="color:red;">**2. Combined and single-level adjustments.** Contrary to the commenter’s observation, adjustment was not limited to one covariate at a time. In addition to individual covariate models, we implemented combined adjustment strategies using three composite exposome indices (e.g., total exposome, physical–social exposome, sociopolitical exposome).</span>

<span style="color:red;">**3. Validation of the results with additional adjustment for educational attainment.** We further extended the framework by incorporating country-level educational attainment (Bachelor’s or equivalent and Doctoral or equivalent), which is associated with foreign-language proficiency in European populations<sup>48</sup>. **Fig. 6** ([Code-12-cross-new-covars-removing-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-12-cross-new-covars-removing-slovakia.ipynb), [Code-13-long-new-covars-removing-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-13-long-new-covars-removing-slovakia.ipynb), [Code-14-cross-new-covars-with-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-14-cross-new-covars-with-slovakia.ipynb), and [Code-15-long-new-covars-with-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-15-long-new-covars-with-slovakia.ipynb)) shows that the cross-sectional associations remain statistically significant and preserve the same direction after education adjustment. Educational attainment data were not available at the longitudinal baseline (2007) and therefore could not be included in longitudinal models. </span>

![FigureR2R_OR_Education-controlled](https://hackmd.io/_uploads/BJ_H2OKvZl.png)


    
<small><em><span style="color:red;">**Figure 6.** Sensitivity analysis adjusting for educational attainment. Cross-sectional odds ratios (ORs) for accelerated aging estimated after additional adjustment for country-level educational attainment (Bachelor’s or equivalent and Doctoral or equivalent). Error bars indicate 95% confidence intervals. All analyses are reported both including (N = 86,149) and excluding (N = 84,127) the Slovakia subsample to ensure direct comparability with the originally reported results, yielding in both cases comparable results in terms of effect size and direction. </span></em></small>

    

<span style="color:red;">**4. Confirmation with additional sequential covariate adjustment.** We conducted additional analyses using cumulative sequential adjustment<sup>49-54</sup>, using a deterministic minimal-impact ordering strategy based on change-in-estimate principle<sup>55</sup> ([Code-16-cross-jerquical-removing-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-16-cross-jerquical-removing-slovakia.ipynb) and [Code-17-long-jerquical-removing-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-17-long-jerquical-removing-slovakia.ipynb)). </span>

<span style="color:red;">In the cross-sectional analyses (**Fig. 7**), effect direction and magnitude remained stable, replicating the original results. Monolingualism consistently showed higher odds of accelerated aging, while the “one additional language”, “two additional languages”, and “≥1 language” indicators remained associated with lower odds. Only the “three additional languages” category reversed after inclusion of migration (which is a result originally reported in the paper), and GDP per capita. This effect was also observed with the novel analysis of high-level education. In the longitudinal analyses (**Fig. 8**), associations were highly stable across all adjustment steps. Monolingualism remained positively associated with accelerated aging, whereas all multilingual exposure categories and the total multilingualism indicator remained associated with lower risk, with only minor attenuation after inclusion of high-level socioeconomic covariates and no sign reversals.</span>

<span style="color:red;">These analyses demonstrate that the mono/multilingualism associations are robust to extensive and progressive confounder adjustment across both cross-sectional and longitudinal frameworks.</span>

![FigureR2R_OR_stepwise_A4](https://hackmd.io/_uploads/ryJeCOFvZl.png)



<small><em><span style="color:red;">**Figure 7. Sequential adjustment of cross-sectional odds ratios**. Odds ratios (ORs) for accelerated aging are shown across cumulative sequential adjustment steps for each linguistic exposure variable (Monolingualism, One additional language, Two additional languages, Three additional languages, and Total ≥1 language). Models were estimated using stepwise specifications in which covariates were added incrementally to the base model following a deterministic minimal-impact ordering strategy. Effect direction and magnitude remain stable across most adjustment steps. The only exception is the “three additional languages” category, which attenuates and reverses direction after inclusion of high-level education, migration and GDP per capita. </span></em></small>
    

![FigureR2R_RR_stepwise_A4](https://hackmd.io/_uploads/SJRaa_FPZx.png)
    
<small><em><span style="color:red;">**Figure 8. Sequential adjustment of longitudinal relative risks**. Relative risks (RR) for accelerated aging are shown across cumulative sequential adjustment steps for each linguistic exposure variable (Monolingualism, One additional language, Two additional languages, Three additional languages, and Total ≥1 language). Models were estimated using stepwise specifications in which covariates were added incrementally to the base model following a deterministic minimal-impact ordering strategy. Effect direction and magnitude remain stable across most adjustment steps, except for the “three additional languages” category after inclusion of migration and GDP per capita. </span></em></small>
    
 

---
   
#### **Comment 1.13: GDP incorrectly controlled for** 
The authors claim to have used per capita GDP as a control variable. Their data and code show that they used GDP—not per capita GDP—instead. 

“*The authors write that one of the exposomes taken into consideration was the GDP per capita. However, the GDP variable in BAG_OR_cross.csv ranges from 13.5 billion to about 3.9 trillion, which is several orders of magnitude larger than any plausible per-capita value. Nowhere in their analysis code do they compute the per capita GDP.*”

<span style="color:red;">**Response 1.13:** Thank you for identifying this inconsistency and we acknowledge the labeling error in Figure 1g and in the sensitivity analysis section. We confirm that all analyses in our study used total GDP, as reported in Table 1 (“GDP, gross domestic product”), not GDP per capita. This issue reflects a reporting inconsistency rather than a modeling error, as the variable implemented in the statistical models corresponds to total GDP in both the released code and data files. Correcting this label does not modify the analytical pipeline or the originally reported results. In any case, below we provide evidence that results are consistent with GDP or GDP per capita. </span>

<span style="color:red;">**Sensitivity analysis using GDP per capita**. To directly assess the impact of this alternative operationalization, we re-ran all epidemiological models using GDP per capita instead of total GDP ([Code-12-cross-new-covars-removing-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-12-cross-new-covars-removing-slovakia.ipynb), [Code-13-long-new-covars-removing-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-13-long-new-covars-removing-slovakia.ipynb), [Code-14-cross-new-covars-with-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-14-cross-new-covars-with-slovakia.ipynb), and [Code-15-long-new-covars-with-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-15-long-new-covars-with-slovakia.ipynb)). The resulting estimates remain consistent with the original analyses, with preserved effect directions, comparable effect magnitudes, and no change in overall statistical significance or substantive interpretation. The only exception is the cross-sectional estimate for speaking three additional languages, while all main patterns remain unchanged (**Fig. 9**). These results indicate that the reported associations are robust to the choice of GDP operationalization. </span>

   
![FigureR2R_OR_GDP-comparison](https://hackmd.io/_uploads/B1kjLFKPZg.png)

<small><em><span style="color:red;">**Figure 9. Sensitivity analyses using GDP per capita.** (A). Cross-sectional epidemiological associations estimated after adjusting for total GDP (left panel) and GDP per capita (right panel). (B). Longitudinal epidemiological associations estimated after adjusting for total GDP (left panel) and GDP per capita (right panel). Error bars indicate 95% confidence intervals. All analyses are reported both including (N = 86,149) and excluding (N = 84,127) the Slovakia subsample to ensure direct comparability with the originally reported results. OR, odds ratios; RR, relative risks.</span></em></small>
    
    
    
    

---

#### **Comment 1.14: Insufficient accounting for nesting** 
The nested nature of the data (respondents in cohorts in countries) is not accounted for sufficiently. 

“*The models fitted in ORs_cross.ipynb do not take the nested nature of the data into account: the respondents’ data were collected in different waves in different countries. It is quite plausible that the reported confidence intervals would be considerably wider once this nesting is properly accounted for. Since the predictors in these models are situated at the country level (e.g., country-level multilingualism and GDP), simple data aggregation would be a viable approach.*”

<span style="color:red;">**Response 1.14:** Thank you for raising this point. This critique reflects a misunderstanding of our multilevel design, which intentionally models <u>country-level exposures against individual-level outcomes</u>. Introducing country random effects or aggregating to country means would alter the estimand and reduce power, and permutation-based analyses preserving country structure confirm that the results are robust and not driven by a small subset of countries. Please see the responses step by sept below. </span>

<span style="color:red;">**Two stage model of BBAGs estimation (individual level data) and subsequent multilingualism modulation (aggregate, country-level):** BBAGs are estimated at the individual level using protective/risk factors, and country-level indicators are then introduced as predictors of individual BBAGs<sup>1</sup>. This design directly tests whether cross-national variation in exposure levels is associated with variation in individual aging outcomes.</span>

<span style="color:red;">**Inadequacy of country as random effects:** Because the multilingualism predictors of interest are defined at the country level, including country as a random effect would absorb the between-country variance that the model is explicitly designed to evaluate and would therefore be invalid. Similarly, aggregating individual BBAGs to country-level means, as suggested by the commenter, would change the estimand and the scientific question being addressed. This reduces the effective sample size from ≈86,000 individuals to 26 country-level observations, discard within-country variability, substantially reduce statistical power, and shift the analysis to a purely ecological design. Compared with our cross-level framework, this approach is less informative, less statistically powerful, and more vulnerable to ecological bias, and is therefore not methodologically preferable for addressing the research question of interest<sup>56-58</sup>.</span>

<span style="color:red;">**Analysis of country effects with permutation.** To directly assess whether the observed associations could be driven by a small subset of countries, we performed a within-country permutation test ([Code-18-permutation-test](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-18-permutation-test.ipynb)). The outcome variable (GAP_bin) was permuted within each country, preserving individual-level distributions and country-specific sample sizes while breaking the association with multilingualism. Across 1,000 permutations, the observed coefficients for all linguistic predictors (Mono, One, Two, Three, Total) were more extreme than all permuted estimates (Table 3). This indicates that the reported associations are not driven by a small number of influential countries and remain stable when country-level structure is explicitly preserved.</span>

   
    
    
<small><em><span style="color:red;">**Table 3. Within-country permutation test for cross-sectional associations with accelerated aging.**</span></em></small>
    
| Exposure                 | p-values    |
|--------------------------|------------|
| Monolingualism           | p &lt; 0.001 |
| 1 additional language    | p &lt; 0.001 |
| 2 additional languages   | p &lt; 0.001 |
| 3 additional languages   | p &lt; 0.001 |
| Total (≥1 language)      | p &lt; 0.001 |


                                      
### B. Section 2: Reproduction and reanalysis  
---
                                   
#### **Overall comment:** 
“*I decided to also rerun a few of their analyses and to carry out a few additional ones that may be more sensible. The goal of these latter analyses is to what the association between country-level multilingualism and accelerated ageing is if the data are coded in a more meaningful way and if their nested nature is taken into account.*”

<span style="color:red;">**Response**: Thanks for your analyses. As shown in **Comments 2.1** and **2.2** and in **Tables 1–2** (provided by the commenter), the reproduced estimates closely match those reported in our manuscript, confirming the robustness and reproducibility of our results.

<span style="color:red;">Regarding the additional analyses performed by the commenter (**responses 1.9**, **2.3**, **2.4**, and **2.5**), describing these alternative codings as “more meaningful” reflects a commenter’s opinion rather than the identification of a limitation in our original approach. From a methodological perspective<sup>56-59</sup>, our cross-level framework is preferable to fully aggregated designs, as it preserves individual-level variability, provides substantially higher statistical power, and reduces ecological bias.</span>

<span style="color:red;">In contrast, by collapsing both exposures and outcomes to the country level, the commenter’s approach reduces the analytical sample from ≈86,000 individuals to 26 observations. This redefines the estimand, discards within-country information, substantially lowers statistical power, and increases susceptibility to ecological fallacy<sup>59</sup>.</span>
    
<span style="color:red;">Importantly, despite these methodological differences, the commenter’s additional analyses remain directionally consistent with our findings. Rather than weakening our conclusions, these results provide converging evidence that the association between country-level mono/multilingualism and aging outcomes is robust across alternative model specifications.</span>


---

#### **Comment 2.1: Reproducing the odds ratios** 
“*I first tried to reproduce the first couple of odds ratios reported in the authors’ Table 1, namely those reported for the models without additional covariates. The table caption says that these were estimated using logistic regression models. As mentioned above, however, their Python code (ORs_cross.ipynb) fits log-linear models, not logistic models. The output of log-linear models can still be converted to odds ratios, though. When I run the ORs_cross.ipynb notebook and convert the parameters of the log-linear models fitted in it to odds ratio, I obtain slightly different results from the ones reported in the article, see Table 1. There could be several reasons for the discrepancies between the reported odds ratios and the ones that are computed using their code; I refrain from speculating on them.*”

![comm02](https://hackmd.io/_uploads/SktV2KFwbg.png)


<span style="color:red;">**Response 2.1: Reproduction of baseline odds ratios:** We appreciate the commenter’s diligence in re-running our analyses. The recomputed odds ratios closely match those reported in our study and, in several cases, are slightly stronger. For example, the commenter reports an OR of 2.16 for monolingualism compared to the OR of 2.11 in our manuscript. These minor numerical differences do not affect effect direction, statistical significance, or substantive interpretation and further support the robustness of the reported association.</span>

<span style="color:red;">**The commenter’s analysis does not use fixed random seeds and permutation-based calibration.** Discrepancies are expected when stochastic components are re-estimated without synchronized random seeds. In our pipeline, random seeds were fixed (seed = 42), and permutation-based calibration was applied to stabilize estimates. Fixing random seeds is a good practice for reproducibility in machine learning models<sup>60</sup>, as it enforces deterministic behavior in otherwise stochastic algorithms. As explicitly noted by the commenter, his analyses did not apply these procedures, which explain the small numerical deviations.</span>

<span style="color:red;">In any case, the commenter’s reproduction of similar effect estimates support (rather than undermine) the robustness and reproducibility of our findings. The reproducibility of the results can be corroborated using the scripts [Code-10-cross-removing-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-10-cross-removing-slovakia.ipynb) and [Code-04-long-removing-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-04-long-removing-slovakia.ipynb).</span>


---

#### **Comment 2.2** 
“*Next, let us take a closer look at some of the other results in their Table 1. These concern logistic regression models for which another predictor was taken into account. Because of the issue identified with the GDP variable, I have focused on reproducing the findings for this analysis. As Table 2 shows, the results in the authors’ Table 1 are indeed roughly consistent with the models fitted in ORs_cross.pynb in which raw (as opposed to per capita) was used as a control variable.*”
    
    
![comm03](https://hackmd.io/_uploads/BJ3ATFKw-x.png)

    
<span style="color:red;">**Response 2.2: Reproduction of adjusted models**: We thank the commenter for extending the reproduction analyses with additional covariates. As shown in the commenter’s **Table 2**, once again the recomputed estimates are consistent with those reported in our study and, in some cases, slightly stronger. For example, the commenter reports an OR of 2.20 for monolingualism compared to the OR of 2.16 in our manuscript. These minor numerical differences do not affect effect direction, statistical significance, or substantive interpretation. As indicated in **response 2.1**, these discrepancies are expected when stochastic components are re-estimated without synchronized random seeds or stabilization procedures<sup>60</sup>. </span>

<span style="color:red;">Regarding GDP, the labeling issue and the corresponding sensitivity analyses using both total GDP and GDP per capita are addressed in **response 1.13**.</span>


---

#### **Comment 2.3: Taking nesting and per capita GDP into account** 
“*The dataset BAG_OR_cross.csv, on which the cross-sectional analyses are based, does not specify the country and the wave of data collection to which the respondents belong, nor does it contain any information about the respondents’ age or the corrected GAP value. Only country/cohort level covariates and the binary BAG variable are available; the latter is called GAP_bin in the dataset. There are 97 unique combinations of country- and cohort-level predictors in BAG_OR_cross.csv. Using the information provided in the supplementary materials, I pieced together which of these combinations corresponded to which country and wave of data collection. I also had ChatGPT create a table with the approximate population of each country in each year of data collection, so that per capita GDP values could be computed.
Since the multilingualism and GDP predictors are situated at the country level, I suggest that the nested structure be taken into account by means of aggregation. For simplicity, I calculated the weighted average percentage of monolinguals as well as the weighted average per capita GDP per country across data collection waves. Figure 1 shows how these variables are associated with one another as well as with the proportion of respondents with a BAG value of 1.*”
    
![comm04](https://hackmd.io/_uploads/B1MYCYYwbl.png)

<span style="color:red;">**Clarification:** These are the model results from the commenter’s analyses reported in his blog but not included in the preprint. </span>

<span style="color:red;">**1.	Association between accelerated aging and monolingualism, both at the aggregated level**</span>


![comm05](https://hackmd.io/_uploads/r1Ma0KFwWx.png)

<span style="color:red;">**2.	Association between accelerated aging and monolingualism conditioned on GDP**</span>
    
![comm06](https://hackmd.io/_uploads/Hyx3y15FPWl.png)
    
    
<span style="color:red;">**Response 2.3:** We appreciate the commenter’s diligence in exploring these alternative analyses. <u>Averaging the ≈86,000 individual-level outcomes to 26 country-level measures is an inadequate methodological decision, which explains the differences with our original cross-level framework</u><sup>56-59</sup>. Our approach preserves individual-level variability, provides substantially higher statistical power, and reduces ecological bias. In contrast, the commenter’s model, inadequately redefines the estimand, deletes within-country variability, reduces statistical power, and increases susceptibility to ecological fallacy<sup>59</sup> (see **Overall Response**).</span>

<span style="color:red;">But even with this *particular* approach, the commenter’s results (i.e., descriptive plots  of **Figure 1**) reproduce the same directional patterns: higher national monolingualism is associated with higher prevalence of accelerated aging (β = 0.36, p = 0.0012; adjusted R² = 0.33), whereas higher GDP per capita is associated with lower prevalence of accelerated aging, as previously reported by our group in Nature Medicine studies<sup>1,61</sup>. Notably, GDP per capita and monolingualism show weak coupling, and in the aggregated OLS model including both predictors, monolingualism remains statistically significant (β = 0.29, p = 0.0156), whereas GDP per capita does not (p = 0.16). These results support linguistic exposure as an independent macro-level factor, distinct from and not explained by socioeconomic status.</span>

<span style="color:red;">**Inadequacy of power effects for the analyses performed by the commenter:** The OLS collapsing individual factors into country averages are severely underpowered. With only 26 country-level observations, post-hoc power is low (0.47 assuming f² = 0.15, α = 0.05, one predictor; and 0.36 after inclusion of GDP per capita; calculated using G*Power 3.1.9.7)<sup>62</sup>, limiting reliable statistical inference. In contrast, our framework is well powered. Using standard epidemiological benchmarks for meaningful effects (OR = 1.5–2.0), our sample sizes provide >99% power to detect an OR of 1.8 and >95% power to detect smaller effects (OR = 1.3), with all country subsamples exceeding minimum requirements. Even under these severely underpowered conditions, the aggregated analyses ran by the commenter remain directionally consistent with our main findings.</span>

    

---

#### **Comment 2.4** 
“*Binomial logistic regression models involving these variables suffer from substantial overdispersion, rendering the standard errors and confidence intervals that can be derived from them too optimistic. I therefore fitted quasibinomial logistic models instead. According to a quasibinomial logistic model with the percentage of monolinguals per country as its sole predictor, a country with 19% monolinguals (the sample median) is expected to have about 45% of its respondents show accelerated ageing (odds of about 0.82-to-1). A 10-percentage-point difference in monolingualism between countries is associated with 1.11 times higher odds of accelerated ageing (95% CI: (1.02, 1.19)).
In addition, a quasibinomial logistic model that also contains log-per capita GDP as a predictor expects a country with 19% monolinguals and a per capita GDP of about 26,600 (the sample median) to have about 46% of its respondents show accelerating ageing (odds of about 0.86-to-1). Keeping per capita GDP constant, a 10-percentage-point difference in monolingualism between countries is associated with 1.07 times higher odds of accelerated ageing (95% CI: (0.99, 1.16)).
Alternative model specifications are, of course, possible. Moreover, here I only looked at a single possible confounder (per capita GDP) as I had earlier identified a problem with it. This does not mean that only this confounder should be considered when causal conclusions are to be drawn.*”

    
Code and outputs generated by the commenter for the fully aggregated binomial and quasibinomial models]
    
<span style="color:red;">**1.	Binomial**</span>
![comm07](https://hackmd.io/_uploads/ryiQx9tw-g.png)

    
<span style="color:red;">**2.	Quasibinomia**</span>
 ![comm08](https://hackmd.io/_uploads/SJs4gcYDZe.png)
 
    
<span style="color:red;">**3.	Quasibinomial adjusted by GDP per capita**</span>
![comm09](https://hackmd.io/_uploads/HkUHecKP-g.png)

    
<span style="color:red;">**Response 2.4:** We thank the commenter for exploring alternative outcome averaged models. However, these binomial and quasibinomial specifications depart from our analytical framework and weaken inference by collapsing individual-level data into country-level proportions (see **Overall Response**). This aggregation discards within-country variability and artificially inflates residual variance. The rationale provided by the commenter for this aggregation, namely that within-country variability in monolingualism is negligible (*“The proportion of monolinguals tends to vary fairly little within each country (…). So I’ll simply aggregate the data per country instead.”*), is not supported by the data. As shown in **Fig. 10**, substantial within-country variability is present across multiple countries ([Code-19-Dispersion](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-19-Dispersion.ipynb)). </span>
    

![FigureR2R_dispersion_A4](https://hackmd.io/_uploads/HJfjx9tvbx.png)

<small><em><span style="color:red;">**Figure 10. Variability of monolingualism across countries.** Boxplots display variability for the countries with the large dispersion, highlighting substantial within-country heterogeneity. </span></em></small>
    
    
<span style="color:red;">Consistent with this, the extreme overdispersion observed in the commenter’s models is a direct consequence of this data collapse. The estimated dispersion parameters (83.38 in the unadjusted model and 69.35 after GDP adjustment) are far beyond values considered acceptable<sup>63</sup> and indicate severe model misspecification under the aggregated formulation. Applying a quasibinomial specification does not resolve this issue, as it merely absorbs heterogeneity that is artificially introduced by the aggregation step itself. In contrast, our cross-level framework preserves and models individual-level heterogeneity and avoids the artificial overdispersion induced by fully aggregated designs. Notably, even under the commenter’s aggregated specification, the association between monolingualism and accelerated aging remains statistically significant in the unadjusted analysis and directionally consistent after adjustment.</span>
    
### C. Section 3: Conclusion
    

---

#### **Comment 3.1** 
“*Numerous problems beset Amoruso et al.’s article. The conclusions that feature prominently in the article’s title and abstract are unfounded and should not inform research or policy.*”

<span style="color:red;">**Response 3.1:** We welcome the commenter’s inspection of our data and code and his identification of technical issues, which allowed us to further clarify and strengthen the study in a transparent way. These include: the number of predictors used in the age-prediction model (twelve instead of fourteen), a country-label mismatch (Serbia instead of Slovakia, leading to the unintended exclusion of participants), the labeling of GDP (reported as per capita while total GDP was used), and wording errors (e.g., referring to “monolinguals” or “individuals speaking one language”). As detailed throughout this response, we explicitly acknowledged these errors and implemented the corresponding corrections. Re-estimating the age model with all fourteen predictors yielded virtually identical performance. Correcting the country mapping and reintegrating Slovakia resulted in equal or stronger epidemiological effects. Additional models using both total GDP and GDP per capita produced highly consistent results.  None of these corrections substantially affected the direction, magnitude, or statistical significance of the main findings originally reported, nor the conclusions of the study.</span>

<span style="color:red;">We have provided also responses to some of the commenter's assessments, which rest on methodological misunderstandings and inappropriate re-specification of the prespecified analytic framework. We addressed each issue systematically, including concerns arising from collapsing ~86,000 individual observations into 26 country-level means, misinterpretation of standard aging-clock methods and scaling transformations, confusion between exposure definitions, and incorrect assumptions regarding nesting, power, and calibration. Expected differences were observed when commenter's analyses did not applied fixed random seeding and permutation-based calibration to stabilize estimates. Importantly, even under the commenter's alternative analytic choices, re-analyses reproduced the direction (and in some cases the magnitude) of the original effects, demonstrating that the central findings remain unchanged and robust.</span>

<span style="color:red;">In brief, monolingualism is associated with accelerated aging, whereas multilingualism is associated with delayed aging. Accordingly, the commenter’s claim that the main conclusions of our study are “unfounded” is inadequate.</span>
    

### D. Section 4: Additional criticisms on the aging clock framework raised by the commenter in his personal blog and not included in the Preprint


---

#### **Comment 4.1: Continuous data** 
“*Up till now, I used the values that Amoruso et al. provided in the data.csv dataset. To recall (see Section 2.3), these values are binary indicators of whether the respondent’s predicted age is older than their actual age, after correcting for the overprediction of younger ages and the underprediction of older ages. The predicted ages aren’t actually shared in any of the datasets: Amoruso et al. fit the models predicting age from biobehavioural factors in a couple of scripts, but these don’t contain the code for exporting the predicted ages. So I adapted their Jupyter notebooks in order to compute and export the predicted ages myself.*”

<span style="color:red;">**Response 4.1:** We appreciate these observations. Yet, we want to clarify that, contrary to this assertion, the GitHub code already outputs chronological age, predicted age, BBAG (labeled as GAP in the code), corrected BBAG, and corrected predicted age. These outputs can be exported in standard formats (e.g., CSV, Excel, Parquet) using the same export functions applied by the commenter (e.g., to_csv). The code used by the commenter is essentially the same as the version we provided in our GitHub repository, with the only difference being that the commenter exports the outputs to CSV using the to_csv function, which can be directly applied to the original pipeline.</span> 

<span style="color:red;">To further facilitate reproducibility, we have now added the fully exported datasets, including subject identifiers and all variables required to reproduce the cross-sectional ([Code-10-cross-removing-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-10-cross-removing-slovakia.ipynb)) and longitudinal ([Code-04-long-removing-slovakia](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-04-long-removing-slovakia.ipynb)) analyses, directly to the public repository.</span>


---

#### **Comment 4.2** 
“*I stuck to Amoruso et al.’s approach, even though I’m pretty skeptical about it. Based on their Python code, I wrote my own Python script, compute_bag.py. In it, 26 models are trained using gradient boosting to predict respondents’ age from their biobehavioural factors, always leaving out a different country. I excluded the Slovak data seeing as these did not enter into Amoruso et al.’s analyses. For each model, a hyperparameter search was conducted. The ages for the out-of-fold respondents were then predicted, and their scores computed accordingly. To correct for the overestimation of the ages of the youngest participants and the underestimation of those of the oldest participants, I fitted linear regression models just like in the original to the training data. The corrected scores were computed as in the original. One additional difference to the original is that I didn’t set all the random seeds to 42.*”

<span style="color:red;">**Response 4.2:** The modeling framework used in our study is well established in biological aging research <sup>14,17-24,61 </sup> and its application to biobehavioral age gaps has been previously validated in a large-scale Nature Medicine study<sup>1</sup>. Within this framework, predicted age is estimated from the joint contribution of risk and protective factors known to shape healthy and unhealthy aging trajectories<sup>64-66 </sup>. In addition, the commenter explicitly notes that random seeds were not fixed in his reimplementation. In contrast, all analyses reported in our manuscript used fixed random seeds (seed = 42), following standard best practice<sup>60</sup> to ensure numerical stability and reproducibility of stochastic model components (see **response 2.1**).</span>


---

#### **Comment 4.3** 
“The predicted ages and values are stored in data_predictions.csv. Let’s first reassure ourselves that the model output is comparable to that reported by Amoruso et al. As the scatterplot in Figure 6 shows, the prediction is far from good. Up till age 66, the respondents’ age is overestimated; from then onwards, their age is underestimated.”

![comm10](https://hackmd.io/_uploads/SJ7Lm5YDWx.png)

<span style="color:red;">**Response 4.3:** The reported pattern provided by the commenter reflects a well-documented age-related bias in aging-clock models<sup>13-16,19,32,67</sup>. Predicted age is systematically overestimated in younger individuals and underestimated in older individuals, motivating the application of age correction as a standard practice<sup>13-16,19,32,67</sup>. Accordingly, the figure provided by the commenter should be re-computed using available age-correction procedures rather than the raw model outputs. When this correction is applied, the expected pattern is observed, as shown in **Fig. 11** below ([Code-20-Age-bias–corrected-predicted-age-vs-chronological-age](https://github.com/euroladbrainlat/Biobehavioral-age-gaps-Multilingualism-r2r-git/blob/main/scripts/Code-20-Age-bias%E2%80%93corrected-predicted-age-vs-chronological-age.ipynb)).</span>

<span style="color:red;">In addition, the predictive performance of our model is within the expected range for aging models trained on behavioral variables. The observed MAE and R² values are comparable to those reported in other studies<sup>30,68</sup> and highlight the ability of this framework to extract meaningful aging-related signal from low-cost, scalable, real-world data. </span>
  
    
![FigureR2R_y-vs-ypred-corrected_A4](https://hackmd.io/_uploads/rJJC7qtD-x.png)

<small><em><span style="color:red;">**Figure 11. Age-bias–corrected predicted age versus chronological age.** Boxplots show the distribution of age-corrected predicted age across chronological age. The solid curve represents a generalized additive model (GAM) fit summarizing the central trend across ages. After bias correction, predicted age closely tracks chronological age across the full age range, indicating effective removal of systematic age-dependent prediction bias.</span></em></small>
    

---

#### **Comment 4.4** 
“*Let’s now take a look at the corrected values, Fig. 7. Note that a slight nonlinear trend remains.*” 

<span style="color:red;">**Response 4.4:** We appreciate the commenter’s remark. However, our correction applied in the computation of age gaps is not intended to remove non-linearity, which is minimal in the Figure shown. Rather, the correction is applied to address the well-known regression-to-the-mean bias in aging clock models<sup>13-16,19,32,67</sup>.</span>


---
    
### References
<span style="color:red;"> ESTO LO TENGO QUE PONER DIRECTO EN EL GIT PORQUE SE AGOTARON LOS CARACTERES LIBRES. </span>
    

    

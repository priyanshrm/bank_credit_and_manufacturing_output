# Does Bank Credit Build Factories?

**Evidence from Indian states, 2009-10 to 2024-25**

India's policy for small manufacturers rests on a simple idea: many firms are held back because they cannot borrow, so more bank credit should mean more production. This project tests that idea with data for 33 Indian states and union territories over 15 years.

**Short answer:** once you compare each state with itself over time, **more manufacturing credit is not followed by more manufacturing output.** The effect is also **not larger in states where credit was scarce**. The data rule out anything more than a small positive effect. A 10% rise in credit goes with at most about a 1.2% rise in output.

![Real manufacturing credit and output, India](figures/fig4_2_india_trend.png)

*From 2009-10 to 2024-25, real manufacturing output rose about 2.5 times. Real manufacturing credit rose until 2015-16, fell until 2021-22, and ended only about 1.35 times its starting level. For much of the decade, the two moved in opposite directions.*

---

## The idea in one example

Sita runs a small garment unit in Bihar. She has orders and workers, but her bank will lend her only ₹5 lakh, so she can afford only two sewing machines. If her credit limit doubles, she buys two more machines, and her output rises. Ramesh runs a large auto-parts plant in Maharashtra. He can already borrow as much as he needs, so extra credit lets him refinance an old loan, and his output barely changes.

Two predictions follow:

| | Hypothesis | Meaning |
|---|---|---|
| **H1** | More credit raises output | States like Sita's, where firms are constrained, should produce more when credit grows |
| **H2** | The effect is larger where credit was scarce | One more rupee matters more to Sita than to Ramesh |

### The same idea in one equation

A firm produces with capital $K$ and labour $L$: $Y = A K^{\alpha} L^{1-\alpha}$. A constrained firm can buy only as much capital as its loan allows, so $K \le \lambda \cdot \text{Credit}$. Add up all the firms in a state. If a share $\theta_s$ of the state's output comes from constrained firms like Sita's, the state's output responds to credit with elasticity

$$\frac{\partial \ln Y_s}{\partial \ln \text{Credit}_s} = \alpha\,\theta_s .$$

This one line gives both hypotheses. The effect is positive whenever some firms are constrained (H1). It is larger where more firms are constrained ($\theta_s$ is high), which should be the credit-scarce states (H2). It also shows what a null result means at the state level: either few firms are constrained, or the extra credit is not reaching the ones that are.

---

## The most useful lesson: watch the number shrink

What does the data say if you just ask whether states with more credit produce more? The answer looks like a resounding yes. The rest of the analysis is about why that answer is misleading.

| How the comparison is made | Credit elasticity | What it really compares |
|---|---:|---|
| Pooled regression, no controls | **0.82** \*\*\* | Maharashtra with Mizoram. Big states have more of *everything*. |
| + State fixed effects | 0.26 \* | Each state with its own average. But all states grew together. |
| + Year fixed effects | −0.02 | Each state with itself, after removing India-wide trends |
| + Last year's income per person (**main estimate**) | **−0.075** (wild bootstrap *p* = 0.48) | The same, holding the state's level of development fixed |

A strong "effect" of 0.82 disappears once we stop comparing big states with small ones and good years with bad years. This is a general lesson. Many striking correlations in economics, such as "countries with more banks are richer" or "districts with more roads have more firms", are partly or wholly this kind of size and trend effect.

---

## Results at a glance

| Question | Finding | Verdict |
|---|---|---|
| **H1:** Does credit raise output? | Elasticity −0.075, 95% CI [−0.27, 0.12] | Not supported. Effects above 0.12 are ruled out. |
| **H2:** Is the effect larger where credit was scarce? | Lowest third of states −0.16, highest third +0.11 | Not supported. The point estimates lean the *other* way. |
| Does credit reaching **small borrowers** matter? | Small-ticket credit +0.035, CI [−0.02, 0.09] | Positive in every version, but never significant |
| Does output drive credit instead? | Granger and Dumitrescu-Hurlin tests: no link in either direction | No evidence of reverse causality |

### Stress tests

The main result was challenged in every way I could think of, and reviewers suggested more. None of the checks produced a positive, significant credit effect.

- **Twelve alternative specifications.** These cover longer lags (2 and 3 years), cumulative lags, dropping outliers, small states, or Maharashtra and Delhi, weighting by state size, a different deflator, total instead of manufacturing credit, and a long-difference regression.
- **The 2015 bad-loan clean-up.** Did write-offs of stressed loans hide the effect? Before the clean-up (FY11 to FY15) the estimate is −0.29. After it (FY16 to FY25) it is −0.06, which rules out anything above 0.05. There was no effect before the crisis either.
- **State-specific trends.** Did slow changes inside one state, such as new highways, power capacity or industrial policy, hide the effect? With a separate trend for each state, the estimate becomes −0.15, and the upper confidence limit falls to zero.
- **Small-sample inference.** With only 33 states, ordinary clustered standard errors can make results look significant when they are not. All the headline *p*-values come from a wild cluster bootstrap. One H2 result looked highly significant (\*\*\*) under the usual method and fell to *p* = 0.26 under the bootstrap.
- **Dynamic panel GMM.** System GMM gives a positive estimate (0.22). It is set aside because a key test rejects its extra instruments (difference-in-Hansen *p* = 0.05 to 0.07). It also vanishes with deeper lags, and Difference GMM does not confirm it.

---

## Why might credit not show up in output?

The analysis cannot settle this, but the data point to five explanations:

1. **A loan balance is not new investment.** The data record how much is *outstanding* on 31 March. That includes working capital, rolled-over loans and loans to struggling firms. When a bad loan is written off, credit falls but the factory keeps running.
2. **Most manufacturing credit goes to large firms.** In credit-rich states, only about 10% of manufacturing credit is in small loans. The average loan is ₹61 lakh, against ₹8 lakh in credit-scarce states. Firms that are not constrained ($\theta_s \approx 0$) should not respond to extra credit.
3. **Credit is booked where the bank branch is, not where the factory is.** A firm producing in Gujarat may borrow through a corporate branch in Mumbai.
4. **Credit needs partners.** A loan for a machine helps only if the factory also has reliable power, roads, skilled workers and buyers.
5. **State output data are partly estimated**, which blurs the year-to-year signal.

None of this says credit does not matter for individual firms; firm-level studies in India find that it does. It says that, measured as a stock across whole states, credit growth has not translated into a detectable rise in output.

---

## Data

All data are public and come from the Reserve Bank of India's [Database on Indian Economy (DBIE)](https://dbie.rbihub.in/statistics).

| # | DBIE table | Used for |
|---|---|---|
| 1 | [Bank credit of SCBs – bank group, population group, occupation, district-wise](https://dbie.rbihub.in/statistics?table=financial_sector.r1222_bank_credit_of_scbs_bank_group_population_group_occupatio) (BSR-1) | Manufacturing credit, accounts, limits, small-ticket and grassroots credit. More than two million district-level records. |
| 2 | [Components and economic activity of domestic product – state-wise](https://dbie.rbihub.in/statistics?table=real_sector.comp_eco_act_nsdp_fact_cst_rn) | Manufacturing output (net state value added, constant prices) |
| 3 | [Gross state domestic product](https://dbie.rbihub.in/statistics?table=real_sector.gross_state_dom_prd_rn) | Initial credit depth (credit / GSDP) |
| 4 | [Per capita net state domestic product](https://dbie.rbihub.in/statistics?table=real_sector.per_cap_net_sdp_rn) | Income control and state price deflator |
| 5 | [Loans and advances of SCBs – state and occupation-wise (BSR-1)](https://dbie.rbihub.in/statistics?table=financial_sector.lna_scb_sr_occ_bsr1_a_rn) | Checking the units of the district credit data |
| 6 | [CPI – rural, urban, combined (state-wise)](https://dbie.rbihub.in/statistics?table=real_sector.cpi_ruc_st_rn) | Alternative deflator |
| 7 | [Annual Survey of Industries](https://dbie.rbihub.in/statistics?table=real_sector.ann_surv_inds_rn) | Context on registered factories |
| 8 | [Important banking indicators – regional rural banks](https://dbie.rbihub.in/statistics?table=financial_sector.r331_important_banking_indicators_regional_rural_banks_outstand) | Grassroots lending context |
| 9 | [Self-help group – bank linkage programme](https://dbie.rbihub.in/statistics?table=financial_sector.r338_self_help_group_bank_linkage_programme) | Grassroots lending context |

**Final panel:** 33 states and union territories, FY2009-10 to FY2024-25, with 519 state-years (486 with lagged credit).

**Cleaning decisions worth knowing:**
- Older output series are spliced backwards onto the 2011-12 base.
- Andhra Pradesh enters from 2013-14, after Telangana was carved out, so its territory is the same throughout.
- 34 state-years with implausible jumps are flagged rather than deleted, and tested separately.

---

## Method in plain words

- **Fixed effects.** Compare each state only with itself, and each year only with the national pattern for that year.
- **Lagged credit.** Use last year's credit to explain this year's output, because a machine bought this year produces next year.
- **H2 interaction.** Let the credit effect vary with each state's credit depth in its first year (credit / GSDP). States are also split into thirds by that depth.
- **Small-borrower proxies.** The data do not label firms by size, so two proxies are used:
  - **Small-ticket credit:** loans in cells averaging at most ₹25 lakh per account.
  - **Grassroots credit:** loans from regional rural banks, small finance banks and local area banks, or from rural and semi-urban branches.
- **Honest inference.** Wild cluster bootstrap *p*-values (Rademacher weights, 1,999 replications), with Driscoll-Kraay standard errors as a further check.

**Main equation:**

$$\ln Y_{s,t} = \beta_1 \ln \text{Credit}_{s,t-1} + \gamma \ln y_{s,t-1} + \mu_s + \tau_t + \varepsilon_{s,t}$$

Here $\mu_s$ is the state fixed effect, $\tau_t$ is the year fixed effect, and $y$ is income per person. H1 predicts $\beta_1 > 0$.

---

## Repository layout

```
├── data/              raw DBIE downloads (not tracked) and the cleaned panels
├── notebooks/         the analysis, one step per notebook section (Steps 1–11)
├── figures/           charts used in the paper
├── tables/            regression output as CSV
└── paper/             LaTeX source and PDF (full paper, conference version, extended abstract)
```

| Step | What it does |
|---|---|
| 1–2 | Research question, hypotheses and derivation |
| 3 | Merge the 9 files into `master_dataset.csv`, clean, flag jumps, build `analysis_panel.csv` |
| 4 | Descriptive charts and tables |
| 5 | H1: main regressions and 12 diagnostic checks |
| 6 | H2: interaction, terciles and leverage checks |
| 7 | Small-ticket and grassroots credit |
| 8 | Reverse causality: Granger, Dumitrescu-Hurlin, System and Difference GMM |
| 9 | Robustness: drop Maharashtra and Delhi, growth rates, total credit, drop COVID years |
| 10 | Before vs after the 2015 bad-loan clean-up |
| 11 | State-specific linear and quadratic trends |

## Reproduce

```bash
pip install pandas numpy scipy linearmodels statsmodels matplotlib
```

1. Download the nine tables above from DBIE as CSV and place them in `data/`.
2. Run the notebook cells in order. Each step reads the output of the previous one.

Python 3.10+ is required. The GMM estimator is written from scratch, because the available package does not work with NumPy 2. It was checked by simulation: it recovers the true parameters on artificial data.

---

## Five things this project taught me

1. **A strong correlation can be almost entirely size and trend.** The estimate went from 0.82 to −0.08 without any change in the data, only in what was compared with what.
2. **Read the measurement before the regression.** "Credit" here means a balance on 31 March, not money spent building factories. That one detail shapes how every result should be read.
3. **With few groups, standard errors can mislead.** Thirty-three states is a small number of clusters. A result marked \*\*\* by the usual method was not significant under the bootstrap.
4. **Passing diagnostic tests is not the same as being right.** System GMM passed the usual AR(2) and Hansen tests and still gave an estimate that fell apart under closer checks.
5. **A careful "no" is a result.** Ruling out large effects of credit on output is informative for policy, even though it is not the answer the theory predicted.

---

## Limitations

- **The design rules out large effects, not small ones.** It uses 33 states and 15 years.
- **The small-borrower measures are proxies** for firm size, not firm size itself.
- **Credit outstanding is not new lending.** The data do not report new loans by state and sector.
- **Fixed effects and state trends cannot remove every one-off state-specific shock.**

## Author

**Priyansh**, Ahmedabad University
Questions, corrections and suggestions are welcome via GitHub issues.

If you use this work, please cite:

> Priyansh (2026). *Does Bank Credit Build Factories? Evidence from Indian States, 2009-10 to 2024-25.* Working paper, Ahmedabad University.

# Maternal Mortality: Brazil vs. United States (2000–2023)

Comparative analysis of official World Health Organization data

> Brazil maintained stable maternal mortality for 23 years (67.96→67.0, −1.4%) while the United States increased 35% (12.59→17.0) over the same period, despite spending 20 times more per capita on health.

**Live report:** https://portalf5.github.io/mortalidade-materna-br-us  
**Repository:** https://github.com/portalf5/mortalidade-materna-br-us  
**ORCID:** [0009-0004-6401-3465](https://orcid.org/0009-0004-6401-3465)  
**DOI:** 10.5281/zenodo.XXXXXXX (forthcoming)

---

## Executive Summary

This analysis compares official WHO/UNICEF/UNFPA/World Bank maternal mortality ratio (MMR) data for Brazil and the United States from 2000 to 2023. The data reveals opposite trajectories: Brazil maintained MMR stability at approximately 67-68 deaths per 100,000 live births, while the United States experienced a 35% increase from 12.59 to 17.0 deaths per 100,000 live births.

**Key Metrics:**

| Country | 2000 | 2023 | Change | Trend |
|---------|------|------|--------|-------|
| **Brazil** | 67.96/100k | 67.00/100k | −1.4% | Stability |
| **United States** | 12.59/100k | 17.00/100k | +35.0% | Deterioration |
| **Gap** | 55.4 points | 50.0 points | −5.4 points | Convergence |
| **Ratio (BR/US)** | 5.4x | 3.9x | −1.5x | Narrowing |

---

## Data Sources & Methodology

**Primary Source:**  
WHO/UNICEF/UNFPA/World Bank/UNDESA · Maternal Mortality Estimation Inter-Agency Group (MMEIG)

**Publication:**  
*Trends in maternal mortality 2000 to 2023: estimates by WHO, UNICEF, UNFPA, World Bank Group and UNDESA/Population Division* · Geneva: WHO; 2024  
**ISBN:** 978-92-4-010846-2

**Access Points:**
- Main publication: https://www.who.int/publications/i/item/9789240108462
- IRIS repository: https://iris.who.int/handle/10665/381012
- Full PDF: https://www.unfpa.org/sites/default/files/pub-pdf/9789240108462-eng.pdf
- WHO Global Health Observatory: https://www.who.int/data/gho/data/indicators/indicator-details/GHO/maternal-mortality-ratio-(per-100-000-live-births)

**Data Quality:**
- All values are real annual data published by WHO (no interpolation)
- **Brazil:** 18 years of real annual data (2000–2017) + 3 MMEIG estimates (2019, 2020, 2023)
- **United States:** 14 years of real annual data (2000–2013) + 4 MMEIG estimates (2015, 2019, 2020, 2023)
- **Data gaps:** Brazil (2018, 2021–2022); U.S. (2014, 2016–2018, 2021–2022) — not published by WHO
- Every data point is traceable to WHO Country Profiles (Brazil_BRA_Profiles_EN.pdf and United_States_of_America_USA_Profiles_EN.pdf)

**Operational Definition:**  
Maternal Mortality Ratio (MMR): The number of deaths of women during pregnancy or within 42 days of termination of pregnancy, from any cause related to or aggravated by the pregnancy, expressed per 100,000 live births (ICD-10: O00–O99).

**MMEIG Methodology:**  
The WHO does not publish directly measured maternal mortality data. Instead, it uses the MMEIG methodology developed in collaboration with UNICEF, UNFPA, World Bank, and UNDESA. This approach adjusts estimates for underreporting (particularly in countries with developing vital registration systems) and harmonizes classifications between countries. MMEIG processes data from multiple sources (household surveys, vital records, specialized studies) and produces estimates with confidence intervals.

---

## Data Files

### `dados_mmr.json`
Consolidated dataset containing:
- **series:** Annual MMR values for Brazil (21 data points) and U.S. (18 data points)
- **estatisticas:** Descriptive statistics (initial, final, minimum, maximum, variation %)
- **tendencias:** Linear regression analysis (pre-pandemic and full period)
- **eventos:** Historical milestones in maternal health policy (2000–2020)
- **metadata:** Complete documentation of sources, methodology, and notes

### `coletar_mmr.py`
Reproducible Python pipeline for data collection and analysis.

```bash
pip install pandas numpy scipy
python coletar_mmr.py
# Output: dados_mmr.json
```

---

## Repository Structure

```
mortalidade-materna-br-us/
├── index.html              # Bilingual interactive report (PT/EN)
├── dados_mmr.json          # Consolidated WHO data series (2000–2023)
├── coletar_mmr.py          # Python pipeline (reproducible)
├── README.md               # Full methodology & documentation
├── RELEASE_NOTES.md        # Version history & technical details
├── LICENSE                 # MIT License
└── .nojekyll               # GitHub Pages configuration
```

---

## Key Findings

### Brazil: Stability Despite Policy Shifts
Brazil's MMR remained consistently in the 58–80 deaths per 100,000 range throughout the 23-year period. The lowest point was reached in 2012 (58.63), following implementation of the Rede Cegonha (Stork Network) initiative in 2011. The 2016 Zika virus epidemic produced temporary gestational complications, but the long-term trend remained stable. The 2020 pandemic spike (72.0) reflected global health system stress but was followed by partial recovery to 67.0 by 2023.

**Pre-pandemic trend (2000–2019):** Annual reduction of 0.85 deaths per 100,000 live births per year (p < 0.001, statistically significant).

### United States: Persistent Deterioration
The U.S. experienced continuous increase in MMR from 2000 onward, with acceleration after 2007. The 2020 pandemic produced a dramatic spike to 23.8 (the highest value in the dataset). By 2023, the ratio had partially recovered to 17.0 but remained 35% higher than 2000 baseline.

**Documented causes** include: racial disparities in access to quality care, fragmentation of the healthcare system, increasing comorbidities (hypertension, diabetes) in pregnant populations, and systemic barriers to prenatal care.

### The Paradox: Spending ≠ Outcomes
The U.S. health system expends approximately $12,000 per capita annually, compared to Brazil's $600. Despite a 20-fold difference in per-capita spending, Brazil's system produced superior maternal health outcomes over the period studied. This inverted relationship suggests that universal, prevention-oriented systems may outperform fragmented, procedure-heavy approaches in maternal mortality reduction.

---

## Historical Context

Seven major policy and public health milestones shaped trajectories during 2000–2020:

1. **2000:** UN Millennium Development Goal 5 — reduce maternal mortality by 75% by 2015
2. **2004:** Brazil's National Policy for Comprehensive Women's Health (PNAIGSM) — standardized clinical protocols
3. **2010:** U.S. Affordable Care Act — expanded maternal health coverage
4. **2011:** Brazil's Rede Cegonha (Stork Network) — federal investment in maternity hospitals
5. **2015:** UN Sustainable Development Goal 3.1 — reduce global MMR below 70 by 2030
6. **2016:** Zika virus epidemic in Brazil — temporary gestational complications
7. **2020:** COVID-19 pandemic — pregnant women classified as vulnerable population, health systems overwhelmed

---

## Limitations

1. **Data availability:** Official WHO data for 2021–2022 were not published in the latest update; estimates for earlier years (Brazil 2018, U.S. 2014, 2016–2018) are also missing.
2. **Methodology:** MMEIG estimates use confidence intervals; point estimates represent midpoints and may obscure uncertainty ranges.
3. **Causality:** This analysis documents correlation between policy interventions and outcomes but does not establish causation.
4. **Scope:** Analysis is limited to MMR; other maternal health indicators (morbidity, antenatal care coverage) are not examined.

---

## Suggested Citation

```bibtex
@article{marinho2026,
  title={Opposite Trajectories: Maternal Mortality Trends in Brazil and the United States, 2000–2023},
  author={Marinho, Wederson},
  journal={Portal F5},
  year={2026},
  url={https://portalf5.github.io/mortalidade-materna-br-us},
  doi={10.5281/zenodo.XXXXXXX},
  orcid={0009-0004-6401-3465}
}
```

Or Harvard style:
```
Marinho, W. (2026). Opposite Trajectories: Maternal Mortality Trends in Brazil 
and the United States, 2000–2023. Portal F5. 
https://portalf5.github.io/mortalidade-materna-br-us 
ORCID: 0009-0004-6401-3465 | DOI: 10.5281/zenodo.XXXXXXX
```

---

## License

**Code:** MIT License  
**Data:** Creative Commons Attribution 4.0 (CC-BY-4.0)  
**Original WHO data:** Open Data, WHO

---

## Author

**Wederson Marinho**  
ORCID: [0009-0004-6401-3465](https://orcid.org/0009-0004-6401-3465)  
LinkedIn: [marinhobusiness](https://linkedin.com/in/marinhobusiness)

---

## Disclaimer

This analysis is based on official WHO/UNICEF/UNFPA/World Bank data and publications. 
Interpretation and analysis are the responsibility of the author. The data and code are provided 
"as-is" without warranty of any kind. Users are responsible for independently verifying all claims 
and data before making policy or medical decisions.

---

**Last updated:** April 22, 2026  
**Repository:** https://github.com/portalf5/mortalidade-materna-br-us  
**Status:** v1.0.0 Final Release

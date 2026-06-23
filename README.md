# Green Compliance vs. Productivity Premium: Evaluating the Environmental-TFP Link in Indonesia
Cross-sectional analysis of whether green practice adoption is associated with firm-level Total Factor Productivity (TFP) in Indonesian manufacturing using the IBS 2021 dataset and a two-stage OLS estimation strategy.

---

## Project Overview

This repository contains the code, derived data, and manuscript examining whether eco-friendly practices — using green inputs, producing green goods, or holding environmental certifications such as ISO 14001 — are associated with higher Total Factor Productivity (TFP) among Indonesian manufacturing firms.

Using the **2021 Indonesian Annual Manufacturing Survey (IBS)** from Statistics Indonesia (BPS), we analyse a final sample of **10,573 firms** drawn from 30,788 surveyed establishments across 24 two-digit industries and 34 provinces. Green practices are aggregated into an additive **Green Index** (0–3), constructed from three binary components:

1. **Green input (GREEN)** — uses eco-friendly raw materials (66.0% adoption)
2. **Green output (YGREEN)** — produces eco-friendly goods (61.0% adoption)
3. **Green certification (SNIISO/ECOLAB)** — holds ISO 14001 or an eco-label (25.6% adoption)

**Key Finding:** The Green Index shows no statistically significant association with TFP (coefficient = 0.001, insignificant), whether estimated as a combined index or as individual components, and regardless of whether TFP is measured via gross-output or value-added specification. Productivity is instead robustly driven by **foreign ownership** (DASING: +0.104\*\*), **innovation** (INOV: +0.070\*\*), and **automation/AI adoption** (AUTOAI: +0.090\*\*). This is consistent with a literature suggesting green adoption in Indonesian manufacturing is currently shaped more by regulatory compliance than efficiency-seeking, with transition costs neutralizing short-term productivity gains.

---

## Methodology

This project uses a **two-stage OLS approach**:

**Stage 1 — TFP Estimation:** Gross-output Cobb–Douglas production function estimated by OLS, with log-transformed labour (L), capital (K), and materials (M). TFP is the Solow residual. Estimated elasticities: L = 0.37, K = 0.13, M = 0.61 (returns to scale ≈ 1.11). A value-added specification (labour and capital only) is used as a robustness check.

**Stage 2 — Green-TFP Regression:** OLS regression of estimated ln(TFP) on the Green Index, firm controls, and fixed effects:

```
ln TFP_i = α₀ + α₁ GreenIndex_i + X'_i η + γ_s + δ_p + u_i
```

- **Controls:** Foreign ownership, R&D, innovation, automation/AI
- **Fixed effects:** 2-digit industry (γ_s) and province (δ_p)
- **Standard errors:** Clustered by 2-digit industry (24 clusters)
- **Winsorization:** 1st and 99th percentiles on the log scale
- **Limitation:** Cross-sectional design; results are conditional associations, not causal effects. OLS input elasticities are subject to transmission bias; control-function corrections (Olley-Pakes, Levinsohn-Petrin, ACF) are infeasible without panel data.

---

## Repository Structure

```
├── scripts/          # R or Stata scripts for data cleaning, TFP estimation, and Stage 2 regression
├── paper/            # Manuscript (LaTeX source and PDF)
└── data/             # IBS 2021 firm-level dataset (BPS)
```

---

## Main References

- Ackerberg, D. A., Caves, K., & Frazer, G. (2015). Identification properties of recent production function estimators. *Econometrica*, 83(6), 2411–2451.
- Amiti, M., & Konings, J. (2007). Trade liberalization, intermediate inputs and productivity: Evidence from Indonesia. *American Economic Review*, 97(5), 1611–1638.
- Calì, M., Cantore, N., Iacovone, L., Pereira-López, M., & Presidente, G. (2022). Too much energy: The perverse effect of low fuel prices on firms. *Journal of Environmental Economics and Management*, 111, 102587.
- He, W., Liu, C., Lu, J., & Cao, J. (2015). Impacts of ISO 14001 adoption on firm performance: Evidence from China. *China Economic Review*, 32, 43–56.
- Hendrawan, A. S., & Suhartini, D. (2025). Green innovation pada kinerja perusahaan manufaktur di Indonesia? *Jambura Economic Education Journal*, 7(1), 169–185.
- Olley, G. S., & Pakes, A. (1996). The dynamics of productivity in the telecommunications equipment industry. *Econometrica*, 64(6), 1263–1297.
- Setiawan, N., Soewarno, N., Rahmiati, A., Isnalita, I., & Utama, A. A. G. S. (2026). The impact of green innovation on business performance in the Indonesian automotive industry: The moderating role of environmental regulation. *Measuring Business Excellence*, 1–16.

---

## Author

Kornelius Hasiholan Pardosi

*Faculty of Economics and Business, University of Indonesia*

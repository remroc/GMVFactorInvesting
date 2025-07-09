# GMVFactorInvesting

Portfolio Management project with Prepas Baimbridge students of class 2025 :
- Timothy Boucher
- Gabin Clabe
- Keislan Dow
- Antony Guiougou

After gaining a datacamp certification on portfolio management, we are applying Markowitz theory, Global Minimum Variance portfolio, French-Fama and CVar to build a practical solution that executes orders on MetaTrader5...

More info : 
- on my course given to Guadeloupe's students : www.agialgo.fr
- my linkedin : https://www.linkedin.com/in/rremife/
- video on project :

[![Watch the video](https://github.com/remroc/GMVFactorInvesting/blob/main/video.png)](https://vimeo.com/1094430543)



## 📈 Quick Primer on Core Portfolio-Theory Concepts

### 1. Markowitz Modern Portfolio Theory (MPT)
Harry Markowitz (1952) formalized the idea that **portfolio risk matters more than the risk of any single asset**.  
Key take-aways:

| Idea | Why it matters |
|------|----------------|
| **Mean–Variance Optimisation** | Select weights that *minimise variance* for a given expected return (or maximise return for a given variance). |
| **Diversification Benefit** | Low/negative-correlated assets can reduce overall risk without proportionally reducing return. |
| **Efficient Set** | The collection of portfolios that are not dominated (no other portfolio has both higher expected return *and* lower variance). |

---

### 2. Global Minimum-Variance (GMV) Portfolio & the Efficient Frontier
* **GMV Portfolio** – the single point on the efficient set with the **lowest possible variance**.  
  *Mathematically*:  
  \[
  \min_{\mathbf{w}} \; \mathbf{w}^\top \Sigma \mathbf{w}
  \quad\text{s.t.}\quad
  \mathbf{1}^\top \mathbf{w}=1
  \]
  where \(\Sigma\) is the covariance matrix of asset returns.

* **Efficient Frontier** – the curve traced out by optimal portfolios as the target return varies.  
  *Visual intuition*: everything **below** the curve is sub-optimal, everything **above** is infeasible.

---

### 3. Fama–French Multifactor Models
Extends CAPM by adding systematic factors that explain cross-sectional returns:

| Version | Factors (risk premia) | Interpretation |
|---------|----------------------|----------------|
| **3-Factor (1993)** | Market, Size (SMB), Value (HML) | Small-cap and high book-to-market stocks historically earn extra return. |
| **5-Factor (2015)** | + Profitability (RMW), Investment (CMA) | High-profit, conservative-investment firms command higher returns. |

*Usage*: Regress asset/portfolio excess returns on these factors to measure **factor loadings** (βs) and isolate **alpha**.

---

### 4. Conditional Value-at-Risk (CVaR)
Also called **Expected Shortfall**. Measures *average* loss in the worst-case tail beyond a chosen confidence level \( \alpha \):

\[
\text{CVaR}_\alpha = \mathbb{E}[\,L \mid L \ge \text{VaR}_\alpha\,]
\]

* **Coherent risk metric** – satisfies sub-additivity, so it rewards diversification unlike plain VaR.  
* **Practical reading** – “Given the worst 5 % of scenarios, how big is the *average* loss?”  
* **Optimisation** – can be directly minimised via linear programming, making it popular for downside-risk-focused portfolio design.

---

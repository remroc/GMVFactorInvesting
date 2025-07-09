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
#### 🚀 Efficient Frontier (made simple)

- **Imagine** plotting every possible mix of your chosen assets on a chart:
  - **X-axis** ➜ risk (how much the portfolio’s value wiggles).
  - **Y-axis** ➜ expected return (how much you hope it will grow).

- **Efficient Frontier** = the upper-left curved edge of that cloud of dots.  
  *Why it matters*:  
  * Every point **on** the curve is the best you can do for its level of risk.  
  * Anything **below** the curve is “worse”—same risk but less return.  
  * Anything **above** the curve is impossible with the data you gave it.

- **How do we draw the curve?**  
  1. Pick a target return (say 7 %).  
  2. Find the mix of assets that gives that return with the **least** risk.  
  3. Record its risk & return on the chart.  
  4. Repeat for lots of targets (5 %, 6 %, 8 %, …); connect the dots ➜ frontier.


---

#### 🌱 Global Minimum-Variance (GMV) Portfolio

- The **GMV** point is the **far-left tip** of the frontier.  
  *It’s the single portfolio with the lowest possible risk*, regardless of return.

- **When is GMV useful?**  
  * As a super-diversified “core” holding if you care most about stability.  
  * As a benchmark—if your proposed portfolio is riskier **and** returns less than GMV, it’s clearly inefficient.

![Efficient Frontier](https://github.com/remroc/GMVFactorInvesting/blob/main/GMV.png)

---

**Take-away:**  
1. Feed expected returns & correlations into an optimiser.  
2. The optimiser traces the efficient frontier; the left-most point is GMV.  
3. Choose a spot on the curve that matches your personal risk-comfort level.
ble.

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
Also called **Expected Shortfall**. Measures *average* loss in the worst-case tail beyond a chosen confidence level \( $$\alpha \$$):

$$
CVaR_\alpha = \mathbb{E}[\,L \mid L \ge \text{VaR}_\alpha\,]
$$

* **Coherent risk metric** – satisfies sub-additivity, so it rewards diversification unlike plain VaR.  
* **Practical reading** – “Given the worst 5 % of scenarios, how big is the *average* loss?”  
* **Optimisation** – can be directly minimised via linear programming, making it popular for downside-risk-focused portfolio design.

---

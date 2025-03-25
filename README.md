## 【一】反轉因子（Reversal）

| 因子名稱 | 中文名稱 | 類別 | 衍生方式 | 所需原始欄位 | 計算公式 |
|----------|----------|------|----------|----------------|------------|
| ret_1w | 1週報酬率 | Reversal | 原始值 | 收盤價（前5日） | (P_t / P_{t-5}) - 1 |
| ret_1m | 1個月報酬率 | Reversal | 原始值 | 收盤價（前21日） | (P_t / P_{t-21}) - 1 |
| rev_12m | 12個月反轉 | Reversal | 原始值 | 12M報酬高低點 | -1 × momentum |
| ret_1w_avg12m | 1週報酬12M均 | Reversal | 12M平均 | ret_1w | MA(ret_1w, 12M) |
| ret_1w_z | 1週報酬Z分數 | Reversal | 標準化 | ret_1w 全市場樣本 | (x - μ) / σ |

---

## 【二】價值因子（Value）

| 因子名稱 | 中文名稱 | 類別 | 衍生方式 | 所需原始欄位 | 計算公式 |
|----------|----------|------|----------|----------------|------------|
| pe | 本益比 | Value | 原始值 | 收盤價, EPS | P / EPS |
| pb | 市淨率 | Value | 原始值 | 股價, 每股帳面價值 | P / B |
| bm | 帳面市值比 | Value | 原始值 | 股東權益, 市值 | B / MV |
| div_yield | 股利殖利率 | Value | 原始值 | 每股股利, 股價 | D / P |
| pe_qoq | 本益比季增率 | Value | QoQ | PE 本期與前期 | (PE_t / PE_{t-1}) - 1 |
| pb_z | 市淨率Z分數 | Value | 標準化 | 全市場PB | (PB - μ) / σ |

---

## 【三】規模因子（Size）

| 因子名稱 | 中文名稱 | 類別 | 衍生方式 | 所需原始欄位 | 計算公式 |
|----------|----------|------|----------|----------------|------------|
| mktcap | 市值 | Size | 原始值 | 收盤價 × 股數 | P × Shares |
| total_assets | 資產總額 | Size | 原始值 | 財報總資產欄位 | - |
| mktcap_yoy | 市值年增率 | Size | YoY | 去年與今年市值 | (MV_t / MV_{t-12}) - 1 |
| total_assets_z | 資產Z分數 | Size | 標準化 | 全市場總資產 | (x - μ) / σ |

---

## 【四】動能因子（Momentum）

| 因子名稱 | 中文名稱 | 類別 | 衍生方式 | 所需原始欄位 | 計算公式 |
|----------|----------|------|----------|----------------|------------|
| ret_3m | 3月報酬率 | Momentum | 原始值 | 收盤價（前63日） | (P_t / P_{t-63}) - 1 |
| ret_6m | 6月報酬率 | Momentum | 原始值 | 收盤價（前126日） | (P_t / P_{t-126}) - 1 |
| ret_12m | 12月報酬率 | Momentum | 原始值 | 收盤價（前252日） | (P_t / P_{t-252}) - 1 |
| ret_6m_avg12m | 6M報酬12M均 | Momentum | 12M平均 | ret_6m | MA(ret_6m) |
| rsi_14 | RSI 指標 | Momentum | 原始值 | 收盤價連續14日 | RSI 計算公式 |
| macd_dif | MACD DIF | Momentum | 原始值 | EMA12, EMA26 | EMA_12 - EMA_26 |
| ret_12m_z | 12M報酬Z分數 | Momentum | 標準化 | ret_12m 全樣本 | (x - μ) / σ |

---

## 【五】品質因子（Quality）

| 因子名稱 | 中文名稱 | 類別 | 衍生方式 | 所需原始欄位 | 計算公式 |
|----------|----------|------|----------|----------------|------------|
| roe | 股東權益報酬率 | Quality | 原始值 | 淨利, 股東權益 | NetIncome / Equity |
| roa | 資產報酬率 | Quality | 原始值 | 淨利, 總資產 | NetIncome / Assets |
| de | 負債權益比 | Quality | 原始值 | 總負債, 股東權益 | Debt / Equity |
| gross_margin | 毛利率 | Quality | 原始值 | 毛利, 營收 | GrossProfit / Revenue |
| eps | 每股盈餘 | Quality | 原始值 | 淨利, 股數 | NetIncome / Shares |
| roe_qoq | ROE季增率 | Quality | QoQ | 當期與上期 ROE | (ROE_t / ROE_{t-1}) - 1 |
| eps_z | EPS Z分數 | Quality | 標準化 | EPS 全樣本 | (x - μ) / σ |

---

## 【六】衍生因子（Derived）

| 因子名稱 | 中文名稱 | 類別 | 衍生方式 | 所需原始欄位 | 計算公式 |
|----------|----------|------|----------|----------------|------------|
| ret_std_5 | 報酬率5日標準差 | Risk | 原始值 | 報酬率 | std_5(ret) |
| ret_std_10 | 報酬率10日標準差 | Risk | 原始值 | 報酬率 | std_10(ret) |
| illiq | 流動性指標 | Liquidity | 原始值 | 報酬率, 成交量 | |Return| / Volume |
| asset_growth_yoy | 資產成長率 | Growth | YoY | 當期與一年前資產 | (A_t / A_{t-4}) - 1 |
| turnover | 週轉率 | Volume | 原始值 | 成交量, 流通股 | Vol / Shares |
| ret_ma_5 | 報酬5日均 | Trend | 原始值 | 報酬率 | MA_5(ret) |
| ret_ma_10 | 報酬10日均 | Trend | 原始值 | 報酬率 | MA_10(ret) |
| eps_qoq | EPS 季增率 | Growth | QoQ | EPS 當期與前期 | (EPS_t / EPS_{t-1}) - 1 |

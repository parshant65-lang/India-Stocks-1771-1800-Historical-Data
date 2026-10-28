# India-Stocks-1771-1800-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 1771 to 1800)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-1771-1800-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (1771 to 1800)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 1771 | `NIPPOBATRY` | Indo-National Limited | `NIPPOBATRY.NS` |
| 1772 | `NIRAJ` | Niraj Cement Structurals Limited | `NIRAJ.NS` |
| 1773 | `NIRAJISPAT` | Niraj Ispat Industries Limited | `NIRAJISPAT.NS` |
| 1774 | `NIRLON` | Nirlon Limited | `NIRLON.NS` |
| 1775 | `NITCO` | Nitco Limited | `NITCO.NS` |
| 1776 | `NITINSPIN` | Nitin Spinners Limited | `NITINSPIN.NS` |
| 1777 | `NITIRAJ` | Nitiraj Engineers Limited | `NITIRAJ.NS` |
| 1778 | `NITTAGELA` | Nitta Gelatin India Limited | `NITTAGELA.NS` |
| 1779 | `NITYAS` | Nityas Gems and Jewellery Limited | `NITYAS.NS` |
| 1780 | `NIVABUPA` | Niva Bupa Health Insurance Company Limited | `NIVABUPA.NS` |
| 1781 | `NKIND` | NK Industries Limited | `NKIND.NS` |
| 1782 | `NOCIL` | NOCIL Limited | `NOCIL.NS` |
| 1783 | `NOIDATOLL` | Noida Toll Bridge Company Limited | `NOIDATOLL.NS` |
| 1784 | `NORBTEAEXP` | Norben Tea & Exports Limited | `NORBTEAEXP.NS` |
| 1785 | `NORTHARC` | Northern Arc Capital Limited | `NORTHARC.NS` |
| 1786 | `NOVAAGRI` | Nova Agritech Limited | `NOVAAGRI.NS` |
| 1787 | `NOVARTIND` | Novartis India Limited | `NOVARTIND.NS` |
| 1788 | `NPST` | Network People Services Technologies Limited | `NPST.NS` |
| 1789 | `NRAIL` | N R Agarwal Industries Limited | `NRAIL.NS` |
| 1790 | `NRBBEARING` | NRB Bearing Limited | `NRBBEARING.NS` |
| 1791 | `NRL` | Nupur Recyclers Limited | `NRL.NS` |
| 1792 | `NSIL` | Nalwa Sons Investments Limited | `NSIL.NS` |
| 1793 | `NTCIND` | NTC Industries Limited | `NTCIND.NS` |
| 1794 | `NUCLEUS` | Nucleus Software Exports Limited | `NUCLEUS.NS` |
| 1795 | `NURECA` | Nureca Limited | `NURECA.NS` |
| 1796 | `OAL` | Oriental Aromatics Limited | `OAL.NS` |
| 1797 | `OBCL` | OBCL Limited | `OBCL.NS` |
| 1798 | `OCCLLTD` | OCCL Limited | `OCCLLTD.NS` |
| 1799 | `ODIGMA` | Odigma Consultancy Solutions Limited | `ODIGMA.NS` |
| 1800 | `ODYCORP` | Odyssey Corporation Limited | `ODYCORP.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream NIPPOBATRY 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-1771-1800-Historical-Data/main/NIPPOBATRY/1m/2026/10/NIPPOBATRY_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```

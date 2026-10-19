# Steam Gaming Market Analytics & Interactive Power BI Dashboard

[![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![Python](https://img.shields.io/badge/Python-Analysis-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Processing-150458?logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Clustering-F7931E?logo=scikitlearn&logoColor=white)](https://scikit-learn.org/)
[![License](https://img.shields.io/badge/License-Not%20specified-lightgrey)](#license)
[![HCMUS](https://img.shields.io/badge/HCMUS-Data%20Visualization-0054A6)](https://www.hcmus.edu.vn/)

An interactive Power BI analysis of Steam's game market, combining release, genre, publisher, review, engagement, and hardware-requirement perspectives. The project examines a representative sample of 290 games alongside review and company-level data, and uses K-Means segmentation to describe distinct player-engagement profiles. Its findings are intended to help developers and publishers reason about market entry, launch timing, portfolio strategy, and player satisfaction.

> **Project:** Data Visualization, Lab 3 — University of Science, Vietnam National University Ho Chi Minh City (HCMUS)  
> **Dashboard:** [`Dashboard.pbix`](./Dashboard.pbix) · **Report:** [`DV_Lab3_Eng.pdf`](./DV_Lab3_Eng.pdf)

## 🎯 Executive Summary & Business Value

Steam is a large, competitive marketplace where release volume, visibility, player engagement, and user satisfaction do not necessarily move together. This project brings those signals into a four-page interactive dashboard covering market activity from 2004 to 2024 and a dataset of 290 representative games, 205 developers, 168 publishers, and more than 990,000 user reviews.

The dashboard is designed to support practical questions such as:

- **Market entry:** How has game supply changed over time, and which genres or categories are prominent?
- **Release planning:** How does engagement vary by release timing, and what launch windows may be worth considering?
- **Portfolio strategy:** How do publisher and developer volume relate to player approval? How do indie and non-indie titles compare?
- **Player retention and product quality:** When do negative reviews occur, how helpful are reviews, and which engagement profiles appear in the market?
- **Hardware positioning:** What PC requirements are typical in the analyzed sample?

Use these findings as directional evidence for planning and further investigation, rather than as causal claims or guarantees of commercial performance.

## 📊 Dashboard Preview & Key Features

The report describes four interactive dashboard pages addressing 13 structured market and business research objectives. The page themes below summarize that coverage; they are descriptive groupings, not claimed verbatim tab names.

| Dashboard area | KPI and analysis focus |
| --- | --- |
| **Market supply, demand & release trends** | Game-market activity across 2004–2024, supply-versus-demand signals, and release timing/seasonality. |
| **Genre composition & category trends** | Genre/category shares and trends, including Sports/Racing and Strategy composition. |
| **Publisher, developer & portfolio performance** | Company title volume and user approval, plus indie/non-indie rating comparisons. |
| **Reviews, engagement & player segments** | Review volume, positive/negative feedback, helpfulness, playtime, the first-two-hour window, and the three K-Means segments. |

The Power BI experience is described as interactive, with slicers and cross-filtering to explore relevant subsets and relationships. The report/dashboard materials use these visual types:

| Visual | Analytical use |
| --- | --- |
| **Waterfall** | Shows how component values contribute to a change or total. |
| **Donut** | Shows category composition and share. |
| **Stacked Bar** | Compares category composition across groups. |
| **Scatter Plot** | Explores relationships between two measures. |
| **Treemap** | Shows hierarchical/category proportions. |
| **Radar Chart** | Compares multi-measure profiles. |

> **Preview availability:** No dashboard image exports or demo video are included in the current workspace. Open the `.pbix` file in Power BI Desktop to interact with the report.

## ⚙️ Data Pipeline & Methodology

### Dataset scope

The analysis covers:

- **290** top representative Steam games
- **205** developers and **168** publishers
- **990,000+** user reviews
- Release and review patterns spanning **2004–2024**
- Game hardware requirements, with typical analyzed requirements around **4–8 GB RAM** and **50 GB storage**

The raw data files are not separately included in this repository snapshot. The figures above describe the analysis reported in the project materials.

### Preparation and modeling

1. **Data cleaning and preprocessing:** Python/Pandas and Power Query are used to prepare the data for analysis and dashboard use.
2. **Data modeling:** The prepared data is organized for connected exploration across games, release attributes, companies, reviews, and engagement.
3. **Measures and visuals:** DAX measures support dashboard KPIs and comparisons. Interactive report visuals and slicers let users investigate the reported market questions.
4. **Player segmentation:** A K-Means model with **k = 3** is described as implemented through the Power Query/Python workflow. The clustering uses playtime, total reviews, positive-review rates, and community-feedback metrics. The reported segment names are:
   - **Hardcore**
   - **Casual/Mass**
   - **Story/Short Experience**

The clustering is an exploratory segmentation of the analyzed sample; it should not be interpreted as a definitive taxonomy of all Steam players.

## 💡 Key Market Insights & Findings

| Finding | Reported metric or observation | Strategic implication |
| --- | --- | --- |
| **Indie advantage** | Indie titles have an **85.65%** positive rating, compared with **74.99%** for non-indie titles. | Independent status alone does not preclude strong player approval; product quality and audience fit warrant attention alongside scale. |
| **Quality over quantity** | Valve leads in user approval at **87.19%**, despite lower title volume than EA/Sega. | A larger catalog does not automatically translate into higher satisfaction. |
| **Language localization** | The report finds that a higher non-English review ratio does **not** negatively impact game success in the analyzed data. | Core gameplay quality can transcend language barriers; localization should be evaluated alongside audience and product context. |
| **First two hours matter** | Approximately **65%** of negative reviews occur within the **<2-hour** play window. | The early player experience is a critical product-quality and retention checkpoint; the finding also overlaps with Steam's refund window. |
| **Revenue and satisfaction are different signals** | Top-revenue games are not necessarily the top-rated or most reviewed games. The top-reviewed group has approximately **420 hours** average playtime. | Separate commercial performance, approval, review volume, and depth of engagement when evaluating success. |
| **Genre composition** | Sports/Racing accounts for approximately **25.17%**; Strategy accounts for approximately **20.69%** in the reported genre composition. | Genre share offers market context, but a large category should not be assumed to be an easier opportunity. |
| **Seasonality** | August and December are reported as peak engagement periods, at approximately **336K average reviews per game**. | Consider seasonal audience activity when planning launch and promotion timing; validate the measure and its aggregation in the report before using it operationally. |
| **Smaller-studio timing** | February, April, and October are identified as strategic launch windows for indie/small studios; the report also discusses summer-window dynamics. | These are suggested timing opportunities from the analysis, not guaranteed low-competition or high-sales periods. |
| **Hardware profile** | Typical player requirements are reported as **4–8 GB RAM** and approximately **50 GB storage**. | Use the analyzed hardware profile as a broad reference when considering accessibility and minimum/recommended specifications. |

> Metrics and interpretations above are reproduced from the project details and report summary available for this repository. Values described as approximate retain that qualification.

## 🛠️ Tech Stack

| Category | Tools |
| --- | --- |
| Business intelligence | Power BI Desktop |
| Data preparation | Power Query Editor |
| Measures and calculations | DAX |
| Data analysis | Python, Pandas |
| Machine learning | Scikit-learn (K-Means clustering) |
| Documentation | LaTeX-authored English PDF report |
| Demo | Video demo is mentioned in the project brief but is not included in this workspace |

## 🗂️ Project Structure

```text
Steam-Gaming-Analytics/
├── Dashboard.pbix       # Interactive Power BI dashboard
├── DV_Lab3_Eng.pdf      # English project report
└── README.md            # Project overview and findings
```

**Data files, dashboard image exports, and demo media are not present in the current repository snapshot.** They are therefore not shown as existing folders or linked resources above.

## 🚀 How to Explore / Reproduce

### Explore the dashboard

1. Install **Power BI Desktop**.
2. Download or clone this repository.
3. Open [`Dashboard.pbix`](./Dashboard.pbix) in Power BI Desktop.
4. Use the report pages, slicers, and cross-filtering to explore the analyses.

The raw data files are not included separately here. If Power BI requests a source file or credentials when opening or refreshing the report, access to the original data source is required; the dashboard can only be refreshed when that source is available.

### Read the report

Open [`DV_Lab3_Eng.pdf`](./DV_Lab3_Eng.pdf) for the written project report, methodology, and analysis.

### Demo video

No demo-video file or URL was present in the workspace at the time this README was prepared.

## 👥 Contributors & Acknowledgments

**Course:** Data Visualization (23KHDL)  
**Institution:** University of Science, Vietnam National University Ho Chi Minh City (HCMUS)  
**Faculty:** Faculty of Information Technology

**Contributors** (as listed on the report cover):

- Le Tuan Anh
- Nguyen Hoang Gia Bao
- Tran Huu Loc
- Nguyen Thanh Loi

Thanks to the course instructors and academic supervisors acknowledged in the project report.

## 📄 License

No license file or license terms were present in the workspace. Unless a license is added, reuse and redistribution are subject to the applicable rights of the project contributors and any third-party dataset owners.

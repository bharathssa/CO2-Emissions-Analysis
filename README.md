# CO2 Emissions Analysis

A comprehensive data analysis project examining global CO2 emissions from energy sectors with economic correlations and 2050 forecasting models.

**Course:** BUSINFO 701 | **Group:** 20 | **University:** University of Auckland

---

## 📋 Table of Contents

- [Overview](#overview)
- [Project Objectives](#project-objectives)
- [Dataset Description](#dataset-description)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Key Findings](#key-findings)
- [Technologies](#technologies)
- [Team](#team)
- [License](#license)

---

## 🎯 Overview

This project analyzes **global CO2 emissions trends from energy sectors** (2000-2021) and projects future emissions to 2050. The analysis correlates emissions with economic indicators (GDP) and population growth to understand the relationship between economic development and carbon emissions.

**Key Focus Areas:**
- Energy Industries (Public Electricity & Heat Production)
- Petroleum Refining
- Solid Fuel Manufacturing
- 101 countries across multiple years

---

## 🔍 Project Objectives

1. **Understand emission patterns** across different energy sectors and countries
2. **Identify correlations** between GDP, population, and CO2 emissions
3. **Build predictive models** to forecast 2050 emissions scenarios
4. **Provide insights** for climate policy and energy planning
5. **Create visualizations** for stakeholder communication

---

## 📊 Dataset Description

### Data Sources

| File | Description | Rows | Columns |
|------|-------------|------|---------|
| `co2 emissions inventories.xlsx` | UN UNFCCC CO2 emissions data by sector | 50K+ | Reference area, Measure, Time Period, Emissions |
| `gdp_val.xlsx` | World Bank GDP data by country | Various | Country, Year, GDP |
| `population_data_webscrap.csv` | Web-scraped population data | Various | Country, Year, Population |
| `final_2050.csv` | Processed dataset ready for analysis | 37,829 | Country, Emission_Sectors, Time_Period, CO2_Emission_Tonnes |

### Data Fields

```
Country: 101 unique countries
Emission_Sectors: Energy industry subsectors (1.A.1.a, 1.A.1.b, 1.A.1.c)
Time_Period: 2000-2021
CO2_Emission_Tonnes: Emissions in tonnes
GDP: Gross Domestic Product (USD)
Population: Total population
```

---

## 📁 Project Structure

```
CO2-Emissions-Analysis/
├── README.md                              # Project documentation
├── .gitignore                             # Git ignore rules
│
├── notebooks/
│   └── BUSINFO701 -Group20_ Project_Report.ipynb
│       └── Complete analysis pipeline
│
├── data/
│   ├── raw/
│   │   ├── co2 emissions inventories.xlsx
│   │   ├── gdp_val.xlsx
│   │   └── population_data_webscrap.csv
│   │
│   └── processed/
│       └── final_2050.csv                 # Clean, ready for analysis
│
├── presentations/
│   ├── 701-Group project (2).pptx         # Technical presentation
│   └── BUSINFO701 -Group20.pptx           # Group presentation
│
└── reports/
    └── Project outputs and visualizations
```

---

## 🚀 Installation

### Prerequisites

- Python 3.8+
- Jupyter Notebook
- Git

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/bharathssa/CO2-Emissions-Analysis.git
   cd CO2-Emissions-Analysis
   ```

2. **Create a virtual environment**
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install pandas numpy matplotlib seaborn plotly scikit-learn openpyxl
   ```

4. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

---

## 📖 Usage

### Running the Analysis

1. Open `notebooks/BUSINFO701 -Group20_ Project_Report.ipynb` in Jupyter
2. Execute cells sequentially to:
   - Load and explore raw data
   - Clean and preprocess emissions data
   - Filter required energy sectors (1.A.1.a, 1.A.1.b, 1.A.1.c)
   - Merge with GDP and population data
   - Perform exploratory data analysis
   - Build forecasting models
   - Generate visualizations and insights

### Key Analysis Steps

```python
# Data Loading
co2_df = pd.read_excel('co2 emissions inventories.xlsx', sheet_name=1)

# Data Cleaning
co2_df = co2_df.rename(columns={
    'Reference area': 'Country',
    'Measure': 'Emission_Sectors',
    'OBS_VALUE': 'CO2_Emission_Tonnes',
    'TIME_PERIOD': 'Time_Period'
})

# Sector Filtering
required_sectors = [s for s in sectors 
                    if isinstance(s, str) 
                    and '1.A.1.' in s 
                    and '1.A.1.c.ii' not in s]
co2_df = co2_df[co2_df['Emission_Sectors'].isin(required_sectors)].copy()

# Data Export
co2_df.to_csv('data/processed/final_2050.csv', index=False)
```

---

## 📈 Key Findings

### Data Insights

- **37,829 records** after filtering for required energy sectors
- **101 countries** across **21 years** (2000-2021)
- **4 primary energy subsectors** analyzed
- **Strong correlation** between GDP growth and emissions

### Preliminary Results

- Developed economies show stabilizing/declining emission trends
- Emerging economies exhibit rapid emission growth
- Energy sector is major contributor to total CO2 emissions
- 2050 projections indicate diverse scenarios based on policy interventions

---

## 🛠️ Technologies

| Technology | Purpose |
|-----------|---------|
| **Python 3.8+** | Core programming language |
| **Pandas** | Data manipulation and cleaning |
| **NumPy** | Numerical computations |
| **Matplotlib/Seaborn** | Static visualizations |
| **Plotly** | Interactive visualizations |
| **Scikit-learn** | Machine learning & forecasting |
| **Jupyter Notebook** | Interactive analysis environment |

---

## 📝 License

This project is created for educational purposes as part of BUSINFO 701 at the University of Auckland. 

---

## 📧 Contact & Support

For questions or collaboration:
- **GitHub:** [bharathssa](https://github.com/bharathssa)
- **Repository:** [CO2-Emissions-Analysis](https://github.com/bharathssa/CO2-Emissions-Analysis)

---

## 📚 References

- [UNFCCC Emissions Data](https://unfccc.int/)
- [World Bank GDP Data](https://data.worldbank.org/)
- [UN Sustainable Development Goals](https://sdgs.un.org/)

---

**Last Updated:** January 2026


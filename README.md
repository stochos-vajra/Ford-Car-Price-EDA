# 🚗 Ford Car Price — Exploratory Data Analysis

## 📋 Dataset Overview
- **Source**: Kaggle Ford Car Price Dataset
- **Original rows**: 17,966
- **Final rows after cleaning**: 17,760
- **Original features**: 9
- **Final features after engineering**: 26

---

## 🔧 Libraries Used
- pandas, numpy, matplotlib, seaborn, sklearn

---

## 🧹 Data Cleaning
| Issue | Action | Rows Affected |
|---|---|---|
| Duplicate rows | Removed | 154 |
| Year 2060 | Removed | 1 |
| Engine size 0.0 | Removed | 51 |
| Space in Focus model | Fixed | 1 |

---

## 📊 Phase 4 — Univariate Analysis

### Price Distribution
![Price Distribution](graphs/01_price_distribution.png)
- Most cars priced between £8,000 - £12,000
- Distribution is right skewed
- Median price: £11,290

### Mileage Distribution
![Mileage Distribution](graphs/02_mileage_distribution.png)
- Most cars have 10,000 - 15,000 miles
- Few cars with very high mileage (outliers)

### Year Distribution
![Year Distribution](graphs/03_year_distribution.png)
- Most cars from 2017
- Very few cars before 2010

### MPG Distribution
![MPG Distribution](graphs/04_mpg_distribution.png)
- Most cars have 55-60 MPG
- One suspicious outlier at 200 MPG

### Tax Distribution
![Tax Distribution](graphs/05_tax_distribution.png)
- Two groups: £0-30 (low emission) and £145-150 (standard)
- Most cars pay £145-150 tax

### Engine Size Distribution
![Engine Size Distribution](graphs/06_enginesize_distribution.png)
- Most cars have 1.0 litre engine
- Very few cars with large engines above 2.5

### Model Count
![Model Count](graphs/07_model_count.png)
- Fiesta dominates with 6,489 cars
- Followed by Focus and Kuga

### Transmission Count
![Transmission Count](graphs/08_transmission_count.png)
- 86% of cars are Manual
- Automatic and Semi-Auto are much fewer

### Fuel Type Count
![Fuel Type Count](graphs/09_fueltype_count.png)
- 68% of cars are Petrol
- Diesel is second most common

---

## 📊 Phase 5 — Bivariate Analysis

### Year vs Price
![Year vs Price](graphs/10_year_vs_price.png)
- Newer cars cost significantly more
- Strongest relationship with price (correlation: 0.64)

### Mileage vs Price
![Mileage vs Price](graphs/11_mileage_vs_price.png)
- Higher mileage = Lower price generally
- Strong negative correlation (-0.53)

### Engine Size vs Price
![Engine Size vs Price](graphs/12_enginesize_vs_price.png)
- Bigger engines generally more expensive
- Not perfectly linear

### Transmission vs Price
![Transmission vs Price](graphs/13_transmission_vs_price.png)
- Automatic (£15,720) > Semi-Auto (£14,897) > Manual (£11,783)

### Fuel Type vs Price
![Fuel Type vs Price](graphs/14_fueltype_vs_price.png)
- Hybrid most expensive typically
- Petrol cheapest on average (£11,602)

### MPG vs Price
![MPG vs Price](graphs/15_mpg_vs_price.png)
- No clear pattern between MPG and price

### Tax vs Price
![Tax vs Price](graphs/16_tax_vs_price.png)
- No clear pattern between Tax and price

### Correlation Heatmap
![Correlation Heatmap](graphs/17_correlation_heatmap.png)
- Year strongest positive correlation (0.64)
- Mileage strongest negative correlation (-0.53)

### Average Price by Model
![Model vs Price](graphs/18_model_vs_price.png)
- Mustang most expensive (avg £34,967)
- Streetka cheapest (avg £1,924)

---

## 📊 Phase 5 — Multivariate Analysis

### Mileage vs Price by Transmission
![Mileage vs Price by Transmission](graphs/19_mileage_vs_price_by_transmission.png)
- Higher mileage = lower price for ALL transmission types
- Automatic cars sit higher in price at same mileage

### Year vs Price by Fuel Type
![Year vs Price by Fuel Type](graphs/20_year_vs_price_by_fueltype.png)
- Both Petrol and Diesel follow year trend
- Hybrid only appears in recent years

### Year vs Price by Transmission
![Year vs Price by Transmission](graphs/21_year_vs_price_by_transmission.png)
- Semi-Auto only appeared from 2017
- Manual exists across all years but generally cheaper

### Engine Size vs Price by Fuel Type
![Engine Size vs Price by Fuel Type](graphs/22_enginesize_vs_price_by_fueltype.png)
- Diesel only comes in mid range engines (1.5-2.0)
- Petrol comes in all engine sizes

### Year vs Price by Engine Size
![Year vs Price by Engine Size](graphs/23_year_vs_price_by_enginesize.png)
- Bigger engine + newer year = most expensive combination

---

## 🎯 Final Conclusions

### What Affects Ford Car Price:
| Feature | Impact | Direction |
|---|---|---|
| Year | ✅ Strongest | Newer = Higher |
| Mileage | ✅ Strong | Higher = Lower |
| Model | ✅ Strong | Mustang highest |
| Transmission | ✅ Moderate | Automatic highest |
| Engine Size | ✅ Moderate | Bigger = Higher |
| Fuel Type | ✅ Moderate | Hybrid highest |
| Tax | ❌ Weak | No clear pattern |
| MPG | ❌ Weak | No clear pattern |

### Features Dropped:
- Tax — no clear relationship with price
- MPG — very weak relationship with price

### Feature Engineering Done:
- Rare models (below 50 cars) grouped into Other
- Model encoded using One Hot Encoding
- Transmission encoded using Label Encoding
- Fuel Type encoded using One Hot Encoding

---
*EDA performed by a Plutonian who just landed on Earth! 🪐*

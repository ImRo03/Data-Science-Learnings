# Used Car EDA

This project explores used-car listings with Pandas, Matplotlib and Seaborn. The goal is to understand price patterns and compare prices with brand, fuel type, manufacturing year, mileage and city.

## Dataset
- Source: [Used Car Information — Kaggle](https://www.kaggle.com/datasets/sanjeetsinghnaik/used-car-information)
- Download Dataset.csv from Kaggle. The raw CSV is not included in this repository.
- Place it in data/Dataset.csv beside the notebook, or use one of the alternative paths checked in the loading cell.

## What I did
- Checked shape, columns, data types, missing values and exact duplicate rows.
- Checked year, price, mileage and car age.
- Investigated the 9 rows with mileage above 200,000 km.
- Found 425 rows matching on all non-ID columns. The notebook keeps one copy per matching set for the charts; this is a working choice, not proof that the rows represent the same physical car.
- Compared listed prices by fuel type, brand, manufacturing year, mileage and city.
- Created six charts: price distribution, fuel type, brand, price versus mileage, manufacturing year and city.

## Initial findings
- Original dataset: 1,725 rows and 23 columns; no missing values were found.
- Unnamed: 0 and Id matched exactly. No full-row duplicates were found when IDs were included, but 425 rows matched after ignoring the two ID columns.
- Original median listed price: ₹8.75 lakh; range: ₹62,500 to ₹1.47 crore.
- Manufacturing years: 1990–2021; median year: 2016.
- Median mileage: 49,000 km. Maximum mileage: 790,000 km; 9 rows exceeded 200,000 km.
- After keeping one copy of matching car details, 1,300 rows were used for the charts.
- In the chart dataset, the median price was ₹8.425 lakh. Diesel listings had a median of ₹13 lakh (688 listings), Petrol ₹5.90 lakh (599), Hybrid ₹21 lakh (1), CNG + 1 ₹3.95 lakh (7), and Petrol + 1 ₹3.25 lakh (5). Categories with few listings should not be compared strongly.
- Among the 10 cities with the most listings, median price ranged from ₹4.45 lakh in Noida to ₹37 lakh in Dehradun. City differences may reflect which cars are listed.

## Limitations
High values are investigated rather than removed automatically. Matching details do not confirm that two rows represent the same car. The results describe listings in this dataset and do not prove cause and effect.

## Notebook
[Used_Car_EDA.ipynb](Used_Car_EDA.ipynb)

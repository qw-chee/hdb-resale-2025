# Predicting HDB Resale Prices in Singapore
By: Chee Qian Wen, Delwyn Goh, Elaine Lee, Jason Ng, Kathleen Loke

## Description
The HDB resale market in Singapore has become increasingly dynamic, with shifting buyer preferences, evolving government regulations, and fluctuating property prices. As competition grows, homebuyers are no longer making decisions based purely on proximity to amenities. Instead, factors such as flat size, remaining lease, accessibility to key business districts, and regional demand trends are playing a crucial role in determining resale value.

To stay ahead in this evolving landscape, real estate agents need data-driven insights to accurately assess and forecast HDB resale prices. By leveraging predictive modelling, the aim of this project was to identify the key predictors of HDB resale prices, to help buyers and sellers make well-informed decisions.

## Data Dictionary
The following table details the data and their descriptions:
| Column Name	| Description	| Data Type |
| --- | --- | --- | 
| id | identification no. of transaction | Integer |
| resale_price | the property's sale price in Singapore dollars | Integer |
| town | HDB township where the flat is located | Integer |
| flat_type | type of the resale flat unit | String |
| mid_storey | median value of storey_range | Integer |
| floor_area_sqft | floor area of the resale flat unit in square feet | Float |
| max_floor_lvl | highest floor of the resale flat | Integer |
| Mall_Nearest_Distance | distance (in metres) to the nearest mall | Float |
| Hawker_Nearest_Distance | distance (in metres) to the nearest hawker centre | Float |
| mrt_nearest_distance | distance (in metres) to the nearest MRT station | Float |
| bus_stop_nearest_distance | distance (in metres) to the nearest bus stop | Float |
| pri_sch_nearest_distance | distance (in metres) to the nearest primary school | Float |
| sec_sch_nearest_dist | distance (in metres) to the nearest secondary school | Float |
| cbd_distance | distance to Downtown Core (1.2867° N, 103.8535° E) by each transaction co-ordinates in kilometers | Float |
| cpi | consumer price index | Float |
| remaining_lease | number of years left before the lease expires | Integer |
| amenities_within_1km | total number of malls and hawkers within 1 kilometre | Integer |
| region | classification of HDB towns into regions (C, E, N, NE, W region) | String |
| sora_3mth | 3 month average bank interest rates data from Sora | Float |

## Results
Four machine learning models were built: Linear Regression, Decision Tree, XGBoost, and CatBoost.

The aim of these ML models was to learn from the dataset to predict HDB resale prices.

The following table summarizes the performance of the models:
| Model | Train Accuracy | Test Accuracy | Train-test Difference | Runtime |
| --- | --- | --- | --- | --- |
| Linear Regression | 81.02% | 81.29%	| 0.27% | 0.07s |
| Decision Tree | 99.99% | 92.71%	| 7.28% | 1.97s |
| XGBoost | 98.09% | 96.81%	| 1.28% | 1.71s |
| CatBoost | 96.98% | 96.51%	| 0.47% | 13.00s |

By evaluating the trade-offs between train and test accuracy, model discrepancies, and runtime, XGBoost was been identified as the best model for demonstrating superior performance with no significant overfitting.

## Key Features
Based on our analyses, the 18 features that predict HDB resale prices are listed below in descending order:
1. Flat type 4 room
2. Floor area (sqft)
3. CBD distance
4. Region East
5. Region Northeast
6. Remaining lease
7. Max floor level
8. MRT distance
9. Region West
10. Mid storey
11. SORA (3 mth)
12. Mall distance
13. Amenities 1km
14. Hawker distance
15. Sec school distance
16. Consumer Price Index
17. Pri school distance
18. Bus stop distance

## Conclusion
This project demonstrates that key factors such as lease remaining, proximity to MRT stations, and flat types are strong predictors of HDB resale prices. Price trends consistently show higher values for units located near the CBD and MRT access points, while government regulations and market events—such as cooling measures and the COVID-19 pandemic—have notable impacts on demand and pricing.

The predictive model developed offers practical value for real estate agents and buyers, enabling more informed decision-making based on data-driven insights. Future enhancements, such as integrating sentiment analysis from public forums or news sources, could further refine price forecasts and reflect market sentiment more accurately.

## Project Structure
project-folder/
<br>│── README.md
<br>│── 01_Code.ipynb
<br>│── 02_Data.csv
<br>│── 03_Slides.pdf

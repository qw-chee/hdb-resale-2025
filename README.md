# Predicting HDB Resale Prices in Singapore

## Description
The HDB resale market in Singapore has become increasingly dynamic, with shifting buyer preferences, evolving government regulations, and fluctuating property prices. As competition grows, homebuyers are no longer making decisions based purely on proximity to amenities. Instead, factors such as flat size, remaining lease, accessibility to key business districts, and regional demand trends are playing a crucial role in determining resale value.

To stay ahead in this evolving landscape, real estate agents need data-driven insights to accurately assess and forecast HDB resale prices. By leveraging predictive modelling, the aim of this project was to identify the key predictors of HDB resale prices, to help buyers and sellers make well-informed decisions.

## Data Dictionary
The following table details the data and their descriptions:
**| Column Name	| Description	| Data Type |**
| --- | --- | --- | 
| id | identification no. of transaction | Integer |
| resale_price | the property's sale price in Singapore dollars | Integer |
| Tranc_YearMonth | year and month of the resale transaction | Integer |
| town | HDB township where the flat is located | Integer |
| flat_type | type of the resale flat unit | String |
| storey_range | floor level (range) of the resale flat unit | String |
| floor_area_sqm | floor area of the resale flat unit in square metres | Integer |
| lease_commence_date | commencement year of the flat unit's 99-year lease | Integer |
| mid_storey | median value of storey_range | Integer |
| floor_area_sqft | floor area of the resale flat unit in square feet | Float |
| max_floor_lvl | highest floor of the resale flat | Integer |
| commercial | boolean value if resale flat has commercial units in the same block | Boolean |
| total_dwelling_units | total number of residential dwelling units in the resale flat | Integer |
| Latitude | Latitude based on postal code | Float |
| Longitude | Longitude based on postal code | Float |
| Mall_Nearest_Distance | distance (in metres) to the nearest mall | Float |
| Mall_Within_500m | number of malls within 500 metres | Integer |
| Mall_Within_2km | number of malls within 2 kilometres | Integer |
| Hawker_Nearest_Distance | distance (in metres) to the nearest hawker centre | Float |
| Hawker_Within_500m | number of hawker centres within 500 metres | Integer |
| Hawker_Within_2km | number of hawker centres within 2 kilometres | Integer |
| hawker_market_stalls | number of hawker and market stalls in the nearest hawker centre | Integer |
| mrt_nearest_distance | distance (in metres) to the nearest MRT station | Float |
| bus_interchange | boolean value if the nearest MRT station is also a bus interchange | Boolean |
| mrt_interchange | boolean value if the nearest MRT station is a train interchange station | Boolean |
| bus_stop_nearest_distance | distance (in metres) to the nearest bus stop | Float |
| pri_sch_nearest_distance | distance (in metres) to the nearest primary school | Float |
| pri_sch_name | name of the nearest primary school | String |
| pri_sch_affiliation | boolean value if the nearest primary school has a secondary school affiliation | Boolean |
| sec_sch_nearest_dist | distance (in metres) to the nearest secondary school | Float |
| cbd_distance | distance to Downtown Core (1.2867° N, 103.8535° E) by each transaction co-ordinates in kilometers | Float |
| infl_rate | inflation rate reflecting the overall rise in the cost of living in Singapore | Float |
| cpi | consumer price index | Float |
| mature | if resale flat is classified as Mature (1) or Non-Mature estate (0) | Boolean |
| hdb_age | number of years from lease_commence_date to Tranc_Year | Integer |
| remaining_lease | number of years left before the lease expires | Integer |
| rental_ratio | ratio of rental transactions across different room types to the total number of dwelling units in the resale flat | Float |
| remaining_lease_2021 | number of years left before the lease expires | Integer |
| amenities_within_500m | total number of malls and hawkers within 500 metres | Integer |
| amenities_within_1km | total number of malls and hawkers within 1 kilometre | Integer |
| amenities_within_2km | total number of malls and hawkers within 2 kilometres | Integer |
| facilities_within_500m | boolean value if resale flat has all 4 - Mall, Hawker, MRT and bus_stop within 500m | Boolean |
| region | classification of HDB towns into regions (C, E, N, NE, W region) | String |
| sora | monthly end-of-period bank interest rates data from Sora | Float |
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
<br>│── 04_Slides.pdf

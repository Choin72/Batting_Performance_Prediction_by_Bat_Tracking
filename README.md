# Batting_Performance_Prediction_by_Bat_Tracking (2024)

paper name : Application and Analysis of Nonlinear Regression Models Using Bat Tracking and Hitting Metrics for Baseball Batting Performance Prediction

paper URL : https://www.kci.go.kr/kciportal/ci/sereArticleSearch/ciSereArtiView.kci?sereArticleSearchBean.artiId=ART003161074

## Abstract
This study focuses on analyzing and interpreting the relationship between Bat Tracking metrics and traditional hitting metrics using non-linear regression analysis to predict baseball batter performance.
Based on data provided by MLB Statcast, we analyzed the relationships between Average Bat Speed, Squared-up Rate, Blast, Swing Length, and key performance indicators such as Hits, Home Runs, Batting Average, Slugging Percentage, and OPS. The analysis revealed that Squared-up Rate had a significant positive impact on Hits, while Blast showed a substantial negative impact on both Hits and Slugging Percentage. In the case of Home Runs and OPS, the interaction between Blast and Squared-up Rate was crucial, showing positive effects. This study provides important insights into understanding the complex interactions between Bat Tracking metrics and hitting metrics to more accurately predict batter performance, offering practical contributions to baseball analytics and player evaluation.

## About Bat Tracking metrics
### fast-swing
![Image](https://github.com/user-attachments/assets/f53591b9-f99f-4a06-90aa-99ab07cd6442)
https://www.mlb.com/glossary/statcast/fast-swing-rate
### squared-up rate
![Image](https://github.com/user-attachments/assets/820cf2c3-0ec8-4e85-9c94-ce6308d8176c)
https://www.mlb.com/glossary/statcast/squared-up
### blast
![Image](https://github.com/user-attachments/assets/f531d692-30d4-473e-8821-ef8437dd1640)
https://www.mlb.com/glossary/statcast/squared-up
### swing-length
![Image](https://github.com/user-attachments/assets/d9e38dae-bc1b-49fc-be34-6f3d14979be2)
![Image](https://github.com/user-attachments/assets/dc5b3ec5-7e41-4927-8cac-9d50eaf9bfb1)
https://www.mlb.com/glossary/statcast/swing-length

## Equations obtained by machine learning
### Hits
$$H = -1038.45 + 21.41F_1 + 5166.63F_2 - 50493.81F_3 + 96.00F_4 - 107.24F_1F_2 + 659.61F_1F_3 - 218F_1F_4 + 19941.85F_2F_3 - 315.40F_2F_4 + 7613.04F_3F_4 - 2468.81F_1F_2F_3 + 9.26F_1F_2F_4 - 31151.87F_2F_3F_4 - 99.75F_1F_3F_4 + 398.83F_1F_2F_3F_4
$$

### Homeruns
$$HR = 5506.90 - 74.92F_1 - 22889.00F_2 - 90926.93F_3 - 811.72F_4 + 304.98F_1F_2 + 1272.04F_1F_3 + 11.08F_1F_4 + 386191.78F_2F_3 + 33584F_2F_4 + 1287461F_3F_4 - 5364.70F_1F_2F_3 - 45.86F_1F_2F_4 - 54906.12F_2F_3F_4 - 179.67F_1F_3F_4 + 762.06F_1F_2F_3F_4
$$

### Average
$$AVG = -1.00 + 0.02F_1 - 4.56F_2 - 3386F_3 - 0.13F_4 + 0.03F_1F_2 + 0.46F_1F_3 + 0.00F_1F_4 + 230.31F_2F_3 - 2.14F_2F_4 + 7.97F_3F_4 - 3.65F_1F_2F_3 - 0.02F_1F_2F_4 - 47.14F_2F_3F_4 - 0.11F_1F_3F_4 + 0.63F_1F_2F_3F_4
$$

### Slugging
$$SLG = 51.42 - 0.71F_1 - 233.81F_2 - 895.67F_3 - 7.87F_4 + 3.21F_1F_2 + 12.65F_1F_3 + 0.11F_1F_4 + 3908.40F_2F_3 + 36.25F_2F_4 + 130.38F_3F_4 - 54.78F_1F_2F_3 - 0.50F_1F_2F_4 - 571.00F_2F_3F_4 - 1.84F_1F_3F_4 + 7.99F_1F_2F_3F_4
$$

### On base Plus Slugging (OPS)
$$OPS = 81.62 - 1.11F_1 - 358.23F_2 - 1334.98F_3 - 12.49F_4 + 4.86F_1F_2 + 18.69F_1F_3 + 0.17F_1F_4 + 5824.37F_2F_3 + 55.88F_2F_4 + 195.49F_3F_4 - 80.95F_1F_2F_3 - 0.76F_1F_2F_4 - 857.48F_2F_3F_4 - 2.73F_1F_3F_4 + 11.91F_1F_2F_3F_4
$$

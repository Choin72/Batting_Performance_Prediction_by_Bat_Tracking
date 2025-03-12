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

## Prediction examples
```
--------------------------------------------------
Randomly Selected Player Index: 8
Player Data:
id                                     660271
name                           Ohtani, Shohei
swings_competitive                        626
percent_swings_competitive           0.903319
contact                                   448
avg_bat_speed                       75.641972
hard_swing_rate                      0.579872
squared_up_per_bat_contact           0.377232
squared_up_per_swing                 0.269968
blast_per_bat_contact                0.252232
blast_per_swing                      0.180511
swing_length                         7.665783
swords                                      5
batter_run_value                    15.014938
whiffs                                    178
whiff_per_swing                      0.284345
batted_ball_events                        232
batted_ball_event_per_swing          0.370607
H                                         117
HR                                         29
AVG                                     0.316
SLG                                     0.635
OPS                                     1.035
Name: 8, dtype: object

Predicted H: 82.88, Actual H: 92, Error: 9.12
Predicted HR: 12.63, Actual HR: 12, Error: -0.63
Predicted AVG: 0.252, Actual AVG: 0.278, Error: 0.026
Predicted SLG: 0.425, Actual SLG: 0.435, Error: 0.010
Predicted OPS: 0.741, Actual OPS: 0.745, Error: 0.004
==================================================
Randomly Selected Player Index: 24
Player Data:
id                                   663728
name                           Raleigh, Cal
swings_competitive                      614
percent_swings_competitive         0.905605
contact                                 443
avg_bat_speed                     74.422296
hard_swing_rate                    0.449511
squared_up_per_bat_contact         0.293454
squared_up_per_swing               0.211726
blast_per_bat_contact              0.180587
blast_per_swing                    0.130293
swing_length                        7.73427
swords                                    6
batter_run_value                  -1.742716
whiffs                                  171
whiff_per_swing                    0.278502
batted_ball_events                      174
batted_ball_event_per_swing        0.283388
H                                        68
HR                                       20
AVG                                   0.216
SLG                                   0.435
OPS                                   0.734
Name: 24, dtype: object

Predicted H: 84.13, Actual H: 85, Error: 0.87
Predicted HR: 13.75, Actual HR: 13, Error: -0.75
Predicted AVG: 0.251, Actual AVG: 0.23, Error: -0.021
Predicted SLG: 0.431, Actual SLG: 0.373, Error: -0.058
Predicted OPS: 0.748, Actual OPS: 0.664, Error: -0.084
==================================================
Randomly Selected Player Index: 11
Player Data:
id                                             665489
name                           Guerrero Jr., Vladimir
swings_competitive                                594
percent_swings_competitive                    0.90687
contact                                           468
avg_bat_speed                               75.360381
hard_swing_rate                              0.530303
squared_up_per_bat_contact                   0.339744
squared_up_per_swing                         0.267677
blast_per_bat_contact                        0.224359
blast_per_swing                              0.176768
swing_length                                 7.678556
swords                                              7
batter_run_value                             1.002297
whiffs                                            126
whiff_per_swing                              0.212121
batted_ball_events                                241
batted_ball_event_per_swing                  0.405724
H                                                 107
HR                                                 14
AVG                                             0.288
SLG                                             0.456
OPS                                             0.815
Name: 11, dtype: object

Predicted H: 81.00, Actual H: 103, Error: 22.00
Predicted HR: 10.01, Actual HR: 14, Error: 3.99
Predicted AVG: 0.251, Actual AVG: 0.305, Error: 0.054
Predicted SLG: 0.402, Actual SLG: 0.476, Error: 0.074
Predicted OPS: 0.715, Actual OPS: 0.87, Error: 0.155
==================================================
Randomly Selected Player Index: 19
Player Data:
id                                    682985
name                           Greene, Riley
swings_competitive                       591
percent_swings_competitive          0.913447
contact                                  450
avg_bat_speed                      74.657067
hard_swing_rate                     0.465313
squared_up_per_bat_contact          0.324444
squared_up_per_swing                0.247039
blast_per_bat_contact               0.173333
blast_per_swing                      0.13198
swing_length                        7.186697
swords                                     3
batter_run_value                     4.38025
whiffs                                   141
whiff_per_swing                     0.238579
batted_ball_events                       216
batted_ball_event_per_swing         0.365482
H                                         96
HR                                        17
AVG                                    0.271
SLG                                    0.503
OPS                                    0.867
Name: 19, dtype: object

Predicted H: 74.18, Actual H: 57, Error: -17.18
Predicted HR: 10.21, Actual HR: 12, Error: 1.79
Predicted AVG: 0.232, Actual AVG: 0.204, Error: -0.028
Predicted SLG: 0.393, Actual SLG: 0.38, Error: -0.013
Predicted OPS: 0.698, Actual OPS: 0.648, Error: -0.050
==================================================
Randomly Selected Player Index: 22
Player Data:
id                                          665487
name                           Tatis Jr., Fernando
swings_competitive                             481
percent_swings_competitive                0.904135
contact                                        367
avg_bat_speed                            74.494638
hard_swing_rate                           0.463617
squared_up_per_bat_contact                0.370572
squared_up_per_swing                      0.282744
blast_per_bat_contact                     0.217984
blast_per_swing                            0.16632
swing_length                              7.296101
swords                                          19
batter_run_value                         -5.648485
whiffs                                         114
whiff_per_swing                           0.237006
batted_ball_events                             195
batted_ball_event_per_swing               0.405405
H                                               86
HR                                              14
AVG                                          0.279
SLG                                          0.468
OPS                                          0.822
Name: 22, dtype: object

Predicted H: 84.43, Actual H: 84, Error: -0.43
Predicted HR: 9.93, Actual HR: 9, Error: -0.93
Predicted AVG: 0.257, Actual AVG: 0.269, Error: 0.012
Predicted SLG: 0.395, Actual SLG: 0.41, Error: 0.015
Predicted OPS: 0.717, Actual OPS: 0.741, Error: 0.024
==================================================
```

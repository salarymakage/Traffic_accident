# Synthetic Traffic Data Generation and Analysis

## **1. Data Generation**
A synthetic dataset was generated to analyze traffic accidents, considering various factors such as severity, gender, age, vehicle type, human factors, and environmental conditions.

### **Key Variables in Data Generation**
- **Severity Levels:** Fatal, Severe, Minor
- **Gender Distribution Based on Severity**
- **Age Groups Based on Severity and Transport Type**
- **Transport Mode:** Pedestrian, Car Driver, Motorcycle Driver, etc.
- **Human Factors:** Speeding, Disregarding traffic signs, Drunk driving, etc.
- **Helmet Usage for Motorcyclists**
- **Road, Vehicle, and Weather Conditions**
- **Accident Type:** Motorcycle vs. Motorcycle, Car vs. Truck, etc.
- **Time of Day and Vehicle Speed Distribution**

The generated dataset was saved as `synthetic_traffic_data.csv`.

#### **Sample Data**

```
Synthetic dataset successfully created!
  Gender    Age               Role               Human Factors Helmet  \
0   Male  18-45         Pedestrian                    Speeding   None   
1   Male  18-45      Car Passenger               Drunk driving   None   
2   Male  18-45  Motorcycle Driver  Disregarding traffic signs    Yes   
3   Male   1-17      Car Passenger               Drunk driving   None   
4   Male  18-45      Car Passenger                    Speeding   None   

  Road Factors vehicle Factors Weather      Road Type  \
0  Normal Road          Normal  Normal  Straight Road   
1  Normal Road          Normal  Normal    Curved Road   
2  Normal Road          Normal  Normal  Straight Road   
3  Normal Road          Normal  Normal  Straight Road   
4  Normal Road          Normal  Normal  Straight Road   

                   Collision Time of Day  Vehicle Speed Severity  
0       Other vs. Pedestrian       Night      96.328557    Fatal  
1              Car vs. Other     Evening      73.822428    Fatal  
2  Motorcycle vs. Motorcycle   Afternoon      74.392234   Severe  
3         Car vs. Motorcycle     Morning      56.931449   Severe  
4              Car vs. Other     Evening      48.021362    Minor  
```

---

## **2. Exploratory Data Analysis (EDA)**
### **Severity Distribution**
- Visualized the distribution of accidents by severity using a bar plot.

### **Gender and Role Distributions**
- Analyzed gender distribution by severity.
- Investigated the roles (Car Driver, Passenger, Pedestrian) involved in accidents.

### **Vehicle Speed Analysis**
- Box plot analysis of vehicle speed distribution across severity levels.

### **Human Factors and Helmet Usage**
- Examined human factors contributing to accidents.
- Assessed helmet usage among motorcyclists.

---

## **3. Data Preprocessing**
### **Feature Engineering**
- Label Encoding for categorical variables such as Age and Helmet Usage.
- One-hot encoding for categorical features (Gender, Role, Human Factors, etc.).
- Standardized numerical features for better model performance.
- Split dataset into training and testing sets.

---

## **4. Machine Learning Models**
### **Model Training and Evaluation**
- **Linear Regression** for severity prediction.
- **Random Forest Classifier** for classification tasks.
- **Support Vector Machine (SVM)** for severity prediction.
- **XGBoost Classifier** for improved accuracy.

### **Model Performance Metrics**
- Evaluated models using **accuracy score** and **classification reports**.
- **Feature Importance** analysis from Random Forest.

#### **Model Comparison**
```
Model Comparison:
Linear Regression: 0.26
Random Forest: 0.69
SVM: 0.68
```

---

## **5. Model Tuning and Feature Selection**
### **Feature Selection**
- Applied `SelectKBest` with chi-square test to identify important features.
- Selected Features:
```
['Vehicle Speed' 'Gender_Male' 'Role_Car Passenger'
 'Role_Motorcycle Driver' 'Role_Motorcycle Passenger' 'Role_Others'
 'Role_Pedestrian' 'Collision_Car vs. Car'
 'Collision_Other vs. Motorcycle' 'Collision_Other vs. Pedestrian']
```

### **Hyperparameter Tuning**
- Used **GridSearchCV** to find the best hyperparameters for Random Forest.
- Best Parameters:
```
{'max_depth': None, 'min_samples_split': 10, 'n_estimators': 200}
Best Accuracy: 0.6957
```

---

## **6. Results and Insights**
- Random Forest and XGBoost models outperformed others in classification tasks.
- Speeding and disregarding traffic rules were significant human factors.
- Helmet usage significantly impacted accident severity.
- Feature selection improved model performance by reducing noise.

---

## **7. Conclusion**
- The synthetic dataset provided insights into accident causes and severity.
- Machine learning models effectively predicted accident severity.

The entire workflow involved data generation, preprocessing, exploratory analysis, model training, tuning, and result evaluation.

## **8. Reference**

- National Road Safety Committee (2024 Summary Report) {lost link}
- [Traffic Accidents Leading Cause of Death in Cambodia](https://www.voanews.com/a/traffic-accidents-are-leading-cause-of-death-in-cambodia/3403777.html)
- [Nearly 1800 Die on Roads in 2017](https://www.phnompenhpost.com/national/nearly-1800-die-roads-2017)
- [Traffic Accident Deaths and Injuries Increase in 2022](https://www.khmertimeskh.com/501212055/traffic-accident-deaths-and-injuries-increase-in-2022/)
- [Traffic Accident Fatalities Rise 14% in 2022](https://www.khmertimeskh.com/501229688/traffic-accident-fatalities-rise-14-in-2022/)
- [Almost 1600 People Die in Car Crashes in Cambodia (2023)](https://www.khmertimeskh.com/501437417/almost-1600-people-die-in-car-crashes-in-cambodia-in-2023/)

- National Social Security Fund {lost link}
![Reference Report](image/Screenshot%202025-02-07%20141023.png)

---

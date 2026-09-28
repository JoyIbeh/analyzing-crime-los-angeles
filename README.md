# Analyzing Crime in Los Angeles

## 📊 DataCamp Data Analysis Project

This project analyzes crime data from **Los Angeles, California**, to identify patterns in criminal behavior. The analysis was completed as part of a **DataCamp data analysis project**, using Python and the `crimes.csv` dataset.

The goal is to generate insights that can help the **Los Angeles Police Department (LAPD)** better understand crime patterns and inform how resources could be allocated across different times and geographic areas.

---

## 🎯 Project Objectives

The analysis focuses on three key questions:

1. **What hour has the highest frequency of crimes?**
2. **Which area has the largest frequency of night crimes**, defined as crimes committed between 10:00 PM and 3:59 AM?
3. **What is the distribution of crimes by victim age group?**

---

## 📁 Dataset

The project uses a modified version of publicly available **Los Angeles Open Data**.

The main dataset is:

`crimes.csv`

### Key Variables

| Variable       | Description                                      |
| -------------- | ------------------------------------------------ |
| `DR_NO`        | Division of Records Number                       |
| `Date Rptd`    | Date the crime was reported                      |
| `DATE OCC`     | Date the crime occurred                          |
| `TIME OCC`     | Time the crime occurred                          |
| `AREA NAME`    | LAPD geographic area/patrol division             |
| `Crm Cd Desc`  | Description of the crime committed               |
| `Vict Age`     | Victim's age                                     |
| `Vict Sex`     | Victim's sex                                     |
| `Vict Descent` | Victim's descent                                 |
| `Weapon Desc`  | Description of the weapon used, where applicable |
| `Status Desc`  | Crime status                                     |
| `LOCATION`     | Location/address of the crime                    |

---

## 🛠️ Tools & Technologies

* **Python**
* **Pandas** – data manipulation and analysis
* **NumPy** – numerical operations
* **Matplotlib** – data visualization
* **Seaborn** – statistical visualization
* **Jupyter Notebook**

---

## 🔍 Analysis Performed

### 1. Crime by Hour

The `TIME OCC` variable was processed to extract the hour at which each crime occurred.

A new variable, `HOUR OCC`, was created to represent the hour of occurrence.

A Seaborn count plot was then used to examine the frequency of crimes across the 24-hour period.

**Finding:**
The analysis identified **12:00 PM (midday)** as the hour with the highest frequency of reported crimes.

```python
peak_crime_hour = 12
```

---

### 2. Night Crime Analysis

Night-time crimes were defined as crimes occurring between:

* 10:00 PM
* 11:00 PM
* 12:00 AM
* 1:00 AM
* 2:00 AM
* 3:00 AM

The data was filtered using the `HOUR OCC` variable and grouped by `AREA NAME` to determine which geographic area recorded the highest volume of night-time crime.

```python
night_time = crimes[
    crimes["HOUR OCC"].isin([22, 23, 0, 1, 2, 3])
]
```

The area with the highest number of night crimes was then stored in:

```python
peak_night_crime_location
```

---

### 3. Victim Age Analysis

Victims were grouped into the following age categories:

* 0–17
* 18–25
* 26–34
* 35–44
* 45–54
* 55–64
* 65+

The analysis used `pandas.cut()` to create the age brackets.

```python
age_bins = [0, 17, 25, 34, 44, 54, 64, np.inf]

age_labels = [
    "0-17",
    "18-25",
    "26-34",
    "35-44",
    "45-54",
    "55-64",
    "65+"
]
```

The resulting distribution was stored as the Pandas Series:

```python
victim_ages
```

---

## 📈 Key Skills Demonstrated

This project demonstrates practical skills in:

* Data loading with Pandas
* Data cleaning and transformation
* Working with time-based data
* Creating categorical age groups
* Filtering datasets
* Grouping and aggregating data
* Frequency analysis
* Exploratory data analysis (EDA)
* Data visualization
* Extracting insights from structured data
* Translating analytical questions into Python code

---

## 📂 Project Structure

```text
Analyzing-Crime/
│
├── Analyzing Crime.ipynb
├── crimes.csv
├── la_skyline.jpg
└── README.md
```

> **Note:** If `crimes.csv` or `la_skyline.jpg` is not included in the repository, the notebook may not run correctly for other users unless the files are provided or the data source is documented.

---

## 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/Analyzing-Crime.git
```

### 2. Navigate to the project directory

```bash
cd Analyzing-Crime
```

### 3. Install the required libraries

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
Analyzing Crime.ipynb
```

---

## 💡 Project Context

The analysis demonstrates how data can be used to identify **when and where crime occurs and which victim age groups are represented in the dataset**.

These types of insights can support data-informed discussions around crime monitoring, resource allocation, and public safety planning.

---

## 👩🏽‍💻 Author

**Joy Ibeh Chinwendu**

Data & Monitoring, Evaluation and Learning Professional | Data Analyst

🔗 LinkedIn: [linkedin.com/in/ibeh-joy-chinwendu](https://linkedin.com/in/ibeh-joy-chinwendu/)

🔗 Portfolio: [joyibeh.netlify.app](https://joyibeh.netlify.app/)

---

## 📌 Project Source

This project was completed as part of a **DataCamp learning project** focused on exploratory data analysis with Python.

# **Ride Bookings Data Cleaning Project**

## **Project Overview**

This project focuses on the cleaning and preprocessing of a ride bookings dataset. The primary objective is to handle missing values and inconsistencies within the data to prepare a clean, reliable dataset suitable for exploratory data analysis, visualization, and machine learning modeling. The raw dataset contained numerous missing values across both numerical and categorical columns, which were systematically addressed using appropriate imputation techniques.

## **Dataset**

* **Source:** Bookings.csv  
* **Dimensions:** 103,024 rows × 19 columns

### **Columns**

The dataset includes the following columns:

* Date  
* Time  
* Booking\_ID  
* Booking\_Status  
* Customer\_ID  
* Vehicle\_Type  
* Pickup\_Location  
* Drop\_Location  
* V\_TAT (Vendor Turnaround Time)  
* C\_TAT (Customer Turnaround Time)  
* Canceled\_Rides\_by\_Customer  
* Canceled\_Rides\_by\_Driver  
* Incomplete\_Rides  
* Incomplete\_Rides\_Reason  
* Booking\_Value  
* Payment\_Method  
* Ride\_Distance  
* Driver\_Ratings  
* Customer\_Rating

## **Data Cleaning Process**

The data cleaning process involved several key steps to ensure data quality and integrity:

1. **Initial Data Exploration:**  
   * The dataset was loaded into a pandas DataFrame.  
   * Initial analysis was performed using .head(), .tail(), .shape, and .info() to understand its structure, data types, and identify columns with null values.  
2. **Missing Value Analysis:**  
   * A comprehensive count of missing values for each column was generated using .isnull().sum().  
   * Significant percentages of missing data were found in columns like Canceled\_Rides\_by\_Customer (89.8%), Canceled\_Rides\_by\_Driver (82.1%), Incomplete\_Rides\_Reason (96.2%), and several others with around 38% missing values.  
   * The distribution of missing values was visualized using bar charts to clearly identify the most affected columns.  
3. Imputation Strategy:  
   A two-pronged approach was used to handle the missing data:  
   * **Numerical Columns:** Missing values in numerical columns (V\_TAT, C\_TAT, Booking\_Value, Ride\_Distance, Driver\_Ratings, Customer\_Rating) were filled using the **mean** of their respective columns.  
   * **Categorical (Object) Columns:** Missing values in categorical columns (Canceled\_Rides\_by\_Customer, Canceled\_Rides\_by\_Driver, Incomplete\_Rides, etc.) were imputed using the **mode** (most frequent value) of each column.  
4. **Verification:**  
   * After the imputation process, a final check was performed to confirm that all missing values had been successfully handled. The final dataset is complete with zero null values.

## **Results**

The outcome of this project is a thoroughly cleaned dataset, free of missing values. This prepared data is now a reliable foundation for further analysis, such as:

* Analyzing ride cancellation patterns.  
* Evaluating driver and customer ratings.  
* Building predictive models for booking success or ride value.

## **How to Use**

To replicate the data cleaning process:

1. **Clone the repository:**  
   git clone \[https://github.com/your-username/your-repository-name.git\](https://github.com/your-username/your-repository-name.git)

2. **Install the required libraries:**  
   pip install pandas numpy seaborn matplotlib jupyter

3. Run the Jupyter Notebook:  
   Open and run the datacleaned.ipynb notebook to see the step-by-step data cleaning process.

## **Tools and Technologies**

* **Language:** Python  
* **Libraries:**  
  * Pandas (for data manipulation and analysis)  
  * NumPy (for numerical operations)  
  * Matplotlib & Seaborn (for data visualization)  
* **Environment:** Jupyter Notebook

## **License**

This project is licensed under the MIT License \- see the LICENSE file for details.

## **Contact**

**Nitin K**

* **Email:** Nitinx321@gmail.com

# Ride-Hailing Service Booking Data Cleaning 🚕

## Project Description
This project focuses on cleaning and pre-processing a dataset of ride-hailing bookings. The primary goal is to handle inconsistencies and missing values within the data to prepare a robust, clean dataset ready for exploratory data analysis, visualization, and machine learning modeling. The process involves identifying and rectifying issues in both numerical and categorical columns to ensure data quality and integrity.

---

## Dataset
The dataset, `Bookings.csv`, contains transactional data for a ride-hailing service.

* **Source**: `Bookings.csv`
* **Size**: 103,024 rows × 19 columns
* **Structure**: The dataset includes the following columns:
    * `Date`, `Time`, `Booking_ID`, `Booking_Status`, `Customer_ID`, `Vehicle_Type`, `Pickup_Location`, `Drop_Location`, `V_TAT` (Vehicle Turnaround Time), `C_TAT` (Customer Turnaround Time), `Canceled_Rides_by_Customer`, `Canceled_Rides_by_Driver`, `Incomplete_Rides`, `Incomplete_Rides_Reason`, `Booking_Value`, `Payment_Method`, `Ride_Distance`, `Driver_Ratings`, `Customer_Rating`.

---

## Data Cleaning Steps
The cleaning process was executed systematically to address data quality issues.

1.  **Initial Assessment**:
    * Loaded the dataset into a Pandas DataFrame.
    * Conducted a preliminary analysis using `df.info()`, `df.shape`, and `df.isnull().sum()` to understand data types, dimensions, and the extent of missing values.

2.  **Missing Value Analysis**:
    * Calculated the total count and percentage of missing values for each column.
    * Visualized the missing data distribution using a `seaborn` heatmap and bar plot to quickly identify columns requiring attention. Columns like `Incomplete_Rides_Reason` and `Canceled_Rides_by_Customer` had over 89% missing data.

3.  **Handling Missing Numerical Data**:
    * Identified all columns with `float64` and `int64` data types that contained null values (`V_TAT`, `C_TAT`, `Driver_Ratings`, `Customer_Rating`).
    * Applied **mean imputation** to fill the missing values in these numeric columns. The mean was chosen to maintain the central tendency of the original data distribution.

4.  **Handling Missing Categorical Data**:
    * Identified all columns with the `object` data type containing null values (`Canceled_Rides_by_Customer`, `Canceled_Rides_by_Driver`, `Incomplete_Rides`, etc.).
    * Applied **mode imputation** to fill these missing values. The mode (most frequent value) was used as it is the most representative value for categorical data.

5.  **Verification**:
    * After imputation, a final check was performed using `df.isnull().sum().sum()` to confirm that the DataFrame was completely free of null values.

---

## Tools and Libraries
* **Language**: Python 3
* **Libraries**:
    * `Pandas`: For data manipulation and analysis.
    * `NumPy`: For numerical operations.
    * `Seaborn` & `Matplotlib`: For data visualization.
* **Environment**: Jupyter Notebook

---

## Usage
To replicate the cleaning process, follow these steps:

1.  **Clone the repository** or download the project files.
2.  **Ensure you have the dataset** `Bookings.csv` in the same directory as the notebook or update the file path in the notebook accordingly.
3.  **Install the required libraries**:
    ```bash
    pip install pandas numpy seaborn matplotlib jupyter
    ```
4.  **Launch Jupyter Notebook** and open `Bookingdataclean.ipynb`.
5.  **Run the cells sequentially** from top to bottom to execute the cleaning pipeline.

---

## Output
The primary output of this project is a **cleaned Pandas DataFrame** where all missing values have been successfully imputed. This clean dataset is ready for downstream analytical tasks.

Additionally, the notebook generates several visualizations that document the cleaning process:
* A heatmap showing the concentration of null values before cleaning.
* Bar plots illustrating the number of missing values in categorical columns.

---

## Future Improvements
While the current cleaning process is robust, it could be enhanced with the following:

* **Advanced Imputation**: Instead of mean/mode, techniques like K-Nearest Neighbors (KNN) or MICE (Multivariate Imputation by Chained Equations) could be used for more accurate imputation.
* **Outlier Detection**: Implement statistical methods like IQR (Interquartile Range) or Z-score to identify and handle potential outliers in numerical columns like `Booking_Value` and `Ride_Distance`.
* **Data Type Conversion**: Convert the `Date` column from `object` to a `datetime` format to enable time-series analysis.
* **Text Standardization**: Standardize text in categorical columns like `Pickup_Location` and `Drop_Location` to correct typos and ensure consistency.

---

## License
This project is available under the MIT License. See the `LICENSE` file for more details.

---

## Contact & Acknowledgements
* Feel free to reach out with any questions or suggestions!
* This project relies on the incredible open-source libraries developed by the Python community. Thanks to the creators of Pandas, NumPy, Seaborn, and Matplotlib.

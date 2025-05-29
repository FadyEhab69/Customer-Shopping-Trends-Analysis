# Customer-Shopping-Trends-Analysis
# Project Overview

This project analyzes a customer shopping trends dataset to uncover insights into purchasing behavior, payment method preferences, and demographic patterns. Using Python with Pandas and Matplotlib in a Jupyter Notebook, the dataset was cleaned, explored, and visualized to inform business strategies such as targeted marketing, inventory management, and payment system optimization. This documentation outlines the data cleaning process, analysis methodology, key insights, and visualizations, demonstrating proficiency in data manipulation, exploratory data analysis (EDA), and data visualization.

# Data Cleaning

Used df.info() and df.describe() to check data types, missing values, and summary statistics.

Handling Missing Values:

Identified missing values with df.isnull().sum().

Imputed numerical columns (e.g., Review Rating) with the mean: df['Review Rating'].fillna(df['Review Rating'].mean(), inplace=True).

Imputed categorical columns (e.g., Gender, Category) with the mode: df['Gender'].fillna(df['Gender'].mode()[0], inplace=True).

Dropped rows with missing critical values (e.g., Purchase Amount (USD)) if necessary.

Data Type Correction:

Converted categorical columns to category type for efficiency: df['Gender'] = df['Gender'].astype('category').

Verified numerical columns (Age, Purchase Amount (USD), Review Rating) were correctly typed as integers or floats.

Removing Duplicates:

Checked for duplicates with df.duplicated().sum() and removed them: df.drop_duplicates(inplace=True).

Standardizing Categorical Data:

Standardized text case in categorical columns: df['Gender'] = df['Gender'].str.lower().

Ensured consistency in Payment Method and Frequency of Purchases (e.g., corrected typos or variations).

Outlier Detection:

Identified outliers in Age and Purchase Amount (USD) using IQR method.

Capped extreme values (e.g., Purchase Amount (USD) > Q3 + 1.5*IQR) to reduce skew.

Feature Engineering:

Created age bins for segmentation: df['Age Group'] = pd.cut(df['Age'], bins=[18, 25, 35, 45, 55, 100], labels=['18-25', '26-35', '36-45', '46-55', '55+']).


# Key Insights
# Payment Method Preferences:

Credit Card and PayPal likely dominate total purchase amounts, reflecting their convenience for online transactions.

Cash and Bank Transfer have smaller shares, suggesting they are less common in e-commerce settings.

# Customer Behavior:

Customers with Subscription Status = "Yes" frequently use discounts and promo codes, indicating loyalty programs drive engagement.

Frequent shoppers (Weekly, Fortnightly) contribute significantly to total spending, particularly via digital payment methods.

# Seasonal Trends:

Purchases peak in Spring and Winter, suggesting seasonal demand for items like Sweaters (Winter) and Sandals (Spring).

# Demographic Patterns:

The customer base spans a wide age range (19–55+), enabling targeted marketing by age group (e.g., trendy items for younger customers).

Gender analysis may reveal unique preferences (e.g., Males purchasing Blouses suggest unisex trends).

# Business Recommendations:

Marketing: Target frequent shoppers with personalized offers via Credit Card/PayPal.

Inventory: Prioritize Clothing and Footwear for Spring/Winter, focusing on popular sizes (M, L) and colors (Maroon, Turquoise).

Payment Systems: Enhance support for digital payments to streamline transactions.



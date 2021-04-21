

# DATA ANALYSIS ON COMPANY XYZ

This analysis  was carried out on the chain of supermarkets owned by Company XYZ across the country to help the company understand sales trends and determine its growth, using recorded sales information provided by the branches for the past three months.

# Project Steps

Step 1: Loading Datasets

    - Libraries were imported.
    - "glob" was used to match the pattern "csv" in order to generate a list of the branch files.
    - The resulting list of files was then combined using the "pd.concat" method and assigned to the variable "combined".
    - The variable "combined" is then exported as a csv file, "combined.csv"
    - The csv was then read using "pd.read_csv" method and assigned to a dataframe "combined_df"


Step 2 : Data Exploration

    - More libraries were imported.
    - The head() method was used to view the first five rows of the dataset.
    - The shape attribute was used to check the number of rows and columns present, which resulted to 1000 rows and 27 columns.
    - The column attribute was used to generate the names of the 27 columns present in the dataset.
    - The describe method() was used to get the statistical summary of the dataframe.
    - From the dataframe's statistical summary, some findings like count, mean, std, min, 25%, 50%, 75% and max were described.
    - The isna() and sum() methods were used to check the sum of missing values in each columns of the dataframe, which resulted to zero,i.e, no missing values in the dataset.
    - The info() method was used to get a concise summary of the dataframe including the data types for each of the columns.


 Step 3: Dealing with DateTime Features

    - The to_datetime() method was used to convert the Date and Time column to datetime.
    - The dtype attribute was used to check the data types of both Date and Time to confirm if they are in datetime.
    - The Day, Month, Year, and Hour features were extracted accurately into new columns of Day, Month, Year and Hour respectively.
    - The nunique() method was used to determine the number of unique hours of sales in the supermarket.
    - The unique() method was used to return an array of unique hours of sales.  


Step 4: Unique Values in Columns

    - The len(), unique() and tolist() methods were used to generate the number and list of unique values in the categorical columns which includes Invoice ID, Branch, City, Customer type, Gender, Product line and Payment.
    -  The value_counts() method was used to generate the count figure of the values under each category.


Step 5: Aggregation with GroupBy

    - A groupby object with the "City" column was created and assigned to the variable "city_groups"
    - An aggregation function of "sum" and "np.mean" was assigned to "func".
    - A table was created using the groupby object and aggregation function to show the gross income of each city.
    - The idxmax() method was used with the aggregation function to determine the city with the highest total gross income.
    - The max() method was used to print the value of the highest total gross income.
    - The groupby object was used to explore other columns like "Unit Price", "Quantity", "gross margin percentage" and "Rating" using aggregation function of sum, min, max and np.mean.


Step 6: Data Visualization

    - Countplots were used to determine the branch with the highest sales record, the most used payment method, the highest and lowest sold product lines

    - More countplots were used to determine the type of payment channel (Card, Epay or Cash) used by most customers to pay for each product line and also to determine the payment channel that was mostly used in the branches, setting the "Payment" column as the hue parameter.

    - A box plot was used to determine the branch with the lowest rating

    - To ascertain that the gender type affects the kind of products purchased in the supermarket, a chart visualization using catplot() was generated with the "Product line" column on the x-axis while the "Quantity" and "Total" columns on the y-axis, setting hue as "Gender".

    - To explore the interaction of the Unit price and the Quantity of goods purchased, catplot() was used to plot Product line per Unit price and Product line per Quantity.



# Insights

From using the isnull() method, it is clear there are no missing values.

From the aggregation with groupby, it is observed that Port Harcourt has the highest gross income while Lagos has the lowest gross income.

From the use of different countplots, the following were determined:
    - The branch with the highest sales record is Branch A while the branch with the least sales record is Branch C.
    - The most used payment method is Epay while the least used payment method is Card.
    - The highest product line in terms of sales record is Fashion accessories while the lowest product line in terms of sales record is Health and body.

From the use of countplot to determine the payment method of each product line, the following were observed:
    - The most used Payment Method used in Food and beverages product line : Card
    - The most used Payment Method used in Fashion Accessories product line : Epay
    - The most used Payment Method used in Electronic Accessories product line : Cash
    - The most used Payment Method used in Sports and travel product line : Cash
    - The most used Payment Method used in Home and lifestyle product line : Epay
    - The most used Payment Method used in Health and beauty product line : Epay

From the use of countplot to determine the most used payment method in each branch, the following were observed:
    - The most used Payment Method used in Branch B: Epay
    - The most used Payment Method used in Branch A: Epay
    - The most used Payment Method used in Branch C: Cash

From the use of boxplots, the following were determined:
    - All the branches have a minimum rating of 4.0 and maximum rating of 10.0.
    - Branch A and Branch C have same ratings of 5.60 falling under the 1st quartile, 7.10 falling under the 2nd quartile and 8.50 falling - under the 3rd quartile.
    - Branch B has ratings of 5.30 for the 1st quartile, 6.70 for the 2nd quartile and 8.20 for the 3rd quartile.
    Therefore, Branch A and B both have the highest ratings while Branch C has the least.

- From the use of catplot() for visualizing the effect of gender on the type of products purchased, the following were observed:
    - The Female Gender buys more quantities of products from Food and Beverages, Fashion Accessories, Electronic Accessories, Sports and Travel and Home and lifestyle product lines than the Male Gender.Whereas the Male Gender buys more quantities of products from the Health and Beauty product line than the Female Gender
    - The Female Gender has a larger value of total amount spent on products from Food and Beverages, Fashion Accessories, Electronic Accessories and Home and lifestyle product lines compared to that of the Male Gender.Whereas the Male Gender has a larger value of total amount spent on products from Sports and Travel and Health and Beauty product lines compared to that of the Female Gender

-From the use of catplot() to visualize the interaction between Unit price and Quantity, the following was observed:
    - The Electronic Accessories product line has the least average unit price of N19,278 and the highest average value of Quantity sold at N5.71. Whereas the Fashion Accessories product line has the highest average unit price of N20,575 and the lowest average value of Quantity sold at N5.06.
    - This could mean that the lower the unit price, the more quantity sold and the higher the unit price, the lesser the quantity sold




# Future Work

For future analysis:
    - More datasets is required that includes age of customers, occupation of customers, proximity of customer"s address to branch locations, weather condition at the time, 

    - These extra information will help answer questions like:
        - Does the age and occupation of customers affect the product they purchase?
        - Does proximity of customer's address to branch location affect customer type?
        - Does the weather condition at the time affects product being purchased?

    - Insights will then be made using chart visualizations to determine, trends and relationships.

# Standout Section

Some questions were raised and these questions were answered with the aid of chart visualizations:

    1.Does Customer type affect the gross income of the supermarket? 
    2.Does the time of day, especially the hour affect the amount of sales in each branch?
    3.What time of day did the supermarket record its highest sales?
        3.1.What gender and customer type visited the supermarket during the 14th hour?
        3.2.Does the gender contribute to high sales at the 14th hour?
    4.What month recorded the highest sales?
        4.1.What month did the cities record their highest sales?
        4.2.What products did customers spend more on during the past months?
    5.Does the gender and customer type affect rating?
    6.What product line has the least ratings?

1.DOES CUSTOMER TYPE AFFECT THE GROSS INCOME OF THE SUPERMARKET
    Approach:
        Used a bar plot to generate visualization for the "product line" on x-axis then setting hue as "Customer type".

    Insights
        The average total price of goods purchased by the Member customers is higher than that of the Normal customers, also more quantities of products are purchased by Members, therefore leading to a higher gross income for this customer type.


2.DOES THE TIME OF DAY, ESPECIALLY THE HOUR AFFECT THE AMOUNT OF SALES IN EACH BRANCH?
    Approach:
        Used a line plot to generate visualization for the "Hours" on x-axis and "total", "quantity" and "gross income" on the y-axis

    Insights
        It was observed that at the 19th hour (7.00PM), Branch A made more sales, then, at the 14th hour (2.00PM) and 17th hour (5.00PM), Branch B made more sales while at the 11th hour(11.00AM), Branch C makes more sales. All these sales led to an increase in the overall gross income of the supermarket.Overall, Branch C has the highest gross income when compared to other branches


3.WHAT TIME OF DAY DID THE SUPERMARKET RECORD ITS HIGHEST SALES?
    Approach:
        Used a line plot to generate visualization for the "Hours" on x-axis and "total", "quantity" and "gross income" on the y-axis

    Insights
        It was evident from the charts that at the 14th hour(2.00PM), more quantities of products were sold, more purchases were made, therefore leading to a corresponding increase in the overall gross income.

    3.1.WHAT GENDER AND CUSTOMER TYPE VISITED THE SUPERMARKET DURING THE 14TH HOUR?
        Approach:
            Used a count plot to generate visualization for the "customer type" on x-axis, then setting hue as "Gender".

        Insights
             - More Members visited the supermarket than Normal customers.
             - The Male Gender visited the supermarket more than the Female Gender.

    3.2.DOES THE GENDER CONTRIBUTE TO HIGH SALES AT THE 14TH HOUR?
        Approach:
            Used a bar plot to generate visualization for the "Gender" on x-axis and "total" and "gross income" on the y-axis.

        Insights
            The Male Gender spend more on their purchases which results to a higher total price of good purchased which leads to an increase in the gross income of the Male Gender, thereby resulting to a corresponding increase in the overall gross income.

4.WHAT MONTH RECORDED THE HIGHEST SALES?
    Approach:
        Used a bar plot to generate visualization for the "Month" on x-axis with "total", "Quantity" and "gross income" on the y-axis

    Insights
        In the month of January, more quantities of products were purchased, leading to a higher total price in the amount of goods bought, thereby resulting to a much higher gross income when compared to other months.

    4.1.WHAT MONTH DID THE CITIES RECORD THEIR HIGHEST SALES?
        Approach:
            Used a bar plot to generate visualization for the "City" on x-axis with "total", "Quantity" and "gross income" on the y-axis, then setting hue as "Month".

        Insights
            - In the month of January, Abuja had its highest total price of goods purchased by the customers, leading to Abuja having a higher increase in gross income compared to other months.
            - In the month of January, Lagos had its highest total price of goods purchased by the customers, leading a higher increase in gross income compared to other months.
            - In the month of March, Port Harcourt had its largest quantities of products purchased and the highest total price of goods purchased by the customers, leading to a higher increase in gross income compared to other months.

    4.2.WHAT PRODUCTS DID THE CUSTOMERS SPEND MORE ON DURING THE PAST MONTHS?
        Approach:
            Used a bar plot to generate visualization for the "product line" on x-axis and "total" and "gross income" on the y-axis, then setting hue as "Month".

        Insights
            In the month of JANUARY, customers spent more on products from Food and beverages, Electronic accessories, Home and lifestyle and Health and beauty. In the month of FEBRUARY, customers spent more on products from Fashion accessories while in the month of MARCH, customers spent more on products from Sports and travel.

        4.2.1.WHAT PRODUCTS DID THE CUSTOMERS PURCHASE MORE IN THE BRANCHES DURING THE MONTHS?
            Approach:
                Used a line plot to generate visualization for the "product line" on x-axis and "total", "quantity" and "gross income" on the y-axis, then setting hue as "Month".
            Insights
                - It should be noted that in the month of February, all the product lines except Food and beverages and Sports and travel lines experienced a decrease in the quantities of goods purchased and also in their gross income compared to the previous month(January). Then in the month of March, all the product lines except the Electronic accessories, Health and beauty and Sports and travel product lines experienced a further decrease in the quantities of goods purchased and also in their gross income compared to the previous month(February).

                - It should be noted that in the month of February, all the product lines except Home and lifestyle experienced a decrease in the quantities of goods purchased and also in their gross income compared to the previous month(January). Then in the month of March, all the product linces except the Sports and travel, Home and lifestyle and Health and beauty lines experienced a further decrease in the quantities of goods purchased and also in their gross income compared to the previous month(February).

                - It should be noted that in the month of February, all the product lines except Fashion accessories and Health and beauty experienced a decrease in the quantities of goods purchased and also in their gross income compared to the previous month(January)
                . Then in the month of March, all the product linces except the Fashion accessories and Sports and travel lines experienced an increase in the quantities of goods purchased and also in their gross income compared to the previous month(February).

5.DOES GENDER AND CUSTOMER TYPE AFFECT RATINGS?
    Approach:
        Used a boxplot to generate statistical summary of "ratings" based on "Gender" and "Customer type"

    Insights
    - The genders gave high ratings but the Male gender gave much higher ratings.
    - The two customer types gave high ratings but the Normal customers gave much higher ratings.

6.WHAT PRODUCT LINE HAS THE LEAST RATINGS?
    Approach:
        Used a boxplot to generate statistical summary of "ratings" based on "Product line"

    Insights
    The Electronic accessories, Sports and travel and Health and beauty product lines received much higher ratings than products from the Food and beverages, Fashion accessories and Home and lifestyle product lines.


# Executive Summary.

To-Do - Include your Executive Summary document in your repository.

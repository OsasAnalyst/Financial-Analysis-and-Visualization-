# Finance Data Analysis & Visualization Project

## Objective of the Project
The primary objective of this project is to analyze the financial performance of Nike Inc using key financial metrics (KPIs) over a specific period. By leveraging Power BI, I created a comprehensive dashboard that allows stakeholders to visualize important financial metrics such as revenue, profit margins, expenses, and liquidity. The goal is to provide insights that can guide decision-making regarding cost management, profitability, and financial health.

## Step-by-Step Guide to Completing the Project

1. **Data Acquisition and Preparation**  
   The dataset used in this analysis consisted of financial statements, including Income Statements and Balance Sheets, from the company over multiple fiscal years. I imported this data into Power BI from Excel using the "Get Data" feature.

2. **Data Cleaning and Transformation (Power Query M Language)**  
   In Power Query, I performed several data cleaning and transformation steps, such as:
   - Removing unnecessary columns (empty columns, notes, etc.).
   - Ensuring each table (Profit & Loss, Balance Sheet, Cash Flow) is structured correctly, with fiscal years as columns and financial metrics as rows.
   - **Transposing the dataset** to facilitate effective visualization and summation of the values, ensuring that fiscal years became rows instead of columns. This restructuring enhanced clarity and accessibility of the data for analysis.
   - **Creating a year column** to bring out the year for better time-based analysis.
   - Renaming columns for better readability (e.g., renaming "FY '09" to "2009", "FY '10" to "2010", etc.).


3. **Creating Measures in DAX**  
   Using DAX (Data Analysis Expressions), I created several measures to calculate financial KPIs dynamically:
   - **Total Revenue:**  
     ```dax
     Total Revenue = sum('Profit & Loss Statement'[Revenues])
     ```
   - **Net Income:**  
     ```dax
     Net Income = sum('Profit & Loss Statement'[Net income])
     ```
   - **Gross Profit Margin:**  
     ```dax
     Gross Profit Margin = divide(sum('Profit & Loss Statement'[Gross Profit]),sum('Profit & Loss Statement'[Revenues]),0)
     ```
   - **Current Ratio:**  
     ```dax
     Current Ratio = divide(sum('Balance Sheet'[Total current assets]),sum('Balance Sheet'[Total current liabilities]),0)
     ```
   - **Operating Expenses:**  
     ```dax
     Operating Expenses = sum('Profit & Loss Statement'[Total selling and administrative expense])
     ```
   - **Operating Income:**  
     ```dax
     Operating Income = sum('Profit & Loss Statement'[Income before income taxes])
     ```

4. **Creating a Date Table**  
   To enhance time-based analysis, I created a date table for time intelligence:
   ```dax
   DateTable = CALENDAR(DATE(2009,1,1), DATE(2018,12,31))
   ```
   I established relationships between the fiscal year columns in my data and the Date Table, facilitating accurate time-based calculations.

5. **Report and Visualization Design**  
   After calculating the necessary KPIs, I designed the following visualizations in Power BI:
   - **Line Chart:**  
     Displaying Operating Expenses over time (by fiscal year) to show the trend of expenses.
   - **Clustered Bar Chart:**  
     Comparing Net Profit and Gross Profit Margin side by side across fiscal years to assess profitability performance.
   - **Stacked Column Chart:**  
     Visualizing Total Revenue and Net Income together to show the proportion of revenue retained as net income over the years.

6. **Insights and Recommendations**  
   Based on the visualizations and KPIs, I derived several insights:
   - **Profitability Trends:**  
     Gross profit margin and net income have shown consistent improvement over the years, indicating that the company is effectively controlling production costs and increasing profitability, but dropped by 54.4% for year 2018.
   - **Expense Management:**  
     The line chart of operating expenses indicated a gradual increase in costs, suggesting that the company should focus on cost management strategies to prevent expenses from outpacing revenue growth.
   - **Liquidity and Financial Health:**  
     The current ratio was consistently above 1, indicating that the company is in a favorable position to cover its short-term liabilities with its current assets.

   **Recommendations:**
   - Implement cost-cutting measures to prevent operating expenses from rising disproportionately.
   - Continue optimizing production processes to sustain or improve gross profit margins.
   - Monitor liquidity closely, ensuring that the Current Ratio remains healthy.

7. **Limitations of the Analysis**  
   While this analysis provided useful insights, several limitations were encountered:
   - **Data Availability:**  
     The dataset only covered a limited number of fiscal years. A more extensive dataset would provide a clearer picture of long-term trends.
   - **Lack of Industry Benchmarks:**  
     The analysis was not compared against industry benchmarks, making it difficult to gauge the company’s performance relative to competitors.
   - **Static Data:**  
     The data was static, meaning any real-time changes in financial performance were not reflected in the dashboard.

8. **Future Enhancements**  
   To further improve the analysis, I would recommend:
   - Adding more financial metrics such as Return on Assets (ROA) and Return on Equity (ROE).
   - Integrating industry benchmark data for comparative analysis.
   - Automating the data refresh process to keep the dashboard up-to-date with real-time financial data.

## Key Performance Indicators (KPIs) Used

- **Total Revenue:** Represents the total income generated from sales.
- **Net Income:** Measures the company’s profitability after all expenses are deducted.
- **Gross Profit Margin:** Indicates the percentage of revenue that exceeds the cost of goods sold.
- **Operating Income:** Shows the profit earned from core business operations.
- **Current Ratio:** Measures the company’s ability to cover short-term liabilities with current assets.
- **Operating Expenses:** Represents the total costs incurred in running the business, excluding the cost of goods sold.

## How This Analysis Can Benefit the Company

The insights from this analysis can help the company in several ways:
- **Strategic Decision-Making:** By understanding trends in profitability and expenses, management can make informed decisions regarding investments, cost-cutting measures, and growth strategies.
- **Improved Financial Health Monitoring:** KPIs such as the current ratio help in assessing the company’s liquidity, ensuring that short-term obligations can be met.
- **Enhanced Operational Efficiency:** Monitoring operating expenses enables the company to identify areas where costs can be reduced, leading to improved operational efficiency.

## Conclusion

This project demonstrates my ability to analyze financial data using Power BI, create meaningful visualizations, and derive actionable insights. By showcasing this project, I aim to highlight my skills in financial analysis, data visualization, and decision-making support using industry-standard tools.

![Screenshot](https://github.com/user-attachments/assets/e7c604e1-ed7e-433d-ae68-cd2e23ac2286)

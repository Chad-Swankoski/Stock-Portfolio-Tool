# Stock Portfolio Analysis Dashboard Tool

**By:** Chad Swankoski  
**Email:** Chad.Swankoski123@gmail.com  
**Phone:** (267-796-4055)

---

## Introduction

This Excel dashboard and analysis tool is designed to help retail investors track their stock holdings, monitor performance, and compare individual stocks for higher quality decision-making. It provides a structured and straightforward way to log stock purchases, calculate real-time gains and losses, and analyze trends using built-in visualizations. The included analysis tool allows for side-by-side company comparisons, making it easier to identify consistently high-performing investments.

---

## Key Features

- **Portfolio Calculations**  
  Log stock purchases with price, quantity, and date. The dashboard tracks values using Excel’s `STOCKHISTORY` function and calculates real-time gains/losses.

- **Data Visualization**  
  Charts and graphs track lifetime gain/loss, portfolio makeup, and market capitalization.

- **Performance Analysis**  
  Compare stocks with dynamic closing price history for different time periods.

---

## How To Use

### Inputting Stock Data

1. Go to the **Transactions** tab.
2. Fill in:
   - **Purchase Date**
   - **Company** – connects to stock exchange data.
   - **Ticker** – auto-fills.
   - **Transaction Type** – BUY or SELL.
   - **Units** and **Price**
3. Table auto-calculates Adjusted Units and Total Transaction Amount.

### Performing Individual Stock Analysis

1. Go to the **Analysis** tab.
2. Enter:
   - **Company name** under "Stock Search".
   - **Time period (in months)** under "Time Period".
3. The line chart updates accordingly.

### Performing Comparative Analysis

1. Go to the **Analysis** tab.
2. Input:
   - First company name under "Stock Search".
   - Time period (in months).
   - Second company name under "Comparison Company".
3. The double-line chart updates with new data.

### Sorting, Filtering & Customization

- **Sorting**: Use column headers in the Transactions tab.
- **Filtering**: Use Excel's built-in filters.
- **Customization**: Modify formulas, add stocks, or format to fit your needs.

---

## Technical Details

### Noteworthy Formulas and Functions

- **`STOCKHISTORY()`** – Fetches stock data.  
  _Example:_ `=STOCKHISTORY(C4, EDATE(TODAY(), -C6), TODAY())`

- **`IF()` / `IFERROR()`** – Conditional logic.  
  _Example:_ `=IF([@[Transaction Type]]="BUY", [@Units], -[@Units])`

- **`UNIQUE()` / `FILTER()` + `SUMIFS()`** – Unique stock list with units > 0.  
  _Example:_ `=UNIQUE(FILTER(TrackData[Company], SUMIFS(...)))`

- **`SUMIFS()`** – Calculates totals.  
  _Example:_ `=SUMIFS(TrackData[AdjustedUnits], TrackData[Company], B8#)`

- **`HYPERLINK()`** – Creates dynamic Yahoo Finance links.  
  _Example:_ `=HYPERLINK("https://finance.yahoo.com/quote/" & C8, "View Stock")`

- **Data Validation** – Used for dropdowns and error prevention.

- **Conditional Formatting** – Visual cues in key columns.

- **Sheet Protection** – Lock cells except input fields (e.g., L4, S4, L29 in Analysis tab).

---

## Why This Matters

This tool demonstrates data analytics, financial modeling, and Excel proficiency by organizing and analyzing stock data. It’s designed for both beginners and experienced investors to support better decision-making.

### Key Skills Demonstrated

- **Data Analytics** – Real-time calculations and trends.
- **Financial Modeling** – Investment growth and portfolio tracking.
- **Excel Proficiency** – Advanced functions and formatting.

### Practical Applications

- Investment management for retail investors.
- Financial analysis for finance-related roles.
- Business intelligence and decision-making.

---

## Potential Enhancements & Future Development

- **Live Stock Price Updates**  
  Integrate APIs or Power Query to replace `STOCKHISTORY`.

- **Automated Alerts**  
  Use macros to notify users of major price changes or thresholds.

- **Risk Metrics**  
  Add volatility, beta, and standard deviation tracking directly within the workbook.

---

## Known Bugs

- `STOCKHISTORY()` can return `#Connect` errors.  
  _Fix:_ Save > Close > Reopen workbook.

- Graphs may fail to resize after time period changes.  
  _Fix:_ Save > Close > Reopen or manually resize chart.

---

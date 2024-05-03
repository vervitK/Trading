# Zerodha API Integration for Stock Market Data Retrieval

This Python script provides functionalities to interact with Zerodha API for accessing stock market data, placing orders, and retrieving historical data.

## Prerequisites

Ensure you have the required Python libraries installed:

- `requests`
- `dateutil`

You can install these dependencies using pip:

```bash
pip install requests python-dateutil
```

## Setup

1. **API Authentication**:
   - Obtain your Zerodha API credentials (user_id, password, twofa) to authenticate API requests.

2. **Installation**:
   - Clone or download the script to your local machine.

3. **Run the Script**:
   - Open the script in your Python environment and execute it.

## Script Overview

The script provides the following functionalities:

- **Authentication**:
  - Authenticate user credentials and obtain the `enctoken` for subsequent API calls.

- **Zerodha API Wrapper**:
  - Implements a `KiteApp` class to interact with Zerodha API endpoints.
  - Provides methods for fetching instruments, quotes, historical data, margins, orders, and positions.

- **Data Retrieval**:
  - Retrieve historical market data for specified stock symbols within a date range.
  - Supports multi-threading for efficient data retrieval.

## Usage

1. **Initialize Zerodha API**:
   - Obtain the `enctoken` from Zerodha web and initialize the `KiteApp` instance.

2. **Retrieve Historical Data**:
   - Modify the `symbol_list` and date parameters to specify the stocks and date range for data retrieval.
   - Run the script to retrieve and store historical data in CSV format.

3. **Customization**:
   - Customize the script by adjusting API endpoints, adding new functionalities, or modifying data processing logic.

## File Structure

- `zerodha_api_integration.py`: Main script for Zerodha API integration.
- `nifty.csv`: CSV file containing stock symbols and IDs for data retrieval.
- `Data/`: Directory to store retrieved market data in CSV format.

## Notes

- Ensure you have valid Zerodha API credentials and permissions to access the required endpoints.
- Customize the script as per your specific requirements and data retrieval preferences.
- Use multi-threading for efficient data retrieval across multiple stock symbols and date ranges.


# Resampling Stock Market Data into 5-Minute Intervals

This Python script allows you to resample stock market data stored in CSV files into 5-minute intervals (OHLCV format) and save the resampled data to separate CSV files.

## Prerequisites

Before using this script, ensure you have the following installed:

- Python (3.x recommended)
- Required Python libraries (`pandas`, `numpy`, `glob`)

Install the required libraries using pip:

```bash
pip install pandas numpy
```

## Script Overview

The script performs the following tasks:

1. **Import Libraries**:
   - Import necessary libraries including `pandas`, `numpy`, `glob`, `datetime`, and `warnings`.

2. **Set Paths**:
   - Define the paths for reading original data (`path`) and saving resampled data (`path_to_save_data`).

3. **Read Files**:
   - Use `glob.glob()` to retrieve a list of file paths for the original data.

4. **Resampling Process**:
   - Loop through each file path and read the CSV file into a pandas DataFrame.
   - Convert the 'Date' and 'TIME1' columns to datetime format and set the 'Datetime' column as the index.
   - Resample the data to 5-minute intervals (`"5T"`), aggregating OHLCV values.
   - Filter the resampled data to include only market hours (between 09:15 AM and 03:25 PM) and remove any NaN values.

5. **Save Resampled Data**:
   - Rename columns for consistency (e.g., 'CLOSE' to 'Close').
   - Define the file save path for the resampled data.
   - Save the resampled data to a CSV file without including the index.

## Usage

1. **Specify Paths**:
   - Modify `path_to_save_data` and `path` variables according to your directory structure.

2. **Run the Script**:
   - Execute the script in your Python environment.

3. **Output**:
   - The resampled data will be saved as separate CSV files in the specified `path_to_save_data` directory.

## Notes

- Ensure that the original data files are in CSV format with columns for 'Date', 'TIME1', 'Open', 'High', 'Low', 'CLOSE', and 'VOLUME'.
- Customize the script as needed to handle different data formats or adjust the resampling parameters.
- Use this script to preprocess and organize stock market data for further analysis and modeling.



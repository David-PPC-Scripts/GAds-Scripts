Budget Tracking Scripts for Google Ads and Microsoft Ads
These scripts track monthly budget pacing for multiple locations and services by integrating Google Ads and Microsoft Ads spend data. The scripts alert you via email when actual spend deviates by more than 10% from the expected spend. Microsoft Ads data is imported through Google Sheets, allowing seamless integration with Google Apps Script.

Features
Combined Budget Tracking: Tracks budget from both Google Ads and Microsoft Ads.
Email Notifications: Sends alerts when spend deviates by more than 10% from the expected amount.
Regex-Based Filtering: Uses regular expressions to dynamically filter campaigns by location or service in both Google and Microsoft Ads.
Easy Microsoft Ads Integration: Microsoft Ads data is pulled into Google Sheets via Supermetrics.

Setup
Step 1: Set Up Microsoft Ads Data in Google Sheets
Open Google Sheets and launch the Supermetrics add-on.
Select Microsoft Advertising as the data source, and configure the following:
Date Range: Set to “First day of the month” to “Today.”
Metrics: Select Cost.
Split By: Choose Account Name.
Data Placement: Set up your query to start in cell A2.
Column A: Campaign names (e.g., containing location keywords such as "Location1").
Column B: Spend (in currency).
Schedule Refresh: Set Supermetrics to refresh daily to ensure the data is up-to-date.
Step 2: Update the Script Configurations
In the script, update the following configurations in the config object:

emails: List of emails to receive notifications.
microsoftSheetURL: Link to the Google Sheet containing Microsoft Ads data.
microsoftSheetName: Name of the sheet where Microsoft Ads data is stored.
microsoftDataRange: Range of cells in Google Sheets where Microsoft Ads campaign data is located.
locations or services: Each location or service should have:
name: The name of the location/service.
budget: The monthly budget for this location/service.
pattern: A regex pattern matching relevant campaign names in both Google Ads and Microsoft Ads.


Email Notifications
The main() function calculates the deviation from expected spend and sends an email if it is greater than ±10%. The email includes a summary table with budget tracking information for each location/service.


Troubleshooting
Incorrect Spend Data: Ensure that Supermetrics is pulling data from Microsoft Ads correctly and that microsoftSheetURL, microsoftSheetName, and microsoftDataRange in the script match the actual Google Sheets setup.
Regex Matching Issues: Verify that the pattern in each location/service is correct and matches the campaign naming convention in both Google Ads and Microsoft Ads.
Email Notifications Not Sending: Confirm that the script is authorized to send emails and that the emails list is correctly set.

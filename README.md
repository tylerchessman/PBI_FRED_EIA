# Enpublica data connector for Power BI
A custom Power BI Data Connector for the St. Louis Federal Reserve (FRED) and U.S. Energy Information Administration (EIA) database

### Summary
The Enpublica data connector provides easy access to over 1 million economic and energy-related time series directly in Power BI.  In addition to simple time series (i.e. date/value), the FRED and EIA databases also host a variety of multidimensional datasets.  Finally, this connector exposes a small set of supplemental datasets directly from Enpublica - including older historical data and a custom date dimension.

### Prerequisites
Each data source requires its own api_key - which needs to be obtained directly from the respective publisher:
* FRED - https://fred.stlouisfed.org/docs/api/api_key.html
* EIA - https://www.eia.gov/opendata/register.php
* Enpublica - Submit an <a href="mailto:api_key_request@enpublica.com?subject=New%20api_key%20request&body=I%20would%20like%20to%20request%20a%20new%20api_key%20for%20Enpublica%20datasets.">email request</a> for a new api_key.

### Connector Installation - Power BI Desktop
After obtaning the necessary api_key(s), download and register the connector in the Power BI Desktop; registration can be done either:
* Automatically.  Download and run the signed self-extracting installer - .  This file will install the connector, and add it as a trusted connection. **Note:** requires Admin privileges.
* Manually.  Download the connector file, Enpublica.pqx, and then:
    * Put the connector file in the local [Documents]\Power BI Desktop\Custom Connectors folder. If the folder doesn't exist, create it.
    * Adjust the data extension security settings; refer to https://learn.microsoft.com/en-us/power-bi/connect-data/desktop-connector-extensibility for instructions.

### Getting Started
Learn how to use the connector by working through the tutorials.



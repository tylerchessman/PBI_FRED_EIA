# Enpublica data connector for Power BI
A Power BI Data Connector for the St. Louis Federal Reserve (FRED) and U.S. Energy Information Administration (EIA) databases.

### Summary
The Enpublica data connector provides access to over 1 million economic and energy-related time series directly in Power BI.  In addition to simple time series (i.e. date/value), the FRED and EIA databases host a variety of multidimensional datasets.  This connector also exposes a small set of supplemental datasets directly from Enpublica - including historical data and a custom date dimension.

### Key Benefits
While the FRED and EIA databases provide access to datasets through a REST API, the Enpublica connector provides several ease-of-use and productivity benefits, including:
*  API Key management.  Instead of including api_key values directly in the URL, the Enbublica connector uses Power BI key authentication to keep keys secure and encrypted.
*  JSON parsing.  Many of the API calls require JSON parsing before the resultsets are usable within Power BI; the connector does this automatically.
*  Data type conversion.  Rather than having to manually find/adjust numeric and date values, the connector does this for you.
*  Automatic paging.  When retrieving large datasets, the APIs return only a subset of rows at a time.  The connector automatically pagination, and introduces waits to avoid hitting API call limits.
*  Parameter management.  Instead of having to manually append parameters to a URL, the connector allows parameters to be easily entered through the Power BI Query Editor.
*  Multi Series retrieval.  Need to retrieve multiple series at the same time?  The connector does this automatically - while also giving you the option to use series names (instead of series ids).

### Prerequisites
Each data source requires its own api_key - which needs to be obtained directly from the respective publisher:
* FRED - https://fred.stlouisfed.org/docs/api/api_key.html
* EIA - https://www.eia.gov/opendata/register.php
* Enpublica - submit an <a href="mailto:Support@enpublica.com?subject=New%20API_KEY%20Request&body=Hello%2C%20I%20would%20like%20to%20request%20a%20new%20api_key.%0A%0A%3CNewKeyRequestV1%20DO%20NOT%20MODIFY%20THIS%20LINE%3E">email request</a> for a new api_key.

**Note** - Each api key is stored/managed in Power BI, and only transmitted to the respective data source.

### Connector Installation - Power BI Desktop
After obtaning the necessary api_key(s), download and configure the connector in the Power BI Desktop; configuration can be done either:
* Automatically.  Download and run the signed self-extracting installer - <a href="https://github.com/tylerchessman/PBI_FRED_EIA/raw/main/Enpublica_DataConn_PBI.exe">Enpublica_DataConn_PBI.exe</a>.  This file will install the connector, and add it as a trusted connection. **Note:** requires Admin privileges.
* Manually.  Download the connector file Enpublica.pqx and then:
    * Copy the connector file to the local [Documents]\Power BI Desktop\Custom Connectors folder. If the folder doesn't exist, create it.
    * Adjust the data extension security settings; refer to https://learn.microsoft.com/en-us/power-bi/connect-data/desktop-connector-extensibility for instructions.

**Tip!**  If you install the connector _while_ Power BI Desktop is open, make sure you close/re-open Power BI Desktop to ensure the connector is loaded.

### Connector Installation - Power BI Service
To use this connector in the service (e.g., for scheduled refresh), you will need to enable custom data connectors in the gateway; this can be configured in the gateway app. Refer to https://learn.microsoft.com/en-us/power-bi/connect-data/service-gateway-custom-connectors for instructions.

**Update!**  See this <a href="./Tutorials/5_DataRefresh/Enpublica_DC_ForPBI_TGateway.pdf">quick tutorial</a> for using the gateway with the Enpublica data connector.

### Getting Started
Learn how to use the connector by working through the <a href="./Tutorials">tutorials</a>.



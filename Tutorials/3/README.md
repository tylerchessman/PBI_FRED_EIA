## Using the [Enpublica Data Connector](https://github.com/tylerchessman/PBI_FRED_EIA) for Power BI – Tutorial 3 (Additional FRED API Calls)

_A new data connector provides easy access to over 1 million economic and energy-related time series directly in Power BI_

### Summary

In the first few tutorials, we looked at how to connect to the FRED database – and focused primarily on using two calls ( **fred\_series** and **fred\_series\_observations** ) to retrieve series related metadata and observations. In this post, we review some of the other FRED API Calls, including the use of categories and releases to simultaneously query/import multiple related series.

### Getting Started

Download the report for this tutorial, [Enpublica_Tutorial3.pbix](https://github.com/tylerchessman/PBI_FRED_EIA/raw/main/Tutorials/3/Enpublica_Tutorial3.pbix) (note – this tutorial uses data from the FRED database, you'll need to obtain an api key to refresh the data; see Tutorial 1, part 1 for details, or visit the FRED website to [request a key](https://fred.stlouisfed.org/docs/api/api_key.html)). Then, open the report in Power BI Desktop.

![](./images/Picture1.png)

Next, open the Power Query Editor by clicking **Transform data** from the **Home** Ribbon. You'll notice several query Groups (ctgry, misc, releases, series, and sources), function definitions, and queries have already been added to this report:

![](./images/Picture2.png)

As a quick reminder, these initial functions definitions were added by clicking **New Source** (from the Home Ribbon), selecting the **Enpublica** Connector, and then (after choosing **enpublica\_FRED** as the initial Data Source) selecting all the functions in the Navigator window:

![](./images/Picture3.png)

Let's now review the functionality/use cases for these functions.

### Function Definitions

#### Category functions

- **fn\_fred\_category** – returns a category given a particular category id.

![](./images/Picture4.png)

- **fn\_fred\_category\_children** – returns the child categories for a given category id. Note, a category can contain multiple _levels_ of child categories; this function returns only the top-level children.

![](./images/Picture5.png)

- **fn\_fred\_category\_series** – returns all series for a given category id, with optional parameters used for filtering.

![](./images/Picture6.png)

#### Miscellaneous functions

- **fn\_delimited\_string\_from\_table** – this isn't part of FRED - rather, it is a utility function that can come in handy when trying to pass the _output_ of an API call as an _input_ to another call. For example, in the pictures below, the output of **qry\_fred\_category\_series** (a table containing the series metadata for a given category id) is invoked to generate a comma delimited string.

![](./images/Picture7.png)

![](./images/Picture8.png)

This string value ( **qry\_delimited\_string\_from\_table** ) is then used in the query **qry\_fred\_series\_observations** as the first parameter.

![](./images/Picture9.png)

Note: If this is a bit confusing, check out the video tutorial (link at the beginning of this tutorial) to see it in action.

- **fn\_fred\_other.** The Enpublica Data Connector implements most of, but not all, the various API calls available from FRED. To make use of one of the calls not explicitly implemented, you can use **fn\_fred\_other** (note, calling this function will require a bit more custom transformation – as the native output from FRED is json)

![](./images/Picture10.png)

![](./images/Picture11.png)

#### Releases tables/functions

- **releases** – this table returns information about the 300+ sources that make up the FRED database.

![](./images/Picture12.png)

- **fn\_fred\_release\_series** – similar to fn\_fred\_category\_series, this function returns the series for a given release id.
- **fn\_fred\_release\_table** – returns a "release table" for a given release id and optional element id. To get familiar with release tables, head over to the FRED site and browse by Release. For example, as shown in the animated picture below, navigate to [https://fred.stlouisfed.org](https://fred.stlouisfed.org/); select the **Release** link, and then find/select **Gross Domestic Product**. Then, select **Section 1 – Domestic Product and Income**. You'll see several tables – select **Table 1.1.6. Real Gross Domestic Product, Chained Dollars** , and then **Quarterly**. The resulting table summarizes the key accounts that comprise GDP (personal consumption, investment, net exports, and government) for the latest quarter.

![](./images/ReleaseTable.gif)

To see an example of using this API call, look at the query **qry\_fred\_release\_table** and (in the Power BI Desktop) the visual titled **Release Table** in the **Release** page.

![](./images/Picture14.png)

![](./images/Picture15.png)

#### Series functions

- fn\_fred\_series – returns metadata about one or more series, this has been used heavily in prior tutorials
- fn\_fred\_series\_observations – also discussed in prior tutorials, this returns the observations for one or more series.

#### Sources table

- **sources** – returns a table containing the 110+ sources used by FRED

![](./images/Picture16.png)

### Summary

We've wrapped up the initial tutorials covering the FRED-related functions and tables. In the next set of tutorials, we'll turn our attention to the API calls available from the U.S. Energy Information Administration (EIA) – stay tuned!

## Fixing Connection Errors for New Data Sources

In Power BI, you are often prompted to enter credentials when connecting to a new data source. If you enter incorrect credentials the first time, it can be a bit tricky to fix the problem. For example, let's use the Enpublica Data Connector for Power BI.

![](RackMultipart20230512-1-46c724_html_f62ac026f1a7c15d.png)

After clicking the OK button, we are prompted for an api\_key. In this example, we intentionally enter an invalid key.

![](RackMultipart20230512-1-46c724_html_5b6f254ca0622565.png)

We click Connect – and receive an error message.

![](RackMultipart20230512-1-46c724_html_2ee320f20021ec9d.png)

If we click **Retry** , it attempts to reconnect using the _same credentials_. If we instead click **Edit** , it presents the initial Data connection window again.

![](RackMultipart20230512-1-46c724_html_f62ac026f1a7c15d.png)

We click **OK** , but we're back to the error window!

![](RackMultipart20230512-1-46c724_html_2ee320f20021ec9d.png)

What do we do? Don't break anything. Take a deep breath, cancel out of this dialog box and then, from the **Home** ribbon of the Power BI Desktop, click **Transform data – Data source settings.**

![](RackMultipart20230512-1-46c724_html_8545b0521e6c1b4c.png)

Find the corresponding Data Source – add click Edit Permissions to try again!

![](RackMultipart20230512-1-46c724_html_dc52f44ea573a3f4.png)

Last Saved: 5/12/2023 3:29:00 PM

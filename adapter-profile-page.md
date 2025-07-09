## Metadata_Start 
## code: en
## title: Adapter Profile Page 
## slug: adapter-profile-page 
## seoTitle: Adapter Profile Page 
## description: Learn how to navigate and utilize the Adapter Profile Page in Axonius to configure and manage integrations for comprehensive IT asset visibility. 
## contentType: Markdown 
## Metadata_End
The **Adapter Profile** page shows you information about each adapter, including all the connections on that adapter and their status. In addition, it provides access to links to configure **Advanced Settings** for  **Adapter Configuration**, **Advanced Configuration**, **Ingestion Rules Configuration** and **Discovery Configuration**. 

![Adapter Profile New.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/Adapter%20Profile%20New.png){height="" width=""}

The **Adapter Profile** shows the adapter description, the asset types the adapter fetches and information about the adapter connection as well as its status. Hover over to see more details. When you click on a connection, the **Edit Connection** drawer opens for more details. You can copy the URL and share it with others for direct access.

To sort by a specific value, click on a column. For instance, you can sort by **Connection Status**. Note that sorting is not available for complex fields and **Connection Label**.

## The Side Pane
The side pane header  presents a summary of the adapter's information at a glance: The logo, category and number of connections and their status.
 
You can click the arrow to collapse and expand the side pane. Use **Search** to find any value in the side pane.

### Viewing More Connection Information
Click on **Adapter Profile** in the side panel  to display a summary of the Adapter connection configuration for each of the connections for that adapter. Each connection and its connection status is displayed on a different row. Click on the **Adapter Connections** button at the top of the page to view further information about the Adapter connections.
Click on **Adapters Fetch History** to display  **Adapters Fetch History**  filtered by that adapter.

![Adapter Profile Adapter Fetch History.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/Adapter%20Profile%20Adapter%20Fetch%20History.png){height="" width=""}


In the  **Advanced Settings** section you can  configure: 

* [Adapter Configuration](/pl/docs/advanced-settings) (Advanced Settings for each adapter)
* [Advanced Configuration for Adapters](/pl/docs/advanced-configuration-for-adapters)
* [Ingestion Rules Configuration](/pl/docs/setting-adapter-ingestion-rules)
* [Discovery Configuration](/pl/docs/adapter-discovery-configuration)


## Searching for Settings

Use the Adapter Profile page to search for settings in two places:

### Search Connections
You can search for information about connections using the Connections Search bar. Enter any value to search the connections table.
![Adapter Profile Search Bar.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/Adapter%20Profile%20Search%20Bar.png){height="" width=""}

 


### Search Settings in Side Pane

 
Enter search text in the **Search** bar in the left pane to easily search the **Connections** and **Configuration** settings names, as well as the titles and field names in the configuration pages for any setting that you need. This includes  search to easily find any Advanced Configuration setting for that adapter. As soon as you start entering text in the search bar,  a list of options containing the search text appears, with the search text highlighted in blue.
Once you have results, select the entry you need to jump to it. Click X on the right of the search bar to close the list of options. 

![Search](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/Search.png){height="" width=""}

 
#### Adding a New Connection
Click **Add Connection** to add a new connection for this adapter. Refer to [Adding a New Adapter Connection](/pl/docs/adding-a-new-adapter-connection).




 

 
For Axonius-hosted (SaaS) customers only:
* An Axonius Gateway  is required to connect adapters whose sources are only accessible by an internal network and not from the internet. Use **Manage Gateways** to add a Gateway for this adapter if required. 
* For details about configuring and installing the Axonius Gateway, see [Installing the Axonius Gateway](/docs/installing-axonius-tunnel).
 
<br>



 
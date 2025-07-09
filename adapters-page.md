## Metadata_Start 
## code: en
## title: Adapters Page 
## slug: adapters-page 
## seoTitle: Adapters Page 
## description: Learn how to work with Axonius adapters to configure integrations with Axonius. 
## contentType: Markdown 
## Metadata_End
The **Adapters** page displays the list of the solutions Axonius integrates with, called adapters. 

To open the **Adapters** page, click the **Adapters** icon on the left navigation panel. If you are working with a smaller screen, you may need to click **More** to find the **Adapters** icon.

The **Adapters** page shows all the adapters in the system, the category to which they belong, the assets they fetch and their connection status.  You can use categories and asset types to help you decide which additional adapters you can connect, and to easily find adapters relevant for your use case and the asset types you want to investigate.


The adapters are arranged as cards. The top section of the page shows  adapters that have connections configured (out of all available adapters) in alphabetical order, while all the other adapters are shown below.


When you choose an adapter category, **Configured Adapters** shows the number of adapters configured in that category out of all the adapters available in that category.


![Adapters Page New without graphics.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/Adapters%20Page%20New%20without%20graphics.png){height="" width=""}




 



## Card Information

 

![TileExample](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/TileExample.png){height="" width=""}

The following information is shown on each adapter card:

* **Adapter logo** - A unique logo that represents the adapter in the Axonius system.
* **Adapter Name** - The name of the adapter.
* **Assets Fetched** - Adapters can fetch a wide range of assets. Some assets are fetched by default for that adapter, while others must be configured using advanced configuration. Up to four asset types are displayed for each adapter, if there are more, a number shows that there are more asset types. Hover over to see all asset types in a list.
*    **Category** - Categories to which the adapter belongs. An adapter can belong to more than one category. Up to three categories are displayed for each adapter, if there are more, a number shows that there are more categories. Hover over to see all categories in a list.
*    **Number of connections and their status** - Each adapter can have more than one connection. The numbers show the number of connections, while the color indicates their status.  
        * Green - The number of successfully connected connections for this adapter. 
        * Red - The number of configured adapter connections with connection errors.
        * Dark gray - The number of configured connections set as inactive  for this adapter.


* Hover over the card to see the adapter description.
* Hover over the right corner of the card, and from the 3-dot menu select:
  

    ![AdapterOptionsTile](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AdapterOptionsTile.png){height="" width=""}


    * **Add Connection** to add a [new adapter connection](/pl/docs/adding-a-new-adapter-connection)  



  

 

### Finding Adapters
You can use the search and filters to find adapters you want to connect.

**Search Adapters**
Type in the **Search Adapters** field to find adapters, as soon as you start typing, the system presents you with possible matches.
 
![Search Adapters New.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/Search%20Adapters%20New.png){height="" width=""}

**Search Categories**
Click in the **Search Categories** field to search for one or more category names. All the adapters in those categories are displayed. 
![Search Adapter Categories.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/Search%20Adapter%20Categories.png){height="" width=""}

The system also shows you how many adapters in the category you have already configured. Note that *Configured adapters*  relates to the number of adapters in the category you chose and not to the total number of adapters in the system.

 

Click **x** next to an adapter category to remove it from the selection or use **Clear All** to clear all your choices.

**Search Asset Types**
Click in the **Search Asset Type** field to search for one or more asset types. All the adapters that fetch that asset type are displayed.  Learn more about [asset types](https://docs.axonius.com/docs/assets-page#viewing-assets-by-type).
   

 

![Search Asset Types Adapters Page.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/Search%20Asset%20Types%20Adapters%20Page.png){height="" width=""}

Click **x** next to an adapter category to remove it from the selection or use **Clear All** to clear all your choices.

<br>

### Changing Views
The adapter list can also be displayed as a table.
Use the card/table button to toggle the views. The same information is shown on the table as on the cards.

![AdapterviewToggle](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AdapterviewToggle.png){height="" width=""}

![Adapter Table View.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/Adapter%20Table%20View.png){height="" width=""}

### Asset Inventory
Connecting adapters enables Axonius to pull asset information from many sources across the organization. The more adapters you connect, the more comprehensive your asset inventory will be. It is recommended you connect any of the following to Axonius adapters:

* **Device and User management consoles**: such as [Microsoft Active Directory](/docs/microsoft-active-directory-ad){target="_blank"}, [Microsoft Endpoint Configuration Manager (MECM) (formerly SCCM)](/docs/en/microsoft-sccm){target="_blank"}, or [Jamf Pro](/docs/en/jamf-pro){target="_blank"}.

* **Endpoint security agents**: such as [McAfee ePolicy Orchestrator (ePO)](/docs/mcafee-epolicy-orchestrator-epo){target="_blank"}, Symantec, [CrowdStrike Falcon](/docs/crowdstrike-falcon){target="_blank"}, or [VMware Carbon Black EDR](/docs/carbon-black-cb-response){target="_blank"}.

* **Networking**: Axonius integrates with networking infrastructure from a wide variety of vendors including [Aruba](/docs/aruba){target="_blank"}, [Cisco](/docs/cisco){target="_blank"}, [Checkpoint](/docs/checkpoint-infinity){target="_blank"}, [Fortinet](/docs/fortinet-fortigate){target="_blank"}, [Juniper](/docs/juniper-junos){target="_blank"}, and [Palo Alto](/docs/palo-alto-networks-panorama){target="_blank"}.

* **Identity Access Management**: such as [Okta](/docs/okta){target="_blank"}, [Google Workspace (formerly G Suite)](/docs/g-suite-by-google){target="_blank"}, [Duo Beyond](/docs/duo-beyond){target="_blank"}, or other platforms

* **Vulnerability / Patch Management:** such as [Qualys Cloud Platform](/docs/qualys-cloud-platform){target="_blank"}, [Tenable Nessus](/docs/tenable-nessus){target="_blank"}, [Rapid7 Nexpose](/docs/rapid7-nexpose){target="_blank"}, [Kenna Security Platform](/docs/kenna-security-platform){target="_blank"}, or other platforms.

* **Cloud Providers**: such as [Amazon Web Services](/docs/amazon-web-services-aws){target="_blank"}, [Microsoft Azure](https://docs.axonius.com/docs/microsoft-azure){target="_blank"}, or [Google Cloud Platform](/docs/en/google-cloud-platform-gcp){target="_blank"}.

* **Collaboration**: such as [Asana](/docs/asana){target="_blank"}, [Airtable](/docs/airtable-enterprise){target="_blank"}, [Docusign](/docs/docusign){target="_blank"}, [Zendesk](/docs/zendesk){target="_blank"},  [Zoom](/docs/zoom){target="_blank"}, and more.

To see a full list of supported adapters, visit [Adapters List](https://docs.axonius.com/docs/adapters-list).


<Br>



## Adding a New Adapter Connection 

 
To connect a new adapter, provide the access credentials needed.  The details vary by adapter, but include some combination of:
1. IP Addresses
2. User Names
3. Passwords
4. API keys
5. Key Files
6. Any other credentials needed to access the adapters being used

For example, the **Amazon Web Services (AWS)** adapter configuration drawer:
![AWSEG1](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AWSEG1.png){height="" width=""}

You can add a new adapter connection either from the **Adapters** page or from the **Connections** page.
Learn more about [Adding a New Adapter Connection](/docs/adding-a-new-adapter-connection).   



## Bulk Set Advanced Settings
 
Use **Bulk Set Advanced Settings** to set  [Adapter Advanced Settings](/docs/advanced-settings) values for all adapters or for adapters without configured connections. You can use this to set new defaults for Adapter Advanced settings on your system.
:::(Info) (Note:)  
To modify the advanced settings for a single adapter, click the relevant adapter and then  **Advanced Settings**.
:::
In  **Bulk Set Advanced Settings**, select the settings you want to set for all adapters, then set the required value in the corresponding input fields.
Then select whether to apply these new values to all adapters or only to adapters without configured connections.
![BulkSEt](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/BulkSEt.png){height="" width="500"}
    
 ## Adapters Fetch History
 The [**Adapters Fetch History**](/adapters-fetch-history) opens the Adapters Fetch History page and displays the fetch results over time for each adapter and for specific adapter connections.
 
##  Connections
Click **Adapter Connections** to open the **Connections** page. The **Connections** page displays detailed information about each connection. See **[Adapter Connections](/docs/adapter-connections)**.
 
 
<br>
  
 



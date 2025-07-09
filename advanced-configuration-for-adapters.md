## Metadata_Start 
## code: en
## title: Advanced Configuration for Adapters 
## slug: advanced-configuration-for-adapters 
## seoTitle: Advanced Configuration for Adapters 
## description: Learn how to set up advanced Configuration for Axonius adapters to make the most of the integrations for comprehensive asset inventory 
## contentType: Markdown 
## Metadata_End


You can configure Advanced Configuration parameters for a  wide range of adapters.
You can configure the Advanced Configuration parameters for all connections for an adapter, or configure separate parameters for each adapter connection. Configuring separate parameters for each connection can be useful if you want to configure a number of fetch cycles for the same set of assets. For instance, if you want to configure a light frequent fetch cycle, and a fetch cycle which is less frequent but consumes more resources.
 
##  Configuring  Advanced Configuration Parameters for all Connections
 
To configure Advanced Configuration parameters for all connections for an adapter:
1.     Select the adapter you want to configure
2.     Under  **Advanced Settings**, select **Advanced Configuration**.
 
    ![AdvacnedSettingsADaptersNew](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AdvacnedSettingsADaptersNew.png){height="" width=""}

    
 

 

3.     Verify that **Enable advanced configuration  for each connection separately** is not toggled on.

![AdvConfigig](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AdvConfigig.png){height="" width=""}


4.     Configure the settings as required as explained in the relevant documentation for the adapter.
<br>

##  Configuring  Advanced Configuration Parameters for each Connection
 
 To configure separate advanced configuration parameters for each connection for an adapter:
 
1.     Under  **Advanced Settings**, select **Advanced Configuration**.
   ![AdvacnedSettingsADaptersNew](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AdvacnedSettingsADaptersNew.png){height="" width=""}


 
2.     Toggle on **Enable advanced configuration  for each connection separately**.
 

![EnableAdvConfig](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/EnableAdvConfig.png){height="" width=""}
 
3.     Click **Save.** The **Advanced Configuration** tab now also appears on the **Add Connection** drawer.
4.     Click **Add Connection**. The **Connection Configuration** drawer now has 2 tabs.
 

![AdvConfig5](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AdvConfig5.png){height="" width=""}

5. Configure the  **Connection Configuration** tab.
6. Click **Advanced Configuration**.

 

![AdvConfig5a](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AdvConfig5a.png){height="" width=""}


7.     Toggle on **Enable advanced configuration**. The advanced configuration parameters are displayed with the default settings for this adapter.
 
8.     Configure the required parameters for this connection. If you do not configure specific parameters, the connection uses the default settings for that adapter.
 
9.     If necessary, set a specific scheduling for this connection. Refer to [Adapter Discovery Configuration]( /docs/adapter-discovery-configuration).
 

10. After completing the configuration, select either **Save** or **Save and Fetch**.

 

![adv6New](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/adv6New.png){height="" width=""}


:::(Info) (Note:)
Once you have configured advanced configuration for a specific adapter connection, if you toggle off the configuration, the system keeps your choices.
:::
 
 

<br>
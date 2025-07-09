## Metadata_Start 
## code: en
## title: Adding a New Adapter Connection 
## slug: adding-a-new-adapter-connection 
## seoTitle: Adding a New Adapter Connection 
## description: Find out how to add a new adapter connection in Axonius to seamlessly integrate and manage your IT systems for enhanced asset visibility and control. 
## contentType: Markdown 
## Metadata_End
You can add a new adapter connection either from the **Adapters** page or from the **Connections** page.


:::(Info) (Note:)
 
* The Axonius-hosted (SaaS) instance resides in the cloud and is not part of your organization's internal network. Axonius securely fetches data from the organization's data sources, known as adapters.
* The Axonius Gateway enables establishing a link between  an internal network or segregated network (for Customer-hosted (on-premises / private cloud)) and the primary Axonius instance.
* Axonius Gateway is only required to connect adapters whose sources are only accessible by an   internal network or segregated network (for Customer-hosted (on-premises / private cloud)) 
* Axonius Gateway is not required to connect adapters whose sources are accessible from the internet or the primary Axonius instance.
* Once a Gateway is successfully installed, you need to select the Gateway in the **Adapter Configuration** drawer under the **Gateway** field.
* For details on configuring and installing the Axonius Gateway, see [Installing the Axonius Gateway](/docs/installing-axonius-tunnel).
:::


 

## Adding a New Adapter Connection from the Adapters Page

To add an adapter connection, do the following:
1. In the left navigation panel, click the ![Adapters icon.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/Adapters%20icon%281%29.png) icon. The **Adapters** page opens.
2. Hover over the adapter card and from the 3-dot menu choose **Add Connection**. The **Add Connection** drawer opens.

 
    ![AddConnectionMa](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AddConnectionMa.png){height="" width=""}

3.  Or click on the adapter card, and the **Adapter Profile** page opens displaying the list of configured connections for that adapter (if connections are already configured).
 
![Adapter Profile New.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/Adapter%20Profile%20New.png){height="" width=""}


4. Click **Add Connection** at the top of the page. The **Add Connection** drawer opens.
5. See [Setting Adapter Connection Parameters ](/docs/Adding-a-new-adapter-connection#settin-adapter-connection-parameters) for more information, and refer to the specific adapter page for configuration details for each adapter.

## Adding a New Adapter Connection From the Connections Page


1. On the adapters page, click **Adapter Connections**. The **Connections** page opens.
2. Click **Add Connection**  ![AddConnectionButton.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AddConnectionButton.png) to add a new adapter connection. 
3. The **Add Connection** drop down box appears.



![AddConnectionsNew](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AddConnectionsNew.png){height="" width=""}

4. Click the arrow to select an adapter.


![AddconnectionDropDown.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AddconnectionDropDown.png){height="" width=""}

5. Click **Next**.


![AddConnectionNExt.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AddConnectionNExt.png){height="" width=""}

The **Add Connection** drawer for the adapter you chose opens.

![AWSEG1](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AWSEG1.png){height="" width="500"}


6. See [Setting Adapter Connection Parameters ](/docs/Adding-a-new-adapter-connection#setting-adapter-connection-parameters) for more information, and refer to the specific adapter page for configuration details for each adapter.


## Setting Adapter Connection Parameters

The connections you set in the Adapter Connection parameters drawer are specific for the connection you are currently configuring.
Configure the required settings for each adapter.  Refer to the parameters in the documentation for each parameter for more details. 
In addition, you can configure the following:
1. **Connection Label** *(optional, default: empty)* - An optional label to help distinguish between multiple connections for the same adapter. This label is concatenated to the relevant Adapter Name in the **Asset Profile** page and the full text is visible when you hover over the **Adapters** column in the assets pages. It is also possible to query the connection label in the **Query Wizard**, otherwise only the adapter name is displayed.

      @(Info)(Note:)(Some adapters require additional steps to gain the relevant connection details, such as generating API keys or other steps. To understand the required actions for connecting each adapter, open its connection documentation page. For more details, see [Adapters List](/docs/adapters-list) on the product documentation and the [Adapter list on the Axonius website](https://www.axonius.com/platform/adapters/).)
2. **Add Note** - add a note of up to 50 characters for this adapter connection. 
3. **Select Gateway** -  Select the Gateway to use when connecting adapters whose sources are only accessible by an internal network. To use this option you need to set up an Axonius Gateway.
4. The **Active Connection** toggle button is set to on by default and when switched on, the configured connection is considered as **active**.
     * The connection can be saved and fetch data from its source. Therefore once you fill in all the required parameters on the Connection Configuration drawer:
         * The **Check Network Connectivity** button is enabled.
          * The **Save and Fetch** button is enabled.
         * During a discovery cycle, data is fetched from the source of this connection.
3. To set the connection as inactive, switch off the Active Connection toggle button. When switched off, the configured connection is considered as **inactive**
    * The connection can be saved, but it will not fetch data from its source. Therefore:
        *  The **Check Network Connectivity** button is disabled.
        *  The **Save and Fetch** button is  disabled  
        *  During a discovery cycle, this connection will be ignored and no data will be fetched from its source, but all your settings are saved.        
4. To test the network connectivity to the supplied hostname or  IP address, click **Check Network Connectivity**. 
5. To save the configuration changes and to initiate data fetch from the configured source, click **Save and Fetch**.
6. To save the configuration changes without initiating data fetch, click **Save**.

 


Once you create a connection, the connection is added to the adapter's connection list and to the Connections page:
* If the adapter connection is connected successfully,   ![image.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/image%28160%29.png)  icon is displayed on the adapter connection record. 
* If the connection has an error, error icon ![image.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/image%28161%29.png)  appears.
* If the connection is inactive, inactive icon ![image.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/image%281336%29.png) appears.
@(Info)(Note:)(Axonius generates activity log events, and additional [Syslog messages](/docs/configuring-syslog-settings), [HTTPs Log](/docs/configuring-https-log-settings) messages, and [emails](/docs/configuring-email-settings), if those are enabled. For details, see [Managing External Integrations](https://docs.axonius.com/docs/managing-external-integrations). )
To see the connection error reason and to fix the configuration, on the **Adapter** page click the connection record to open the **Add Connection** drawer. Or, on the **Connection** page click any of the fields except for the Adapter name, see [Editing Connection Information](/docs/adapter-connections#editing-connection-information-for-a-specific-adapter) 

![image.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/image%28159%29.png){height="" width=""}

In addition, you can set various Advanced Settings for each adapter. Refer to [Advanced Settings](/docs/advanced-settings).

:::(Info) (Notes:)
* Each adapter includes documented connection instructions. To view the instructions, click  help ('?').
* You can connect multiple connections. For example, to connect multiple Microsoft Active Directory (AD) domain controllers, configure a different connection for each domain controller.
* When the Axonius VM connects to these connections, it must have connectivity to that address, i.e. it must be able to connect to that IP/URL on that port.
* All fields not marked as 'optional' are mandatory and must be populated.
:::

## Configuring an Adapter API Gateway Connection (Optional)
Some adapters have the option to add a connection using API gateway parameters for authentication. In these adapters, the **Add Connection** drawer contains an **API Gateway** toggle, disabled by default.

![GatewayToggle](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/image-3EV3K622.png){height="" width="600"}

When you enable **API Gateway**, the option to select an **API Gateway Type** becomes available. The API gateway parameters that appear depend on the type selected.

:::(Info) (Note)
When you use an API gateway connection, the other authentication parameters are not required.  However, to add the connection successfully, you need to enter placeholder values in these fields.
:::

### Layer7 API Gateway Parameters
Layer7 API Gateway ensures secure communication by filtering requests, enforcing rate limits, and validating authentication tokens before forwarding them to the backend services. 

![Layer7](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/image-FTSJRKKS.png){height="" width="600"}

The fields required for authenticating Layer7 API Gateway are as follows:
* **Client ID** - The Client ID you set up in Layer 7.
* **Client Secret** -  The Client Secret you set up in Layer 7.
* **Service Name Suffix** - The suffix appended to the API Gateway Host Name to construct the full endpoint of the target service. 
* **Host name or IP Address** (from the adapter fields) - the API Gateway Host Name.
While authentication requests are sent directly to the Host Name, i.e., the API Gateway domain, all other service requests are routed to the appropriate service by appending this suffix.



## Connecting your SSO Solution Provider 
Single Sign-On (SSO) solutions such as Okta, Microsoft Entra ID (Azure AD) and others, provide authentication and access management capabilities that enable organizations to ensure secure access to all corporate accounts, whilst providing visibility into this access at a granular per-user-level.

Axonius SaaS Management leverages the data fetched from an adapter that is configured as an 'SSO Provider' as part of its logic to determine managed and unmanaged applications and users.

When connecting an adapter that is used as your organization's SSO solution, the **SSO provider** option should be switched on.

<br>
## Metadata_Start 
## code: en
## title: Adapter Discovery Configuration 
## slug: adapter-discovery-configuration 
## seoTitle: Adapter Discovery Configuration 
## description: Learn how to configure adapter discovery in Axonius to ensure comprehensive and accurate detection of IT assets across your environment. 
## contentType: Markdown 
## Metadata_End
The discovery cycle is set globally for all adapters.
You can also set a custom discovery cycle for a specific adapter and all of its connections, or for a specific adapter connection.


To set custom discovery cycles:
1. Click ![Adapters icon.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/Adapters%20icon%281%29.png) to open the **Adapters** page.
2. Search for and click the relevant adapter. The **Adapters Profile** page opens displaying the list of connected connections.
3. Under **Advanced Settings**, select **Discovery Configuration**.

    ![AdvDiscovery1New](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AdvDiscovery1New.png){height="" width=""}


 The **Discovery Pane** opens:
 

![ADapterDiscN](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/ADapterDiscN.png){height="" width=""}
 


## Adapter Custom Cycle
Use **Adapter Custom Scheduling** to set a custom discovery cycle for an adapter.  Axonius will fetch data from all of the adapter’s connections as part of the custom cycle, unless a specific connection has its own [Connection Custom Cycle](#connection-custom-cycle).

To configure an adapter custom cycle:

1. Under the **Adapter Custom Scheduling** section, toggle on **Enable custom scheduling of discovery for this adapter**.

   

![AdvDiscvocery2](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AdvDiscvocery2.png){height="" width=""}


2. Configure the discovery scheduling for the adapter:

### Setting Repeat Scheduled Discovery
From  **Repeat scheduled discovery** select the repeat option for the scheduled discovery. The following options are available

  *  **Every x hours**  - The adapter custom cycle runs every number of hours defined in the **Repeat scheduled discovery every (hours)** field.
        *  The adapter custom cycle start time is determined based on the specified value, starting midnight. For example, if the specified value is 6, the custom discovery times are 12am, 6am, 12pm, 6pm, 12am, etc.
        *       The start time for the first adapter custom discovery is the closest interval. For example, If the specified value is 6, and the configuration was saved at 10am, the next adapter custom discovery starts at 12pm.
        * The maximum possible interval is 24.
*    **Every x days** - The adapter custom cycle  runs at the time specified in the  **Scheduled discovery time** field every number of days as defined in the **Repeat scheduled discovery every (days)** field. The start time is determined based on the specified value, starting the 1st of each month. For example, if the specified value is 10, the discovery is triggered on 1st, 11th, 21st, 31st (if it exists), 1st, 11th, etc. The first start time is the closest interval. For example, If the specified value is 10, and the configuration was saved on the 12th, the  next discovery will be on the 21st. The maximum possible interval is 30.
* **Days of week** - The adapter custom cycle runs at the time specified in **Scheduled discovery time** field on the selected days of the week.   
*  **Days of month** - The adapter custom cycle runs at the time specified in **Scheduled discovery time** field on the selected days of the month.   

     
### Setting More Than One Scheduled Discovery Time

When you choose   **Every x days** or  **Days of week** you can set a number of discovery times that will run at set hours on the days that you chose.  In this way you can run a discovery time, at defined hours, and not every X hours, for instance to fit in with specific events during the working day.

* Click the + button to set more than one discovery time, to run the discovery at defined hours during the day.


![AdvDisocvery3](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AdvDisocvery3.png){height="" width=""}

* Use **Delete** to delete a scheduled discovery time.

*  Click **Save** to save configuration changes.

## Connection Custom Cycle
Use  **Connection Custom Scheduling**  to enable   a custom discovery cycle for a specific adapter connection. Axonius will fetch data from the adapter’s connection only as part of the connection custom schedule.

### Enabling a Custom Cycle for each Adapter Connection
To enable a connection custom cycle:

1. Under  **Connection Custom Scheduling**, toggle on  **Enable custom scheduling of discovery per adapter connection**.

![AdvDisovrey4](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AdvDisovrey4.png){height="" width=""}

2. Click **Save**; the **Scheduling Configuration** tab is now  visible in all connections for this adapter. 

![Adapter Scheduling Config tab.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/Adapter%20Scheduling%20Config%20tab.png){height="" width=""}


### Configuring the Custom Cycle for the Adapter Connection

To configure the connection custom cycle, do the following:
1. Click on an adapter connection.
2. Select the **Scheduling Configuration** tab.
3. Toggle on the **Enable custom scheduling** toggle switch.

![Adapter Enable Custom Scheduling.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/Adapter%20Enable%20Custom%20Scheduling.png){height="" width=""}



4. Configure the custom cycle for the adapter connection:
    Refer to:

    *     [Setting Repeat Scheduled Discovery](/pl/docs/adapter-discovery-configuration#setting-repeat-scheduled-discovery)  
    *      [Setting More Than one Scheduled Discovery Time](/pl/docs/adapter-discovery-configuration#setting-more-than-one-scheduled-discovery-time) 
5. To save the scheduling configuration, click **Save**.

<br>
            

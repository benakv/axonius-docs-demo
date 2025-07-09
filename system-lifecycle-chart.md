## Metadata_Start 
## code: en
## title: System Lifecycle and Discovery Log Charts 
## slug: system-lifecycle-chart 
## seoTitle: System Lifecycle Chart 
## description: Explore how to use the System Lifecycle Chart in Axonius to track and visualize the lifecycle stages of your IT assets for better management and planning. 
## contentType: Markdown 
## Metadata_End
The **[System Lifecycle](/pl/docs/system-lifecycle-chart#system-lifecycle-chart)** chart shows information about the Discovery Cycle that is currently running, or the last **discovery cycle**, if a cycle is not currently running.

The **[Discovery Log](/pl/docs/system-lifecycle-chart#discovery-log-chart)** chart shows the last five  Discovery Cycles. The most recent  Discovery Cycle appears first in the list.

![AxoniusDashboard_Nov24](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AxoniusDashboard_Nov24.png){height="" width=""}

## System Lifecycle Chart

![SystemLifeCycleChartUp](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/SystemLifeCycleChartUp.png){height="" width=""}

The **System Lifecycle** chart displays the progress of the discovery cycle and the current phase in the cycle.

During a Discovery Cycle, in the Fetch Assets and in the Fetch Scanner Assets discovery phases hover over the chart to display the fetch status for each adapter that is pending.
The System Lifecycle chart also displays information regarding:

* The number of hours until the next automatic discovery cycle starts.
* The last discovery cycle's start and end timestamps. 
* The duration of the cycle.
* The time the next cycle is due to start.

For more details, see [Discovery Cycle](/docs/discovery-cycle).

![InspectLogs](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/InspectLogs.png){height="" width=""}

From the **Inspect Logs** list you can:

* Click **Adapters Fetch History** to open the **Adapters Fetch History** page filtered by this **Discovery Cycle** and see detailed information about the fetch status of each adapter being fetched by Axonius. To learn more, see [Adapters Fetch History](/docs/adapters-fetch-history).

  
* Click **Activity Log** to open the **Activity Logs** page filtered by this **Discovery Cycle** and see detailed information about the events in this **Discovery Cycle**. To learn more, see [Activity Logs Page](/docs/activity-logs-page).

* Click **Enforcement Run History** to open the Enforcement Run History page filtered by this **Discovery Cycle** and see detailed information about the events in this **Discovery Cycle**. To learn more, see [Viewing Enforcement Set Run History](/docs/view-ec-set-history).

## Discovery Log Chart

The **Discovery Log** chart shows the last five Discovery Cycles. 

![DiscoveryLogChart-Dates.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/DiscoveryLogChart-Dates.png){height="" width=""}

Click the arrow next to any of the Discovery Cycles to see all of the phases of that cycle.

![DiscoveryLogChart-Dates-Open.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/DiscoveryLogChart-Dates-Open.png){height="" width=""}

You can see detailed information about when the stage started, when it ended, and how long it took. To investigate a stage, click any three-dot menu to the right and then **[Activity Log](/docs/activity-logs-page)**, **[Adapter Fetch History](/docs/adapters-fetch-history)**, or **[Enforcment Run History](/docs/view-ec-set-history)** to open those pages filtered by the cycle. 

![DiscoveryLogChart-Dates-Links.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/DiscoveryLogChart-Dates-Links.png){height="" width=""}

* **Adapter Fetch History** is only relevant for steps that involve **Adapter Fetch**.
* You can view all the Enforcement activities in the current Discovery Cycle, by selecting the **Activity Log** option from the **Post-Correlations** stage three-dot menu. The Activity Log opens, showing all activities from the **Enforcement** category for this Discovery Cycle.  The **Discovery Cycle** column shows the start date and time of the current Discovery Cycle.

![DiscoveryCyclePostCorrelationMenu](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/DiscoveryCyclePostCorrelationMenu.png){height="" width=""}



<br>



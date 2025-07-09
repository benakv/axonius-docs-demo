## Metadata_Start 
## code: en
## title: Setting Adapter Ingestion Rules 
## slug: setting-adapter-ingestion-rules 
## seoTitle: Setting Adapter Ingestion Rules 
## description: Learn how to set adapter ingestion rules in Axonius to customize and control the data ingested from your IT assets for improved accuracy and relevance. 
## contentType: Markdown 
## Metadata_End
Use **Ingestion Rules** to decide which entities to ingest from the data fetched from adapters. You can configure Ingestion Rules for all connections for an adapter, configure different Ingestion Rules for each adapter connection, or only configure Ingestion Rules for a specific adapter connection. Ingestion Rules support all Axonius asset types.
 

## Required Permissions
 In order to use this feature, you require the following permissions:

* **View ingestion rules**
* **Update ingestion rules**

## Ingestion Rules Structure

* Ingestion rules work using Boolean operator conditions. 

* Ingestion rules support multiple statements. These are either handled using **OR** or **AND** as follows:

    * Choose **OR** to ingest an entity once one of the rules applies (this is the default).
    * Choose **AND** to ingest an entity only if all of the rules apply.

![Ingestiondiagram](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/Ingestiondiagram.png){height="" width="500"}

## Using Ingestion Rules

1.  Click the ![image.png](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/AdapterIcon.png)  icon on the left navigation panel to open the **Adapters** page.
2. Search for and select the relevant adapter. The **Adapter Profile** page opens displaying the list of connected connections.
3. Under **Advanced Settings**,  choose **Ingestion Rules Configuration**. The **Ingestion Rules Configuration** page is displayed. 
![IngestionPaneNEw](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/IngestionPaneNEw.png){height="" width=""}



4. Toggle on **Enable ingestion rules to configure which data to ingest from the adapter into the system**.
![IngestionRules1](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/IngestionRules1.png){height="" width=""}

6.  If you want to add more than one rule, from the **Select logical operator for all rules** drop-down, select the operator to apply between the rules: **OR** (the default) or  **AND**.
   
7.   Enter one Ingestion Rule statement in the **Custom ingestion statement** input box. Click the **+** button to add another Ingestion Rule statement. Learn [how to create an Ingestion Rule statement](#creating-an-ingestion-rule-statement).
8.  Once you have entered all the rules you need, click **Save** to save your settings. An entity is ingested according to the Boolean logic of the operator that you set. 

 
##  Configuring Ingestion Rules for each Adapter Connection
 
**To configure Ingestion Rules separately for each adapter connection**

1. On the Ingestion rules Configuration page, toggle on **Enable ingestion rules settings for each connection separately**.

![ingestioneach connection](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/ingestioneach%20connection.png){height="" width=""}


2.  Click **Save**.  The **Ingestion Rules  Configuration** tab now also appears on the **Add Connection** drawer.
3.     Click **Add Connection**. The **Connection Configuration** drawer now has an additional tab (**Ingestion Rules Configuration**).

![newTabingest](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/newTabingest.png){height="" width=""}


4.  Select the Ingestion Rules Configuration tab and toggle on **Enable ingestion rules to configure which data to ingest from the adapter into the system**.  The Ingestion Rules configuration pane opens.
![IngestToggleOn](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/IngestToggleOn.png){height="" width=""}

5. Configure the Ingestion rules that you want for this specific  connection,  and then select **Save** or **Save and Fetch**. 


## Creating an Ingestion Rule Statement
To use Ingestion Rules, you need to create at least one **Custom ingestion statement** that describes the data to ingest. Each statement is made up of a primary statement and an optional post action.

### Primary Statement

An entity is considered for ingestion if the pre-ingestion statement is true. A pre-ingestion statement can be built in one of two ways (use the relevant asset name in the first parenthesis):

* *{device | user}.{flattened key path of the entity} {operator} {rule values}*
* *{device | user} {operator} {rule values}*

#### Complex Primary Statements
Primary statements support complex conditions by combining multiple sub-rules using AND, OR, and parentheses. This enables creating detailed asset ingestion criteria. For example: ((Value >  50 AND Confidence = HIGH) OR (Value > 90 AND Confidence = LOW))

* Each sub-rule within a primary statement is evaluated independently for an asset.
  * OR: If any sub-rule is TRUE, the statement is TRUE. Evaluation stops when a TRUE sub-rule is found.
   * AND: All sub-rules must be TRUE for the statement to be TRUE.
  
 *      If multiple primary statements exist, each is evaluated independently.
     *     OR: If any primary statement is TRUE, the asset is ingested. Evaluation stops when a TRUE primary statement is found.
     *      AND: All primary statements must be TRUE for the asset to be ingested.

**Examples**

```TEXT
{entity}.{key} {operator} {value} or/and {entity} {operator} {value}
```
:::(Info) (Note:)
The above complex statement is equivalent to creating the following two simple primary statements with an OR or AND operator: 
```TEXT
{entity}.{key} {operator} {value}
```
OR/AND
```TEXT
{entity} {operator} {value}
:::

```TEXT
({entity}.{key} {operator} {value} or/and {entity} {operator} {value}) and/or {entity}.{key} {operator} {value}
```

```TEXT
({entity}.{key} {operator} {value} or/and {entity} {operator} {value}) and/or ({entity}.{key} {operator} {value} or/and {entity} {operator} {value})
```


### Post Action

Post actions are optional actions performed on the entity before it is ingested into Axonius. Common use cases for post statements are to filter out poor data or to drop PII.

The syntax is as follows:

*{primary statement} then {action} {post rule values}*

##  Ingestion Rule Components

### Entities
Defines which entity (asset type) this rule will be applied on (device, user, certificates, etc.).

### Flattened Key Path

The flattened key path of the entity is the name of the key path as presented in the Axonius database. The following example can explain how to obtain this value. “I want to only ingest device from the cmdb_ci_server table in ServiceNow”. You can translate this to a Query Wizard statement.


![IngestionFlattenedEg](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/IngestionFlattenedEg.png){height="" width=""}

This statement is automatically translated into an Axonius statement in the **Devices** search bar. 

``` TEXT
("adapters_data.service_now_adapter.class_name" == "cmdb_ci_server")
```

Because Ingestion rules are already being performed at an adapter level, you can ignore adapters_data.service_now_adapter.

That leaves the flattened key path to simply be `class_name`

![IngestionPathMain](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/IngestionPathMain.png){height="" width="500"}

When working with complex objects such as network interface IP addresses, you need to copy the complete complex object, for instance `network_interfaces.ips `.

![IngestionMore](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/IngestionMore.png){height="" width="500"}


### Operators Supported
The following operators are supported:

####  **Equal\Not Equal (== | !=)** 

Checks whether the value from the entity is equal or not equal to the rule value\s. 
:::(Info) (Note:)

The condition asset.key != "value" only returns assets where the field key exists and is not equal to "value". To also include assets where key is missing or empty, use: (asset.key != 'value' or asset key_not_exists ["key"]). See below an explanation of key_not_exists.
:::

```TEXT
device.class_name == "cmdb_ci_computer"
```

```TEXT
(device.class_name != "cmdb_ci_computer" or device key_not_exists ["class_name"])
```

```
(device key_not_exists ["vlan"] or device.vlan != "888") and (device key_not_exists ["ssid"] or device.ssid != "ALLETEGUEST")
```

     
Do not use equals with lists, as they will be converted to strings.


```TEXT
 'device.ad_dc_source != ["10.10.11.0/24"]` (checks if value is equal to str(list))
```
 

####  **Dates** **Smaller Than\Greater Than (< |>)**

Checks whether the value from the entity is smaller or greater than the date in the rule value.

```TEXT
user.termination_date > date(2024-10-31)
```

Ingest users whose termination date is greater than October 31st 2024

```TEXT
user.last_logon > date(now-10d)
```
 Ingest all users with last_logon within the last 10 days
 
 
:::(Info) (Note:)
Dates currently do not support greater than or equal to >= OR less than or equal to <=
:::
 
#### **Numbers**

   Checks whether the value from the entity is greater than or less than the value provided.


```TEXT
device.confidence_level < 65 then skip_field ["os.type", "os.distribution", "os.type_distribution", "os.os_str"]
```

If the confidence level for devices is below 65, then do not ingest OS level information. 

:::(Info) (Note:)
This rule excludes all devices with a confidence level >=65. Using the following rule in conjunction with the OR operator ensures that all devices are still ingested from that adapter.
```TEXT
device key_exists ["id"]
```
:::


```TEXT
device.policies_compliance_count >= 1
```

   Ingests all devices with at least one compliance policy present.
 


####  **Value In\Value Not In (in | not_in)** 
Checks whether the value from the entity is in or not in the list of rule values
```TEXT
device.ad_name in ["EC2AMAZ-71GIQSBBB", "EC2AMAZ-71GIQSORRRR"]
```
    
```TEXT
device.ad_name not_in ["EC2AMAZ-71GIQSBBB", "EC2AMAZ-71GIQSORRRR", "EC2AMAZ-71GIQSO"]
```
   
    
 
 

####  **IP Address In or Not In (in_net | not_in_net)** 

Checks whether the IP address\network value from the entity is in or not in the rule_values IP network. This means that you can check if an IP\Subnet is in a CIDR. This is applicable both for IPv4 and for IPv6.

  **Examples** 
```TEXT
device.network_interfaces.ips in_net ["10.10.11.0/24"]
```
 
 
```TEXT
device.network_interfaces.ips not_in_net ["192.168.11.0/24"]
```
  
 
 
####  **Starts or Does not Start with (starts_with | not_starts_with)** 

Checks whether the value from the entity starts with or does not start with a required pattern that was entered.

**Examples**

```TEXT
device.ad_usn_changed starts_with ["91"]
```

```TEXT
device.ad_name not_starts_with ["EC2", "S3"]
```
  
  
####  **Ends or Does not End With (ends_with | not_ends_with)**

Checks whether the value from the entity ends with or does not end with a required pattern that was entered.

**Examples**

```TEXT
user.mail ends_with ["@gmail.com", "@yahoo.com"]
```

```TEXT
user.username not_ends_with ["_test"]
```
     
   
#### **Key Exists or Does Not Exist (key_exists | key_not_exists)**
Checks whether **all supplied** key values exist or not.

```TEXT
device key_exists ["network_interfaces.ip", "ad_name"]
```

```TEXT
user key_not_exists ["database"]
```
       
   
#### **Field Equal\Not Equal (field_equal |field_not_equal)** 
Checks whether the value from the value of one field in an entity is equal or not equal to the value of another field in that entity.

**Examples**

```TEXT
device.hostname field_not_equal ["ad_name"]
```
   
 
Only ingest devices where the hostname field is not equal to the value in the ad_name field.

####  Field Starts With (field_starts_with) 
Checks whether the value of one field in an entity starts with the value of another field in that entity.

**Examples**

```TEXT
device.ad_sAMAccountName field_starts_with ["ad_name"]
```
   
 
Ingest the device only if its sAMAccountName name begins with the ad_name.

 

####   Field Not Starts With ( field_not_starts_with)  
Checks whether the value of one field in an entity does not start with the value of another field in that entity.

**Examples**

 

```TEXT
device.hostname field_not_starts_with ["name"] then skip_field ["hostname", "fqdn"]
```
The device will only be ingested if its hostname does not start with its asset name. Those devices ingested will also have their hostname and FQDN fields dropped. Consider adding `device key_exists` ["id"] to this rule (OR'd together) if you would still like to ingest devices where their hostname begins with their asset name. 

#### Contains (contains) and Not Contains (not_contains)

Checks whether the value from the entity does or does not contain any of the rule values. This is case insensitive.

**Examples**

```
device.ad_sAMAccountName contains ["axonius"]
device.ad_sAMAccountName not_contains ["check1", "check2"]
```

#### Matches or Does Not Match Regex Value (match_regex|not_match_regex) 

Checks whether the provided regex string pattern matches or does not match the device field value.

**Examples**
```
device.name match_regex ["WIN.+test"]
```
 

### Post Actions

Post actions can perform additional operations on the entity (asset) before it is ingested. A post action is not required for an Ingestion Rule statement. 
The following post action operators are available.

#### **Skip Field (skip_field)** 

Removes the supplied fields from the entity and does not insert them into the database. 

**Examples**

```TEXT
device.ad_dc_source == "10.10.11.5" then skip_field ["network_interfaces.ips", "ad_name"]
```
:::(Info) (Note:)
This rule excludes all devices with an ad_dc_source not equal to 10.10.11.5. Therefore, if you want to include ALL entities (assets), but only skip fields on a subset of entities, include the following rule (in conjunction with the OR operator) to ensure that all entities are still ingested from that adapter.
```TEXT
device key_exists ["id"]
```
:::
   

```TEXT
 device.ad_usn_changed starts_with ["91"] then skip_field ["ad_dc_source"]
```

 
 
 If you want to skip a field(s) on all devices coming from an adapter, change the ingestion rule to the following:
 
 
```TEXT
device key_exists ["id"] then skip_field ["physical_location", "qualys_agnet_ports"]
```

 

* `device key_exists ["id"]` ensures that all devices are ingested from that adapter.
* then `skip_field ["physical_location", "qualys_agnet_ports"]` allows you to specify the field(s) to not ingest on those devices.

 
 

####  **Remove Values (remove_values)** 

Removes values from a list field or from a field in a list object. Note that if you already fetched these values, they still appear in the asset table for the amount of time set in [**Delete devices (or users) and other assets that have not been returned from the source in the last X hours**](https://docs.axonius.com/docs/advanced-settings#adapter-configuration). To only see the latest values, from the Query Wizard create a query that shows “from last fetch” = true. Use **remove_values** on fields that contain a list of simple objects such as strings (**Last Used Users from WMI** as seen above) or numbers, or on fields that contain a list of complex objects.


![IngestionremoveValue](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/IngestionremoveValue.png){height="" width=""}

**Example 1 - Removes values from a list field**

```TEXT
device key_exists ["last_used_users"] then remove_values last_used_users starts_with ["Admin"]

```
 
This rule will ingest all devices with a last used user, but will only include last used users that do not start with "Admin"

**Example 2 - Removes values from a field in a list object**

```TEXT
device key_exists ["id"] then remove_values network_interfaces.mac == "00:00:4f:21:53:af"

```
 
This rule will ingest all devices with an ID, but will remove the MAC address from each device that has a network interface with MAC equal to 00:00:4f:21:53:af.

#### **Remove Items (remove_items)** 
Removes items from a list field.  Some fields contain lists of items, for example **network_interfaces**, which contains subfields such as MAC addresses, IP addresses, etc. If a condition is applied to one of the subfields, then when it is true, the complete item is removed and is not ingested. **remove_items** should be used for lists of complex objects, such as Network Interfaces.


 

![egNetworkIn](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/egNetworkIn.png){height="" width=""}


**Example**
```TEXT
device key_exists ["id"] then remove_items network_interfaces.ip4 in_net ["10.20.0.0/24"]
```

 
This rule will ingest all devices, but will remove all associated network interface information for IPs between 10.10.10.0 - 10.10.10.255


#### **Trim Prefix/Suffix** (trim_suffix / trim_prefix) 
Removes a certain prefix or suffix from the field if it exists.

**Examples**
```TEXT
device key_exists ["id"] then trim_prefix hostname ["domain.local"]
```

```TEXT
device key_exists ["id"] then trim_prefix network_interfaces.ips ["(IP Address)", "IP Prefix"]
``` 

```TEXT
user key_exists ["id"] then trim_suffix hostname [".com"]
```
<br>
:::(Info) (Note:)
If you want to run a post action on only a subset of entities and still ingest all other entities, you will need to include the following rule:
`device|user key_exists ["id"]`
:::

This is useful for scenarios when you would like to remove employee IDs from an MSSP that collides with your primary email. 

The Ingestion Rules would look like the following (joined with 'OR')

```TEXT
user.email ends_with ["@mssp.com"] then skip_field ["employee_id"]

user key_exists ["id"]
```

### Performing Post Action Only if Field Value Exists / Not Exists
Use **key_exists** and **key_not_exists** operators in the post action of an ingestion rule so that the post action is performed on the asset, only if a value exists or does not exist in the specified field (key).

**Example**
```TEXT
device key_exists ["id"] then remove_items network_interfaces.ips_v4 key_not_exists
```
This rule ingests all devices, but removes all network interfaces without a value in ips_v4, i.e., without an IPv4 address.

<br>       


## Testing Ingestion Rules
From the **Add Connection** page, click **Save and Fetch** to test the Ingestion Rules. 
The system then performs a fetch. Each entity brought from the adapter goes through the Ingestion Rule process.

:::(Info) (Note:)
Instead of initiating a fetch to test the Ingestion Rules, you can wait until the adapter fetches in accordance with your discovery cycle.
:::

After the fetch is complete, open the relevant assets page in order to see your results. In the Query Wizard, specify your adapter and select “From Last Fetch - yes”  

![TestIngestoion](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/TestIngestoion.png){height="" width=""}


In the **Adapter Fetch History**, you can also see how many assets of each asset type were ignored before and after the Ingestion Rules were implemented.

![IngestionAdapterFetch](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/IngestionAdapterFetch.png){height="" width=""}

If required, you can fine-tune the rules and rerun a fetch.

Entities not ingested will still appear in Axonius for the amount of time set in **Delete devices (or users) and other assets that have not been returned from the source in the last X hours**  setting.


## Ingestion Rules Examples
### A problematic MAC address is being added to my devices after using an ethernet connection. 
Perhaps the same ethernet connection is used when imaging company workstations. This might cause the same MAC address to appear on multiple devices, resulting in unintended correlation issues.

```TEXT
device key_exists ["id"] then remove_items network_interfaces.mac == "00:00:5E:00:53:AF"
```
 

This will find any network interface records containing this MAC address and remove it from the device.

### Exclude device records that have neither open ports NOR hostname.
Whenever you want to “exclude” a device, you need to think about the other side of the coin. What type of devices do you want to “ingest”?

It would be equivalent to say the following, “I want to ingest devices that have an open port OR hostname”

```TEXT
device key_exists ["hostname"]
```
 
```TEXT
device key_exists ["open_ports"]
```
These rules can be used together with OR.

 

![IngestionEG1](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/IngestionEG1.png){height="" width=""}


Why can’t we combine these statements into a single rule?

```TEXT
device key_exists ["hostname", "open_ports"]
```



That is because BOTH keys need to exist on the device when we insert both fields into the list. Again, key_exists checks whether all supplied key values exist or not. If any key does not exist, then the device will not be ingested.

### Exclude data from an acquired company in your CMDB 
Perhaps you acquire another company and begin putting their devices into your CMDB. However, perhaps you do not want to ingest those devices into Axonius. You could use the following ingestion rule:

```TEXT
device.company != "Child Company"
```


### Working with Boolean Values




![IngestionEG2](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/IngestionEG2.png){height="" width="500"}

While **has_agent** is a boolean field (True|False), the UI shows Yes|No. How do you only ingest devices with an agent?

While the field in the UI shows 'Yes' or 'No', you use the actual value 'True' or 'False' in the rule, as follows:

```TEXT
device.has_agent == "True"
```
 

### Exclude specific classes from the CMDB
Let’s filter the following classes from the ServiceNow fetch list: cmdb_ci_win_server, cmdb_ci_linux_server, cmdb_ci_unix_server, etc.

Before building the rule, we can build a field segmentation to get a rough idea of the devices we want to exclude.


![IngestionEG4](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/IngestionEG4.png){height="" width="500"}

8 Win Servers + 7 Unix Servers + 5 Linux Servers = 20 total devices to exclude

The ingestion rule should ignore 20 additional devices after implementation.

```TEXT
device.class_name not_in ["cmdb_ci_win_server", "cmdb_ci_linux_server", "cmdb_ci_unix_server"]
```

 
![IngestionCMDB](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/IngestionCMDB.png){height="" width="500"}

Success. Note the adapter was already ignoring 5 devices prior to the ingestion rule


### Filtering AWS Resources Coming from CrowdStrike
Maybe your security controls are installed on ephemeral EC2 instances in AWS that constantly get spun up and spun down. While we have filtered these devices from the AWS adapter, they are still appearing in Axonius from the other adapters that see them, such as CrowdStrike. 

![Ingestionnext](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/Ingestionnext.png){height="" width="500"}

To start we might want to remove based on cloud_provider.

```TEXT
device.cloud_provider != "AWS"
```

 

With this rule, we should expect 3 devices to be ignored.

![IngestinEG6](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/IngestinEG6.png){height="" width="500"}

However, this rule excluded our non-AWS devices too. Because those devices don’t have a cloud_provider field, the ingestion rule failed on those devices. So, we need another check to bring in devices that don’t have a cloud_provider.

```TEXT
device key_not_exists ["cloud_provider"]
```
![IngestionEG7](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/IngestionEG7.png){height="" width="500"}


These rules would be used together with OR

 

### Excluding Expired Certificates
Perhaps we are pulling in certificate data from a Certificate Lifecycle Management system such as Digicert, Sectigo, or Venafi, and we want to filter out expired certificates that are considered stale. In this scenario, we want to exclude all certs that expired more than 30 days ago.

```TEXT
device.certificate.cert_expiry_date > date(now - 30d)
```

 
This statement will look back 30 days and ingest all certificates that have expired in the last 30 days or have yet to expire.

### Skip physical location field for multiple OS-type devices
The organization has a prefix for each device hostname in its environment. This example presents a complex Ingestion Rule, which determines to ingest only those devices with:
* device.hostname starts_with ["worg"] and device.os.type == "Windows"
* device.hostname starts_with ["morg"] and device.os.type == "MacOS"

in ingested devices (matching either of those rules), skips the physical location field.

```TEXT
(device.hostname starts_with ["worg"] and device.os.type == "Windows") or (device.hostname starts_with ["morg"] and device.os.type == "MacOS") then skip_field ["physical_location"]
```
![IngestionRuleComplexConfiguration](https://cdn.document360.io/95e0796d-2537-45b0-b972-fc0c142c6893/Images/Documentation/IngestionRuleComplexConfiguration.png){height="" width=""}

###  Ingest specific servers

The following rule ingests servers according to the following customer use case: 

* When a server's hostname starts with "SER_" AND the OS is "windows" --> Do not ingest. 
* If the server's hostname starts with "SER_" and the OS is Linux or any other OS  --> Ingest.
* if the server's hostname does not start with SER_ and the OS is any OS  --> Ingest.


```TEXT
(device.hostname not_starts_with "SER_" or device.os.type != "windows"))
```
According to this rule, devices with the following field values will or will not be ingested.
* Hostname = SER_123 AND OS = windows --> NOT ingested
* Hostname = SER_124 AND OS = Linux --> Ingested
* Hostname = Linux_ser123 AND OS = windows --> Ingested



<br>

<h2>About the connector</h2>

<p>FortiEDR protects endpoints pre and post infection, stopping data breaches in real-time and automatically orchestrating incident investigation and response. This connector facilitates the automated operations related to events, forensics and collectors.</p>

<p>This document provides information about the Fortinet FortiEDR connector, which facilitates automated interactions, with a Fortinet FortiEDR server using FortiSOAR&trade; playbooks. Add the Fortinet FortiEDR connector as a step in FortiSOAR&trade; playbooks and perform automated operations with Fortinet FortiEDR.</p>

<h3>Version information</h3>

<p>Connector Version: 2.1.0</p>

<p>FortiSOAR&trade; Version Tested on: 7.4.1-3167</p>

<p>Fortinet FortiEDR Version Tested on: </p>

<p>Authored By: Fortinet</p>

<p>Certified: Yes</p>

<h2>Release Notes for version 2.1.0</h2>

<p>Following enhancements have been made to the Fortinet FortiEDR connector in version 2.1.0:</p>

<ul>
<li>Added a new parameter Organization in connector configuration. </li>
<li><p>Added the following new operations and playbooks:</p>

<ul>
<li>Search IOC</li>
<li>Execute an API Request </li>
</ul></li>
</ul>

<h2>Installing the connector</h2>

<p>Use the <strong>Content Hub</strong> to install the connector. For the detailed procedure to install a connector, click <a href="https://docs.fortinet.com/document/fortisoar/0.0.0/installing-a-connector/1/installing-a-connector" target="_top">here</a>.</p><p>You can also use the <code>yum</code> command as a root user to install the connector:</p>

<pre>yum install cyops-connector-fortinet-fortiedr</pre>

<h2>Prerequisites to configuring the connector</h2>

<ul>
<li>You must have the credentials of Fortinet FortiEDR server to which you will connect and perform automated operations.</li>
<li>The FortiSOAR&trade; server should have outbound connectivity to port 443 on the Fortinet FortiEDR server.</li>
</ul>

<h2>Minimum Permissions Required</h2>

<ul>
<li>Not applicable</li>
</ul>

<h2>Configuring the connector</h2>

<p>For the procedure to configure a connector, click <a href="https://docs.fortinet.com/document/fortisoar/0.0.0/configuring-a-connector/1/configuring-a-connector">here</a></p>

<h3>Configuration parameters</h3>

<p>In FortiSOAR&trade;, on the Connectors page, click the <strong>Fortinet FortiEDR</strong> connector row (if you are in the <strong>Grid</strong> view on the Connectors page) and in the <strong>Configurations</strong> tab enter the required configuration details:</p>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Server URL</td><td>URL of the Fortinet FortiEDR server to which you will connect and perform the automated operations.</td></tr>
<tr><td>Username</td><td>Username that contains a Rest API role and using which you will access the Fortinet FortiEDR server to which you will connect and perform the automated operations. Note: Specify the username in the following format: 'Organization\username' if Organization field is left blank.</td></tr>
<tr><td>Password</td><td>Password used to access the FortiEDR server to which you will connect and perform the automated operations.</td></tr>
<tr><td>Organization</td><td>Specify the organization name using which you will access the Fortinet FortiEDR server. The organization must be specified in a multi-tenancy environment.</td></tr>
<tr><td>Verify SSL</td><td>Specifies whether the SSL certificate for the server is to be verified. <br/>By default, this option is selected, i.e., set to <code>true</code>.</td></tr>
</tbody></table>

<h2>Actions supported by the connector</h2>

<p>You can use the following automated operations in playbooks and also use the annotations to access operations:</p>

<table border=1><thead><tr><th>Function</th><th>Description</th><th>Annotation and Category</th></tr></thead><tbody><tr><td>Get Event by ID</td><td>Retrieves a specific event from Fortinet FortiEDR based on the event ID you have specified.</td><td>get_event <br/>Investigation</td></tr>
<tr><td>Get Events</td><td>Retrieves all the events from Fortinet FortiEDR that match the condition(s) you have specified. Note: If none of the input parameters that you specify match the events in Fortinet FortiEDR, then an empty result set is returned.</td><td>get_event_list <br/>Investigation</td></tr>
<tr><td>Update Events</td><td>Updates events in Fortinet FortiEDR that match the condition(s) you have specified. Note: If none of the input parameters that you specify match the events in Fortinet FortiEDR, then an empty result set is returned.</td><td>update_event <br/>Investigation</td></tr>
<tr><td>Get Raw Data Items</td><td>Retrieves the raw data items from Fortinet FortiEDR based on the event ID and other input parameters you have specified.</td><td>get_raw_data_items <br/>Investigation</td></tr>
<tr><td>Get Event Count</td><td>Retrieves the event count from Fortinet FortiEDR based on the filter parameters you have specified.</td><td>get_event_count <br/>Investigation</td></tr>
<tr><td>Get Event List Extended</td><td>Retrieves archived/unarchived events together from Fortinet FortiEDR based on the filter parameters you have specified. Note: If none of the input parameters that you specify match the events in Fortinet FortiEDR, then an empty result set is returned.</td><td>get_event_list <br/>Investigation</td></tr>
<tr><td>Search Filehash</td><td>Searches a file hash among the current events, threat hunting repository, and communicating applications that exist in the Fortinet FortiEDR system.</td><td>search_filehash <br/>Investigation</td></tr>
<tr><td>Get File</td><td>Retrieves a specific file from the specified device from Fortinet FortiEDR, based on the device type, device name/ID, and file paths you have specified, and adds it as an attachment in the "Attachments" module</td><td>get_file <br/>Investigation</td></tr>
<tr><td>Retrieve File or Memory</td><td>Retrieves a file or memory related to a specific event from Fortinet FortiEDR based on the raw event ID and other input parameters you have specified and adds it as an attachment in the "Attachments" module.</td><td>get_event_file <br/>Investigation</td></tr>
<tr><td>Remediate Device</td><td>Takes remedial actions on Fortinet FortiEDR such as killing a process, deleting a file and/or cleaning persistent data on which malware was detected based on the device type, device name/ID, and other input parameters you have specified.</td><td>remediate_device <br/>Remediation</td></tr>
<tr><td>Get Collector List</td><td>Retrieves the list of the collectors from Fortinet FortiEDR based on the device names or IDs, and other input parameters you have specified.</td><td>get_collector_list <br/>Investigation</td></tr>
<tr><td>Isolate Collector</td><td>Isolates a collector from the Fortinet FortiEDR network based on the list of device IDs or names, and other input parameters you have specified.</td><td>isolate_collector <br/>Investigation</td></tr>
<tr><td>Unisolate Collector</td><td>Unisolates a collector from the Fortinet FortiEDR network based on the device ID and other input parameters you have specified.</td><td>unisolate_collector <br/>Investigation</td></tr>
<tr><td>Create Exception</td><td>Creates a new exception in Fortinet FortiEDR based on the event ID and other input parameters you have specified.</td><td>create_exception <br/>Investigation</td></tr>
<tr><td>Get Exception List</td><td>Retrieves the list of all exceptions or specific exceptions from Fortinet FortiEDR based on the input parameters you have specified.</td><td>list_exception <br/>Investigation</td></tr>
<tr><td>Update Exception</td><td>Updates a specific exception in Fortinet FortiEDR based on the event ID, exception ID, and other input parameters you have specified.</td><td>update_exception <br/>Investigation</td></tr>
<tr><td>Get Event Exceptions</td><td>Retrieves the list of event exceptions from Fortinet FortiEDR based on the event ID and other input parameters you have specified.</td><td>get_event_exceptions <br/>Investigation</td></tr>
<tr><td>Get Raw JSON Event Data</td><td>Retrieve the raw data of specific events from Fortinet FortiEDR based on the event ID and other input parameters you have specified.</td><td>get_raw_json_event_data <br/>Investigation</td></tr>
<tr><td>Create IPSet</td><td>Creates an IPSet in Fortinet FortiEDR using the set of IP addresses and other parameters you have specified.</td><td>create_ipset <br/>Investigation</td></tr>
<tr><td>Get IPSet List</td><td>Retrieves a list of IPSets from Fortinet FortiEDR based on the IP address and other input parameters you have specified.</td><td>get_ipset_list <br/>Investigation</td></tr>
<tr><td>Update IPSet</td><td>Updates IP addresses in the specific IPSet in Fortinet FortiEDR using the set of IP addresses, the IPSet name, and other parameters you have specified.</td><td>update_ipset <br/>Investigation</td></tr>
<tr><td>Delete IPSet</td><td>Deletes specific IPSets from Fortinet FortiEDR based on the IPSet names and other input parameters you have specified.</td><td>delete_ipset <br/>Investigation</td></tr>
<tr><td>Get Agent Groups</td><td>Retrieves a list of all agent group lists from Fortinet FortiEDR.</td><td>get_agent_group <br/>Investigation</td></tr>
<tr><td>Get System Summary</td><td>Retrieves a summary of the environment from Fortinet FortiEDR.</td><td>get_system_summary <br/>Investigation</td></tr>
<tr><td>Get Organizations</td><td>Retrieves a detailed list of organizations from the FortiEDR server.</td><td>get_organizations <br/>Investigation</td></tr>
<tr><td>Move Collectors</td><td>Move collectors between organizations based on the collectors, target collectors group, and other input parameters that you have specified.</td><td>move_collectors <br/>Investigation</td></tr>
<tr><td>Search IOC</td><td>Threat hunting by searching for Indicators of Compromise (IOCs), potential threats, and malware within the activity data collected and stored on the Repository server.</td><td>search_ioc <br/>Investigation</td></tr>
<tr><td>Execute an API Request</td><td>Execute any FortiEDR REST API using the specified API method, endpoint, and payload as input parameters.</td><td>generic_rest_api_call <br/>Investigation</td></tr>
</tbody></table>

<h3>operation: Get Event by ID</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Event ID</td><td>ID of the event that you want to retrieve from Fortinet FortiEDR. NOTE: You can get event IDs using the Get Events action.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>[
    {
        "action": "",
        "archived": "",
        "certified": "",
        "classification": "",
        "handlingState": "",
        "collectors": [
            {
                "collectorGroup": "",
                "device": "",
                "id": "",
                "ip": "",
                "lastSeen": "",
                "macAddresses": [],
                "operatingSystem": ""
            }
        ],
        "comment": "",
        "destinations": [],
        "eventId": "",
        "firstSeen": "",
        "handled": "",
        "lastSeen": "",
        "loggedUsers": "",
        "muteEndTime": "",
        "muted": "",
        "organization": "",
        "process": "",
        "processOwner": "",
        "processPath": "",
        "processType": "",
        "rules": [],
        "seen": "",
        "severity": "",
        "threatDetails": {
            "threatFamily": "",
            "threatName": "",
            "threatType": ""
        }
    }
]</pre>

<h3>operation: Get Events</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Event IDs</td><td>(Optional) List of event IDs based on which you want to retrieve events from Fortinet FortiEDR.</td></tr>
<tr><td>Device Name</td><td>(Optional) Name of the device on which the events occurred that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Collector Groups</td><td>(Optional) List of collector groups whose collector had reported the events that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Operating System</td><td>(Optional) Name of the operating system of the devices on which the events occurred that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Device IPs</td><td>(Optional) List of IP addresses of the devices on which the events occurred that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>MAC Addresses</td><td>(Optional) MAC addresses where the events occurred that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>File Hash</td><td>(Optional) Hash signature of the main process of the event that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Process</td><td>(Optional) Name of the main process of the event that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Process Path</td><td>(Optional) Path of the processes related to the event that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>First Seen From</td><td>(Optional) "From" date when the event that you want to retrieve from Fortinet FortiEDR, was seen for the first time. Use this parameter together with the "First Seen To" parameter to specify a date range.</td></tr>
<tr><td>First Seen To</td><td>(Optional) "To" date when the event that you want to retrieve from Fortinet FortiEDR, was seen for the first time. Use this parameter together with the "First Seen From" parameter to specify a date range.</td></tr>
<tr><td>Last Seen From</td><td>(Optional) "From" date when the event that you want to retrieve from Fortinet FortiEDR, was seen for the last time. Use this parameter together with the "Last Seen To" parameter to specify a date range.</td></tr>
<tr><td>Last Seen To</td><td>(Optional) "To" date when the event that you want to retrieve from Fortinet FortiEDR, was seen for the last time. Use this parameter together with the "Last Seen From" parameter to specify a date range.</td></tr>
<tr><td>Classification</td><td>(Optional) Classification of the events that you want to retrieve from Fortinet FortiEDR. Classification is a list of strings that contain one or more of the following values: Malicious, Suspicious, Inconclusive, Likely Safe, PUP, or Safe.</td></tr>
<tr><td>Actions</td><td>(Optional) Actions that were enforced on the events that you want to retrieve from Fortinet FortiEDR. You can choose from the following options: Block, Simulation Block, or Log.</td></tr>
<tr><td>Destinations</td><td>(Optional) Connection destination(s) of the events that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Rule</td><td>(Optional) Short rule name of the rule that triggered the events that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Logged in User</td><td>(Optional) Logged-in user associated with the events that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Seen</td><td>(Optional) True/False parameter indicating whether events that you want to retrieve from Fortinet FortiEDR were read/unread by the user operating the API.</td></tr>
<tr><td>Handled</td><td>(Optional) True/False parameter indicating whether events that you want to retrieve from Fortinet FortiEDR were handled/unhandled.</td></tr>
<tr><td>Signed</td><td>(Optional) True/False parameter indicating whether the event that you want to retrieve from Fortinet FortiEDR is signed/unsigned.</td></tr>
<tr><td>Severities</td><td>(Optional) Select the severity to filter retrieved results. You can select one of the following options: Critical High Medium</td></tr>
<tr><td>Muted</td><td>(Optional) True/False parameter indicating whether the event that you want to retrieve from Fortinet FortiEDR is muted/unmuted.</td></tr>
<tr><td>Organization</td><td>(Optional) Select how the operation applies to an organization. Some parts of the Fortinet Endpoint Protection and Response Platform system have separate, non-shared data that is organization-specific. Other parts of the system have data that is shared by all organizations. The value that you specify for the organization parameter, determines the organization to which this operation applies. You can select from the following options: Exact Organization Name: Specify the exact name of the organization whose associated events you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR. All Organizations: Select to fetch events from data shared by all organizations within Fortinet FortiEDR.<br><strong>If you choose 'Exact Organization Name'</strong><ul><li>Organization Name: Specify the exact name of the organization whose associated events you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</li></ul></td></tr>
<tr><td>Archived</td><td>(Optional) Select to include only archived events while retrieving events from Fortinet FortiEDR. By default, this is not selected, i.e., set to false.</td></tr>
<tr><td>Strict Mode</td><td>(Optional) Select to perform strict matching on the search parameters while retrieving events from Fortinet FortiEDR. By default, this is not selected, i.e., set to false.</td></tr>
<tr><td>Device Control</td><td>(Optional) Select to include or exclude device control events. Leave blank to ignore the parameter when retrieving results.</td></tr>
<tr><td>Expired</td><td>(Optional) Select to include or exclude expired events. Leave blank to ignore the parameter when retrieving results.</td></tr>
<tr><td>Page Number</td><td>(Optional) Page number from which you want to retrieve records.</td></tr>
<tr><td>Items Per Page</td><td>(Optional) Maximum number of events that this operation should return for the current page. Default value is 100 and the maximum value is 1000.</td></tr>
<tr><td>Sorting</td><td>(Optional) Name of the fields by which you want to sort the results retrieved by this operation. You can enter the fields in the following format: {"column1":true, "column2":false}. True indicates sorting in descending order. Results are sorted by the first field, then by the second field, and so on.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>[
    {
        "action": "",
        "archived": "",
        "certified": "",
        "classification": "",
        "collectors": [
            {
                "collectorGroup": "",
                "device": "",
                "id": "",
                "ip": "",
                "lastSeen": "",
                "macAddresses": [],
                "operatingSystem": ""
            }
        ],
        "comment": "",
        "destinations": [],
        "eventId": "",
        "firstSeen": "",
        "handled": "",
        "lastSeen": "",
        "loggedUsers": [],
        "muteEndTime": "",
        "muted": "",
        "organization": "",
        "process": "",
        "processOwner": "",
        "processPath": "",
        "processType": "",
        "rules": [],
        "seen": "",
        "severity": "",
        "threatDetails": {
            "threatFamily": "",
            "threatName": "",
            "threatType": ""
        }
    }
]</pre>

<h3>operation: Update Events</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Field to Update on Event</td><td>Select one or more fields to update the event. IMPORTANT: Select only one of Read, Handle, and Archive fields. You can select from the following options: Read: Select an option from the Mark as Read field to mark the event as read or unread. True: Select to mark an event as Read. False: Select to mark an event as Unread. Handle: Select an option from the Mark as Handled field to mark the event as handled or ignored. True: Select to mark an event as Handled. False: Select to mark an event as Unhandled. Archive: Select an option from the Archive Event field to archive or unarchive the event. True: Select to archive an event. False: Select to unarchive the event. Classification: Select a classification from the Classify Event field to update the event. You can choose from the following options: Malicious PUP Safe Mute: Select an option from the Mute Event field to mark the event as muted or unmuted. True: Select to mark an event as muted. Specify values in following fields: Mute Duration: Select the duration for which you want to mute or unmute the event in Fortinet FortiEDR. You can choose from the following values: Week Month Year Permanently Forced Unmute: Select to force unmute of an event. Once selected specify a value for the Forced to Unmute an Event field. True: Select to force an event to be archived even when the event is muted. False: Select to force an event to be unarchived even when the event is muted. Family Name: Specify the family name of the event in Family Name field. Malware Type: Specify the malware type of the event in Malware Type field. Threat Name: Specify the threat name of the event in Threat Name field.<br><strong>If you choose 'Read'</strong><ul><li>Mark as Read: Select an option from the Mark as Read field to mark the event as read or unread.</li></ul><strong>If you choose 'Handle'</strong><ul><li>Mark as Handled: Select an option from the Mark as Handled field to mark the event as handled or ignored.</li><li>Add Comment: Free text to be added as a comment to the event. The event must be handled in order to accept comments (supported for version 2.6.4 and above).</li></ul><strong>If you choose 'Archive'</strong><ul><li>Archive Event: Select an option from the Archive Event field to archive or unarchive the event.</li></ul><strong>If you choose 'Classification'</strong><ul><li>Classify Event: Select a classification from the Classify Event field to update the event. You can choose from the following options:  Malicious, PUP or Safe (supported in V2.7.3 and above).</li><li>Add Comment: Free text to be added as a comment to the event. The event must be handled in order to accept comments (supported for version 2.6.4 and above).</li></ul><strong>If you choose 'Mute'</strong><ul><li>Mute Event: Select an option from the Mute Event field to mark the event as muted or unmuted.</li><strong>If you choose 'True'</strong><ul><li>Mute Duration: Specifies the mute duration time. Allowed values are Week, Month, Year or Permanently.</li></ul><strong>If you choose 'False'</strong><ul><li>Forced to Unmute an Event: Select to force unmute of an event. Once selected specify a value for the Forced to Unmute an Event field.</li></ul></ul><strong>If you choose 'Family Name'</strong><ul><li>Family Name: Specify the family name of the event in Family Name field.</li></ul><strong>If you choose 'Malware Type'</strong><ul><li>Malware Type: Specify the malware type of the event in Malware Type field.</li></ul><strong>If you choose 'Threat Name'</strong><ul><li>Threat Name: Specify the threat name of the event.</li></ul></td></tr>
<tr><td>Event IDs</td><td>(Optional) List of event IDs based on which you want to update events in Fortinet FortiEDR.</td></tr>
<tr><td>Device Name</td><td>(Optional) Name of the device on which the events occurred that you want to update in Fortinet FortiEDR.</td></tr>
<tr><td>Collector Groups</td><td>(Optional) List of collector groups whose collector had reported the events that you want to update in Fortinet FortiEDR.</td></tr>
<tr><td>Operating System</td><td>(Optional) Name of the operating system of the devices on which the events occurred that you want to update in Fortinet FortiEDR.</td></tr>
<tr><td>Device IPs</td><td>(Optional) List of IP addresses of the devices on which the events occurred that you want to update in Fortinet FortiEDR.</td></tr>
<tr><td>File Hash</td><td>(Optional) Hash signature of the main process of the event that you want to update in Fortinet FortiEDR.</td></tr>
<tr><td>Process</td><td>(Optional) Name of the main process of the event that you want to update in Fortinet FortiEDR.</td></tr>
<tr><td>Process Path</td><td>(Optional) Path of the processes related to the event that you want to update in Fortinet FortiEDR.</td></tr>
<tr><td>First Seen From</td><td>(Optional) "From" date when the event that you want to update in Fortinet FortiEDR, was seen for the first time. Use this parameter together with the "First Seen To" parameter to specify a date range.</td></tr>
<tr><td>First Seen To</td><td>(Optional) "To" date when the event that you want to update in Fortinet FortiEDR, was seen for the first time. Use this parameter together with the "First Seen From" parameter to specify a date range.</td></tr>
<tr><td>Last Seen From</td><td>(Optional) "From" date when the event that you want to update in Fortinet FortiEDR, was seen for the last time. Use this parameter together with the "Last Seen To" parameter to specify a date range.</td></tr>
<tr><td>Last Seen To</td><td>(Optional) "To" date when the event that you want to update in Fortinet FortiEDR, was seen for the last time. Use this parameter together with the "Last Seen From" parameter to specify a date range.</td></tr>
<tr><td>Seen</td><td>(Optional) True/False parameter indicating whether events that you want to update in Fortinet FortiEDR were read/unread by the user operating the API.</td></tr>
<tr><td>Handled</td><td>(Optional) True/False parameter indicating whether events that you want to update in Fortinet FortiEDR were handled/unhandled.</td></tr>
<tr><td>Severities</td><td>(Optional) A severity value for the filter to match. An option with one of the following values: Critical, High, or Medium.</td></tr>
<tr><td>Destinations</td><td>(Optional) Connection destination(s) of the events that you want to update in Fortinet FortiEDR.</td></tr>
<tr><td>Actions</td><td>(Optional) Actions that were enforced on the events that you want to update in Fortinet FortiEDR. You can choose from the following options: Block, Simulation Block, or Log.</td></tr>
<tr><td>Rule</td><td>(Optional) Short rule name of the rule that triggered the events that you want to update in Fortinet FortiEDR.</td></tr>
<tr><td>Strict Mode</td><td>(Optional) True/False parameter indicating whether or not to perform strict matching on the search parameters while retrieving events from Fortinet FortiEDR. By default, this is set as false.</td></tr>
<tr><td>Classification</td><td>(Optional) Classification of the events that you want to retrieve from Fortinet FortiEDR. Classification is a list of strings that contain one or more of the following values: Malicious, Suspicious, Inconclusive, Likely Safe, PUP, or Safe.</td></tr>
<tr><td>Organization</td><td>(Optional) Select how the operation applies to an organization. Some parts of the Fortinet Endpoint Protection and Response Platform system have separate, non-shared data that is organization-specific. Other parts of the system have data that is shared by all organizations. The value that you specify for the organization parameter, determines the organization to which this operation applies. You can select from the following options: Exact Organization Name: Specify the exact name of the organization whose associated events you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR. All Organizations: Select to fetch events from data shared by all organizations within Fortinet FortiEDR.<br><strong>If you choose 'Exact Organization Name'</strong><ul><li>Organization Name: Specify the exact name of the organization whose associated events you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</li></ul></td></tr>
<tr><td>Muted</td><td>(Optional) True/False parameter indicating whether the event that you want to update in Fortinet FortiEDR is muted/unmuted.</td></tr>
<tr><td>Device Control</td><td>(Optional) Select to include or exclude device control events. Leave blank to ignore the parameter when updating events.</td></tr>
<tr><td>Expired</td><td>(Optional) Select to include or exclude expired events. Leave blank to ignore the parameter when updating events.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>{
    "result": ""
}</pre>

<h3>operation: Get Raw Data Items</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Event ID</td><td>ID of the event that holds the raw data items that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Device Name</td><td>(Optional) Name of the device on which the raw event that you want to retrieve from Fortinet FortiEDR occurred.</td></tr>
<tr><td>Collector Groups</td><td>(Optional) List of collector groups whose collector had reported the raw events that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>First Seen From</td><td>(Optional) "From" date when the raw event that you want to retrieve from Fortinet FortiEDR, was seen for the first time. Use this parameter together with the "First Seen To" parameter to specify a date range.</td></tr>
<tr><td>First Seen To</td><td>(Optional) "To" date when the raw event that you want to retrieve from Fortinet FortiEDR, was seen for the first time. Use this parameter together with the "First Seen From" parameter to specify a date range.</td></tr>
<tr><td>Last Seen From</td><td>(Optional) "From" date when the raw event that you want to retrieve from Fortinet FortiEDR, was seen for the last time. Use this parameter together with the "Last Seen To" parameter to specify a date range.</td></tr>
<tr><td>Last Seen To</td><td>(Optional) "To" date when the raw event that you want to retrieve from Fortinet FortiEDR, was seen for the last time. Use this parameter together with the "Last Seen From" parameter to specify a date range.</td></tr>
<tr><td>Strict Mode</td><td>(Optional) True/False parameter indicating whether or not to perform strict matching on the search parameters while retrieving events from Fortinet FortiEDR. By default, this is set as false.</td></tr>
<tr><td>Full Data Requested</td><td>(Optional) True/False parameter indicating whether to include the event internal information for the raw events that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Raw Event Ids</td><td>(Optional) Specify a list of event IDs to retrieve raw data items.</td></tr>
<tr><td>Page Number</td><td>(Optional) Page number from which you want to retrieve records.</td></tr>
<tr><td>Items Per Page</td><td>(Optional) Maximum number of events that this operation should return for the current page. Default value is 100 and the maximum value is 1000.</td></tr>
<tr><td>Sorting</td><td>(Optional) Name of the fields by which you want to sort the results retrieved by this operation. You can enter the fields in the following format: {"column1":true, "column2":false}. True indicates sorting in descending order. Results are sorted by the first field, then by the second field, and so on.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>[
    {
        "eventId": "",
        "rawEventId": "",
        "device": "",
        "deviceIp": "",
        "destination": "",
        "firstSeen": "",
        "lastSeen": "",
        "count": "",
        "loggedUsers": [],
        "remediateDevice": {
            "Executables": [],
            "Processes": [
                {
                    "Path": "",
                    "Pid": ""
                }
            ]
        }
    }
]</pre>

<h3>operation: Get Event Count</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Event IDs</td><td>(Optional) List of comma-separated event IDs based on which you want to retrieve event counts from Fortinet FortiEDR.</td></tr>
<tr><td>Device Name</td><td>(Optional) Name of the device on which the event whose counts you want to retrieve from Fortinet FortiEDR occurred.</td></tr>
<tr><td>Collector Groups</td><td>(Optional) List of collector groups whose collector had reported the events whose counts you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Operating System</td><td>(Optional) Name of the operating system of the devices on which the events whose counts you want to retrieve from Fortinet FortiEDR occurred.</td></tr>
<tr><td>Device IPs</td><td>(Optional) List of IP addresses of the devices on which the events whose counts you want to retrieve from Fortinet FortiEDR occurred.</td></tr>
<tr><td>MAC Addresses</td><td>(Optional) MAC addresses where the events whose counts you want to retrieve from Fortinet FortiEDR occurred.</td></tr>
<tr><td>Filehash</td><td>(Optional) Hash signature of the main process of the events whose counts you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Process</td><td>(Optional) Name of the main process of the events whose counts you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Process Path</td><td>(Optional) Path of the processes related to the events whose counts you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>First Seen From</td><td>(Optional) "From" date when the events whose counts you want to retrieve from Fortinet FortiEDR, were seen for the first time. Use this parameter together with the "First Seen To" parameter to specify a date range.</td></tr>
<tr><td>First Seen To</td><td>(Optional) "To" date when the events whose counts you want to retrieve from Fortinet FortiEDR, were seen for the first time. Use this parameter together with the "First Seen From" parameter to specify a date range.</td></tr>
<tr><td>Last Seen From</td><td>(Optional) "From" date when the events whose counts you want to retrieve from Fortinet FortiEDR, were seen for the last time. Use this parameter together with the "Last Seen To" parameter to specify a date range.</td></tr>
<tr><td>Last Seen To</td><td>(Optional) "To" date when the events whose counts you want to retrieve from Fortinet FortiEDR, were seen for the last time. Use this parameter together with the "Last Seen From" parameter to specify a date range.</td></tr>
<tr><td>Classification</td><td>(Optional) Classification of the events whose counts you want to retrieve from Fortinet FortiEDR. Classification is a list of strings that contain one or more of the following values: Malicious, Suspicious, Inconclusive, Likely Safe, PUP, or Safe.</td></tr>
<tr><td>Actions</td><td>(Optional) Actions that were enforced on the events whose counts you want to retrieve from Fortinet FortiEDR. You can choose from the following options: Block, Simulation Block, or Log.</td></tr>
<tr><td>Destinations</td><td>(Optional) Connection destination(s) of the events whose counts you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Rule</td><td>(Optional) Short rule name of the rule that triggered the events whose counts you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Seen</td><td>(Optional) True/False parameter indicating whether events whose counts you want to retrieve from Fortinet FortiEDR were read/unread by the user operating the API.</td></tr>
<tr><td>Handled</td><td>(Optional) True/False parameter indicating whether events whose counts you want to retrieve from Fortinet FortiEDR were handled/unhandled.</td></tr>
<tr><td>Signed</td><td>(Optional) True/False parameter indicating whether the events whose counts you want to retrieve from Fortinet FortiEDR are signed/unsigned.</td></tr>
<tr><td>Muted</td><td>(Optional) True/False parameter indicating whether the events whose counts you want to retrieve from Fortinet FortiEDR are muted/unmuted.</td></tr>
<tr><td>Logged in User</td><td>(Optional) Logged-in user associated with the events whose counts you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Organization</td><td>(Optional) Select how the operation applies to an organization. Some parts of the Fortinet Endpoint Protection and Response Platform system have separate, non-shared data that is organization-specific. Other parts of the system have data that is shared by all organizations. The value that you specify for the organization parameter, determines the organization to which this operation applies. You can select from the following options: Exact Organization Name: Specify the exact name of the organization whose associated events you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR. All Organizations: Select to fetch events from data shared by all organizations within Fortinet FortiEDR.<br><strong>If you choose 'Exact Organization Name'</strong><ul><li>Organization Name:  Specify the exact name of the organization whose associated events you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</li></ul></td></tr>
<tr><td>Archived</td><td>(Optional) True/False parameter indicating whether to include only archived events while retrieving event counts from Fortinet FortiEDR. By default, this is set as false.</td></tr>
<tr><td>Strict Mode</td><td>(Optional) True/False parameter indicating whether or not to perform strict matching on the search parameters while retrieving event counts from Fortinet FortiEDR. By default, this is set as false.</td></tr>
<tr><td>Device Control</td><td>(Optional) Select to include or exclude device control events. Leave blank to ignore the parameter when updating events.</td></tr>
<tr><td>Expired</td><td>(Optional) Select to include or exclude expired events. Leave blank to ignore the parameter when updating events.</td></tr>
<tr><td>Page Number</td><td>(Optional) Page number from which you want to retrieve records.</td></tr>
<tr><td>Items Per Page</td><td>(Optional) Maximum number of events that this operation should return for the current page. Default value is 100 and the maximum value is 1000.</td></tr>
<tr><td>Sorting</td><td>(Optional) Name of the fields by which you want to sort the results retrieved by this operation. You can enter the fields in the following format: {"column1":true, "column2":false}. True indicates sorting in descending order. Results are sorted by the first field, then by the second field, and so on.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>{
    "event_count": ""
}</pre>

<h3>operation: Get Event List Extended</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Event IDs</td><td>(Optional) List of comma-separated event IDs based on which you want to retrieve archived/unarchived events from Fortinet FortiEDR.</td></tr>
<tr><td>Device Name</td><td>(Optional) Name of the device on which the events that you want to retrieve from Fortinet FortiEDR occurred.</td></tr>
<tr><td>Collector Groups</td><td>(Optional) List of collector groups whose collector had reported the events that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Operating System</td><td>(Optional) Name of the operating system of the devices on which the events that you want to retrieve from Fortinet FortiEDR occurred.</td></tr>
<tr><td>Device IPs</td><td>(Optional) List of IP addresses of the devices on which the events that you want to retrieve from Fortinet FortiEDR occurred.</td></tr>
<tr><td>MAC Addresses</td><td>(Optional) MAC addresses where the events that you want to retrieve from Fortinet FortiEDR occurred.</td></tr>
<tr><td>Filehash</td><td>(Optional) Hash signature of the main process of the events that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Process</td><td>(Optional) Name of the main process of the events that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Process Path</td><td>(Optional) Path of the processes related to the events that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>First Seen From</td><td>(Optional) "From" date when the events that you want to retrieve from Fortinet FortiEDR, were seen for the first time. Use this parameter together with the "First Seen To" parameter to specify a date range.</td></tr>
<tr><td>First Seen To</td><td>(Optional) "To" date when the events that you want to retrieve from Fortinet FortiEDR, were seen for the first time. Use this parameter together with the "First Seen From" parameter to specify a date range.</td></tr>
<tr><td>Last Seen From</td><td>(Optional) "From" date when the events that you want to retrieve from Fortinet FortiEDR, were seen for the last time. Use this parameter together with the "Last Seen To" parameter to specify a date range.</td></tr>
<tr><td>Last Seen To</td><td>(Optional) "To" date when the events that you want to retrieve from Fortinet FortiEDR, were seen for the last time. Use this parameter together with the "Last Seen From" parameter to specify a date range.</td></tr>
<tr><td>Classification</td><td>(Optional) Classification of the events that you want to retrieve from Fortinet FortiEDR. Classification is a list of strings that contain one or more of the following values: Malicious, Suspicious, Inconclusive, Likely Safe, PUP, or Safe.</td></tr>
<tr><td>Actions</td><td>(Optional) Actions that were enforced on the events that you want to retrieve from Fortinet FortiEDR. You can choose from the following options: Block, Simulation Block, or Log.</td></tr>
<tr><td>Destinations</td><td>(Optional) Connection destination(s) of the events that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Rule</td><td>(Optional) Short rule name of the rule that triggered the events that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Logged in User</td><td>(Optional) Logged-in user associated with the events that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Seen</td><td>(Optional) True/False parameter indicating whether events that you want to retrieve from Fortinet FortiEDR were read/unread by the user operating the API.</td></tr>
<tr><td>Handled</td><td>(Optional) True/False parameter indicating whether events that you want to retrieve from Fortinet FortiEDR were handled/unhandled.</td></tr>
<tr><td>Signed</td><td>(Optional) True/False parameter indicating whether the event that you want to retrieve from Fortinet FortiEDR is signed/unsigned.</td></tr>
<tr><td>Severities</td><td>(Optional) Select the severity to filter retrieved results. You can select one of the following options: Critical High Medium</td></tr>
<tr><td>Muted</td><td>(Optional) True/False parameter indicating whether the event that you want to retrieve from Fortinet FortiEDR is muted/unmuted.</td></tr>
<tr><td>Organization</td><td>(Optional) Select how the operation applies to an organization. Some parts of the Fortinet Endpoint Protection and Response Platform system have separate, non-shared data that is organization-specific. Other parts of the system have data that is shared by all organizations. The value that you specify for the organization parameter, determines the organization to which this operation applies. You can select from the following options: Exact Organization Name: Specify the exact name of the organization whose associated events you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR. All Organizations: Select to fetch events from data shared by all organizations within Fortinet FortiEDR.<br><strong>If you choose 'Exact Organization Name'</strong><ul><li>Organization Name: Specify the exact name of the organization whose associated events you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</li></ul></td></tr>
<tr><td>Strict Mode</td><td>(Optional) True/False parameter indicating whether or not to perform strict matching on the search parameters while retrieving events from Fortinet FortiEDR. By default, this is set as false.</td></tr>
<tr><td>Device Control</td><td>(Optional) Select to include or exclude device control events. Leave blank to ignore the parameter when retrieving results.</td></tr>
<tr><td>Expired</td><td>(Optional) Select to include or exclude expired events. Leave blank to ignore the parameter when retrieving results.</td></tr>
<tr><td>Page Number</td><td>(Optional) Page number from which you want to retrieve records.</td></tr>
<tr><td>Items Per Page</td><td>(Optional) Maximum number of events that this operation should return for the current page. Default value is 100 and the maximum value is 1000.</td></tr>
<tr><td>Sorting</td><td>(Optional) Name of the fields by which you want to sort the results retrieved by this operation. You can enter the fields in the following format: {"column1":true, "column2":false}. True indicates sorting in descending order. Results are sorted by the first field, then by the second field, and so on.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>[
    {
        "eventId": "",
        "handlingState": "",
        "processOwner": "",
        "threatDetails": {
            "threatFamily": "",
            "threatType": "",
            "threatName": ""
        },
        "process": "",
        "processPath": "",
        "processType": "",
        "firstSeen": "",
        "lastSeen": "",
        "seen": "",
        "handled": "",
        "comment": "",
        "certified": "",
        "archived": "",
        "severity": "",
        "classification": "",
        "destinations": [],
        "rules": [],
        "loggedUsers": "",
        "organization": "",
        "muted": "",
        "muteEndTime": "",
        "collectors": [
            {
                "lastSeen": "",
                "ip": "",
                "collectorGroup": "",
                "macAddresses": [],
                "id": "",
                "device": "",
                "operatingSystem": ""
            }
        ],
        "action": ""
    }
]</pre>

<h3>operation: Search Filehash</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Filehash</td><td>One or more comma-separated file hashes that you want to search for in Fortinet FortiEDR.</td></tr>
<tr><td>Organization</td><td>(Optional) Select how the operation applies to an organization. Some parts of the Fortinet Endpoint Protection and Response Platform system have separate, non-shared data that is organization-specific. Other parts of the system have data that is shared by all organizations. The value that you specify for the organization parameter, determines the organization to which this operation applies. You can select from the following options: Exact Organization Name: Specify the exact name of the organization whose associated events you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR. All Organizations: Select to fetch events from data shared by all organizations within Fortinet FortiEDR.<br><strong>If you choose 'Exact Organization Name'</strong><ul><li>Organization Name: Specify the exact name of the organization whose associated events you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</li></ul></td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>[
    {
        "filehash": "",
        "eventIds": [],
        "applications": [],
        "threatsHunting": [
            {
                "deviceName": "",
                "fileName": "",
                "path": ""
            }
        ]
    }
]</pre>

<h3>operation: Get File</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Type</td><td>Type of the device input parameter from which you want to get the file from Fortinet FortiEDR. You can choose between ID or NAME. If you choose 'ID', then you must specify the following parameter: Device ID: ID of the device from which you want to retrieve the file. If you choose 'NAME', then you must specify the following parameter: Device Name: Name of the device from which you want to retrieve the file.<br><strong>If you choose 'ID'</strong><ul><li>Device ID: ID of the device from which you want to retrieve the file.</li></ul><strong>If you choose 'Name'</strong><ul><li>Device Name: Name of the device from which you want to retrieve the file.</li></ul></td></tr>
<tr><td>File Paths</td><td>List of file paths from which you want to retrieve the file. For example: c:\temp\example.exe</td></tr>
<tr><td>Organization</td><td>(Optional) Name of a specific organization whose associated files you want to retrieve from Fortinet FortiEDR. Note: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>{
    "name": "",
    "@id": "",
    "type": "",
    "file": {
        "uploadDate": "",
        "@type": "",
        "uuid": "",
        "assignee": "",
        "thumbnail": "",
        "id": "",
        "@id": "",
        "file": {
            "@type": ""
        },
        "owners": "",
        "@context": "",
        "filename": "",
        "metadata": [],
        "size": "",
        "mimeType": ""
    },
    "createDate": "",
    "description": "",
    "modifyUser": {
        "avatar": "",
        "uuid": "",
        "@id": "",
        "modifyDate": "",
        "userType": "",
        "createDate": "",
        "modifyUser": "",
        "@type": "",
        "@settings": "",
        "createUser": "",
        "id": "",
        "userId": "",
        "name": ""
    },
    "@type": "",
    "@context": "",
    "modifyDate": "",
    "createUser": {
        "avatar": "",
        "@id": "",
        "modifyDate": "",
        "userType": "",
        "createDate": "",
        "modifyUser": "",
        "uuid": "",
        "@type": "",
        "@settings": "",
        "createUser": "",
        "id": "",
        "userId": "",
        "name": ""
    },
    "id": "",
    "alerts": [],
    "assets": [],
    "incidents": [],
    "indicators": [],
    "tasks": [],
    "warrooms": [],
    "workspaces": [],
    "comments": [],
    "cVEs": [],
    "vulnerabilities": [],
    "people": [],
    "uuid": "",
    "owners": [],
    "recordTags": [],
    "assignee": "",
    "userOwners": []
}</pre>

<h3>operation: Retrieve File or Memory</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Raw Event ID</td><td>ID of the raw event on which you want to perform the memory retrieval from Fortinet FortiEDR.</td></tr>
<tr><td>Retrieve From</td><td>Method to be used to perform the memory retrieval from Fortinet FortiEDR. You can choose between Memory or Disk. If you choose Memory, then you must specify the following parameters: Process ID: ID of the process from which you want to take a memory image. Memory Region Start Address: Memory start range, in Hexadecimal format from which you want to take a memory image. Memory Region End Address: Memory end range, in Hexadecimal format from which you want to take a memory image. If you choose Disk, then you must specify the following parameters: File Paths: List of file paths from which you want to perform the memory retrieval in Fortinet FortiEDR.<br><strong>If you choose 'Disk'</strong><ul><li>File Paths: (Optional) List of file paths from which you want to perform the memory retrieval in Fortinet FortiEDR.</li></ul><strong>If you choose 'Memory'</strong><ul><li>Process ID: (Optional) ID of the process from which you want to take a memory image.</li><li>Memory Region Start Address: (Optional) Memory start range, in Hexadecimal format from which you want to take a memory image.</li><li>Memory Region End Address: (Optional) Memory end range, in Hexadecimal format from which you want to take a memory image.</li></ul></td></tr>
<tr><td>Organization</td><td>(Optional) Name of a specific organization on which you want to perform the memory retrieval in Fortinet FortiEDR. Note: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>{
    "name": "",
    "@id": "",
    "type": "",
    "file": {
        "uploadDate": "",
        "@type": "",
        "@id": "",
        "file": {
            "@type": ""
        },
        "owners": "",
        "@context": "",
        "filename": "",
        "metadata": "",
        "size": "",
        "mimeType": ""
    },
    "createDate": "",
    "description": "",
    "modifyUser": {
        "avatar": "",
        "@id": "",
        "modifyDate": "",
        "userType": "",
        "createDate": "",
        "modifyUser": "",
        "@type": "",
        "@settings": "",
        "createUser": "",
        "id": "",
        "userId": "",
        "name": ""
    },
    "@type": "",
    "@context": "",
    "modifyDate": "",
    "createUser": {
        "avatar": "",
        "@id": "",
        "modifyDate": "",
        "userType": "",
        "createDate": "",
        "modifyUser": "",
        "@type": "",
        "@settings": "",
        "createUser": "",
        "id": "",
        "userId": "",
        "name": ""
    },
    "id": ""
}</pre>

<h3>operation: Remediate Device</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Type</td><td>Type of the device input parameter on which you want to perform the remediation action in Fortinet FortiEDR. You can choose between ID or NAME. If you choose 'ID', then you must specify the following parameter: Device ID: ID of the device on which you want to take the remediation action. If you choose 'NAME', then you must specify the following parameter: Device Name: Name of the device on which you want to take the remediation action.<br><strong>If you choose 'ID'</strong><ul><li>Device ID: ID of the device on which you want to take the remediation action.</li></ul><strong>If you choose 'Name'</strong><ul><li>Device Name: Name of the device on which you want to take the remediation action.</li></ul></td></tr>
<tr><td>Organization</td><td>(Optional) Name of a specific organization that contains the device on which you want to perform the remediation action. Note: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</td></tr>
<tr><td>Remediation Action</td><td>Action that you want to perform on the specified device. You can choose from the following options: Kill Process, Delete File, Handle Persistent Data, or Remediate Thread. If you choose 'Kill Process', then you must specify the following parameters: Process ID: ID of the process you want to terminate on the specified device. Process Name: Name of the process you want to terminate on the specified device. If you choose 'Delete File', then you must specify the following parameter: Delete File at Path: List containing the full path of executable files (*.exe) that you want to delete from the specified device. If you choose 'Handle Persistent Data', then you must specify the following parameter: Persistence Data (Registry) Action: Action that should be taken for persistent data on the specified device. You can choose from the following options: Delete Key, Delete Value, or Update. If you choose 'Delete Key', then you must specify the following parameters: Persistence Data (Registry) Path: Path of the persistent data whose key you want to delete on the specified device. Persistence Data (Registry) Value Name: Name of the key value of the persistent data you want to delete on the specified device. If you choose 'Delete Value', then you must specify the following parameters: Persistence Data (Registry) Path: Path of the persistent data whose value you want to delete on the specified device. Persistence Data (Registry) Value Name: Name of the value of the persistent data that you want to delete on the specified device. If you choose 'Update', then you must specify the following parameters: Persistence Data (Registry) Path: Path of the persistent data that you want to update on the specified device. Persistence Data (Registry) Value Name: Name of the value of the persistent data you want to update on the specified device. Persistence Data (Registry) Value New Type: New data value type that should be applied to the persistent data on the specified device. You can choose from the following options: REG_SZ, REG_EXPAND_SZ, REG_BINARY, REG_DWORD, REG_DWORD_BIG_ENDIAN, REG_LINK, REG_MULTI_SZ, REG_RESOURCE_LIST, REG_FULL_RESOURCE_DESCRIPTOR, REG_RESOURCE_REQUIREMENTS_LIST, or REG_QWORD.threadId: (This specifies the thread ID) Persistence Data (Registry) New Content: New data content that should be applied to the persistent data on the specified device. The content format provided depends on the type used in persistenceDataValueNewType. The format should be provided as follows: String value for the following types: REG_SZ(1), REG_EXPAND_SZ(2), REG_DWORD(4), and REG_QWORD(11). Base64 for the following types: REG_BINARY(3), REG_DWORD_BIG_ENDIAN(5), REG_LINK(6), REG_MULTI_SZ(7), REG_RESOURCE_LIST(8), REG_FULL_RESOURCE_DESCRIPTOR(9), and REG_RESOURCE_REQUIREMENTS_LIST(10) If you choose 'Remediate Thread', then you must specify the following parameter: Thread ID: ID of the thread on which you want to take the remediation action.<br><strong>If you choose 'Kill Process'</strong><ul><li>Process ID: Process ID that you want to terminate on the specified device.</li><li>Process Name: Name of the process on which you want to take remediation action.</li></ul><strong>If you choose 'Delete File'</strong><ul><li>Delete File at Path: List of full paths of executable files (*.exe) that you want to delete on the specified device.</li></ul><strong>If you choose 'Handle Persistent Data'</strong><ul><li>Persistence Data (Registry) Action: Action that should be taken for persistent data on the specified device. You can choose from the following options: DeleteKey, DeleteValue, or Update.</li><strong>If you choose 'Delete Key'</strong><ul><li>Persistence Data (Registry) Path: Path of the persistent data on the specified device.</li><li>Persistence Data (Registry) Value Name: Value name of the persistent data on the specified device.</li></ul><strong>If you choose 'Delete Value'</strong><ul><li>Persistence Data (Registry) Path: Path of the persistent data on the specified device.</li><li>Persistence Data (Registry) Value Name: Value name of the persistent data on the specified device.</li></ul><strong>If you choose 'Update'</strong><ul><li>Persistence Data (Registry) Path: Path of the persistent data on the specified device.</li><li>Persistence Data (Registry) Value Name: Value name of the persistent data on the specified device.</li><li>Persistence Data (Registry) Value New Type: New data value type that should be applied to the persistent data on the specified device. You can choose from the following options: REG_SZ, REG_EXPAND_SZ, REG_BINARY, REG_DWORD, REG_DWORD_BIG_ENDIAN, REG_LINK, REG_MULTI_SZ, REG_RESOURCE_LIST, REG_FULL_RESOURCE_DESCRIPTOR, REG_RESOURCE_REQUIREMENTS_LIST or REG_QWORD.threadId: Specifies the thread ID.</li><li>Persistence Data (Registry) New Content: Specifies the persistent data new content. The content format provided depends on the type used in persistenceDataValueNewType. The format should be provided as follows: String for the following types: REG_SZ(1), REG_EXPAND_SZ(2), REG_DWORD(4) and REG_QWORD(11). Base64 for the following types: REG_BINARY(3), REG_DWORD_BIG_ENDIAN(5), REG_LINK(6), REG_MULTI_SZ(7), REG_RESOURCE_LIST(8), REG_FULL_RESOURCE_DESCRIPTOR(9) and REG_RESOURCE_REQUIREMENTS_LIST(10).</li></ul></ul><strong>If you choose 'Remediate Thread'</strong><ul><li>Thread ID: ID of the thread on which you want to take the remediation action.</li></ul></td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>{
    "result": ""
}</pre>

<h3>operation: Get Collector List</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Type</td><td>(Optional) Type of the device whose associate collector list you want to retrieve from Fortinet FortiEDR. You can choose from following options: ID: Specify a list of device IDs, whose associate collector list you want to retrieve from Fortinet FortiEDR, in the Device IDs field. NAME: Specify a list of device names, whose associate collector list you want to retrieve from Fortinet FortiEDR, in the Device Name field.<br><strong>If you choose 'ID'</strong><ul><li>Device IDs: Specify a list of device IDs, whose associate collector list you want to retrieve from Fortinet FortiEDR, in the Device IDs field.</li></ul><strong>If you choose 'Name'</strong><ul><li>Device Names: Specify a list of device names, whose associate collector list you want to retrieve from Fortinet FortiEDR, in the Device Name field.</li></ul></td></tr>
<tr><td>Collector Groups</td><td>(Optional) List of collector group names whose associated collectors you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>IPs</td><td>(Optional) List of IP addresses whose associated collectors you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Operating Systems</td><td>(Optional) List of operating systems whose associated collectors you want to retrieve from Fortinet FortiEDR. For example: Windows 7 Pro.</td></tr>
<tr><td>OS Families</td><td>(Optional) List of OS Families whose associated collectors you want to retrieve from Fortinet FortiEDR. For example: Windows, Windows Server, OS X.</td></tr>
<tr><td>States</td><td>(Optional) List of collector states to retrieve from Fortinet FortiEDR. You can choose one or more from the following options: New Selected Running Disabled Degraded Disconnected Registered Uninstalling Unmanaged Isolated Expired Pending Reboot PendingMigration Migrate</td></tr>
<tr><td>Last Seen Start</td><td>(Optional) Retrieves collectors from Fortinet FortiEDR that was last seen after the value assigned to this date.</td></tr>
<tr><td>Last Seen End</td><td>(Optional) Retrieve collectors from Fortinet FortiEDR that were last seen before the value assigned to this date.</td></tr>
<tr><td>Versions</td><td>(Optional) List of collector versions that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Strict Mode</td><td>(Optional) True/False parameter indicating whether or not to perform strict matching on the search parameters while retrieving event counts from Fortinet FortiEDR. By default, this is set as false.</td></tr>
<tr><td>Show Expired</td><td>(Optional) True/False parameter indicating whether to show an expired collector in the results retrieved from Fortinet FortiEDR.</td></tr>
<tr><td>Logged in User</td><td>(Optional) Logged-in user associated with the collectors you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Organization</td><td>(Optional) Select how the operation applies to an organization. Some parts of the Fortinet Endpoint Protection and Response Platform system have separate, non-shared data that is organization-specific. Other parts of the system have data that is shared by all organizations. The value that you specify for the organization parameter, determines the organization to which this operation applies. You can select from the following options: Exact Organization Name: Specify the exact name of the organization whose associated collectors you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR. All Organizations: Select to fetch collectors from data shared by all organizations within Fortinet FortiEDR.<br><strong>If you choose 'Exact Organization Name'</strong><ul><li>Organization Name: Specify the exact name of the organization whose associated collectors you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</li></ul></td></tr>
<tr><td>Page Number</td><td>(Optional) Page number from which you want to retrieve records.</td></tr>
<tr><td>Items Per Page</td><td>(Optional) Maximum number of events that this operation should return for the current page. Default value is 100 and the maximum value is 1000.</td></tr>
<tr><td>Sorting</td><td>(Optional) Name of the fields by which you want to sort the results retrieved by this operation. You can enter the fields in the following format: {"column1":true, "column2":false}. True indicates sorting in descending order. Results are sorted by the first field, then by the second field, and so on.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>[
    {
        "accountName": "",
        "collectorGroupName": "",
        "crashDumps": "",
        "degradedReason": "",
        "id": "",
        "ipAddress": "",
        "lastSeenTime": "",
        "loggedUsers": [],
        "macAddresses": [],
        "name": "",
        "operatingSystem": "",
        "organization": "",
        "osFamily": "",
        "state": "",
        "stateAdditionalInfo": "",
        "systemInformation": "",
        "version": ""
    }
]</pre>

<h3>operation: Isolate Collector</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Type</td><td>Type of the device whose associate collectors you want to isolate from the Fortinet FortiEDR network. You can choose between ID or Name. If you choose 'ID', then you must specify the following parameter: Device IDs: List of device IDs whose associate collectors you want to isolate from the Fortinet FortiEDR network. If you choose 'Name', then you must specify the following parameter: Device Names: List of device names whose associate collectors you want to isolate from the Fortinet FortiEDR network.<br><strong>If you choose 'ID'</strong><ul><li>Device IDs: List of device IDs whose associate collectors you want to isolate from the Fortinet FortiEDR network.</li></ul><strong>If you choose 'Name'</strong><ul><li>Device Names: List of device names whose associate collectors you want to isolate from the Fortinet FortiEDR network.</li></ul></td></tr>
<tr><td>Organization</td><td>(Optional) Name of a specific organization whose associated collector you want to unisolate from the Fortinet FortiEDR network. Note: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>{
    "result": ""
}</pre>

<h3>operation: Unisolate Collector</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Type</td><td>Type of the device whose associate collectors you want to unisolate from the Fortinet FortiEDR network. You can choose between ID or Name. If you choose 'ID', then you must specify the following parameter: Device IDs: List of device IDs whose associate collectors you want to unisolate from the Fortinet FortiEDR network. If you choose 'Name', then you must specify the following parameter: Device Names: List of device names whose associate collectors you want to unisolate from the Fortinet FortiEDR network.<br><strong>If you choose 'ID'</strong><ul><li>Device IDs: List of device IDs whose associate collectors you want to unisolate from the Fortinet FortiEDR network.</li></ul><strong>If you choose 'Name'</strong><ul><li>Device Names: List of device names whose associate collectors you want to unisolate from the Fortinet FortiEDR network.</li></ul></td></tr>
<tr><td>Organization</td><td>(Optional) Name of a specific organization whose associated collector you want to unisolate from the Fortinet FortiEDR network. Note: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>{
    "result": ""
}</pre>

<h3>operation: Create Exception</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Event ID</td><td>Specify the ID of the event to add as an exception in Fortinet FortiEDR.</td></tr>
<tr><td>Collector Groups</td><td>(Optional) Select the collector group level at which to create an exception. You can choose from the following options: All Collector Groups: Select this option to create exception for all collector groups. Exact Collector Group: Select this option to create exception for the collectors groups specified in the Exact Collector Groups field.<br><strong>If you choose 'Exact Collector Groups'</strong><ul><li>Exact Collector Groups: Specify the collector group names to add into the exception. Specify in CSV format.</li></ul></td></tr>
<tr><td>All Organizations</td><td>(Optional) Select the organization level at which to create an exception. You can choose from the following options: True: Select this option to create exception for all organizations. False: Select this option to create exception for the organization specified in the configuration parameters. NOTE: This parameter is only relevant in a multi-tenancy environment and is allowed only for users with hoster privileges (general administrator).</td></tr>
<tr><td>Destinations</td><td>(Optional) Select the destination level at which to create an exception. You can choose from the following options: All Destinations: Select this option to create exception for all destinations. Exact Destination IPs: Select this option to create exception for the destination IPs specified in the Exact Destination IPs field.<br><strong>If you choose 'Exact Destination IPs'</strong><ul><li>Exact Destination IPs: List of IP addresses to which the exception applies and/or the value of the internal destinations.</li></ul></td></tr>
<tr><td>Users</td><td>(Optional) Select the user level at which to create an exception. You can choose from the following options: All Users: Select this option to create exception for all userss. Exact Users: Select this option to create exception for users specified in the Exact Users field.<br><strong>If you choose 'Exact Users'</strong><ul><li>Exact Users: Specify the list of users to which the exception should be applied.</li></ul></td></tr>
<tr><td>Comment</td><td>(Optional) Specify a user-defined string to attach to the exception being created in Fortinet FortiEDR.</td></tr>
<tr><td>Force Create</td><td>(Optional) Select whether to force-create an exception. You can choose from the following options: True: Select this option to force-create an exception even if existing exceptions cover a particular event. False: Select this option to create exception for the organization specified in the configuration parameters. True for this parameter to apply to create the exception, even if there are already exceptions that cover the specified event.</td></tr>
<tr><td>Exception JSON Values</td><td>(Optional) In order to set the advanced settings of an exception, the user must know which processes exist in the event and which rules were triggered. Please use following JSON format to insert the correct details: { "useInException": { "process_name_1": { "rule_name1": true, "rule_name2": true }, "process_name_2": { "rule_name_1": false } }, "useAnyPath": { "process_name_1": { "rule_name": true }, "process_name_2": { "rule_name": true } }} For example: { "useInException": { " dynamicCode.exe ": { "Unmapped Executable": true, "Executable Format": true, "Dynamic Code": false, "Writeable Code": false }, " dynamic.dll": {} }, "Unmapped Executable": false, "useAnyPath": { " dynamicCode.exe ": { "Dynamic Code": true, "Executable Format": false, "Unmapped Executable": true, "Writeable Code": true }, " dynamic.dll": { "Unmapped Executable": true } }}</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>{
    "result": ""
}</pre>

<h3>operation: Get Exception List</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Created Before</td><td>(Optional) DateTime before which the exceptions that you want to retrieve from Fortinet FortiEDR were created.</td></tr>
<tr><td>Created After</td><td>(Optional) DateTime after which the exceptions that you want to retrieve from Fortinet FortiEDR were created.</td></tr>
<tr><td>Updated Before</td><td>(Optional) DateTime before which the exceptions that you want to retrieve from Fortinet FortiEDR were updated.</td></tr>
<tr><td>Updated After</td><td>(Optional) DateTime after which the exceptions that you want to retrieve from Fortinet FortiEDR were updated.</td></tr>
<tr><td>Organization</td><td>(Optional) Select how the operation applies to an organization. Some parts of the Fortinet Endpoint Protection and Response Platform system have separate, non-shared data that is organization-specific. Other parts of the system have data that is shared by all organizations. The value that you specify for the organization parameter, determines the organization to which this operation applies. You can select from the following options: Exact Organization Name: Specify the exact name of the organization whose associated exceptions you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR. All Organizations: Select to fetch exceptions from data shared by all organizations within Fortinet FortiEDR.<br><strong>If you choose 'Exact Organization Name'</strong><ul><li>Organization Name: Specify the exact name of the organization whose associated exceptions you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</li></ul></td></tr>
<tr><td>Exception Ids</td><td>(Optional) Specify a list of exception IDs to filter the list retrieved from Fortinet FortiEDR. For example: 211171,211172</td></tr>
<tr><td>Rules</td><td>(Optional) Specify the list of rule names to filter the list retrieved from Fortinet FortiEDR. For example: Test Rule1,Test Rule2</td></tr>
<tr><td>Collector Groups</td><td>(Optional) Specify the list of all the collector groups to which the exception applies.</td></tr>
<tr><td>Process</td><td>(Optional) Specify the process to which the exception applies. For example: Update.exe</td></tr>
<tr><td>Path</td><td>(Optional) Specify the path of the exception. For example: \elasticsearch-8.10.2-windows-x86_64\elasticsearch-8.10.2\lib</td></tr>
<tr><td>Comment</td><td>(Optional) Specify a comment attached to the exception.</td></tr>
<tr><td>Destination IP</td><td>(Optional) Specify a destination IP of the exception.</td></tr>
<tr><td>User</td><td>(Optional) Specify a user of the exception. For example: Local System</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>[
    {
        "exceptionId": "",
        "originEventId": "",
        "userName": "",
        "updatedAt": "",
        "createdAt": "",
        "comment": "",
        "organization": "",
        "selectedUsers": [],
        "optionalUsers": [],
        "selectedDestinations": [],
        "optionalDestinations": [],
        "selectedCollectorGroups": [],
        "optionalCollectorGroups": [],
        "alerts": [
            {
                "ruleName": "",
                "process2": {
                    "name": "",
                    "path": "",
                    "usedInException": "",
                    "useAnyPath": "",
                    "signed": ""
                },
                "script": {
                    "name": "",
                    "usedInException": ""
                },
                "process": {
                    "name": "",
                    "path": "",
                    "usedInException": "",
                    "useAnyPath": "",
                    "signed": ""
                }
            }
        ]
    }
]</pre>

<h3>operation: Update Exception</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Event ID</td><td>ID of the event whose associated exception you want to update in Fortinet FortiEDR.</td></tr>
<tr><td>Exception ID</td><td>ID of the exception that you want to update in the Fortinet FortiEDR.</td></tr>
<tr><td>Organization</td><td>Name of a specific organization that you want to update in the specific exception Fortinet FortiEDR. Note:The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</td></tr>
<tr><td>Add Destinations</td><td>(Optional) Type of destination that you want to update in the specific exception Fortinet FortiEDR. You can choose between Exact Destination or All Destinations. If you choose 'Exact Destination', then in the Exact Destinations (IP Set Names) field, specify the destination names, in the CSV format that you want to add to the specified exception. If you choose 'All Destinations', then the Destination parameter will be set automatically to 'All Destinations'.<br><strong>If you choose 'Exact Destinations'</strong><ul><li>Exact Destinations (IP Set Names): If you choose 'Exact Destination', then in the Exact Destinations (IP Set Names) field, specify the destination names, in the CSV format that you want to add to the specified exception. 

If you choose 'All Destinations', then the Destination parameter will be set automatically to 'All Destinations'. </li></ul></td></tr>
<tr><td>Collector Group</td><td>(Optional) Type of collector group that you want to update in the specific exception Fortinet FortiEDR. You can choose between Exact Collector Group or All Groups. or All Organizations. If you choose 'Exact Collector Group', then in the Exact Collector Group field, specify the collector groups, in the CSV format that you want to add to the specified exception. If you choose 'All Groups' or 'All Organizations', then the Collector Group parameter will be set automatically to 'All Groups' or 'All Organizations' respectively.<br><strong>If you choose 'Exact Collector Group'</strong><ul><li>Exact Collector Group: Specify the collector group names to add into the exception. Specify in CSV format.</li></ul></td></tr>
<tr><td>Add Comment</td><td>(Optional) Free text that you want to add as a comment to the exception that you want to update in Fortinet FortiEDR.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains a non-dictionary value.</p>

<h3>operation: Get Event Exceptions</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Event ID</td><td>ID of the event whose associated exceptions you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Organization</td><td>(Optional) Name of a specific organization whose associated event exceptions you want to retrieve from Fortinet FortiEDR. Note: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>[
    {
        "exceptionId": "",
        "originEventId": "",
        "userName": "",
        "updatedAt": "",
        "createdAt": "",
        "comment": "",
        "organization": "",
        "selectedDestinations": [],
        "optionalDestinations": [],
        "selectedCollectorGroups": [],
        "optionalCollectorGroups": [],
        "optionalUsers": [],
        "selectedUsers": [],
        "alerts": [
            {
                "ruleName": "",
                "process": {
                    "name": "",
                    "path": "",
                    "usedInException": "",
                    "useAnyPath": "",
                    "signed": ""
                }
            }
        ]
    }
]</pre>

<h3>operation: Get Raw JSON Event Data</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Raw Event ID</td><td>ID of the event that holds the raw JSON data that you want to retrieve from Fortinet FortiEDR.</td></tr>
<tr><td>Organization</td><td>(Optional) Name of a specific organization whose associated events hold the raw JSON data that you want to retrieve from Fortinet FortiEDR. Note: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>{
    "updateTime": "",
    "sendToSupportOnly": "",
    "LoggedUsers": [
        {
            "Name": "",
            "LogonTime": ""
        }
    ],
    "AutomationData": {
        "comment": "",
        "exportUrls": {
            "pdflink": "",
            "anotherlink": ""
        },
        "informationBlock": [
            {
                "image": "",
                "items": [
                    {
                        "link": "",
                        "image": "",
                        "title": "",
                        "signed": "",
                        "values": [
                            {
                                "key": "",
                                "more": {},
                                "note": "",
                                "value": "",
                                "linker": "",
                                "copyable": "",
                                "virusTotal": ""
                            }
                        ]
                    }
                ],
                "title": "File",
                "title.localized": [
                    {
                        "translation_key": ""
                    }
                ]
            }
        ],
        "comment.localized": [
            {
                "params": [
                    {
                        "english": ""
                    },
                    {
                        "english": "",
                        "translation_key": ""
                    }
                ],
                "translation_key": ""
            },
            {
                "params": [
                    {
                        "english": ""
                    }
                ],
                "translation_key": ""
            }
        ],
        "classificationList": [
            {
                "date": "",
                "image": "",
                "title": "",
                "description": "",
                "title.localized": [
                    {
                        "translation_key": ""
                    }
                ]
            }
        ]
    },
    "EventType": "",
    "deviceAggregationCrc": "",
    "deviceAggregationShaCrc": "",
    "OsVersion": "",
    "SigningStatus": "",
    "RemediateDevice": "",
    "Alerts": [
        {
            "updateTime": "",
            "Rule": "",
            "RuleContentId": "",
            "Process": "",
            "ProcessScriptModule": "",
            "ProcessMountPoint": "",
            "StackType": "",
            "Severity": "",
            "Action": "",
            "KeyCrc": "",
            "ProcessCrc": "",
            "KeyPathCrc": "",
            "ProcessPathCrc": "",
            "KeyScriptCrc": "",
            "ProcessScriptCrc": "",
            "KeyShaCrc": "",
            "ProcessShaCrc": "",
            "IsKeyBinary": "",
            "Key": "",
            "KeyScriptModule": "",
            "MountPoint": "",
            "UseBoth": "",
            "KeyVendor": "",
            "ProcessVendor": "",
            "OS": "",
            "KeySha": "",
            "ProcessSha": "",
            "KeyAnalysisFlags": "",
            "ProcessAnalysisFlags": "",
            "Is64bit": "",
            "Policy": "",
            "Stacks": [
                {
                    "StackNum": ""
                }
            ],
            "WhitelistingReputation": "",
            "WhitelistingExpirationTime": "",
            "Index": "",
            "MainApp": {
                "Executable": "",
                "ScriptModule": "",
                "Sha1Hash": "",
                "Vendor": "",
                "Flags": "",
                "MalwareLikelihoodPercent": "",
                "Src": "",
                "ExtWhiteListing": {
                    "Hash": {
                        "Hash": "",
                        "HashType": ""
                    },
                    "ExtWhiteListing": {
                        "Reputation": "",
                        "MalwareType": "",
                        "FamilyName": "",
                        "ThreatName": "",
                        "Expiration": ""
                    },
                    "CombinedReputation": "",
                    "RLDetails": {
                        "RLReputation": "",
                        "MalwareType": "",
                        "FamilyName": "",
                        "ThreatName": ""
                    }
                }
            },
            "ClassificationRules": [
                {
                    "ClassificationRuleId": "",
                    "Description": ""
                }
            ],
            "MatchedClassificationRules": [
                {
                    "ClassificationRuleId": "",
                    "Description": ""
                }
            ],
            "Classification": "",
            "ExtWhiteListing": {
                "Hash": {
                    "Hash": "",
                    "HashType": ""
                },
                "ExtWhiteListing": {
                    "Reputation": "",
                    "MalwareType": "",
                    "FamilyName": "",
                    "ThreatName": "",
                    "Expiration": ""
                },
                "CombinedReputation": "",
                "RLDetails": {
                    "RLReputation": "",
                    "MalwareType": "",
                    "FamilyName": "",
                    "ThreatName": ""
                }
            },
            "IsSuppressed": "",
            "OriginalClassification": "",
            "IsOriginallySuppressed": "",
            "ClassifyCount": "",
            "ClassificationChanges": [
                {
                    "ClassificationChangedTo": ""
                }
            ],
            "ClassificationRulesMapSecurityLevel": "",
            "ReputationSource": "",
            "ShouldHaveBeenSuppressed": "",
            "ReputationSourceExt": {
                "ReputationSource": ""
            },
            "PolicyModeWhenAlertWasIssued": "",
            "IsKeySigned": "",
            "IsProcessSigned": ""
        }
    ],
    "EventId": "",
    "Version": "",
    "FirstSeen": "",
    "LastSeen": "",
    "HostName": "",
    "Count": "",
    "MainProcessId": "",
    "OperatingSystem": "",
    "OS": "",
    "GlobalAggregationCrc": "",
    "GlobalShaAggregationCrc": "",
    "Application": "",
    "MountPoint": "",
    "AppScriptModule": "",
    "Is64bit": "",
    "IsSigned": "",
    "AppSha": "",
    "AppVendor": "",
    "EventSource": "",
    "EventCoreVersion": "",
    "AggregationEventId": "",
    "AgentVersion": "",
    "ManagementServerVersion": "",
    "WhitelistingExpired": "",
    "MoreAddresses": "",
    "EventClassification": "",
    "EventClassificationSourceAlert": "",
    "AppDetails": {
        "Executable": "",
        "ScriptModule": "",
        "Sha1Hash": "",
        "Vendor": "",
        "Flags": "",
        "MalwareLikelihoodPercent": "",
        "Src": "",
        "ExtWhiteListing": {
            "Hash": {
                "Hash": "",
                "HashType": ""
            },
            "ExtWhiteListing": {
                "Reputation": "",
                "MalwareType": "",
                "FamilyName": "",
                "ThreatName": "",
                "Expiration": ""
            },
            "CombinedReputation": "",
            "RLDetails": {
                "RLReputation": "",
                "MalwareType": "",
                "FamilyName": "",
                "ThreatName": ""
            }
        }
    },
    "AppSourceAlert": "",
    "ClassifierModelVersion": "",
    "SuppressedAlertCount": "",
    "ContentVersion": "",
    "EventRLStatuses": [
        {
            "Hash": "",
            "RLResult": "",
            "IsAlertGenerated": ""
        }
    ],
    "SecurityLevelWhenIssued": "",
    "EventClassificationStage": "",
    "EventRlMissing": [],
    "RepPreResolveTimerCount": "",
    "RepPreResWastedTimeMs": "",
    "EventWorkerTimeMs": "",
    "WasDeffered": "",
    "LastSentToECS": "",
    "WasChangedOnDeferrer": "",
    "CoreHostName": "",
    "DeferrerChanges": "",
    "ConfigurationVersion": "",
    "FlowInfoFlags": "",
    "CustomerName": "",
    "Exceptions": [
        {
            "updateTime": "",
            "UpdatedBy": "",
            "UpdatedAt": "",
            "CreatedBy": "",
            "CreatedAt": "",
            "Alerts": [
                {
                    "updateTime": "",
                    "Rule": "",
                    "RuleContentId": "",
                    "Process": "",
                    "ProcessScriptModule": "",
                    "ProcessMountPoint": "",
                    "StackType": "",
                    "Severity": "",
                    "Action": "",
                    "KeyCrc": "",
                    "ProcessCrc": "",
                    "KeyPathCrc": "",
                    "ProcessPathCrc": "",
                    "KeyScriptCrc": "",
                    "ProcessScriptCrc": "",
                    "KeyShaCrc": "",
                    "ProcessShaCrc": "",
                    "IsKeyBinary": "",
                    "Key": "",
                    "KeyScriptModule": "",
                    "MountPoint": "",
                    "UseBoth": "",
                    "UseProcess": "",
                    "UseAnyKeyPath": "",
                    "UseAnyProcessPath": "",
                    "UseProcessScript": "",
                    "UseKeyScript": "",
                    "KeyVendor": "",
                    "ProcessVendor": "",
                    "OS": "",
                    "KeySha": "",
                    "ProcessSha": "",
                    "KeyAnalysisFlags": "",
                    "ProcessAnalysisFlags": "",
                    "Is64bit": "",
                    "Policy": "",
                    "WcProcess": "",
                    "WcProcessScriptModule": "",
                    "WcKeyScriptModule": "",
                    "WcKey": "",
                    "WcMask": "",
                    "IsKeySigned": "",
                    "IsProcessSigned": ""
                }
            ],
            "EventId": "",
            "OriginalEventJson": {
                "updateTime": "",
                "sendToSupportOnly": "",
                "LoggedUsers": [
                    {
                        "Name": "",
                        "LogonTime": ""
                    }
                ],
                "EventType": "",
                "Alerts": [
                    {
                        "updateTime": "",
                        "Rule": "",
                        "RuleContentId": "",
                        "Process": "",
                        "ProcessScriptModule": "",
                        "ProcessMountPoint": "",
                        "StackType": "",
                        "Severity": "",
                        "Action": "",
                        "KeyCrc": "",
                        "ProcessCrc": "",
                        "KeyPathCrc": "",
                        "ProcessPathCrc": "",
                        "KeyScriptCrc": "",
                        "ProcessScriptCrc": "",
                        "KeyShaCrc": "",
                        "ProcessShaCrc": "",
                        "IsKeyBinary": "",
                        "Key": "",
                        "KeyScriptModule": "",
                        "MountPoint": "",
                        "UseBoth": "",
                        "UseProcess": "",
                        "UseAnyKeyPath": "",
                        "UseAnyProcessPath": "",
                        "UseProcessScript": "",
                        "UseKeyScript": "",
                        "KeyVendor": "",
                        "ProcessVendor": "",
                        "OS": "",
                        "KeySha": "",
                        "ProcessSha": "",
                        "KeyAnalysisFlags": "",
                        "ProcessAnalysisFlags": "",
                        "Is64bit": "",
                        "Policy": "",
                        "MitreTags": "",
                        "Stacks": [
                            {
                                "StackNum": ""
                            }
                        ],
                        "WhitelistingReputation": "",
                        "WhitelistingExpirationTime": "",
                        "Index": "",
                        "MainApp": {
                            "Executable": "",
                            "ScriptModule": "",
                            "Sha1Hash": "",
                            "Vendor": "",
                            "Flags": "",
                            "MalwareLikelihoodPercent": "",
                            "Src": "",
                            "ExtWhiteListing": {
                                "Hash": {
                                    "Hash": "",
                                    "HashType": ""
                                },
                                "ExtWhiteListing": {
                                    "Reputation": "",
                                    "MalwareType": "",
                                    "FamilyName": "",
                                    "ThreatName": "",
                                    "Expiration": ""
                                },
                                "CombinedReputation": "",
                                "RLDetails": {
                                    "RLReputation": "",
                                    "MalwareType": "",
                                    "FamilyName": "",
                                    "ThreatName": ""
                                }
                            }
                        },
                        "ClassificationRules": [
                            {
                                "ClassificationRuleId": "",
                                "Description": ""
                            }
                        ],
                        "MatchedClassificationRules": [
                            {
                                "ClassificationRuleId": "",
                                "Description": ""
                            }
                        ],
                        "Classification": "",
                        "ExtWhiteListing": {
                            "Hash": {
                                "Hash": "",
                                "HashType": ""
                            },
                            "ExtWhiteListing": {
                                "Reputation": "",
                                "MalwareType": "",
                                "FamilyName": "",
                                "ThreatName": "",
                                "Expiration": ""
                            },
                            "CombinedReputation": "",
                            "RLDetails": {
                                "RLReputation": "",
                                "MalwareType": "",
                                "FamilyName": "",
                                "ThreatName": ""
                            }
                        },
                        "IsSuppressed": "",
                        "OriginalClassification": "",
                        "IsOriginallySuppressed": "",
                        "ClassifyCount": "",
                        "ForcedClassification": "",
                        "ClassificationOriginStackData": "",
                        "OriginalClassificationOriginStackData": "",
                        "ClassificationChanges": [
                            {
                                "ClassificationChangedTo": ""
                            }
                        ],
                        "ClassificationRulesMapSecurityLevel": "",
                        "ReputationSource": "",
                        "ShouldHaveBeenSuppressed": "",
                        "ReputationSourceExt": {
                            "ReputationSource": ""
                        },
                        "OriginalReputationSource": "",
                        "PolicyModeWhenAlertWasIssued": "",
                        "IsKeySigned": "",
                        "IsProcessSigned": ""
                    }
                ],
                "EventId": "",
                "Version": "",
                "ApplicationOwner": "",
                "FirstSeen": "",
                "LastSeen": "",
                "Protocol": "",
                "LocalIp": "",
                "HostName": "",
                "LocalPort": "",
                "RemoteIp": "",
                "Country": "",
                "Asn": "",
                "RemotePort": "",
                "Count": "",
                "MainProcessId": "",
                "OperatingSystem": "",
                "OS": "",
                "OsVersion": "",
                "GlobalAggregationCrc": "",
                "GlobalShaAggregationCrc": "",
                "Application": "",
                "MountPoint": "",
                "AppScriptModule": "",
                "Is64bit": "",
                "IsSigned": "",
                "AppSha": "",
                "AppVendor": "",
                "EventSource": "",
                "EventCoreVersion": "",
                "AggregationEventId": "",
                "AgentVersion": "",
                "ManagementServerVersion": "",
                "WhitelistingExpired": "",
                "MoreAddresses": "",
                "EventClassification": "",
                "EventClassificationSourceAlert": "",
                "AppDetails": {
                    "Executable": "",
                    "ScriptModule": "",
                    "Sha1Hash": "",
                    "Vendor": "",
                    "Flags": "",
                    "MalwareLikelihoodPercent": "",
                    "Src": "",
                    "ExtWhiteListing": {
                        "Hash": {
                            "Hash": "",
                            "HashType": ""
                        },
                        "ExtWhiteListing": {
                            "Reputation": "",
                            "MalwareType": "",
                            "FamilyName": "",
                            "ThreatName": "",
                            "Expiration": ""
                        },
                        "CombinedReputation": "",
                        "RLDetails": {
                            "RLReputation": "",
                            "MalwareType": "",
                            "FamilyName": "",
                            "ThreatName": ""
                        }
                    }
                },
                "AppSourceAlert": "",
                "ClassifierModelVersion": "",
                "SuppressedAlertCount": "",
                "ContentVersion": "",
                "EventClassificationOriginStackData": "",
                "EventRLStatuses": [
                    {
                        "Hash": "",
                        "RLResult": "",
                        "IsAlertGenerated": ""
                    }
                ],
                "SecurityLevelWhenIssued": "",
                "EventClassificationStage": "",
                "ReputationSource": "",
                "ShouldHaveBeenSuppressed": "",
                "EventRlMissing": [],
                "RepPreResolveTimerCount": "",
                "RepPreResWastedTimeMs": "",
                "RepPreResAllowedDelayMs": "",
                "EventWorkerTimeMs": "",
                "WasDeffered": "",
                "LastSentToECS": "",
                "WasChangedOnDeferrer": "",
                "EventDigest": "",
                "CoreHostName": "",
                "DeferrerChanges": "",
                "ConfigurationVersion": "",
                "FlowInfoFlags": "",
                "CustomerName": "",
                "Exceptions": "",
                "MacAddresses": "",
                "CollectorGroup": "",
                "EventAggId": "",
                "ForensicsChart": "",
                "EventUniqueId": "",
                "IsSuppressedEvent": "",
                "IsEventReportedByDeviceNotSupportingWildcardsOrIpSets": "",
                "Muted": "",
                "MuteEndTime": "",
                "DeviceMetadata": "",
                "Action": "",
                "ProcessAggregationCrc": "",
                "DeviceAggregationCrc": "",
                "ProcessShaAggregationCrc": "",
                "DeviceShaAggregationCrc": "",
                "IsRepPreResEnabled": "",
                "IsRepPreResolveTimedOut": "",
                "Organization": "",
                "OrganizationId": "",
                "AgentId": "",
                "StackInfos": "",
                "AggregationClassification": "",
                "AggregationClassificationSource": "",
                "ManagementDbId": ""
            },
            "OS": "",
            "Destinations": [],
            "IpGroups": [],
            "AgentGroups": [],
            "AllAccountsAgentGroups": "",
            "AllAgentGroups": "",
            "AllDestinations": "",
            "Origin": "",
            "ExceptionId": ""
        }
    ],
    "MacAddresses": [],
    "CollectorGroup": "",
    "EventAggId": "",
    "EventUniqueId": "",
    "IsSuppressedEvent": "",
    "Muted": "",
    "Action": "",
    "StackInfos": [
        {
            "StackType": "",
            "Timestamp": "",
            "StackInfoFlags": "",
            "ThreadId": "",
            "ProcessId": "",
            "Is64bit": "",
            "ProcessName": "",
            "ExecutableHash": "",
            "ExecutableHashExtWhiteList": {
                "Reputation": "",
                "MalwareType": "",
                "FamilyName": "",
                "ThreatName": "",
                "Expiration": ""
            },
            "ModuleFlags": "",
            "PeErrorFlags": "",
            "PeVerificationErrorFlags": "",
            "ModuleType": "",
            "CommonFlags": "",
            "MalwareLikelihood": "",
            "MalwareLikelihoodNorm": "",
            "CommonAdditionalInfo": [
                {
                    "Type": "",
                    "Privileges": "",
                    "NumOfPrivilegeChanges": "",
                    "ProcessOwner": "",
                    "ProcessEffectiveOwner": "",
                    "LoggedUsers": [
                        {
                            "Name": "",
                            "LogonTime": ""
                        }
                    ]
                },
                {
                    "Type": "",
                    "ObjVersion": "",
                    "FileOwner": "",
                    "LastModified": "",
                    "IsInternetBit": "",
                    "FileAttributes": ""
                },
                {
                    "Type": "",
                    "RootIssuer": "",
                    "RootCertThumbprint": "",
                    "SubjectOfLastCertificate": "",
                    "LastCertThumbprint": "",
                    "IsSignatureValid": "",
                    "IsUnsupportedDigestAlg": "",
                    "IsCertValid": "",
                    "IsUnsupportedCertDigestAlg": "",
                    "IsSelfSigned": "",
                    "IsCertTrusted": "",
                    "IsInvalidSigninigTime": "",
                    "HasExpired": ""
                },
                {
                    "Type": "",
                    "MountPoint": ""
                },
                {
                    "Type": "",
                    "Company": "",
                    "Description": "",
                    "Version": "",
                    "Product": ""
                },
                {
                    "Type": "",
                    "CommandLine": ""
                }
            ],
            "AuxPid": "",
            "AuxProcessName": "",
            "AuxIs64bit": "",
            "AuxModuleFlags": "",
            "AuxPeErrorFlags": "",
            "AuxPeVerificationErrorFlags": "",
            "AuxModuleType": "",
            "AuxCommonFlags": "",
            "AuxCommonAdditionalInfo": [],
            "NumStackEntries": "",
            "StackEntries": [
                {
                    "StackEntryFlags": "",
                    "Count": "",
                    "ESP": "",
                    "StackValue": "",
                    "CallTarget": "",
                    "CommonFlags": "",
                    "ModuleBase": "",
                    "ModuleEnd": "",
                    "TotalRetCount": "",
                    "TotalNoRetCount": "",
                    "ModuleFlags": "",
                    "PeErrorFlags": "",
                    "PeVerificationErrorFlags": "",
                    "ModuleType": "",
                    "MalwareLikelihood": "",
                    "MalwareLikelihoodNorm": "",
                    "ModuleName": "",
                    "ModuleHash": "",
                    "AdditionalInfo": [],
                    "CommonAdditionalInfo": [
                        {
                            "Type": "",
                            "Company": ""
                        },
                        {
                            "Type": "",
                            "ObjVersion": "",
                            "FileOwner": "",
                            "LastModified": "",
                            "IsInternetBit": "",
                            "FileAttributes": ""
                        },
                        {
                            "Type": "",
                            "RootIssuer": "",
                            "RootCertThumbprint": "",
                            "SubjectOfLastCertificate": "",
                            "LastCertThumbprint": "",
                            "IsSignatureValid": "",
                            "IsUnsupportedDigestAlg": "",
                            "IsCertValid": "",
                            "IsUnsupportedCertDigestAlg": "",
                            "IsSelfSigned": "",
                            "IsCertTrusted": "",
                            "IsInvalidSigninigTime": "",
                            "HasExpired": ""
                        },
                        {
                            "Type": "",
                            "MountPoint": ""
                        }
                    ]
                }
            ]
        }
    ],
    "Organization": "",
    "ProcessAggregationCrc": "",
    "DeviceAggregationCrc": "",
    "ProcessShaAggregationCrc": "",
    "DeviceShaAggregationCrc": "",
    "IsRepPreResEnabled": "",
    "IsRepPreResolveTimedOut": "",
    "AgentId": "",
    "OrganizationId": "",
    "AggregationClassification": "",
    "AggregationClassificationSource": "",
    "ManagementDbId": ""
}</pre>

<h3>operation: Create IPSet</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Organization</td><td>(Optional) Select how the operation applies to an organization. Some parts of the Fortinet Endpoint Protection and Response Platform system have separate, non-shared data that is organization-specific. Other parts of the system have data that is shared by all organizations. The value that you specify for the organization parameter, determines the organization to which this operation applies. You can select from the following options: Exact Organization Name: Specify the exact name of the organization in which to create the IPSet. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR. All Organizations: Select to create an IPSet as data shared by all organizations within Fortinet FortiEDR. Each: Select this option to apply the value of the Organization parameter to each organization by this operation. For example, let's assume that the same user exists in multiple organizations and Each is specified in the organization parameter. Here, each organization can update this user separately.<br><strong>If you choose 'Exact Organization Name'</strong><ul><li>Organization Name: Specify the exact name of the organization in which to create the IPSet. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</li></ul></td></tr>
<tr><td>IP Set Name</td><td>Name of the IPSet you want to create in Fortinet FortiEDR.</td></tr>
<tr><td>Description</td><td>Description of the IPSet you want to create in Fortinet FortiEDR.</td></tr>
<tr><td>IP Address to Include</td><td>List of IP addresses to include in the IPSet you want to create in Fortinet FortiEDR.</td></tr>
<tr><td>IP Address to Exclude</td><td>List of IP Addresses to exclude from the IPSet you want to create in Fortinet FortiEDR.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>{
    "result": ""
}</pre>

<h3>operation: Get IPSet List</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>IP to Search</td><td>IP address using which you want to search for IPSets in Fortinet FortiEDR.</td></tr>
<tr><td>Organization</td><td>(Optional) Select how the operation applies to an organization. Some parts of the Fortinet Endpoint Protection and Response Platform system have separate, non-shared data that is organization-specific. Other parts of the system have data that is shared by all organizations. The value that you specify for the organization parameter, determines the organization to which this operation applies. You can select from the following options: Exact Organization Name: Specify the exact name of the organization whose associated IPSets you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR. All Organizations: Select to fetch IPSets from data shared by all organizations within Fortinet FortiEDR.<br><strong>If you choose 'Exact Organization Name'</strong><ul><li>Organization Name: Specify the exact name of the organization whose associated IPSets you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</li></ul></td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>[
    {
        "name": "",
        "description": "",
        "include": [],
        "exclude": [],
        "organization": ""
    }
]</pre>

<h3>operation: Update IPSet</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Organization</td><td>(Optional) Select how the operation applies to an organization. Some parts of the Fortinet Endpoint Protection and Response Platform system have separate, non-shared data that is organization-specific. Other parts of the system have data that is shared by all organizations. The value that you specify for the organization parameter, determines the organization to which this operation applies. You can select from the following options: Exact Organization Name: Specify the exact name of the organization in which to update the IPSet. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR. All Organizations: Select to update the IPSet as data shared by all organizations within Fortinet FortiEDR. Each: Select this option to apply the value of the Organization parameter to each organization by this operation. For example, let's assume that the same user exists in multiple organizations and Each is specified in the organization parameter. Here, each organization can update this user separately.<br><strong>If you choose 'Exact Organization Name'</strong><ul><li>Organization Name: Specify the exact name of the organization in which to update the IPSet. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</li></ul></td></tr>
<tr><td>IP Set Name</td><td>Name of the IPSet you want to update in Fortinet FortiEDR.</td></tr>
<tr><td>Description</td><td>Description of the IPSet you want to update in Fortinet FortiEDR.</td></tr>
<tr><td>Add IP into Sets</td><td>Select this checkbox to add the IP address to the IPSets Include/Exclude sections. Clear this checkbox to remove the IP address from the IPSets Include/Exclude sections</td></tr>
<tr><td>IP Address to Include</td><td>(Optional) List of IP Addresses to include from the IPSet you want to update in Fortinet FortiEDR.</td></tr>
<tr><td>IP Address to Exclude</td><td>(Optional) List of IP Addresses to exclude from the IPSet you want to update in Fortinet FortiEDR.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>{
    "result": ""
}</pre>

<h3>operation: Delete IPSet</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>IP Set Names</td><td>List of the IPSet names that you want to delete from Fortinet FortiEDR.</td></tr>
<tr><td>Organization</td><td>(Optional) Select how the operation applies to an organization. Some parts of the Fortinet Endpoint Protection and Response Platform system have separate, non-shared data that is organization-specific. Other parts of the system have data that is shared by all organizations. The value that you specify for the organization parameter, determines the organization to which this operation applies. You can select from the following options: Exact Organization Name: Specify the exact name of the organization whose associated IPSets you want to delete from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR. All Organizations: Select to delete IPSets from data shared by all organizations within Fortinet FortiEDR.<br><strong>If you choose 'Exact Organization Name'</strong><ul><li>Organization Name:  Specify the exact name of the organization whose associated IPSets you want to delete from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</li></ul></td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>{
    "result": ""
}</pre>

<h3>operation: Get Agent Groups</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Organization</td><td>(Optional) Select how the operation applies to an organization. Some parts of the Fortinet Endpoint Protection and Response Platform system have separate, non-shared data that is organization-specific. Other parts of the system have data that is shared by all organizations. The value that you specify for the organization parameter, determines the organization to which this operation applies. You can select from the following options: Exact Organization Name: Specify the exact name of the organization whose associated agent groups you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR. All Organizations: Select to fetch agent groups from data shared by all organizations within Fortinet FortiEDR.<br><strong>If you choose 'Exact Organization Name'</strong><ul><li>Organization Name: Specify the exact name of the organization whose associated agent groups you want to retrieve from Fortinet FortiEDR.</li></ul></td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>[
    {
        "id": "",
        "name": "",
        "organization": "",
        "targetVersions": [
            {
                "osFamily": "",
                "version": ""
            }
        ]
    }
]</pre>

<h3>operation: Get System Summary</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Organization</td><td>(Optional) Select how the operation applies to an organization. Some parts of the Fortinet Endpoint Protection and Response Platform system have separate, non-shared data that is organization-specific. Other parts of the system have data that is shared by all organizations. The value that you specify for the organization parameter, determines the organization to which this operation applies. You can select from the following options: Exact Organization Name: Specify the exact name of the organization whose associated environment summary you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR. All Organizations: Select to fetch environment summary from data shared by all organizations within Fortinet FortiEDR.<br><strong>If you choose 'Exact Organization Name'</strong><ul><li>Organization Name: Specify the exact name of the organization whose associated environment summary you want to retrieve from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</li></ul></td></tr>
<tr><td>Add License Blob</td><td>(Optional) Select this option, i.e., set it to 'true' to the license blob to the response retrieved by this operation. By default, addLicenseBlob is set to 'false'.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>{
    "endpointsLicenseCapacity": "",
    "endpointsInUse": "",
    "mobileInUse": "",
    "maxAccountCount": "",
    "repositoryAddOns": "",
    "serialNumber": "",
    "workstationCollectorsLicenseCapacity": "",
    "serverCollectorsLicenseCapacity": "",
    "iotDevicesLicenseCapacity": "",
    "registeredCollectors": "",
    "workstationsCollectorsInUse": "",
    "serverCollectorsInUse": "",
    "iotDevicesInUse": "",
    "collectorsState": {
        "Degraded": "",
        "Pending Reboot": "",
        "Disabled": "",
        "Disconnected": "",
        "RebootPending": "",
        "Running": "",
        "Uninstalling": ""
    },
    "collectorsDegradedState": {
        "BSOD": "",
        "DegradedWin32Offset": "",
        "DriverVerifierDetected": "",
        "MissingPolicyEngine": "",
        "OsxEndpointSecurityExtensionNotApproved": "",
        "OsxEndpointSecurityExtensionWasNotGrantedFullDiskAccess": "",
        "OsxFortiEdrWasNotGrantedFullDiskAccess": "",
        "OsxNeitherExtensionIsApproved": "",
        "OsxNetworkExtensionNotApproved": "",
        "ProcessCannotBeTerminated": "",
        "Stopped": "",
        "Stopping": "",
        "UsingPreviousPolicyEngineFailedToUpgrade": "",
        "ApproveKernelExtensions": "",
        "ContentUpdateError": "",
        "DriverLoadFailure": "",
        "FailedConfigurationUpdate": "",
        "GatewayUnreachable": "",
        "LostConnection": "",
        "MissingMiniFilterSupport": "",
        "NoConfiguration": "",
        "NoDiskSpace": "",
        "OTIFailed": "",
        "PAEDisabled": "",
        "unsupportedOSVersion": ""
    },
    "collectorsRunningState": {
        "autonomously": "",
        "core": ""
    },
    "collectorsDisconnectedState": {
        "disconnected": "",
        "expired": "",
        "migrated": "",
        "pendingMigration": ""
    },
    "collectorsWithDumps": {
        "LinuxKernelPanic": "",
        "MacOSKernelPanic": "",
        "NsloCollector": "",
        "NsloCollectorService": "",
        "WindowsKernelFull": "",
        "WindowsKernelMini": ""
    },
    "licenseExpirationDate": "",
    "managementVersion": "",
    "managementHostname": "",
    "managementExternalIP": "",
    "managementInternalIP": "",
    "collectorVersions": [],
    "collectorVersionsV2": [
        {
            "count": "",
            "version": ""
        }
    ],
    "cores": [
        {
            "name": "",
            "address": "",
            "version": "",
            "status": "",
            "statusV2": ""
        }
    ],
    "aggregators": [
        {
            "name": "",
            "address": "",
            "version": "",
            "status": "",
            "statusv2": ""
        }
    ],
    "repositories": [
        {
            "address": "",
            "status": ""
        }
    ],
    "systemState": "",
    "customerName": "",
    "licenseFeatures": [],
    "licenseType": "",
    "installationId": "",
    "time": "",
    "timeZone": "",
    "environmentUniqueId": "",
    "licenseBlob": "",
    "ecsStatus": "",
    "ecsRegistrationURL": "",
    "contentVersion": ""
}</pre>

<h3>operation: Get Organizations</h3>

<h4>Input parameters</h4>

<p>None.</p>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>[
    {
        "name": "",
        "organizationId": "",
        "workstationsAllocated": "",
        "serversAllocated": "",
        "endpointsAllocated": "",
        "endpointInUse": "",
        "iotAllocated": "",
        "workstationsInUse": "",
        "serversInUse": "",
        "iotInUse": "",
        "expirationDate": "",
        "vulnerabilityAndIoT": "",
        "forensics": "",
        "edr": "",
        "verificationCode": "",
        "eXtendedDetection": "",
        "repositoryAddOns": "",
        "isAdminAccount": ""
    }
]</pre>

<h3>operation: Move Collectors</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Collectors</td><td>Specify a list of collector device names. To move collectors between organizations, the collectors parameter should contain the organization name with a backslash before the name. For example: OrgA\collectorA. Only a user with hosting permissions can move collectors between organizations. In this case, the organization property is mandatory and must have the value as All Organizations.</td></tr>
<tr><td>Target Collector Group</td><td>Specify the target collector group name. To move collectors between organizations, the targetCollectorGroup parameter should contain the organization name with a backslash before the name. For example: OrgA\collectorA. Only a user with hosting permissions can move collectors between organizations. In this case, the organization property is mandatory and must have the value as All Organizations.</td></tr>
<tr><td>Organization</td><td>(Optional) Select how the operation applies to an organization. Some parts of the Fortinet Endpoint Protection and Response Platform system have separate, non-shared data that is organization-specific. Other parts of the system have data that is shared by all organizations. The value that you specify for the organization parameter, determines the organization to which this operation applies. You can select from the following options: Exact Organization Name: Specify the exact name of the organization whose associated collector groups you want to move from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR. All Organizations: Select to move collector groups from data shared by all organizations within Fortinet FortiEDR.<br><strong>If you choose 'Exact Organization Name'</strong><ul><li>Organization Name: Specify the exact name of the organization whose associated collector groups you want to move from Fortinet FortiEDR. NOTE: The value that you specify in this parameter must match exactly with the organization name specified in Fortinet FortiEDR.</li></ul></td></tr>
<tr><td>Force Assign</td><td>(Optional) Indicates whether to force the assignment, even if the organization of the target collector group is under migration.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>{
    "result": ""
}</pre>

<h3>operation: Search IOC</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Organization</td><td>(Optional) Specify the organization name using which you will access the Fortinet FortiEDR server. Note: Specifies the organization name in multi-tenant environments.</td></tr>
<tr><td>Category</td><td>(Optional) Specifies the category name, either: Process, File, Registry, Network or Event Log. All is the default value.</td></tr>
<tr><td>Devices</td><td>(Optional) Specifies the CSV list of devices on which the events have occurred.</td></tr>
<tr><td>Time</td><td>(Optional) Select the time period of the events. Last Hour, Last 12 Hours, Last 24 Hours, Last 7 Days, Last 30 Days or Custom. The default value is Last Hour.<br><strong>If you choose 'Custom'</strong><ul><li>From Time: Specifies the starting (from) creation time of the events.</li><li>From Time: Specifies the ending (to) creation time of events.</li></ul></td></tr>
<tr><td>Filters</td><td>(Optional) Specifies the filters to add to the query in JSON format. fieldName: Specifies the filter field name, includeValues: Specifies whether the values list should be included or excluded from the query (true to include, false to exclude). values: Specifies the list of values to be included or excluded from the query.</td></tr>
<tr><td>Query</td><td>(Optional) Specifies a query with Lucene syntax.</td></tr>
<tr><td>Sorting</td><td>(Optional) Check this option if you want to sort the results based on the provided input parameters.<br><strong>If you choose 'true:'</strong><ul><li>Field: Specifies the field by which to sort.</li><li>Order: Specifies the field by which to sort.</li><li>Priority: Specifies the level of sorting. Sorting can be done based on multiple fields, starting with priority 0 and then internal sorting 1, 2, 3 and so on.</li></ul></td></tr>
<tr><td>Page Number</td><td>(Optional) Specify the page number from which you want to retrieve the results.</td></tr>
<tr><td>Items Per Page</td><td>(Optional) Specifies an integer to be used for paging that indicates the number of activity events to retrieve for the current page. The default is 100.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains the following populated JSON schema:</p>

<pre>[
    {
        "ID": "",
        "Time": "",
        "Type": "",
        "MITRE": [
            {
                "ID": "",
                "Tactic": "",
                "Techniques": [
                    {
                        "ID": "",
                        "Technique": ""
                    }
                ]
            }
        ],
        "rowId": "",
        "Device": {
            "OS": "",
            "Name": "",
            "OSType": "",
            "OSVersion": "",
            "InternalIp": [],
            "CollectorId": "",
            "KernelVersion": "",
            "OrganizationId": "",
            "CollectorVersion": "",
            "OrganizationName": "",
            "CollectorVersionBreakdown": {
                "Build": "",
                "Major": "",
                "Minor": "",
                "Patch": ""
            }
        },
        "Source": {
            "Process": {
                "PID": "",
                "CommandLine": "",
                "TID": "",
                "File": {
                    "Ext": "",
                    "Name": "",
                    "Path": "",
                    "Type": "",
                    "Owner": {
                        "UserId": "",
                        "Username": ""
                    },
                    "MountPoint": "",
                    "VolumeType": "",
                    "CreationTime": "",
                    "OriginalDrive": "",
                    "StaticFileData": {
                        "Size": "",
                        "MD5Hash": "",
                        "SHA1Hash": "",
                        "Reputation": {
                            "Reputation": ""
                        },
                        "SHA256Hash": "",
                        "SigningInfo": {
                            "IsSigned": "",
                            "Signatures": [
                                {
                                    "IsValid": "",
                                    "IssuedBy": "",
                                    "SignedBy": "",
                                    "IsPrimary": "",
                                    "Timestamp": "",
                                    "Thumbprint": "",
                                    "TimestampedBy": "",
                                    "TimestampIsValid": "",
                                    "InternalTimestamp": "",
                                    "TimestampIssuedBy": "",
                                    "TimestampThumbprint": "",
                                    "IsCertificateExpired": "",
                                    "IsSignatureTimeValid": "",
                                    "IsTimestampTimeValid": "",
                                    "TimestampIsCertificateExpired": ""
                                }
                            ]
                        },
                        "MachineLearning": {
                            "Score": "",
                            "ModelVersion": ""
                        },
                        "ExecutableFormatData": {
                            "CompanyName": "",
                            "FileVersion": "",
                            "ProductName": "",
                            "Architecture": "",
                            "ProductVersion": "",
                            "FileDescription": ""
                        }
                    },
                    "ModificationTime": ""
                },
                "Name": "",
                "User": {
                    "UserId": "",
                    "Username": ""
                },
                "OSData": {
                    "Windows": {
                        "UAC": {
                            "IsAdmin": "",
                            "IsTokenFiltered": ""
                        },
                        "IntegrityLevel": ""
                    }
                },
                "SessionID": "",
                "CreationTime": "",
                "ParentProcess": {
                    "PID": "",
                    "Path": "",
                    "CreationTime": ""
                },
                "ApplicationInfo": {
                    "CompanyName": "",
                    "ProductName": "",
                    "ProductVersion": ""
                },
                "OperationSource": {
                    "Type": ""
                }
            }
        },
        "Target": {
            "Process": {
                "PID": "",
                "CommandLine": "",
                "File": {
                    "Ext": "",
                    "Name": "",
                    "Path": "",
                    "Type": "",
                    "Owner": {
                        "UserId": "",
                        "Username": ""
                    },
                    "MountPoint": "",
                    "VolumeType": "",
                    "CreationTime": "",
                    "OriginalDrive": "",
                    "StaticFileData": {
                        "Size": "",
                        "MD5Hash": "",
                        "SHA1Hash": "",
                        "Reputation": {
                            "Certainty": "",
                            "Reputation": ""
                        },
                        "SHA256Hash": "",
                        "SigningInfo": {
                            "IsSigned": "",
                            "Signatures": [
                                {
                                    "IsValid": "",
                                    "IssuedBy": "",
                                    "SignedBy": "",
                                    "IsPrimary": "",
                                    "Timestamp": "",
                                    "Thumbprint": "",
                                    "TimestampedBy": "",
                                    "TimestampIsValid": "",
                                    "InternalTimestamp": "",
                                    "TimestampIssuedBy": "",
                                    "TimestampThumbprint": "",
                                    "IsCertificateExpired": "",
                                    "IsSignatureTimeValid": "",
                                    "IsTimestampTimeValid": "",
                                    "TimestampIsCertificateExpired": ""
                                }
                            ]
                        },
                        "MachineLearning": {
                            "Score": "",
                            "ModelVersion": "2"
                        },
                        "ExecutableFormatData": {
                            "CompanyName": "",
                            "FileVersion": "",
                            "ProductName": "",
                            "Architecture": "",
                            "ProductVersion": "",
                            "FileDescription": ""
                        }
                    },
                    "ModificationTime": ""
                },
                "Name": "",
                "User": {
                    "UserId": "",
                    "Username": ""
                },
                "OSData": {
                    "Windows": {
                        "UAC": "",
                        "IntegrityLevel": ""
                    }
                },
                "SessionID": "",
                "CreationTime": "",
                "AdditionalData": {
                    "Ancestors": [
                        {
                            "PID": "",
                            "Path": "",
                            "CreationTime": ""
                        },
                        {
                            "PID": "",
                            "Path": "",
                            "CreationTime": ""
                        }
                    ],
                    "BaseAddress": ""
                },
                "ApplicationInfo": {
                    "CompanyName": "",
                    "ProductName": "",
                    "ProductVersion": ""
                }
            }
        },
        "Category": "",
        "DeviceId": "",
        "SaveDate": "",
        "Sequence": "",
        "TimeZone": "",
        "TimeFromBoot": "",
        "EventProcessTime": ""
    }
]</pre>

<h3>operation: Execute an API Request</h3>

<h4>Input parameters</h4>

<table border=1><thead><tr><th>Parameter</th><th>Description</th></tr></thead><tbody><tr><td>Endpoint</td><td>Specify the REST API endpoint for the action to perform, e.g., /events/list-raw-data-items, /ip-sets/list-ip-sets, etc. The full list of available actions is accessible from FNDN at https://fndn.fortinet.net/index.php?/fortiapi/1210-fortiedr/. Note: Do not specify a REST API endpoint path that starts with /management-rest, as this is internally handled.</td></tr>
<tr><td>Method</td><td>The HTTP Method to use</td></tr>
<tr><td>query_params</td><td>(Optional) Specify the he Rest API query parameters object in JSON format.</td></tr>
<tr><td>Payload</td><td>(Optional) The payload needed for the call. Use empty brackets if there is no payload.</td></tr>
</tbody></table>

<h4>Output</h4>

<p>The output contains a non-dictionary value.</p>

<h2>Included playbooks</h2>

<p>The <code>Sample - Fortinet FortiEDR - 2.1.0</code> playbook collection comes bundled with the Fortinet FortiEDR connector. These playbooks contain steps using which you can perform all supported actions. You can see bundled playbooks in the <strong>Automation</strong> &gt; <strong>Playbooks</strong> section in FortiSOAR&trade; after importing the Fortinet FortiEDR connector.</p>

<ul>
<li>&gt; FortiEDR &gt; Controlled Asset Creation</li>
<li>&gt; FortiEDR &gt; Create and Link Asset</li>
<li>&gt; FortiEDR &gt; Fetch Events</li>
<li>&gt;&gt; FortiEDR &gt; Handle Macro</li>
<li>Create Exception</li>
<li>Create IPSet</li>
<li>Delete IPSet</li>
<li>Execute an API Request</li>
<li>FortiEDR &gt; Ingest</li>
<li>Get Agent Groups</li>
<li>Get Collector List</li>
<li>Get Event Count</li>
<li>Get Event Exceptions</li>
<li>Get Event List Extended</li>
<li>Get Event by ID</li>
<li>Get Events</li>
<li>Get Exception List</li>
<li>Get File</li>
<li>Get IPSet List</li>
<li>Get Organizations</li>
<li>Get Raw Data Items</li>
<li>Get Raw JSON Event Data</li>
<li>Get System Summary</li>
<li>Isolate Collector</li>
<li>Move Collectors</li>
<li>Remediate Device</li>
<li>Retrieve File or Memory</li>
<li>Search Filehash</li>
<li>Search IOC</li>
<li>Unisolate Collector</li>
<li>Update Events</li>
<li>Update Exception</li>
<li>Update IPSet</li>
</ul>

<p><strong>Note</strong>: If you are planning to use any of the sample playbooks in your environment, ensure that you clone those playbooks and move them to a different collection since the sample playbook collection gets deleted during connector upgrade and delete.</p>

<h2>Data Ingestion Support</h2>

<p>Use the Data Ingestion Wizard to easily ingest data into FortiSOAR&trade; by pulling events/alerts/incidents, based on the requirement.</p>

<p><strong>TODO:</strong> provide the list of steps to configure the ingestion with the screen shots and limitations if any in this section.</p>

---
owner: Ops Manager
iaas: Azure
---

**How it works**

<%= partial '_upgrade-planner' %>

<% if vars.product_full == 'VMware Tanzu RabbitMQ for VMs' %>
<%= partial '_upgrade-planner'' %>
<% else %>
When enrolling a Work Managed device, the Intelligent Hub adds a managed Google account to the device.
<% end %>

When enrolling a Work Managed device, the Intelligent Hub adds a managed Google account to the device. The managed Google account is used to push public applications and related policies through the Managed Play Store. 

When Workspace ONE UEM is set up for a closed network deployment, the managed Google account is not added on the device. Therefore, devices need not connect to Google to complete enrollment. Profiles (with the exception of Public App Auto Update), Products, and Internal Applications (uploaded to the Workspace ONE UEM console) can be pushed to the device since these resources are delivered from Workspace ONE to the device directly without Google connectivity. 

**Closed Network Considerations**

When deploying corporate owned devices on a closed network without connection to Google services, consider the following:

- Only Work Managed enrollment is possible. Corporate Owned Personally Enabled (COPE) is not available without Google connectivity. 
- Public applications cannot be deployed as there is no access to the Play Store. By extension, Public App Auto Update profiles also cannot be applied. 
- Applications must be uploaded to the Workspace ONE UEM console as an internal app for deployment to devices on closed networks. 
- If you wish to set up only a portion of your devices in a closed network, you must complete the Android EMM Registration using [Managed Google Accounts](https://docs.vmware.com/en/VMware-Workspace-ONE-UEM/services/Android_Platform/GUID-AWT-SETUP-AFW-ACCOUNT.html). 
- You must use AirWatch Cloud Messaging to manage your Android devices in real time. Firebase Cloud Messaging is not supported as devices cannot connect to these servers.

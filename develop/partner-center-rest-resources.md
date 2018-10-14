---
title: Partner Center REST resources
description: This section provides definitions for the JSON elements needed to create requests and parse responses using the Partner Center REST API.
ms.assetid: E7C51D19-C6A7-4A4C-9F17-B4D39195972A
ms.date: 12/15/2017
ms.localizationpriority: medium
---

# Partner Center REST resources


**Applies To**

-   Partner Center
-   Partner Center operated by 21Vianet
-   Partner Center for Microsoft Cloud Germany
-   Partner Center for Microsoft Cloud for US Government

This section provides definitions for the JSON elements needed to create
requests and parse responses using the Partner Center REST API. For more
information about how to use these elements, including sample code, see
the [Scenarios](scenarios.md) section and the [Partner Center
samples](partner-center-samples.md) section.

## <span id="In_this_section"></span><span id="in_this_section"></span><span id="IN_THIS_SECTION"></span>In this section


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><a href="analytics.md" data-raw-source="[Analytics](analytics.md)">Analytics</a></td>
<td><ul>
<li>PartnerLicensesDeploymentInsights</li>
<li>PartnerLicensesUsageInsights</li>
<li>CustomerLicensesDeploymentInsights</li>
<li>PartnerLicensesUsageInsights</li>
</ul></td>
</tr>
<tr class="even">
<td><a href="auditing.md" data-raw-source="[Auditing](auditing.md)">Auditing</a></td>
<td><ul>
<li>AuditRecord</li>
</ul></td>
</tr>
<tr class="odd">
<td><a href="azure-rate-card.md" data-raw-source="[Azure Rate Card](azure-rate-card.md)">Azure Rate Card</a></td>
<td><ul>
<li>AzureRateCard</li>
<li>AzureMeter</li>
<li>AzureOfferTerm</li>
</ul></td>
</tr>
<tr class="even">
<td><a href="azure-utilization-record.md" data-raw-source="[Azure Utilization Record](azure-utilization-record.md)">Azure Utilization Record</a></td>
<td><ul>
<li>AzureUtilizationRecord</li>
<li>AzureResource</li>
<li>AzureInstanceData</li>
</ul></td>
</tr>
<tr class="odd">
<td><a href="cart.md" data-raw-source="[Cart](cart.md)">Cart</a></td>
<td><ul>
<li>Cart</li>
<li>CartLineItem</li>
<li>CartError</li>
</ul></td>
</tr>
<tr class="even">
<td><a href="conversions.md" data-raw-source="[Conversions](conversions.md)">Conversions</a></td>
<td><ul>
<li>Conversion</li>
<li>ConversionError</li>
<li>ConversionResult</li>
</ul></td>
</tr>
<tr class="odd">
<td><a href="countryinformation.md" data-raw-source="[CountryInformation](countryinformation.md)">CountryInformation</a></td>
<td><ul>
<li>CountryInformation</li>
<li>CountryValidationRules</li>
</ul></td>
</tr>
<tr class="even">
<td><a href="customers.md" data-raw-source="[Customer](customers.md)">Customer</a></td>
<td><ul>
<li>Customer</li>
<li>CustomerCompanyProfile</li>
<li>CustomerBillingProfile</li>
<li>CustomerRelationshipRequest</li>
</ul></td>
</tr>
<tr class="odd">
<td><a href="customer-usage.md" data-raw-source="[Customer Usage Budgeting](customer-usage.md)">Customer Usage Budgeting</a></td>
<td><ul>
<li>CustomerMonthlyUsageRecord</li>
<li>CustomerUsageSummary</li>
<li>PartnerUsageSummary</li>
<li>SpendingBudget</li>
</ul></td>
</tr>
<tr class="even">
<td><a href="entitlement.md" data-raw-source="[Entitlement](entitlement.md)">Entitlement</a></td>
<td><ul>
<li>Entitlement</li>
<li>ReferenceOrder</li>
<li>EntitlementType</li>
<li>Artifact</li>
<li>ArtifactType</li>
<li>VirtualMachineReservedInstanceArtifact</li>
<li>VirtualMachineReservedInstanceArtifactDetails</li>
<li>VirtualMachineReservation</li>
</ul></td>
</tr>
<tr class="odd">
<td><a href="invoice.md" data-raw-source="[Invoice](invoice.md)">Invoice</a></td>
<td><ul>
<li>Invoice</li>
<li>InvoiceDetail</li>
<li>InvoiceLineItem</li>
<li>InvoiceSummary</li>
<li>InvoiceSummaryDetail</li>
<li>InvoiceSummaries</li>
<li>LicenseBasedLineItem</li>
<li>UsageBasedLineItem</li>
<li>InvoiceStatement</li>
</ul></td>
</tr>
<tr class="even">
<td><a href="licenses.md" data-raw-source="[License](licenses.md)">License</a></td>
<td><ul>
<li>License</li>
<li>LicenseUpdate</li>
<li>LicenseAssignment</li>
<li>LicenseWarning</li>
<li>ProductSku</li>
<li>ServicePlan</li>
<li>SubscribedSku</li>
</ul></td>
</tr>
<tr class="odd">
<td><a href="managedservice.md" data-raw-source="[ManagedService](managedservice.md)">ManagedService</a></td>
<td><ul>
<li>ManagedService</li>
<li>ManagedServiceLinks</li>
</ul></td>
</tr>
<tr class="even">
<td><a href="offer.md" data-raw-source="[Offer](offer.md)">Offer</a></td>
<td><ul>
<li>Offer</li>
<li>OfferCategory</li>
<li>OfferLinks</li>
<li>OfferProduct</li>
</ul></td>
</tr>
<tr class="odd">
<td><a href="orders.md" data-raw-source="[Order](orders.md)">Order</a></td>
<td><ul>
<li>Order</li>
<li>OrderLineItem</li>
<li>OrderLinks</li>
<li>OrderLineItemLinks</li>
<li>OrderStatus</li>
</ul></td>
</tr>
<tr class="even">
<td><a href="profiles.md" data-raw-source="[Profile](profiles.md)">Profile</a></td>
<td><ul>
<li>BillingProfile</li>
<li>LegalBusinessProfile</li>
<li>MpnProfile</li>
<li>OrganizationProfile</li>
<li>SupportProfile</li>
</ul></td>
</tr>
<tr class="odd">
<td><a href="products.md" data-raw-source="[Products](products.md)">Products</a></td>
<td><ul>
<li>Product</li>
<li>ItemType</li>
<li>ProductLinks</li>
<li>Sku</li>
<li>Availability</li>
<li>InventoryCheckRequest</li>
<li>InventoryItem</li>
<li>InventoryRestriction</li>
<li>BillingCycleType</li>
</ul></td>
</tr>
<tr class="even">
<td><a href="relationships.md" data-raw-source="[Relationships](relationships.md)">Relationships</a></td>
<td><ul>
<li>PartnerRelationship</li>
<li>RelationshipRequest</li>
</ul></td>
</tr>
<tr class="odd">
<td><a href="servicecosts.md" data-raw-source="[ServiceCosts](servicecosts.md)">ServiceCosts</a></td>
<td><ul>
<li>ServiceCostsSummary</li>
<li>ServiceCostsLineItem</li>
<li>ServiceCostsSummaryLinks</li>
</ul></td>
</tr>
<tr class="even">
<td><a href="servicerequest.md" data-raw-source="[ServiceRequest](servicerequest.md)">ServiceRequest</a></td>
<td><ul>
<li>ServiceRequest</li>
<li>ServiceRequestContact</li>
<li>ServiceRequestNote</li>
<li>ServiceRequestOrganization</li>
<li>SupportTopic</li>
</ul></td>
</tr>
<tr class="odd">
<td><a href="subscriptions.md" data-raw-source="[Subscription](subscriptions.md)">Subscription</a></td>
<td><ul>
<li>Subscription</li>
<li>SubscriptionLinks</li>
<li>SubscriptionProvisioningStatus</li>
<li>SubscriptionRegistrationStatus</li>
<li>SupportContact</li>
<li>RegisterSubscription</li>
</ul></td>
</tr>
<tr class="even">
<td><a href="subscriptionusage.md" data-raw-source="[Subscription Usage](subscriptionusage.md)">Subscription Usage</a></td>
<td><ul>
<li>SubscriptionDailyUsageRecord <em>(Obsolete)</em></li>
<li>SubscriptionMonthlyUsageRecord</li>
<li>SubscriptionUsageSummary</li>
</ul></td>
</tr>
<tr class="odd">
<td><a href="upgrade.md" data-raw-source="[Upgrade](upgrade.md)">Upgrade</a></td>
<td><ul>
<li>Upgrade</li>
<li>UpgradeError</li>
<li>UpgradeResult</li>
<li>UserLicenseError</li>
</ul></td>
</tr>
<tr class="even">
<td><a href="user.md" data-raw-source="[User](user.md)">User</a></td>
<td><ul>
<li>User</li>
<li>CustomerUser</li>
<li>UserCredentials</li>
<li>UserMember</li>
</ul></td>
</tr>
<tr class="odd">
<td><a href="utility-resources.md" data-raw-source="[Utility Resources](utility-resources.md)">Utility Resources</a></td>
<td><ul>
<li>Address</li>
<li>Contact</li>
<li>FieldFilter</li>
<li>FileInfo</li>
<li>Link</li>
<li>PasswordProfile</li>
<li>ResourceLinks</li>
<li>ResourceAttributes</li>
<li>SecureString</li>
</ul></td>
</tr>
</tbody>
</table>

 

 

 





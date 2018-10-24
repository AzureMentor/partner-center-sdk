---
title: Confirm customer acceptance of Microsoft Cloud Agreement
description: This topic explains how to confirm customer acceptance of the Microsoft Cloud Agreement. 
ms.date: 10/14/2018
ms.localizationpriority: medium
---

# Confirm customer acceptance of Microsoft Cloud agreement

**Applies To**

- Partner Center

> [!NOTE]  
> The **Agreement** resource is currently supported by Partner Center in the Microsoft public cloud only. It is not applicable to:
> - Partner Center operated by 21Vianet
> - Partner Center for Microsoft Cloud Germany
> - Partner Center for Microsoft Cloud for US Government

How to confirm customer acceptance of the Microsoft Cloud agreement.

## Prerequisites

- If you are using the Partner Center .NET SDK, version 1.9 or newer is required.
- If you are using the Partner Center Java SDK, version 1.8 or newer is required.
- Credentials as described in [Partner Center authentication](./partner-center-authentication.md). This scenario supports authentication with both standalone App and App+User credentials.
- A customer ID (customer-tenant-id).
- Date when customer accepted the Microsoft Cloud Agreement.
- Information about the user from the organization who accepted the Microsoft Cloud Agreement, including:
  - First name
  - Last name
  - Email address
  - Phone number (optional)

## Examples

### .NET

To confirm or reconfirm that a customer has accepted to the Microsoft Cloud Agreement:

1. Retrieve the agreement metadata for the Microsoft Cloud Agreement. See [Get agreement metadata for Microsoft Cloud Agreement](get-agreement-metadata.md) for details. This step is required to obtain the **TemplateId** of the Microsoft Cloud Agreement.

    ```csharp
    /// IAggregatePartner partnerOperations;
    var agreements = partnerOperations.AgreementDetails.Get();

    AgreementMetaData microsoftCloudAgreement = agreements.Items.FirstOrDefault (agr => agr.AgreementType == AgreementType.MicrosoftCloudAgreement);
    ```

2. Create a new **Agreement** object containing details of the confirmation. Then use the **IAggregatePartner.Customers** collection and call the **ById** method with the specified customer's ID. Then, call the **Agreements** property, followed by calling **Create** or **CreateAsync**.

    ``` csharp
    // string selectedCustomerId;

    var agreementToCreate = new Agreement
    {
        UserId = "3d6f2c09-eb40-48ca-a4b3-d24c9c007531",
        PrimaryContact = new Contact
        {
            FirstName = "Tania",
            LastName = "Carr",
            Email = "SomeEmail@outlook.com",
            PhoneNumber = "1234567890"
        },
        TemplateId = microsoftCloudAgreement.TemplateId,
        DateAgreed = DateTime.UtcNow,
        Type = AgreementType.MicrosoftCloudAgreement
    };

    Agreement agreement = partnerOperations.Customers.ById(selectedCustomerId).Agreements.Create(agreementToCreate);
    ```

#### .NET Sample

A complete sample can be found in the [CreateCustomerAgreement](https://github.com/PartnerCenterSamples/Partner-Center-SDK-Samples/blob/master/Source/Partner%20Center%20SDK%20Samples/Agreements/CreateCustomerAgreement.cs) class from the [console test app](https://github.com/PartnerCenterSamples/Partner-Center-SDK-Samples) project.

### Java

To confirm or reconfirm that a customer has accepted to the Microsoft Cloud Agreement:

1. Retrieve the agreement metadata for the Microsoft Cloud Agreement. See [Get agreement metadata for Microsoft Cloud Agreement](get-agreement-metadata.md) for details. This step is required to obtain the **TemplateId** of the Microsoft Cloud Agreement.

    ```java
    /// IAggregatePartner partnerOperations;

    ResourceCollection<AgreementMetaData> agreements = partnerOperations.getAgreements().get();
    AgreementMetaData microsoftCloudAgreement;

    for (AgreementMetaData metadata : agreements) 
    {
        if(metadata.getAgreementType() == AgreementType.MicrosoftCloudAgreement)
        {
            microsoftCloudAgreement = metadata;
        }
    }
    ```

2. Create a new **Agreement** object containing details of the confirmation. Then use the **IAggregatePartner.getCustomers** function and call the **byId** function with the specified customer's identifier. Then, call the **getAgreements** property, followed by calling the **create** function.

    ```java
    // String selectedCustomerId;

    Contact primaryContact = new Contact();

    primaryContact.setEmail("SomeEmail@outlook.com");
    primaryContact.setFirstName("Tania");
    primaryContact.setLastName("Carr");
    primaryContact.setPhoneNumber("1234567890");

    Agreement agreementToCreate = new Agreement();

    agreementToCreate.setContact(primaryContact);
    agreementToCreate.setDateAgreed(new DateTime());
    agreementToCreate.setTemplateId(microsoftCloudAgreement.getTemplateId());
    agreementToCreate.setType(AgreementType.MicrosoftCloudAgreement);
    agreementToCreate.setUserId("3d6f2c09-eb40-48ca-a4b3-d24c9c007531");

    Agreement agreement = partnerOperations.getCustomers().byId(selectedCustomerId).getAgreements().create(agreementToCreate);
    ```

#### Java Sample

A complete sample can be found in the [CreateCustomerAgreement](https://github.com/Microsoft/Partner-Center-Java-Samples/blob/master/src/main/java/com/microsoft/store/partnercenter/samples/agreements/CreateCustomerAgreement.java) class from the [console test app](https://github.com/Microsoft/Partner-Center-Java-Samples) project.

### PowerShell

1. Retrieve the agreement metadata for the Microsoft Cloud Agreement. See [Get agreement metadata for Microsoft Cloud Agreement](get-agreement-metadata.md) for details. This step is required to obtain the **TemplateId** of the Microsoft Cloud Agreement.  

    ```powershell  
    $agreement = Get-PartnerAgreementDetail | Where-Object {$_.AgreementType -eq 'MicrosoftCloudAgreement'} | Select-Object -First 1
    ```  

2. Execute the [**New-PartnerCustomerAgreement**](https://github.com/Microsoft/Partner-Center-PowerShell/blob/master/docs/help/New-PartnerCustomerAgreement.md) command  

    ```powershell  
    New-PartnerCustomerAgreement -TemplateId $agreement.TemplateId -AgreementType MicrosoftCloudAgreement -CustomerId '14876998-c0dc-46e6-9d0c-65a57a6c32ec' -ContactEmail 'someemail@outlook.com' -ContactFirstName 'Tania' -ContactLastName 'Carr'
    ```  

## <span id="_Request"></span><span id="_request"></span><span id="_REQUEST"></span>REST Request

To confirm or re-confirm that a customer has accepted the Microsoft Cloud Agreement:

1. Retrieve the agreement metadata for the Microsoft Cloud Agreement. See [Get agreement metadata for Microsoft Cloud Agreement](get-agreement-metadata.md) for details. This step is required to obtain the **templateId** of the Microsoft Cloud Agreement.
2. Create a new resource to confirm that a customer has accepted the Microsoft Cloud Agreement. See [Get agreement metadata for Microsoft Cloud Agreement](get-agreement-metadata.md) for details.

To create a new **Agreement** resource to confirm that a customer has accepted the Microsoft Cloud Agreement:

**Request syntax**

| Method | Request URI                                                                                        |
|--------|----------------------------------------------------------------------------------------------------|
| POST   | [*\{baseURL\}*](partner-center-rest-urls.md)/v1/customers/{customer-tenant-id}/agreements HTTP/1.1 |

**URI parameter**

Use the following query parameter to specify the customer you are confirming.

| Name               | Type | Required | Description                                                                                 |
|--------------------|------|----------|---------------------------------------------------------------------------------------------|
| customer-tenant-id | GUID | Y        | The value is a GUID formatted **customer-tenant-id** that allows you to specify a customer. |

**Request headers**

- See [Partner Center REST headers](headers.md) for more information.

**Request body**

This table describes the required properties in the request body.

| Name      | Type   | Description                                                                                  |  
|-----------|--------|----------------------------------------------------------------------------------------------|  
| Agreement | object | Details provided by partner to confirm customer acceptance of the Microsoft Cloud Agreement. |  

### <span id="Agreement"></span><span id="agreement"></span><span id="AGREEMENT"></span>

**Agreement**

This table describes the minimum required fields to create an **Agreement** resource.

| Property       | Type   | Description                              |
|----------------|--------|------------------------------------------|
| userId         | string | Object identifier of the logged in user in the partner tenant who is providing confirmation on behalf of the partner organization. |
| primaryContact | [Contact](./utility-resources.md#contact) | Information about the user from the customer organization who accepted the Microsoft Cloud Agreement, including:  </br> - firstName </br> - lastName</br> - email</br> - phoneNumber (optional) |
| dateAgreed     | string in UTC date time format |The date when the customer accepted the agreement. |
| templateId     |string | Unique identifier of the agreement type accepted by the customer. You can obtain the **templateId** for Microsoft Cloud Agreement by retrieving the agreement metadata for Microsoft Cloud Agreement. See [Get agreement metadata for Microsoft Cloud Agreement](get-agreement-metadata.md) for details. |
| type           |AgreementType enum | Agreement type accepted by the customer. Currently, the only supported value is "MicrosoftCloudAgreement". |
  
**Request example**

```http
POST https://api.partnercenter.microsoft.com/v1/customers/14876998-c0dc-46e6-9d0c-65a57a6c32ec/agreements HTTP/1.1
Authorization: Bearer <token>
Accept: application/json
MS-RequestId: 94e4e214-6b06-4fb7-96d1-94d559f9b47f
MS-CorrelationId: ab993325-1605-4cf4-bac4-fb584142a31b
{
    "userId": "3d6f2c09-eb40-48ca-a4b3-d24c9c007531",
    "primaryContact": {
        "firstName": "Tania",
        "lastName": "Carr",
        "email": " SomeEmail@Outlook.com",
        "phoneNumber": "1234567890"
    },
    "templateId": "998b88de-aa99-4388-a42c-1b3517d49490",
    "dateAgreed": "2018-06-14T00:00:00.000Z",
    "type": "MicrosoftCloudAgreement"
}
```

## <span id="Response"></span><span id="response"></span><span id="RESPONSE"></span>REST Response

If successful, this method returns an **Agreement** resource.

**Response success and error codes**

Each response comes with an HTTP status code that indicates success or failure and additional debugging information. Use a network trace tool to read this code, error type, and additional parameters. For the full list, see [Partner Center REST error codes](error-codes.md).

**Response example**

```http
HTTP/1.1 201 Created
Content-Length: 261
Content-Type: application/json
MS-RequestId: 94e4e214-6b06-4fb7-96d1-94d559f9b47f
MS-CorrelationId: ab993325-1605-4cf4-bac4-fb584142a31b
{
    "userId": "3d6f2c09-eb40-48ca-a4b3-d24c9c007531",
    "primaryContact": {
        "firstName": "Tania",
        "lastName": "Carr",
        "email": " SomeEmail@Outlook.com",
        "phoneNumber": "1234567890"
    },
    "templateId": "998b88de-aa99-4388-a42c-1b3517d49490",
    "dateAgreed": "2018-06-14T00:00:00.000Z",
    "type": "MicrosoftCloudAgreement"
}
```
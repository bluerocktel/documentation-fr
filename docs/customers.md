## Customers

---

### Store a new customer (test)

**POST /api/v1/customers**

#### Parameters

The only mandatory parameter is the name:

- brand_id: branding attached to this customer, default 1
- representative_id: salesperson in charge of the customer
- customerAccount: customerAccount, automatically created if not provided
- accountsReference: reference in the accounting system, if different from customerAccount
- name*: name of the customer
- brand: trading name of the customer, if exists
- registrationNumber: registration number of the customer
- taxRegistrationNumber: tax registration number of the customer
- type: type of company
- capital: capital in your currency,
- mainAddressLine1
- mainAddressLine2
- mainAddressCity
- mainAddressCountry
- website
- active: boolean, default *true*
- isReseller : boolean, default *false*
- resellerLevel: integer,
- chargeVAT: boolean, default *true* (set to *false* if you are not charging VAT to this customer)
- applyVATAutoReverseOperators: boolean, default false (set to *true* if you apply auto-reverse for VAT for this customer on Telecom services)
- onCallDuty: boolean, default *false* (set to *true* if the customer is under on call duty contract)
- vip: boolean, default *false* (set to *true* if customer is vip)

#### Sample request:

##### Curl:

```
curl --request POST \
     --url 'https://bluerockteladmin.test/api/v1/customers?name=Soci%C3%A9t%C3%A9&customerAccount=123456' \
     --header 'authorization: Bearer {token}'
```

##### PHP:

```
<?php
   
   $curl = curl_init();
   
   curl_setopt_array($curl, array(
     CURLOPT_URL => "https://bluerockteladmin.test/api/v1/customers?name=Soci%C3%A9t%C3%A9&customerAccount=123456",
     CURLOPT_RETURNTRANSFER => true,
     CURLOPT_ENCODING => "",
     CURLOPT_MAXREDIRS => 10,
     CURLOPT_TIMEOUT => 30,
     CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
     CURLOPT_CUSTOMREQUEST => "POST",
     CURLOPT_POSTFIELDS => "",
     CURLOPT_HTTPHEADER => array(
       "authorization: Bearer {token}"
     ),
   ));
   
   $response = curl_exec($curl);
   $err = curl_error($curl);
   
   curl_close($curl);
   
   if ($err) {
     echo "cURL Error #:" . $err;
   } else {
     echo $response;
   }
```

##### Python:

```
import http.client
   
   conn = http.client.HTTPSConnection("bluerockteladmin.test")
   
   payload = ""
   
   headers = { 'authorization': "Bearer {token}" }
   
   conn.request("POST", "/api/v1/customers?name=Soci%C3%A9t%C3%A9&customerAccount=123456", payload, headers)
   
   res = conn.getresponse()
   data = res.read()
   
   print(data.decode("utf-8"))
```

#### Response:

The API returns the id of the created customer:
```
{
  "response": 113
}
```

### Get a customer (from customer id)

**GET /api/v1/customers/{customer}**

#### Parameters:

- customer*: customer id

#### Sample request

##### Curl:
```
curl --request GET \
  --url https://bluerockteladmin.test/api/v1/customers/113 \
  --header 'authorization: Bearer {token}'
```
##### PHP:

```
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://bluerockteladmin.test/api/v1/customers/113",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_POSTFIELDS => "",
  CURLOPT_HTTPHEADER => array(
    "authorization: Bearer {token}"
  ),
));

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```

##### Python:

```
import http.client

conn = http.client.HTTPSConnection("bluerockteladmin.test")

payload = ""

headers = { 'authorization': "Bearer {token}" }

conn.request("GET", "/api/v1/customers/113", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

##### Response

```
{
  "customer": {
    "id": 113,
    "brand_id": 1,
    "representative_id": null,
    "customerAccount": "123456",
    "accountsReference": null,
    "name": "Société",
    "brand": null,
    "registrationNumber": null,
    "taxRegistrationNumber": null,
    "mainContactFirstName": null,
    "mainContactLastName": null,
    "type": null,
    "capital": null,
    "activityCode": null,
    "sector_id": null,
    "origin_id": null,
    "mainAddressLine1": null,
    "mainAddressLine2": null,
    "mainAddressPostalCode": null,
    "mainAddressCity": null,
    "mainAddressCountry": null,
    "emailAddress": null,
    "accountEmailAddress": null,
    "website": null,
    "phone": null,
    "mobilePhone": null,
    "fax": null,
    "logo": null,
    "active": 1,
    "activity": null,
    "category": null,
    "qualification": null,
    "prospection_code_id": 1,
    "isReseller": 0,
    "resellerLevel": 0,
    "language_id": 1,
    "acceptEmails": 1,
    "acceptCalls": 1,
    "supplier": 0,
    "chargeVAT": 1,
    "applyVATAutoReverseOperators": 0,
    "language": null,
    "comment": null,
    "mergeInvoices": 1,
    "isGroupingAccount": 0,
    "chargeGroupingAccount": null,
    "isPayer": 0,
    "ftp": 0,
    "ftpServer": null,
    "ftpUsername": null,
    "ftpPassword": null,
    "ftpHomeDirectory": null,
    "ftpAccountId": null,
    "ftpAssociatedEmail": null,
    "quickSearch": null,
    "suppliers": null,
    "onCallDuty": 0,
    "vip": 0,
    "canSendSms": 0,
    "smsAuthorisation": null,
    "numberOfInvoices": 0,
    "lastInvoice": null,
    "quickSearchLabel": null,
    "quickSearchIndex": 0,
    "created_at": "2020-08-04T10:42:27.000000Z",
    "updated_at": "2020-08-04T10:42:27.000000Z"
  }
}
```

### Get a customer (from customerAccount)

**GET /api/v1/customerAccounts/{customerAccount}**

Same as previous, using the customerAccount as parameter instead of BlueRockTEL's customer id.

```
curl --request GET \
  --url https://bluerockteladmin.test/api/v1/customerAccounts/123456 \
  --header 'authorization: Bearer {token}'
```

### Update a customer 

**PUT /api/v1/customers/{customer}**

#### Parameters:

- customer*: customer id
- brand_id: branding attached to this customer, default 1
- representative_id: salesperson in charge of the customer
- customerAccount: customerAccount, automatically created if not provided
- accountsReference: reference in the accounting system, if different from customerAccount
- name: name of the customer
- brand: trading name of the customer, if exists
- registrationNumber: registration number of the customer
- taxRegistrationNumber: tax registration number of the customer
- type: type of company
- capital: capital in your currency,
- mainAddressLine1
- mainAddressLine2
- mainAddressCity
- mainAddressCountry
- website
- active: boolean, default *true*
- isReseller : boolean, default *false*
- resellerLevel: integer,
- chargeVAT: boolean, default *true* (set to *false* if you are not charging VAT to this customer)
- applyVATAutoReverseOperators: boolean, default false (set to *true* if you apply auto-reverse for VAT for this customer on Telecom services)
- onCallDuty: boolean, default *false* (set to *true* if the customer is under on call duty contract)
- vip: boolean, default *false* (set to *true* if customer is vip)












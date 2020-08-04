## Customers

---

### Get a customer

**GET /api/v1/customers/{customer}**


#### Parameters

- customerAccount



### Store a new customer

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

```curl --request POST \
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

```import http.client
   
   conn = http.client.HTTPSConnection("bluerockteladmin.test")
   
   payload = ""
   
   headers = { 'authorization': "Bearer {token}" }
   
   conn.request("POST", "/api/v1/customers?name=Soci%C3%A9t%C3%A9&customerAccount=123456", payload, headers)
   
   res = conn.getresponse()
   data = res.read()
   
   print(data.decode("utf-8"))
```

### Get a customer from customerAccount

**GET /api/v1/customerAccounts/{customerAccount}**










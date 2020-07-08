## Listes de diffusion

### Obtenir les listes de diffusion disponibles

**GET /api/v1/sms/recipientLists**

#### Paramètres :

- customerAccout : compte client Encom.

#### Exemples de requête

##### Curl :

```
curl --request GET \
  --url 'https://telecom0525-clients.bluerocktel.net/api/v1/sms/recipientLists?customerAccount=CL3578' \
  --header 'authorization: Bearer {token} '
```

##### PHP :

```
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://telecom0525-clients.bluerocktel.net/api/v1/sms/recipientLists?customerAccount=CL3578",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_POSTFIELDS => "",
  CURLOPT_HTTPHEADER => array(
    "authorization: Bearer {token} "
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

##### Python :

```
import http.client

conn = http.client.HTTPSConnection("telecom0525-clients.bluerocktel.net")

payload = ""

headers = { 'authorization': "Bearer {token} " }

conn.request("GET", "/api/v1/sms/recipientLists?customerAccount=CL3578", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```
#### Exemple de réponse :

```
[
  {
    "id": 1,
    "customerAccount": "CL3578",
    "name": "Clients Liste 1",
    "created_at": "2020-06-12 17:27:00",
    "updated_at": "2020-07-08 06:48:38"
  },
  {
    "id": 2,
    "customerAccount": "CL3578",
    "name": "Clients Liste 2",
    "created_at": "2020-07-08 06:49:05",
    "updated_at": "2020-07-08 06:49:05"
  },
  {
    "id": 3,
    "customerAccount": "CL3578",
    "name": "Prospects Liste 1",
    "created_at": "2020-07-08 06:49:26",
    "updated_at": "2020-07-08 06:49:40"
  }
]
```
## Messages unitaires

### Envoyer un message unitaire**

**POST /api/v1/sms/singleMessage**

#### Paramètres

- customerAccount * : compte client Encom
- recipient * : numéro de téléphone du destinataire
- message * : texte du message
- type * : type du message, 't' pour 'transactionnel' ou 'm' pour marketing
- idSend: campagne d'envoi (facultatif)
- listener: url recevant la notification de résultat du message (facultatif)

#### Exemples de requête

##### Curl

```
curl --request POST \
  --url 'https://telecom0525-clients.bluerocktel.net/api/v1/sms/singleMessage?customerAccount=CL3578&recipient=0603790931&message=Hello%20World!&type=t&=' \
  --header 'authorization: Bearer {token} '
```

##### PHP

```
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://telecom0525-clients.bluerocktel.net/api/v1/sms/singleMessage?customerAccount=CL3578&recipient=0603790931&message=Hello%20World!&type=t&=",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
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

##### Python

```
import http.client

conn = http.client.HTTPSConnection("telecom0525-clients.bluerocktel.net")

payload = ""

headers = { 'authorization': "Bearer {token} " }

conn.request("POST", "/api/v1/sms/singleMessage?customerAccount=CL3578&recipient=0603790931&message=Hello%20World!&type=t&=", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

#### Exemple de réponse

Lorsque le message est planifié avec succès, l'API retourne un code "201 Created" ainsi que l'id du message :

```
{
  "store": 20
}
```
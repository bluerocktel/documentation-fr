## Clients

Le pack BlueRockTEL 

### Compte client

*customerAccount, string*

Il s'agit du compte vous permettant d'identifier le client.

Par défaut, BlueRockTEL crée un compte de type 'CL0001' pour chaque client, mais vous pouvez choisir le format qui vous convient le mieux.

Si vous n'utilisez pas de comptes clients, vous pouvez laisser cette colonne vide.

### Compte comptable

*accountsReference, string*

Identification du client en comptabilité.

À n'indiquer que s'il est nécessaire (notamment pour vos exports comptables) et différent du compte client.

### Raison sociale

*name, string*

La colonne Raison sociale doit toujours être complétée.

Elle peut être remplacée par le nom complet du client dans le cas d'une personne physique.

### SIRET

*registrationNumber, string*

### Numéro de TVA intracommunautaire

*taxRegistrationNumber, string*

### Type de société

*type*

### Capital social

*capital*

### Première ligne d'adresse

*mainAddressLine1*

Pour un client multisite, l'adresse à indiquer dans la fiche client est toujours l'adresse du siège social. Les adresses des différents sites ou établissements secondaires seront indiquées au niveau des dossiers clients.

### Seconde ligne d'adresse

*mainAddressLine2*

### Code Postal

*postalCode*

### Ville

*mainAddressCity*

### Site Web

*website*

Url du site web du client

### Actif

*active: boolean, default true*

Cette colonne permet d'indiquer si le client est actif ou non.

Indiquez 1 pour actif ou 0 pour inactif.

### Revendeur

*isReseller: boolean, default false*

Cette colonne permet d'indiquer si le client agit comme un revendeur de vos produits et services.

Indiquez 1 s'il est revendeur et 0 dans le cas contraire.

### Niveau de revendeur

*resellerLevel, integer*

Dans le cas ou le client est revendeur, et si vous avez plusieurs niveaux de revendeurs, cette colonne vous permet d'indiquer à quel niveau il appartient.

Cette information sera utile, par exemple, pour appliquer automatiquement des remises revendeurs.

Cette colonne accepte un nombre entier, par exemple 1, 2 ou 3.

### Facturer la TVA

*chargeVAT, boolean default true*

Cette colonne vous permet d'indiquer si vous facturez de la TVA à votre client ou non. Par exemple, si votre entreprise est établie en France et si votre client est établi dans un autre pays de l'Union Européenne, vous ne lui facturerez probablement pas la TVA.

Indiquer 1 si vous facturez de la TVA à votre client, 0 dans le cas contraire.

###  Appliquer la TVA auto-liquidée (opérateur Arcep)

*applyVATAutoReverseOperators, boolean default false*

Si à la fois votre entreprise et votre client sont opérateurs déclarés auprès de l'Arcep, cette colonne vous permet d'indiquer que vous souhaitez appliquer le mécanisme de TVA auto-liquidée sur les services Telecom.

Indiquer 1 si vous souhaitez appliquer le mécanisme de TVA auto-liquidée pour ce client, 0 dans le cas contraire.

### Client sous contrat d'astreinte

*onCallDuty, boolean default false*

Cette colonne vous permet d'indiquer si votre client bénéficie d'un contrat d'astreinte.

Cette information est utile si, par exemple, votre système de téléphonie interroge l'API de BlueRockTEL pour des routages d'appels entrants.

Indiquer 1 si votre client bénéficie d'un contrat d'astreinte, 0 dans le cas contraire.

### Client VIP

*vip, boolean default false*

Cette colonne vous permet d'indiquer si votre client à un statut VIP.

Cette information est utile si, par exemple, votre système de téléphonie interroge l'API de BlueRockTEL pour des routages entrants. Un usage typique est de reconnaître le numéro de l'appelant et de l'envoyer vers le support prioritaire.
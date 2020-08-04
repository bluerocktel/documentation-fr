## Api

---

### Get API version and status

**GET /api/version**

```$ curl --request GET \
     --url https://telecom0517-admin.bluerocktel.net/api/version \
     --header 'authorization: Bearer {token} '
```

#### Response

```{
     "version": "1.0",
     "status": "ok",
     "vendor": "BlueRockTEL",
     "url": "https:\/\/bluerocktel.com"
   }
```


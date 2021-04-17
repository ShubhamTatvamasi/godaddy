# godaddy

get all the records from the domain:
```bash
export GODADDY_API_KEY=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
export GODADDY_API_SECRET=xxxxxxxxxxxxxxxxxxxxxx

curl -s \
  -H "Authorization: sso-key $GODADDY_API_KEY:$GODADDY_API_SECRET" \
  "https://api.godaddy.com/v1/domains/shubhamtatvamasi.com/records" | jq
```


get a specific record:
```bash
curl -s \
  -H "Authorization: sso-key $GODADDY_API_KEY:$GODADDY_API_SECRET" \
  "https://api.godaddy.com/v1/domains/shubhamtatvamasi.com/records/A/nginx.google" | jq
```

delete a specific record:
```bash
curl -s \
  -X "DELETE" \
  -H "Authorization: sso-key $GODADDY_API_KEY:$GODADDY_API_SECRET" \
  "https://api.godaddy.com/v1/domains/shubhamtatvamasi.com/records/A/nginx.google"
```

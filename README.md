# godaddy

get all the records from the domain:
```bash
export GODADDY_API_KEY=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
export GODADDY_API_SECRET=xxxxxxxxxxxxxxxxxxxxxx

curl -s \
  -H 'Content-Type: application/json' \
  -H "Accept: application/json" \
  -H "Authorization: sso-key $GODADDY_API_KEY:$GODADDY_API_SECRET" \
  "https://api.godaddy.com/v1/domains/shubhamtatvamasi.com/records" | jq
```

# godaddy

export environment variables:
```bash
# API keys for Godaddy
export GODADDY_API_KEY=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
export GODADDY_API_SECRET=xxxxxxxxxxxxxxxxxxxxxx
export GODADDY_URL=https://api.godaddy.com

# required for getting a specific record
export DOMAIN=shubhamtatvamasi.com
export RECORD_TYPE=A
export RECORD_NAME=nginx.google
```

get all the records from the domain:
```bash
curl -s \
  -H "Authorization: sso-key $GODADDY_API_KEY:$GODADDY_API_SECRET" \
  "$GODADDY_URL/v1/domains/$DOMAIN/records" | jq
```

get a specific record:
```bash
curl -s \
  -H "Authorization: sso-key $GODADDY_API_KEY:$GODADDY_API_SECRET" \
  "$GODADDY_URL/v1/domains/$DOMAIN/records/$RECORD_TYPE/$RECORD_NAME" | jq
```

delete a specific record:
```bash
curl -s \
  -X "DELETE" \
  -H "Authorization: sso-key $GODADDY_API_KEY:$GODADDY_API_SECRET" \
  "$GODADDY_URL/v1/domains/$DOMAIN/records/$RECORD_TYPE/$RECORD_NAME"
```

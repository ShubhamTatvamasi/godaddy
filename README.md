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

# curl headers and path
export AUTH_HEADER="Authorization: sso-key $GODADDY_API_KEY:$GODADDY_API_SECRET"
export RECORDS_URI="$GODADDY_URL/v1/domains/$DOMAIN/records"
export RECORD_PATH="$RECORDS_URI/$RECORD_TYPE/$RECORD_NAME"
```

get all the records from the domain:
```bash
curl -s -H $AUTH_HEADER $RECORDS_URI | jq
```

get a specific record:
```bash
curl -s -H $AUTH_HEADER $RECORD_PATH | jq
```

delete a specific record:
```bash
curl -s -X "DELETE" -H $AUTH_HEADER $RECORD_PATH | jq
```

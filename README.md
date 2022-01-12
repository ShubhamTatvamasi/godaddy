# godaddy

https://developer.godaddy.com/doc/endpoint/domains

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

# required for setting a specific record
export RECORD_VALUE=8.8.8.8

# data object
export NEW_RECORD="[{\"data\": \"$RECORD_VALUE\"}]"
```

get all the records from the domain:
```bash
curl -s -H $AUTH_HEADER $RECORDS_URI | jq
```

get a specific record:
```bash
curl -s -H $AUTH_HEADER $RECORD_PATH | jq
```

set a specific record:
```bash
curl -s -X "PUT" -d $NEW_RECORD \
  -H 'Content-Type: application/json' \
  -H $AUTH_HEADER $RECORD_PATH
```

delete a specific record:
```bash
curl -s -X "DELETE" -H $AUTH_HEADER $RECORD_PATH
```

---
name: hubspot
description: Manage HubSpot CRM contacts, deals, and notes
tools:
  - name: hubspot
    description: HubSpot CRM operations (create/update/search contacts, log notes, manage deals)
---

# HubSpot CRM

Use the `hubspot` CLI to manage real estate leads in HubSpot.

## Create Contact
```bash
curl -s -X POST https://api.hubapi.com/crm/v3/objects/contacts \
  -H "Authorization: Bearer $HUBSPOT_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"properties":{"firstname":"$FIRST","lastname":"$LAST","email":"$EMAIL","phone":"$PHONE","address":"$ADDRESS","zip":"$ZIP"}}'
```

## Search Contacts
```bash
curl -s -X POST https://api.hubapi.com/crm/v3/objects/contacts/search \
  -H "Authorization: Bearer $HUBSPOT_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"filterGroups":[{"filters":[{"propertyName":"$PROP","operator":"EQ","value":"$VAL"}]}]}'
```

## Add Note to Contact
```bash
curl -s -X POST https://api.hubapi.com/crm/v3/objects/notes \
  -H "Authorization: Bearer $HUBSPOT_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"properties":{"hs_note_body":"$NOTE","hs_timestamp":"$TIMESTAMP"},"associations":[{"to":{"id":"$CONTACT_ID"},"types":[{"associationCategory":"HUBSPOT_DEFINED","associationTypeId":202}]}]}'
```
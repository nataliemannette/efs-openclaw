---
name: rentcast
description: Query Rentcast API for property data, listings, and valuations
tools:
  - name: rentcast
    description: Rentcast property data (expired listings, sold homes, valuations, property details)
---

# Rentcast Property Data

Use the `rentcast` CLI to query real estate data from the Rentcast API.

## Get Expired Listings by Zip Code
```bash
curl -s 'https://api.rentcast.io/v1/listings?zipCode=$ZIP&status=expired&limit=50' \
  -H "X-Api-Key: $RENTCAST_API_KEY" \
  -H "Accept: application/json"
```

## Get Recently Sold Properties
```bash
curl -s 'https://api.rentcast.io/v1/listings?zipCode=$ZIP&status=sold&limit=50&daysOld=30' \
  -H "X-Api-Key: $RENTCAST_API_KEY" \
  -H "Accept: application/json"
```

## Get Property Valuation
```bash
curl -s 'https://api.rentcast.io/v1/avm/value?address=$ADDRESS' \
  -H "X-Api-Key: $RENTCAST_API_KEY" \
  -H "Accept: application/json"
```

## Get Property Details
```bash
curl -s 'https://api.rentcast.io/v1/properties?address=$ADDRESS' \
  -H "X-Api-Key: $RENTCAST_API_KEY" \
  -H "Accept: application/json"
```
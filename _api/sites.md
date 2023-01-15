---
title: /sites
position_number: 1.12
type: get
description: Retrieve a list of sites
parameters:
  - name: account_oid
    content: The account_oid to filter the results by. This parameter is optional.
  - name: region_oid
    content: The region_oid to filter the results by. This parameter is optional.
content_markdown: >-
  If account\_oid or region\_oid parameters are not provided, all sites will be
  returned.

  {: .info}
left_code_blocks:
  - code_block: "curl -X 'GET' \\\r\n  'https://www.as20z.com:9900/api/v1.0/sites?account_oid=YOUR_ACCOUNT_OID' \\\r\n  -H 'accept: application/json' \\\r\n  -H 'Authorization: Bearer YOUR_JWT_TOKEN'"
    title: Curl
    language: bash
right_code_blocks:
  - code_block: "[\n        {\n    \t\"_id\": \"5c814c135b11884e70e8643c\",\n    \t\"site_location\": \"Example Address 1\",\n    \t\"site_name\": \"Example Name 1\"\n        },\n        {\n    \t\"_id\": \"5c814c135b54584e70e8643c\",\n    \t\"site_location\": \"Example Address 2\",\n    \t\"site_name\": \"Example Name 2\"\n        },\n        ...\n\n]"
    title: Example Response
    language: json
---

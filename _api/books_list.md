---
title: /regions
position_number: 1
type: get
description: Retrieves a list of all regions assigned to sites within an account.
parameters:
  - name: account_oid
    content: The account_oid to filter the results by. This parameter is optional.
content_markdown: >-
  This call will return all regions for an account. If regions have not been
  assigned it will return one region labelled "None".

  {: .info}
left_code_blocks:
  - code_block: |-
      curl -X 'GET' \
        'https://www.as20z.com:9900/api/v1.0/regions?account_oid=YOUR_ACCOUNT_OID' \
        -H 'accept: application/json' \
        -H 'Authorization: Bearer YOUR_JWT_TOKEN'
    title: Curl
    language: bash
right_code_blocks:
  - code_block: "[\n        {\n    \t\"account_oid\": \"5c814c135b11884e70e8643c\",\n    \t\"region_desc\": \"Example Description 1\",\n    \t\"region_info\": \"Example Info 1\",\n\t    \"region_name\": \"Example Name 1\",\n\t    \"region_oid\": \"6g814c159doe884e70e8643c \",\n\t    \"site_count\": 100\n        },\n        {\n    \t\"account_oid\": \"5c814c135b11884e70e8643c\",\n    \t\"region_desc\": \"Example Description 2\",\n    \t\"region_info\": \"Example Info 2\",\n\t    \"region_name\": \"Example Name 2\",\n\t    \"region_oid\": \"6g814c159doe884e70e8643c \",\n\t    \"site_count\": 60\n        },\n        ...\n\n]"
    title: Example Response
    language: json
---

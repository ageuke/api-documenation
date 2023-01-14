---
title: /sites
position_number: 1.1
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
  - code_block: |-
      $.post("http://api.myapp.com/books/", {
        "token": "YOUR_APP_KEY",
        "title": "The Book Thief",
        "score": 4.3
      }, function(data) {
        alert(data);
      });
    title: jQuery
    language: javascript
right_code_blocks:
  - code_block: "[\n        {\n    \t\"_id\": \"5c814c135b11884e70e8643c\",\n    \t\"site_location\": \"Example Address 1\",\n    \t\"site_name\": \"Example Name 1\"\n        },\n        {\n    \t\"_id\": \"5c814c135b54584e70e8643c\",\n    \t\"site_location\": \"Example Address 2\",\n    \t\"site_name\": \"Example Name 2\"\n        },\n        ...\n\n]"
    title: Response
    language: json
---

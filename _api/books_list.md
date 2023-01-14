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


  Lists all the photos you have access to. You can paginate by using the
  parameters listed above.
left_code_blocks:
  - code_block: >-
      $.get("http://api.myapp.com/books/", { "token": "YOUR_APP_KEY"},
      function(data) {
        alert(data);
      });
    title: jQuery
    language: javascript
  - code_block: |-
      r = requests.get("http://api.myapp.com/books/", token="YOUR_APP_KEY")
      print r.text
    title: Python
    language: python
  - code_block: >-
      var request = require("request");

      request("http://api.myapp.com/books?token=YOUR_APP_KEY", function (error,
      response, body) {

      if (!error && response.statusCode == 200) {
        console.log(body);
      }
    title: Node.js
    language: javascript
  - code_block: curl http://sampleapi.readme.com/orders?key=YOUR_APP_KEY
    title: Curl
    language: bash
right_code_blocks:
  - code_block: "[\n        {\n    \t\"account_oid\": \"5c814c135b11884e70e8643c\",\n    \t\"region_desc\": \"Example Description 1\",\n    \t\"region_info\": \"Example Info 1\",\n\t \"region_name\": \"Example Name 1\",\n\t \"region_oid\": \"6g814c159doe884e70e8643c \",\n\t \"site_count\": 100\n        },\n        {\n      \"account_oid\": \"5c814c135b11884e70e8643c\",\n    \t\"region_desc\": \"Example Description 2\",\n    \t\"region_info\": \"Example Info 2\",\n\t \"region_name\": \"Example Name 2\",\n\t \"region_oid\": \"6g814c159doe884e70e8643c \",\n\t \"site_count\": 60\n        },\n        ...\n\n]"
    title: Example Response
    language: json
---

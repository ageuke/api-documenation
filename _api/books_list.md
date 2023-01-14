---
title: /regions
position_number: 1
type: get
description: >-
  Retrieves a list of all regions that includes account_oid, region_disc,
  region_info, region_name, region_oid and site_count.
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
  - code_block: |-
      [
        {
          "id": 1,
          "title": "The Hunger Games",
          "score": 4.5,
          "dateAdded": "12/12/2013"
        },
        {
          "id": 1,
          "title": "The Hunger Games",
          "score": 4.7,
          "dateAdded": "15/12/2013"
        },
      ]
    title: Response
    language: json
---

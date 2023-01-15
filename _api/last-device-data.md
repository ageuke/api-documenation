---
title: /last_device_data
position_number: 1.1
type: get
description: |
  Retrieve the last reading for every device of the specified site 
parameters:
  - name: site_oid
    content: String. The site_oid to filter the results by. This parameter is REQUIRED.
content_markdown: >-
  Receive timestamped data for every device in the specified site. The request
  will return the following data points for each individual device/controller:


  * case\_temp: Internal Case Temperature (Optional Sensor)

  * dew\_point: dew point reading from sensor typically mounted directly above
  doors

  * door\_temp: temperature sensor typically mounted to mullion or bottom rail
  of case (also called frame temperature)

  * humidity: humidity directly outside of case

  * room\_temp: temperature directly outside of case

  * htr\_relay\_on: relay state for AS-20z controller


  dev\_type "F1" specifies an AS-20z controller

  {: .info}


  case\_type specifies the type of case. "Freezer" is a low temp case, "Cooler"
  is a medium/normal temp case

  {: .info}


  If case\_temp is not returned, no case temp sensor is installed on that case

  {: .info}


  If the device has never reported data, device\_data and device\_metadata will
  be empty

  {: .info}
left_code_blocks:
  - code_block: |-
      curl -X 'GET' \
        'https://www.as20z.com:9900/api/v1.0/sites/YOUR_SITE_OID/last_device_data' \
        -H 'accept: application/json' \
        -H 'Authorization: Bearer YOUR_JWT_TOKEN'
    title: Curl
    language: bash
right_code_blocks:
  - code_block: "{\r\n  \"site_timezone\": \"PST8PDT\",\r\n  \"site_oid\": \"YOUR SITE_OID\",\r\n  \"device_count\": # of Devices in Store,\r\n  \"site_location\": \"EXAMPLE SITE ADDRESS\",\r\n  \"devices\": [\r\n    {\r\n      \"device_data\": {\r\n        \"door_temp\": [\r\n          {\r\n            \"value\": 49,\r\n            \"timestamp\": \"2021-01-01T00:59:00-08:00\"\r\n          }\r\n        ],\r\n        \"clq\": [\r\n          {\r\n            \"value\": 25,\r\n            \"timestamp\": \"2021-01-01T00:59:00-08:00\"\r\n          }\r\n        ],\r\n        \"room_temp\": [\r\n          {\r\n            \"value\": 69,\r\n            \"timestamp\": \"2021-01-01T00:59:00-08:00\"\r\n          }\r\n        ],\r\n        \"dew_point\": [\r\n          {\r\n            \"value\": 43,\r\n            \"timestamp\": \"2021-01-01T00:59:00-08:00\"\r\n          }\r\n        ],\r\n        \"nlq\": [\r\n          {\r\n            \"value\": 30,\r\n            \"timestamp\": \"2021-01-01T00:59:00-08:00\"\r\n          }\r\n        ],\r\n        \"humidity\": [\r\n          {\r\n            \"value\": 40,\r\n            \"timestamp\": \"2021-01-01T00:59:00-08:00\"\r\n          }\r\n        ],\r\n        \"htr_relay_on\": [\r\n          {\r\n            \"value\": 0,\r\n            \"timestamp\": \"2021-01-01T00:59:00-08:00\"\r\n          }\r\n        ]\r\n      },\r\n      \"loc_uuid\": \"801593dd-a20e-5300-98d6-82136614238b\",\r\n      \"mac_addr\": \"00158D0000993D54\",\r\n      \"case_type\": \"freezer\",\r\n      \"dev_type\": \"F1\",\r\n      \"location\": \"EXAMPLE LOCATION 1\",\r\n      \"device_metadata\": {}\r\n    },\r\n    {\r\n      \"device_data\": {},\r\n      \"loc_uuid\": \"2160d221-34cf-50d6-a139-1862ares93c2\",\r\n      \"mac_addr\": \"00158D00004579B1\",\r\n      \"case_type\": \"freezer\",\r\n      \"dev_type\": \"F1\",\r\n      \"location\": \"EXAMPLE LOCATION 2\",\r\n      \"device_metadata\": {}\r\n    },\r\n  \r\n    {\r\n      \"device_data\": {\r\n        \"door_temp\": [\r\n          {\r\n            \"value\": 44,\r\n            \"timestamp\": \"2021-01-01T00:59:00-08:00\"\r\n          }\r\n        ],\r\n        \"clq\": [\r\n          {\r\n            \"value\": 28,\r\n            \"timestamp\": \"2021-01-01T00:59:00-08:00\"\r\n          }\r\n        ],\r\n        \"dew_point\": [\r\n          {\r\n            \"value\": 43,\r\n            \"timestamp\": \"2021-01-01T00:59:00-08:00\"\r\n          }\r\n        ],\r\n        \"room_temp\": [\r\n          {\r\n            \"value\": 67,\r\n            \"timestamp\": \"2021-01-01T00:59:00-08:00\"\r\n          }\r\n        ],\r\n        \"nlq\": [\r\n          {\r\n            \"value\": 28,\r\n            \"timestamp\": \"2021-01-01T00:59:00-08:00\"\r\n          }\r\n        ],\r\n        \"humidity\": [\r\n          {\r\n            \"value\": 42,\r\n            \"timestamp\": \"2021-01-01T00:59:00-08:00\"\r\n          }\r\n        ],\r\n        \"htr_relay_on\": [\r\n          {\r\n            \"value\": 1,\r\n            \"timestamp\": \"2021-01-01T00:59:00-08:00\"\r\n          }\r\n        ]\r\n      },\r\n      \"loc_uuid\": \"d7c3ed69-177a-5391-b33d-7bd64fds25aa\",\r\n      \"mac_addr\": \"00158D000014598F\",\r\n      \"case_type\": \"freezer\",\r\n      \"dev_type\": \"F1\",\r\n      \"location\": \"EXAMPLE LOCATION 3\",\r\n      \"device_metadata\": {}\r\n    }\r\n  ],\r\n  \"site_name\": \"EXAMPLE SITE NAME\"\r\n}\r\n"
    title: Example Response
    language: json
---

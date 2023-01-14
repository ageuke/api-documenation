---
title: /data
position_number: 1.3
type: get
description: |
  Retrieve all data by device for a specified site and timeframe
parameters:
  - name: site_oid
    content: String. The site_oid to filter the results by. This parameter is REQUIRED.
  - name: time_period
    content: >-
      String. Must be "days_ago", "weeks_ago", or "months_ago". This parameter
      is optional
  - name: time_period_length
    content: >-
      Integer. Corresponds with time_period specified. Example: If time_period =
      days_ago and time_period_length = 1, data for 1 day ago will be returned
  - name: start_timestamp
    content: String. Desired start time in ISO date format.
  - name: end_timestamp
    content: String. Desired end time in ISO date format.
content_markdown: >-
  Receive timestamped data for every device in the specified. The request will
  return the following data points for each individual device/controller:


  * case\_temp: Internal Case Temperature (Optional Sensor)

  * dew\_point: dew point reading from sensor typically mounted directly above
  doors

  * door\_temp: temperature sensor typically mounted to mullion or bottom rail
  of case

  * humidity: humidity directly outside of case

  * room\_temp: temperature directly outside of case

  * htr\_relay\_on: relay state for AS-20z controller


  If neither timeframe parameter is included, it will return the last hour of
  data for the specified site

  {: .info}
left_code_blocks:
  - code_block: "curl -X 'GET' \\\r\n  'https://www.as20z.com:9900/api/v1.0/sites/YOUR_SITE_OID/sensor_data?start_timestamp=2022-10-10T10&end_timestamp=2022-10-10T11' \\\r\n  -H 'accept: application/json' \\\r\n  -H 'Authorization: Bearer YOUR_JWT_TOKEN'"
    title: Curl
    language: bash
right_code_blocks:
  - code_block: "[\n        {\n    \t\"_id\": \"5c814c135b11884e70e8643c\",\n    \t\"site_location\": \"Example Address 1\",\n    \t\"site_name\": \"Example Name 1\"\n        },\n        {\n    \t\"_id\": \"5c814c135b54584e70e8643c\",\n    \t\"site_location\": \"Example Address 2\",\n    \t\"site_name\": \"Example Name 2\"\n        },\n        ...\n\n]"
    title: Response
    language: json
---

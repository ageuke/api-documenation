---
title: /efficiency_data
position_number: 1.4
type: get
description: >
  Retrieve efficiency and savings data for each device and total for a specified
  site
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
  Receive timestamped efficiency and savings data for every device in the
  specified site and the total site efficiency and savings. The request will
  return the following efficiency data points for each individual
  device/controller plus the total site efficiency for the specified timeframe:


  * time\_off: the amount of time (seconds) the heaters were off

  * time\_on: the amount of time (seconds) the heaters were on

  * efficiency: the % of time heaters were turned off

  * kwh\_saved: the number of kwh saved

  * room\_temp: temperature directly outside of case

  * savings: the dollar amount saved


  If neither timeframe parameter is included, you will receive a 500 error. One
  timeframe parameter must be specified

  {: .error}


  If only start\_timestamp is specified, 1 day of data will be returned starting
  at the specified time

  {: .info}


  If only end\_timestamp is specified, 1 day of data prior to the specified time
  will be returned

  {: .info}


  dev\_type "F1" specifies an AS-20z controller

  {: .info}


  case\_type specifies the type of case. "Freezer" is a low temp case, "Cooler"
  is a medium/normal temp case

  {: .info}
left_code_blocks:
  - code_block: |-
      curl -X 'GET' \
        'https://www.as20z.com:9900/api/v1.0/sites/YOUR_SITE_OID/efficiency_data?start_timestamp=2022-10-10&end_timestamp=2022-10-11' \
        -H 'accept: application/json' \
        -H 'Authorization: Bearer YOUR_JWT_TOKEN'
    title: Curl
    language: bash
right_code_blocks:
  - code_block: "{\r\n  \"account_name\": \"EXAMPLE ACCOUNT NAME\",\r\n  \"devices\": [\r\n    {\r\n      \"case_type\": \"freezer\",\r\n      \"dev_type\": \"F1\",\r\n      \"door_count\": 5,\r\n      \"door_rating\": 1.25,\r\n      \"efficiency\": 0.512,\r\n      \"time_off\": 44208.8,\r\n      \"time_on\": 42191.2,\r\n      \"kwh_saved\": 11.208772833333335,\r\n      \"loc_uuid\": \"03b487e0-0b47-5cb5-b147-54aec91e2746\",\r\n      \"location\": \"EXAMPLE LOCATION 1\",\r\n      \"mac_addr\": \"00158D0000997WE5\",\r\n      \"off_time\": 38928.3,\r\n      \"savings\": 1.23\r\n    },\r\n    {\r\n      \"case_type\": \"freezer\",\r\n      \"dev_type\": \"F1\",\r\n      \"door_count\": 3,\r\n      \"door_rating\": 1.25,\r\n      \"efficiency\": 0.43,\r\n      \"time_off\": 37141.9,\r\n      \"time_on\": 49258.1,\r\n      \"kwh_saved\": 5.650211537500001,\r\n      \"loc_uuid\": \"0e48er8f-c7d5-5c43-9058-0f96130d59c5\",\r\n      \"location\": \"EXAMPLE LOCATION 2\",\r\n      \"mac_addr\": \"00158D0000999V8A\",\r\n      \"savings\": 0.62\r\n    },\r\n    ...\r\n      }\r\n    ]\r\n  \"end_date\": \"2020-07-08T00:00:00+00:00\",\r\n  \"time_on\": 847644.7,\r\n  \"generated_date\": \"2021-01-15T17:52:25.741600+00:00\",\r\n  \"site\": {\r\n    \"efficiency\": 0.5540589751683502,\r\n    \"time_off\": 1053155.3,\r\n    \"kwh_saved\": 290.0800957866667,\r\n    \"period_seconds\": 86400,\r\n    \"savings\": 31.9\r\n  },\r\n  \"site_elec_cost\": 0.11,\r\n  \"site_location\": \"EXAMPLE SITE ADDRESS\",\r\n  \"site_name\": \"EXAMPLE SITE NAME\",\r\n  \"site_oid\": \"5e5d25b05b11884r80e8648a\",\r\n  \"start_date\": \"2020-07-07T00:00:00+00:00\"\r\n}"
    title: Example Response
    language: json
---

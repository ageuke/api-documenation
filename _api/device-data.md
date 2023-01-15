---
title: /device_data
position_number: 1.2
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
  Receive timestamped data for every device in the specified site. The request
  will return the following data points for each individual device/controller:


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


  dev\_type "F1" specifies an AS-20z controller

  {: .info}


  case\_type specifies the type of case. "Freezer" is a low temp case, "Cooler"
  is a medium/normal temp case

  {: .info}


  If case\_temp is not returned, no case temp sensor is installed on that case

  {: .info}


  Data can only be pulled for time periods of 24 hours or less

  {: .warning}
left_code_blocks:
  - code_block: |-
      curl -X 'GET' \
        'https://www.as20z.com:9900/api/v1.0/sites/YOUR_SITE_OID/device_data?start_timestamp=2022-10-10T10&end_timestamp=2022-10-10T11' \
        -H 'accept: application/json' \
        -H 'Authorization: Bearer YOUR_JWT_TOKEN'
    title: Curl
    language: bash
right_code_blocks:
  - code_block: |-
      {
          "device_count": 46,
          "devices": [
           "case_type": "freezer",
              "dev_type": "F1",
              "device_data": {
                "case_temp": [
                  {
                    "timestamp": "2022-10-10T10:00:00-06:00",
                    "value": 38.0
                  },
                  {
                    "timestamp": "2022-10-10T10:15:00-06:00",
                    "value": 38.0
                  },
                  {
                    "timestamp": "2022-10-10T10:30:00-06:00",
                    "value": 38.0
                  },
                  {
                    "timestamp": "2022-10-10T10:45:00-06:00",
                    "value": 38.0
                  }
                ],
                "dew_point": [
                  {
                    "timestamp": "2022-10-10T10:00:00-06:00",
                    "value": 34.0
                  },
                  {
                    "timestamp": "2022-10-10T10:15:00-06:00",
                    "value": 34.0
                  },
                  {
                    "timestamp": "2022-10-10T10:30:00-06:00",
                    "value": 34.0
                  },
                  {
                    "timestamp": "2022-10-10T10:45:00-06:00",
                    "value": 33.0
                  }
                ],
                "door_temp": [
                  {
                    "timestamp": "2022-10-10T10:00:00-06:00",
                    "value": 50.0
                  },
                  {
                    "timestamp": "2022-10-10T10:15:00-06:00",
                    "value": 50.0
                  },
                  {
                    "timestamp": "2022-10-10T10:30:00-06:00",
                    "value": 50.0
                  },
                  {
                    "timestamp": "2022-10-10T10:45:00-06:00",
                    "value": 50.0
                  }
                ],
                "htr_relay_on": [
                  {
                    "timestamp": "2022-10-10T10:00:00-06:00",
                    "value": 0.3
                  },
                  {
                    "timestamp": "2022-10-10T10:15:00-06:00",
                    "value": 0.5
                  },
                  {
                    "timestamp": "2022-10-10T10:30:00-06:00",
                    "value": 0.4
                  },
                  {
                    "timestamp": "2022-10-10T10:45:00-06:00",
                    "value": 0.2
                  }
                ],
                "humidity": [
                  {
                    "timestamp": "2022-10-10T10:00:00-06:00",
                    "value": 40.0
                  },
                  {
                    "timestamp": "2022-10-10T10:15:00-06:00",
                    "value": 40.0
                  },
                  {
                    "timestamp": "2022-10-10T10:30:00-06:00",
                    "value": 40.0
                  },
                  {
                    "timestamp": "2022-10-10T10:45:00-06:00",
                    "value": 40.0
                  }
                ],
                "room_temp": [
                  {
                    "timestamp": "2022-10-10T10:00:00-06:00",
                    "value": 58.0
                  },
                  {
                    "timestamp": "2022-10-10T10:15:00-06:00",
                    "value": 58.0
                  },
                  {
                    "timestamp": "2022-10-10T10:30:00-06:00",
                    "value": 58.0
                  },
                  {
                    "timestamp": "2022-10-10T10:45:00-06:00",
                    "value": 58.0
                  }
                ]
              },
              "loc_uuid": "EXAMPLE loc_uuid",
              "location": "Physical Location of Device",
              "mac_addr": "DEVICE MAC ID"
            },
                ...
          }
        ],
        "end_date": "2022-10-10T11:00:00-06:00",
        "site_location": "Example Site Address",
        "site_name": "Example Site Name",
        "site_oid": "YOUR_SITE_OID",
        "site_timezone": "MST7MDT",
        "start_date": "2022-10-10T10:00:00-06:00"  
      }
    title: Example Response
    language: json
---

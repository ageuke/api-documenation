---
title: Errors
position_number: 3
parameters:
  - name:
    content:
content_markdown: >-
  The API uses standard HTTP status codes to indicate success or failure of a
  request. In addition to the HTTP status code, the API may return additional
  error information in the response body.


  *Error Responses*


  Error responses will be returned in JSON format with a specific format that
  includes a code and message field. The code field will be a unique identifier
  for the error, and the message field will provide a short description of the
  error.


  Example of error response:


  \{


  &nbsp; &nbsp; "error": \{


  &nbsp; &nbsp; &nbsp; &nbsp; "code": "401",


  &nbsp; &nbsp; &nbsp; &nbsp; "message": "Unauthorized"


  &nbsp; &nbsp; \}


  \}


  | Code | Name | Description |

  | --- | --- | --- |

  | 200 | OK | Success |

  | 400 | Bad Request | We could not process that action |

  | 403 | Forbidden | You do not have proper access for this request |


  All errors will return JSON in the following format:
left_code_blocks:
  - code_block: |-
      {
        "error": true,
        "message": "error message here"
      }
    title: Response
    language: json
right_code_blocks:
  - code_block:
    title:
    language:
---

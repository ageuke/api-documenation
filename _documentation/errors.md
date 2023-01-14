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


  ***Error Responses***


  Error responses will be returned in JSON format with a specific format that
  includes a code and message field. The code field will be a unique identifier
  for the error, and the message field will provide a short description of the
  error.


  | Code | Name | Description |

  | --- | --- | --- |

  | 200 | OK | Success |

  | 400 | Bad Request | We could not process that action |

  | 403 | Forbidden | You do not have proper access for this request |
left_code_blocks:
  - code_block: |-
      {
        "detail": "403 Forbidden: You dont have access to the requested resource",
        "status": 403,
        "title": "Forbidden"
      }
    title: Example of error response
    language: json
right_code_blocks:
  - code_block:
    title:
    language:
---

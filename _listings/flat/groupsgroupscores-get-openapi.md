---
swagger: "2.0"
x-collection-name: Flat
x-complete: 0
info:
  title: Flat List group's scores
  description: Get the list of scores shared with a group.
  termsOfService: https://flat.io/legal
  contact:
    name: Flat
    url: https://flat.io/support
    email: developers@flat.io
  version: 2.1.0
host: api.flat.io
basePath: /v2
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /groups/{group}/scores:
    get:
      summary: List group's scores
      description: Get the list of scores shared with a group.
      operationId: getGroupScores
      x-api-path-slug: groupsgroupscores-get
      parameters:
      - in: path
        name: group
        description: Unique identifier of the group
      - in: query
        name: parent
        description: Filter the score forked from the score id `parent`
      responses:
        200:
          description: OK
      tags:
      - List
      - Groups
      - Scores
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---
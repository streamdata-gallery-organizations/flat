{
  "info": {
    "name": "Flat List comments",
    "_postman_id": "0b3725a4-4549-4bcf-9a23-dbee82aea77e",
    "description": "This method lists the different comments added on a music score (documents and inline) sorted by their post dates.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "List",
      "item": [
        {
          "id": "099ba975-0614-4f1b-b06a-eeece29b3231",
          "name": "getScoreComments",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.flat.io",
              "path": [
                "v2",
                "scores/:score/comments"
              ],
              "query": [
                {
                  "key": "No Name",
                  "value": "%7B%7D",
                  "disabled": false
                }
              ],
              "variable": [
                {
                  "id": "score",
                  "value": "score",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "This method lists the different comments added on a music score (documents and inline) sorted by their post dates."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "f38d9fb7-be20-4158-a6e8-c4a050b404dd"
            }
          ]
        }
      ]
    }
  ]
}
{
  "info": {
    "name": "Flat List group's scores",
    "_postman_id": "8e7ec6cc-e6ab-4b93-8e5c-53a0125065d0",
    "description": "Get the list of scores shared with a group.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "List",
      "item": [
        {
          "id": "9d04a255-609a-4217-8195-0ea4825a7b69",
          "name": "getGroupScores",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.flat.io",
              "path": [
                "v2",
                "groups/:group/scores"
              ],
              "query": [
                {
                  "key": "parent",
                  "value": "%7B%7D",
                  "disabled": false
                }
              ],
              "variable": [
                {
                  "id": "group",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Get the list of scores shared with a group."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "64f0e2dc-fa2e-43c5-9465-fe4e1d74416b"
            }
          ]
        }
      ]
    }
  ]
}
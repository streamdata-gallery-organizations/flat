{
  "info": {
    "name": "Flat List the revisions",
    "_postman_id": "abee1478-0336-4014-b329-345da4fcee57",
    "description": "When creating a score or saving a new version of a score, a revision is created in our storage. This method allows you to list all of them, sorted by last modification.\n\nDepending the plan of the account, this list can be trunked to the few last revisions.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "List",
      "item": [
        {
          "id": "df1f29bf-e418-461c-8167-d01217810c0d",
          "name": "getScoreRevisions",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.flat.io",
              "path": [
                "v2",
                "scores/:score/revisions"
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
            "description": "When creating a score or saving a new version of a score, a revision is created in our storage. This method allows you to list all of them, sorted by last modification.\n\nDepending the plan of the account, this list can be trunked to the few last revisions."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "f3906fcb-7986-48d3-84a3-0aa9ade21047"
            }
          ]
        }
      ]
    }
  ]
}
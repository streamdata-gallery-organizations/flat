{
  "info": {
    "name": "Flat Get a score's metadata",
    "_postman_id": "85c0919d-5edb-4082-ad5b-a8e744dc31d0",
    "description": "Get the details of a score identified by the `score` parameter in the URL.\nThe currently authenticated user must have at least a read access to the document to use this API call.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Scores",
      "item": [
        {
          "id": "3c5aaed1-be18-4a79-b29c-c27e7dc129f1",
          "name": "getScore",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.flat.io",
              "path": [
                "v2",
                "scores/:score"
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
            "description": "Get the details of a score identified by the `score` parameter in the URL.\nThe currently authenticated user must have at least a read access to the document to use this API call."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "09368bdc-0a0a-4190-a561-02b93dc03399"
            }
          ]
        }
      ]
    }
  ]
}
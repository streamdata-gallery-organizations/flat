{
  "info": {
    "name": "Flat List the collaborators",
    "_postman_id": "30e7d5f7-e0ae-4743-a044-19b462a24a82",
    "description": "This API call will list the different collaborators of a score and their rights on the document. The returned list will at least contain the owner of the document.\n\nCollaborators can be a single user (the object `user` will be populated) or a group (the object `group` will be populated).",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "List",
      "item": [
        {
          "id": "d7eeeb68-b936-44eb-8662-1b6b81fe5eb6",
          "name": "getScoreCollaborators",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.flat.io",
              "path": [
                "v2",
                "scores/:score/collaborators"
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
            "description": "This API call will list the different collaborators of a score and their rights on the document. The returned list will at least contain the owner of the document.\n\nCollaborators can be a single user (the object `user` will be populated) or a group (the object `group` will be populated)."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "63a09b18-d601-4e37-8947-e29a72e5fd5a"
            }
          ]
        }
      ]
    }
  ]
}
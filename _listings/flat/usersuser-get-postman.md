{
  "info": {
    "name": "Flat Get a public user profile",
    "_postman_id": "aae643c2-2b25-4394-8b7d-ab69a235cb63",
    "description": "Get a public profile of a Flat User.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Public",
      "item": [
        {
          "id": "ff30ba76-c3cb-436a-870d-5fa50a5ee164",
          "name": "getUser",
          "request": {
            "url": {
              "protocol": "http",
              "host": "api.flat.io",
              "path": [
                "v2",
                "users/:user"
              ],
              "variable": [
                {
                  "id": "user",
                  "value": "{}",
                  "type": "string"
                }
              ]
            },
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Get a public profile of a Flat User."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "ae17e3c0-5d11-4d2e-9240-a17dcefa6b2a"
            }
          ]
        }
      ]
    }
  ]
}
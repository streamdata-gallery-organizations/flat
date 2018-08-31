{
  "info": {
    "name": "Flat Get current user profile",
    "_postman_id": "e280689b-117e-46d6-8297-12187850946d",
    "description": "Get details about the current authenticated User.",
    "schema": "https://schema.getpostman.com/json/collection/v2.0.0/"
  },
  "item": [
    {
      "name": "Current",
      "item": [
        {
          "id": "a23efc66-e09b-4e19-bc97-19e452b535b1",
          "name": "getAuthenticatedUser",
          "request": {
            "url": "http://api.flat.io/v2/me",
            "method": "GET",
            "body": {
              "mode": "raw"
            },
            "description": "Get details about the current authenticated User."
          },
          "response": [
            {
              "status": "OK",
              "code": 200,
              "name": "Response_200",
              "id": "91339680-8eda-4197-8399-dce42ea63ef7"
            }
          ]
        }
      ]
    }
  ]
}
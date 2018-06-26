---
swagger: "2.0"
x-collection-name: Flat
x-complete: 0
info:
  title: Flat Delete a comment
  description: ""
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
  /me:
    get:
      summary: Get current user profile
      description: Get details about the current authenticated User.
      operationId: getAuthenticatedUser
      x-api-path-slug: me-get
      responses:
        200:
          description: OK
      tags:
      - Current
      - User
      - Profile
  /scores:
    post:
      summary: Create a new score
      description: |-
        Use this API method to **create a new music score in the current User account**. You will need a MusicXML 3 (`vnd.recordare.musicxml` or `vnd.recordare.musicxml+xml`) or a MIDI (`audio/midi`) file to create the new Flat document.

        This API call will automatically create the first revision of the document, the score can be modified by the using our web application or by uploading a new revision of this file (`POST /v2/scores/{score}/revisions/{revision}`).

        The currently authenticated user will be granted owner of the file and will be able to add other collaborators (users and groups).
      operationId: createScore
      x-api-path-slug: scores-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - New
      - Score
  /scores/{score}:
    delete:
      summary: Delete a score
      description: |-
        This API call will schedule the deletion of the score, its revisions, and whole history.
        The user calling this API method must have the `aclAdmin` rights on this document to process this action.
        The score won't be accessible anymore after calling this method and the user's quota will directly be updated.
      operationId: deleteScore
      x-api-path-slug: scoresscore-delete
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Score
    get:
      summary: Get a score's metadata
      description: |-
        Get the details of a score identified by the `score` parameter in the URL.
        The currently authenticated user must have at least a read access to the document to use this API call.
      operationId: getScore
      x-api-path-slug: scoresscore-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Scores
      - Metadata
    put:
      summary: Edit a score's metadata
      description: |-
        This API method allows you to change the metadata of a score document (e.g. its `title` or `privacy`), all the properties are optional.

        To edit the file itself, create a new revision using the appropriate method (`POST /v2/scores/{score}/revisions/{revision}`).
      operationId: editScore
      x-api-path-slug: scoresscore-put
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Edit
      - Scores
      - Metadata
  /scores/{score}/collaborators:
    get:
      summary: List the collaborators
      description: |-
        This API call will list the different collaborators of a score and their rights on the document. The returned list will at least contain the owner of the document.

        Collaborators can be a single user (the object `user` will be populated) or a group (the object `group` will be populated).
      operationId: getScoreCollaborators
      x-api-path-slug: scoresscorecollaborators-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - List
      - Collaborators
    post:
      summary: Add a new collaborator
      description: |-
        Share a score with a single user or a group. This API call allows to add, invite and update the collaborators of a document.
        - To add an existing Flat user to the document, specify its unique identifier in the `user` property.
        - To invite an external user to the document, specify its email in the `userEmail` property.
        - To add a Flat group to the document, specify its unique identifier in the `group` property.
        - To update an existing collaborator, process the same request with different rights.
      operationId: addScoreCollaborator
      x-api-path-slug: scoresscorecollaborators-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - New
      - Collaborator
  /scores/{score}/collaborators/{collaborator}:
    delete:
      summary: Delete a collaborator
      description: Remove the specified collaborator from the score
      operationId: removeScoreCollaborator
      x-api-path-slug: scoresscorecollaboratorscollaborator-delete
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Collaborator
    get:
      summary: Get a collaborator
      description: Get the information about a collaborator (User or Group).
      operationId: getScoreCollaborator
      x-api-path-slug: scoresscorecollaboratorscollaborator-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Collaborator
  /scores/{score}/comments:
    get:
      summary: List comments
      description: This method lists the different comments added on a music score
        (documents and inline) sorted by their post dates.
      operationId: getScoreComments
      x-api-path-slug: scoresscorecomments-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - List
      - Comments
    post:
      summary: Post a new comment
      description: |-
        Post a document or a contextualized comment on a document.

        Please note that this method includes an anti-spam system for public scores. We don't guarantee that your comments will be accepted and displayed to end-user. Comments are be blocked by returning a `403` HTTP error and hidden from other users when the `spam` property is `true`.
      operationId: postScoreComment
      x-api-path-slug: scoresscorecomments-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - New
      - Comment
  /scores/{score}/comments/{comment}:
    delete:
      summary: Delete a comment
      description: ""
      operationId: deleteScoreComment
      x-api-path-slug: scoresscorecommentscomment-delete
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Comment
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
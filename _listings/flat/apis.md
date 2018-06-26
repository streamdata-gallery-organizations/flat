---
name: Flat
x-slug: flat
description: Whether youre a beginner or a professional composer, our user-friendly
  music composition software gives you all the tools that you need to make your own
  sheet music. You can write, listen, share and discover music scores right in your
  web browser on any device
image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
x-kinRank: "7"
x-alexaRank: "0"
tags: Flat
created: "2018-06-26"
modified: "2018-06-26"
url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/apis.md
specificationVersion: "0.14"
apis:
- name: Flat List group's scores
  x-api-slug: flat
  description: Get the list of scores shared with a group.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//groups/{group}/scores
  tags: List,Groups,Scores
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/groupsgroupscores-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/groupsgroupscores-get-openapi.md
- name: Flat Get current user profile
  x-api-slug: flat
  description: Get details about the current authenticated User.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//me
  tags: Current,User,Profile
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/me-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/me-get-openapi.md
- name: Flat Create a new score
  x-api-slug: flat
  description: |-
    Use this API method to **create a new music score in the current User account**. You will need a MusicXML 3 (`vnd.recordare.musicxml` or `vnd.recordare.musicxml+xml`) or a MIDI (`audio/midi`) file to create the new Flat document.

    This API call will automatically create the first revision of the document, the score can be modified by the using our web application or by uploading a new revision of this file (`POST /v2/scores/{score}/revisions/{revision}`).

    The currently authenticated user will be granted owner of the file and will be able to add other collaborators (users and groups).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores
  tags: New,Score
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scores-post-openapi.md
- name: Flat Delete a score
  x-api-slug: flat
  description: |-
    This API call will schedule the deletion of the score, its revisions, and whole history.
    The user calling this API method must have the `aclAdmin` rights on this document to process this action.
    The score won't be accessible anymore after calling this method and the user's quota will directly be updated.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}
  tags: Score
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscore-delete-openapi.md
- name: Flat Get a score's metadata
  x-api-slug: flat
  description: |-
    Get the details of a score identified by the `score` parameter in the URL.
    The currently authenticated user must have at least a read access to the document to use this API call.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}
  tags: Scores,Metadata
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscore-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscore-get-openapi.md
- name: Flat Edit a score's metadata
  x-api-slug: flat
  description: |-
    This API method allows you to change the metadata of a score document (e.g. its `title` or `privacy`), all the properties are optional.

    To edit the file itself, create a new revision using the appropriate method (`POST /v2/scores/{score}/revisions/{revision}`).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}
  tags: Edit,Scores,Metadata
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscore-put-openapi.md
- name: Flat List the collaborators
  x-api-slug: flat
  description: |-
    This API call will list the different collaborators of a score and their rights on the document. The returned list will at least contain the owner of the document.

    Collaborators can be a single user (the object `user` will be populated) or a group (the object `group` will be populated).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}/collaborators
  tags: List,Collaborators
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecollaborators-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecollaborators-get-openapi.md
- name: Flat Add a new collaborator
  x-api-slug: flat
  description: |-
    Share a score with a single user or a group. This API call allows to add, invite and update the collaborators of a document.
    - To add an existing Flat user to the document, specify its unique identifier in the `user` property.
    - To invite an external user to the document, specify its email in the `userEmail` property.
    - To add a Flat group to the document, specify its unique identifier in the `group` property.
    - To update an existing collaborator, process the same request with different rights.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}/collaborators
  tags: New,Collaborator
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecollaborators-post-openapi.md
- name: Flat Delete a collaborator
  x-api-slug: flat
  description: Remove the specified collaborator from the score
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}/collaborators/{collaborator}
  tags: Collaborator
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecollaboratorscollaborator-delete-openapi.md
- name: Flat Get a collaborator
  x-api-slug: flat
  description: Get the information about a collaborator (User or Group).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}/collaborators/{collaborator}
  tags: Collaborator
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecollaboratorscollaborator-get-openapi.md
- name: Flat List comments
  x-api-slug: flat
  description: This method lists the different comments added on a music score (documents
    and inline) sorted by their post dates.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}/comments
  tags: List,Comments
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecomments-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecomments-get-openapi.md
- name: Flat Post a new comment
  x-api-slug: flat
  description: |-
    Post a document or a contextualized comment on a document.

    Please note that this method includes an anti-spam system for public scores. We don't guarantee that your comments will be accepted and displayed to end-user. Comments are be blocked by returning a `403` HTTP error and hidden from other users when the `spam` property is `true`.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}/comments
  tags: New,Comment
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecomments-post-openapi.md
- name: Flat Delete a comment
  x-api-slug: flat
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}/comments/{comment}
  tags: Comment
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecommentscomment-delete-openapi.md
- name: Flat Update an existing comment
  x-api-slug: flat
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}/comments/{comment}
  tags: Existing,Comment
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecommentscomment-put-openapi.md
- name: Flat Mark the comment as unresolved
  x-api-slug: flat
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}/comments/{comment}/resolved
  tags: Mark,Comment,As,Unresolved
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecommentscommentresolved-delete-openapi.md
- name: Flat Mark the comment as resolved
  x-api-slug: flat
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}/comments/{comment}/resolved
  tags: Mark,Comment,As,Resolved
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecommentscommentresolved-put-openapi.md
- name: Flat Fork a score
  x-api-slug: flat
  description: |-
    This API call will make a copy of the last revision of the specified score and create a new score. The copy of the score will have a privacy set to `private`.

    When using a [Flat for Education](https://flat.io/edu) account, the inline and contextualized comments will be accessible in the child document.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}/fork
  tags: Fork,Score
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorefork-post-openapi.md
- name: Flat List the revisions
  x-api-slug: flat
  description: |-
    When creating a score or saving a new version of a score, a revision is created in our storage. This method allows you to list all of them, sorted by last modification.

    Depending the plan of the account, this list can be trunked to the few last revisions.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}/revisions
  tags: List,Revisions
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorerevisions-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorerevisions-get-openapi.md
- name: Flat Create a new revision
  x-api-slug: flat
  description: Update a score by uploading a new revision for this one.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}/revisions
  tags: New,Revision
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorerevisions-post-openapi.md
- name: Flat Get a score revision
  x-api-slug: flat
  description: |-
    When creating a score or saving a new version of a score, a revision is created in our storage. This method allows you to get a specific
    revision metadata.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}/revisions/{revision}
  tags: Score,Revision
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorerevisionsrevision-get-openapi.md
- name: Flat Get a score revision data
  x-api-slug: flat
  description: |-
    Retrieve the file corresponding to a score revision (the following formats are available: Flat JSON/Adagio JSON `json`, MusicXML
    `mxl`/`xml`, MP3 `mp3`, WAV `wav`, MIDI `midi`, or a tumbnail of the first page `thumbnail.png`).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//scores/{score}/revisions/{revision}/{format}
  tags: Score,Revision,Data
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorerevisionsrevisionformat-get-openapi.md
- name: Flat Get a public user profile
  x-api-slug: flat
  description: Get a public profile of a Flat User.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//users/{user}
  tags: Public,User,Profile
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/usersuser-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/usersuser-get-openapi.md
- name: Flat List liked scores
  x-api-slug: flat
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//users/{user}/likes
  tags: List,Liked,Scores
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/usersuserlikes-get-openapi.md
- name: Flat List user's scores
  x-api-slug: flat
  description: Get the list of scores owned by the User
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2//users/{user}/scores
  tags: List,Users,Scores
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/usersuserscores-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/usersuserscores-get-openapi.md
- name: Flat
  x-api-slug: flat
  description: 'The Flat API allows you to easily extend the abilities of the [Flat
    Platform](https://flat.io), with a wide range of use cases including the following:
    Creating and importing new music scores using MusicXML or MIDI files. Browsing,
    updating, copying, exporting the users scores (for example in MP3, WAV or MIDI).
    Managing educational resources with Flat for Education: creating &amp; updating
    the organization accounts, the classes, rosters and assignments. The Flat API
    is built on HTTP. Our API is RESTful It has predictable resource URLs. It returns
    HTTP response codes to indicate errors. It also accepts and returns JSON in the
    HTTP body.'
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: Flat
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/openapi.md
x-common:
- type: x-developer
  url: https://flat.io/developers
- type: x-embeddable
  url: https://flat.io/developers/embed
- type: x-github
  url: https://github.com/FlatIO
- type: x-pricing
  url: https://flat.io/pricing
- type: x-privacy-policy
  url: https://flat.io/help/en/policies/#coppa-and-ferpa-compliance
- type: x-support
  url: https://flat.io/help
- type: x-twitter
  url: https://twitter.com/flat_io
- type: x-website
  url: http://flat.io
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---
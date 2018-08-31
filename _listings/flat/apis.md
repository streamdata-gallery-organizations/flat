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
created: "2018-08-30"
modified: "2018-08-30"
url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/apis.md
specificationVersion: "0.14"
apis:
- name: Flat - List group's scores
  x-api-slug: groupsgroupscores-get
  description: Get the list of scores shared with a group.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/groupsgroupscores-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/groupsgroupscores-get-openapi.md
- name: Flat - Get current user profile
  x-api-slug: me-get
  description: Get details about the current authenticated User.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/me-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/me-get-openapi.md
- name: Flat - Create a new score
  x-api-slug: scores-post
  description: |-
    Use this API method to **create a new music score in the current User account**. You will need a MusicXML 3 (`vnd.recordare.musicxml` or `vnd.recordare.musicxml+xml`) or a MIDI (`audio/midi`) file to create the new Flat document.

    This API call will automatically create the first revision of the document, the score can be modified by the using our web application or by uploading a new revision of this file (`POST /v2/scores/{score}/revisions/{revision}`).

    The currently authenticated user will be granted owner of the file and will be able to add other collaborators (users and groups).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scores-post-openapi.md
- name: Flat - Delete a score
  x-api-slug: scoresscore-delete
  description: |-
    This API call will schedule the deletion of the score, its revisions, and whole history.
    The user calling this API method must have the `aclAdmin` rights on this document to process this action.
    The score won't be accessible anymore after calling this method and the user's quota will directly be updated.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscore-delete-openapi.md
- name: Flat - Get a score's metadata
  x-api-slug: scoresscore-get
  description: |-
    Get the details of a score identified by the `score` parameter in the URL.
    The currently authenticated user must have at least a read access to the document to use this API call.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscore-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscore-get-openapi.md
- name: Flat - Edit a score's metadata
  x-api-slug: scoresscore-put
  description: |-
    This API method allows you to change the metadata of a score document (e.g. its `title` or `privacy`), all the properties are optional.

    To edit the file itself, create a new revision using the appropriate method (`POST /v2/scores/{score}/revisions/{revision}`).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscore-put-openapi.md
- name: Flat - List the collaborators
  x-api-slug: scoresscorecollaborators-get
  description: |-
    This API call will list the different collaborators of a score and their rights on the document. The returned list will at least contain the owner of the document.

    Collaborators can be a single user (the object `user` will be populated) or a group (the object `group` will be populated).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecollaborators-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecollaborators-get-openapi.md
- name: Flat - Add a new collaborator
  x-api-slug: scoresscorecollaborators-post
  description: |-
    Share a score with a single user or a group. This API call allows to add, invite and update the collaborators of a document.
    - To add an existing Flat user to the document, specify its unique identifier in the `user` property.
    - To invite an external user to the document, specify its email in the `userEmail` property.
    - To add a Flat group to the document, specify its unique identifier in the `group` property.
    - To update an existing collaborator, process the same request with different rights.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecollaborators-post-openapi.md
- name: Flat - Delete a collaborator
  x-api-slug: scoresscorecollaboratorscollaborator-delete
  description: Remove the specified collaborator from the score
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecollaboratorscollaborator-delete-openapi.md
- name: Flat - Get a collaborator
  x-api-slug: scoresscorecollaboratorscollaborator-get
  description: Get the information about a collaborator (User or Group).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecollaboratorscollaborator-get-openapi.md
- name: Flat - List comments
  x-api-slug: scoresscorecomments-get
  description: This method lists the different comments added on a music score (documents
    and inline) sorted by their post dates.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecomments-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecomments-get-openapi.md
- name: Flat - Post a new comment
  x-api-slug: scoresscorecomments-post
  description: |-
    Post a document or a contextualized comment on a document.

    Please note that this method includes an anti-spam system for public scores. We don't guarantee that your comments will be accepted and displayed to end-user. Comments are be blocked by returning a `403` HTTP error and hidden from other users when the `spam` property is `true`.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecomments-post-openapi.md
- name: Flat - Delete a comment
  x-api-slug: scoresscorecommentscomment-delete
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecommentscomment-delete-openapi.md
- name: Flat - Update an existing comment
  x-api-slug: scoresscorecommentscomment-put
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecommentscomment-put-openapi.md
- name: Flat - Mark the comment as unresolved
  x-api-slug: scoresscorecommentscommentresolved-delete
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecommentscommentresolved-delete-openapi.md
- name: Flat - Mark the comment as resolved
  x-api-slug: scoresscorecommentscommentresolved-put
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorecommentscommentresolved-put-openapi.md
- name: Flat - Fork a score
  x-api-slug: scoresscorefork-post
  description: |-
    This API call will make a copy of the last revision of the specified score and create a new score. The copy of the score will have a privacy set to `private`.

    When using a [Flat for Education](https://flat.io/edu) account, the inline and contextualized comments will be accessible in the child document.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorefork-post-openapi.md
- name: Flat - List the revisions
  x-api-slug: scoresscorerevisions-get
  description: |-
    When creating a score or saving a new version of a score, a revision is created in our storage. This method allows you to list all of them, sorted by last modification.

    Depending the plan of the account, this list can be trunked to the few last revisions.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorerevisions-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorerevisions-get-openapi.md
- name: Flat - Create a new revision
  x-api-slug: scoresscorerevisions-post
  description: Update a score by uploading a new revision for this one.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorerevisions-post-openapi.md
- name: Flat - Get a score revision
  x-api-slug: scoresscorerevisionsrevision-get
  description: |-
    When creating a score or saving a new version of a score, a revision is created in our storage. This method allows you to get a specific
    revision metadata.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorerevisionsrevision-get-openapi.md
- name: Flat - Get a score revision data
  x-api-slug: scoresscorerevisionsrevisionformat-get
  description: |-
    Retrieve the file corresponding to a score revision (the following formats are available: Flat JSON/Adagio JSON `json`, MusicXML
    `mxl`/`xml`, MP3 `mp3`, WAV `wav`, MIDI `midi`, or a tumbnail of the first page `thumbnail.png`).
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/scoresscorerevisionsrevisionformat-get-openapi.md
- name: Flat - Get a public user profile
  x-api-slug: usersuser-get
  description: Get a public profile of a Flat User.
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/usersuser-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/usersuser-get-openapi.md
- name: Flat - List liked scores
  x-api-slug: usersuserlikes-get
  description: ""
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/usersuserlikes-get-openapi.md
- name: Flat - List user's scores
  x-api-slug: usersuserscores-get
  description: Get the list of scores owned by the User
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/flat-logo.png
  humanURL: http://flat.io
  baseURL: https://api.flat.io//v2
  tags: API Provider, Music, Profiles, Relative Data, General Data
  properties:
  - type: x-postman-collection
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/usersuserscores-get-postman.md
  - type: x-openapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-organizations/flat/master/_listings/flat/usersuserscores-get-openapi.md
x-common:
- type: x-api-gallery
  url: http://fitbit.api.gallery.streamdata.io
- type: x-api-stack
  url: http://flat.stack.network
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
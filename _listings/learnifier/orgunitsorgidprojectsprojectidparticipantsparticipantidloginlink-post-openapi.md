---
swagger: "2.0"
x-collection-name: Learnifier
x-complete: 0
info:
  title: Learnifier Participant login link
  version: 1.1.0
  description: |-
    Returns a single sign on link for the participant. The link is only usable once and should be used directly. The link expires after a few minutes.

    This operation requires the *login link* permission.
host: learnifier.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /orgunits/{orgid}/projects/{projectid}/participants:
    get:
      summary: Project participants
      description: Returns project participants
      operationId: orgunits.orgid.projects.projectid.participants.get
      x-api-path-slug: orgunitsorgidprojectsprojectidparticipants-get
      parameters:
      - in: path
        name: orgid
        description: Id of the organization unit
      - in: path
        name: projectid
        description: Id of the project
      responses:
        200:
          description: OK
      tags:
      - Organizations
      - Projects
      - Projectid
      - Participants
    post:
      summary: Add participant
      description: Add a user to the project. Participant information is created for
        the user. In the body object, only one of either email or userid must be specified.
        The participant needs to be activated before it the user can access it.
      operationId: orgunits.orgid.projects.projectid.participants.post
      x-api-path-slug: orgunitsorgidprojectsprojectidparticipants-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: path
        name: orgid
        description: Id of the organization unit
      - in: path
        name: projectid
        description: Id of the project
      responses:
        200:
          description: OK
      tags:
      - Organizations
      - Projects
      - Projectid
      - Participants
  /orgunits/{orgid}/projects/{projectid}/participants/${participantId}:
    delete:
      summary: Deletes a participant
      description: "Deletes a participant. The user itself will still remain but any
        state related to the project will be deleted. \nIt might not be possible due
        to constraints from the products in the project to delete the participant.
        However\nthis can only be determined at the time of the delete. If a delete
        fails the participant will have their inError\nflag set."
      operationId: orgunits.orgid.projects.projectid.participants._participantId.delete
      x-api-path-slug: orgunitsorgidprojectsprojectidparticipantsparticipantid-delete
      parameters:
      - in: path
        name: orgid
        description: Id of the organization unit
      - in: path
        name: participantId
        description: Participant id
      - in: path
        name: projectid
        description: Id of the project
      responses:
        200:
          description: OK
      tags:
      - Organizations
      - Projects
      - Projectid
      - Participants
      - $participantId
  /orgunits/{orgid}/projects/{projectid}/participants/${participantId}/activate:
    post:
      summary: Activate participant
      description: Activates a participant so that it can be used
      operationId: orgunits.orgid.projects.projectid.participants._participantId.activate.post
      x-api-path-slug: orgunitsorgidprojectsprojectidparticipantsparticipantidactivate-post
      parameters:
      - in: path
        name: orgid
        description: Id of the organization unit
      - in: path
        name: participantId
        description: Id of the participant
      - in: path
        name: projectid
        description: Id of the project
      responses:
        200:
          description: OK
      tags:
      - Organizations
      - Projects
      - Projectid
      - Participants
      - $participantId
      - Activate
  /orgunits/{orgid}/projects/{projectid}/participants/${participantId}/loginlink:
    post:
      summary: Participant login link
      description: |-
        Returns a single sign on link for the participant. The link is only usable once and should be used directly. The link expires after a few minutes.

        This operation requires the *login link* permission.
      operationId: orgunits.orgid.projects.projectid.participants._participantId.loginlink.post
      x-api-path-slug: orgunitsorgidprojectsprojectidparticipantsparticipantidloginlink-post
      parameters:
      - in: path
        name: orgid
        description: Id of the organization unit
      - in: path
        name: participantId
        description: Id of the participant
      - in: path
        name: projectid
        description: Id of the project
      responses:
        200:
          description: OK
      tags:
      - Organizations
      - Projects
      - Projectid
      - Participants
      - $participantId
      - Loginlink
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
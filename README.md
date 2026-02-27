# Microsoft Teams Sandbox
This is sandbox for the Microsoft Teams Sandbox API, using an OpenAPI specification with examples, Microcks and Bruno as the sandbox interface, and this GitHub repository as the vehicle for delivering as a localized sandbox, or also enabling the working directly with production APIs.

## APIs.json Index
There is an APIs.yml file in the root of this repository, providing an index of all the artifacts used as part of this capability, providing a machine-readable way to read, manage, and execute the resources available here.

## OpenAPI
This capability uses OpenAPI as the definition, providing a complete definition of all available paths for the Microsoft Teams Sandbox. The OpenAPI for this capability uses examples and Microcks extensions to mock the requests and responses for each API operation, something we will iterate and expand upon with richer examples as the capability evolves.

## Microcks
This capability uses Microcks to deliver the mock API. [You just install Microcks, with the Docker extension being the easiest](https://microcks.io/documentation/guides/installation/docker-desktop-extension/), [import the OpenAPI as a service](openapi/notion-openapi.yml), and you have a mocked API for all APIs, available via REST and MCP APIs--providing a multi-protocol sandbox.

## Bruno
This capability [uses Bruno as the client](https://www.usebruno.com/), leveraging Bruno Collections pre-generated from the OpenAPI and Bruno environments that uses the localhost and port of Microcks to work with the mocked API. You just have to install Microcks, then open the collection provided in this repository, select the available environments, and begin calling the Microsoft Teams Sandbox via the sandbox or production.


## OpenAPIs
These are the OpenAPIs available for the Microsoft Teams Sandbox, which are made available via this sandbox API, which can be imported into Microcks and deployed as a sandbox using their mock feature.

  - [Microsoft Teams Openapi.yaml](openapi/microsoft-teams-openapi.yaml)

## Agent Skills
These are the agent skills available for the Microsoft Teams Sandbox, providing a discrete list of capabilities that AI agents can use when working with Microsoft Teams via the Microsoft Graph API. Each skill maps directly to an OpenAPI operation, making it easy for agents to discover and invoke the right capability for a given task.

### Teams
  - [List All Teams](skills/list-teams/SKILL.md) (`listTeams`) — Retrieve a list of teams the caller is a member of.
  - [Create Team](skills/create-team/SKILL.md) (`createTeam`) — Create a new team.
  - [Get Team](skills/get-team/SKILL.md) (`getTeam`) — Get a team by its ID.
  - [Update Team](skills/update-team/SKILL.md) (`updateTeam`) — Update a team's properties.
  - [Delete Team](skills/delete-team/SKILL.md) (`deleteTeam`) — Delete a team.

### Groups
  - [List Groups](skills/list-groups/SKILL.md) (`listGroups`) — List Microsoft 365 groups.
  - [Create Group](skills/create-group/SKILL.md) (`createGroup`) — Create a new Microsoft 365 group.
  - [Get Group](skills/get-group/SKILL.md) (`getGroup`) — Get a group by its ID.
  - [Update Group](skills/update-group/SKILL.md) (`updateGroup`) — Update a group's properties.
  - [Delete Group](skills/delete-group/SKILL.md) (`deleteGroup`) — Delete a group.

### Channels
  - [List Channels](skills/list-channels/SKILL.md) (`listChannels`) — List channels in a team.
  - [Create Channel](skills/create-channel/SKILL.md) (`createChannel`) — Create a new channel in a team.
  - [Get Channel](skills/get-channel/SKILL.md) (`getChannel`) — Get a channel by its ID.
  - [Update Channel](skills/update-channel/SKILL.md) (`updateChannel`) — Update a channel's properties.
  - [Delete Channel](skills/delete-channel/SKILL.md) (`deleteChannel`) — Delete a channel.

### Tabs
  - [List Channel Tabs](skills/list-tabs/SKILL.md) (`listTabs`) — List tabs in a channel.
  - [Add Tab to Channel](skills/create-tab/SKILL.md) (`createTab`) — Add a tab to a channel.
  - [Get Tab](skills/get-tab/SKILL.md) (`getTab`) — Get a tab by its ID.
  - [Update Tab](skills/update-tab/SKILL.md) (`updateTab`) — Update a tab's properties.
  - [Remove Tab](skills/delete-tab/SKILL.md) (`deleteTab`) — Remove a tab from a channel.

### Apps
  - [List Teams Apps](skills/list-apps/SKILL.md) (`listApps`) — List apps in the Teams app catalog.
  - [Publish App to Catalog](skills/publish-app/SKILL.md) (`publishApp`) — Publish an app to the Teams app catalog.
  - [Get App](skills/get-app/SKILL.md) (`getApp`) — Get an app from the catalog by its ID.
  - [Delete App from Catalog](skills/delete-app/SKILL.md) (`deleteApp`) — Remove an app from the catalog.

### App Installations
  - [List Installed Apps](skills/list-team-installed-apps/SKILL.md) (`listTeamInstalledApps`) — List apps installed in a team.
  - [Install App to Team](skills/install-app-to-team/SKILL.md) (`installAppToTeam`) — Install an app to a team.
  - [Uninstall App from Team](skills/uninstall-app-from-team/SKILL.md) (`uninstallAppFromTeam`) — Uninstall an app from a team.

### Chats
  - [List Chats](skills/list-chats/SKILL.md) (`listChats`) — List chats for the signed-in user.
  - [Create Chat](skills/create-chat/SKILL.md) (`createChat`) — Create a new one-on-one or group chat.
  - [Get Chat](skills/get-chat/SKILL.md) (`getChat`) — Get a chat by its ID.
  - [Update Chat](skills/update-chat/SKILL.md) (`updateChat`) — Update a chat's properties such as topic.

### Chat Messages
  - [List Chat Messages](skills/list-chat-messages/SKILL.md) (`listChatMessages`) — List messages in a chat.
  - [Send Chat Message](skills/send-chat-message/SKILL.md) (`sendChatMessage`) — Send a message in a chat.
  - [List Channel Messages](skills/list-channel-messages/SKILL.md) (`listChannelMessages`) — List messages in a channel.
  - [Send Channel Message](skills/send-channel-message/SKILL.md) (`sendChannelMessage`) — Send a message to a channel.
  - [List Message Replies](skills/list-message-replies/SKILL.md) (`listMessageReplies`) — List replies to a channel message.
  - [Reply to Channel Message](skills/reply-to-channel-message/SKILL.md) (`replyToChannelMessage`) — Reply to a channel message.

### Tags
  - [List Team Tags](skills/list-teamwork-tags/SKILL.md) (`listTeamworkTags`) — List tags in a team.
  - [Create Team Tag](skills/create-teamwork-tag/SKILL.md) (`createTeamworkTag`) — Create a tag in a team.
  - [Get Team Tag](skills/get-teamwork-tag/SKILL.md) (`getTeamworkTag`) — Get a tag by its ID.
  - [Update Team Tag](skills/update-teamwork-tag/SKILL.md) (`updateTeamworkTag`) — Update a tag's properties.
  - [Delete Team Tag](skills/delete-teamwork-tag/SKILL.md) (`deleteTeamworkTag`) — Delete a tag from a team.
  - [List Tag Members](skills/list-teamwork-tag-members/SKILL.md) (`listTeamworkTagMembers`) — List members of a tag.
  - [Add Tag Member](skills/add-teamwork-tag-member/SKILL.md) (`addTeamworkTagMember`) — Add a member to a tag.

### Calls
  - [Create Call](skills/create-call/SKILL.md) (`createCall`) — Create an outgoing call.
  - [Get Call](skills/get-call/SKILL.md) (`getCall`) — Get a call by its ID.
  - [End Call](skills/delete-call/SKILL.md) (`deleteCall`) — Hang up or cancel a call.
  - [Answer Call](skills/answer-call/SKILL.md) (`answerCall`) — Answer an incoming call.
  - [Invite Participants](skills/invite-participants/SKILL.md) (`inviteParticipants`) — Invite participants to a call.

### Call IVR
  - [Play Prompt](skills/play-prompt/SKILL.md) (`playPrompt`) — Play a media prompt in a call for IVR scenarios.
  - [Record Response](skills/record-response/SKILL.md) (`recordResponse`) — Record a response from a call participant for IVR scenarios.
  - [Transfer Call](skills/transfer-call/SKILL.md) (`transferCall`) — Transfer a call to another participant.

### Call Records
  - [List Call Records](skills/list-call-records/SKILL.md) (`listCallRecords`) — List call records.
  - [Get Call Record](skills/get-call-record/SKILL.md) (`getCallRecord`) — Get a call record by its ID.
  - [List Call Record Sessions](skills/list-call-record-sessions/SKILL.md) (`listCallRecordSessions`) — List sessions in a call record.

### Online Meetings
  - [List Online Meetings](skills/list-online-meetings/SKILL.md) (`listOnlineMeetings`) — List online meetings for the signed-in user.
  - [Create Online Meeting](skills/create-online-meeting/SKILL.md) (`createOnlineMeeting`) — Create an online meeting.
  - [Get Online Meeting](skills/get-online-meeting/SKILL.md) (`getOnlineMeeting`) — Get an online meeting by its ID.
  - [Update Online Meeting](skills/update-online-meeting/SKILL.md) (`updateOnlineMeeting`) — Update an online meeting's properties.
  - [Delete Online Meeting](skills/delete-online-meeting/SKILL.md) (`deleteOnlineMeeting`) — Delete an online meeting.
  - [Get Attendance Report](skills/get-meeting-attendance-report/SKILL.md) (`getMeetingAttendanceReport`) — Get the attendance report of an online meeting.

### Presence
  - [Get My Presence](skills/get-my-presence/SKILL.md) (`getMyPresence`) — Get the presence status of the signed-in user.
  - [Get User Presence](skills/get-user-presence/SKILL.md) (`getUserPresence`) — Get the presence status of a specific user.
  - [Get Presences for Multiple Users](skills/get-presences-by-user-id/SKILL.md) (`getPresencesByUserId`) — Get presence information for multiple users at once.

### Workforce Integrations
  - [List Workforce Integrations](skills/list-workforce-integrations/SKILL.md) (`listWorkforceIntegrations`) — List workforce integrations.
  - [Create Workforce Integration](skills/create-workforce-integration/SKILL.md) (`createWorkforceIntegration`) — Create a workforce integration.
  - [Get Workforce Integration](skills/get-workforce-integration/SKILL.md) (`getWorkforceIntegration`) — Get a workforce integration by its ID.
  - [Update Workforce Integration](skills/update-workforce-integration/SKILL.md) (`updateWorkforceIntegration`) — Update a workforce integration.
  - [Delete Workforce Integration](skills/delete-workforce-integration/SKILL.md) (`deleteWorkforceIntegration`) — Delete a workforce integration.

### Schedules
  - [Get Team Schedule](skills/get-schedule/SKILL.md) (`getSchedule`) — Get the schedule for a team.
  - [Create or Replace Schedule](skills/create-or-replace-schedule/SKILL.md) (`createOrReplaceSchedule`) — Create or replace a schedule for a team.

### Shifts
  - [List Shifts](skills/list-shifts/SKILL.md) (`listShifts`) — List shifts in a schedule.
  - [Create Shift](skills/create-shift/SKILL.md) (`createShift`) — Create a new shift.
  - [Get Shift](skills/get-shift/SKILL.md) (`getShift`) — Get a shift by its ID.
  - [Replace Shift](skills/replace-shift/SKILL.md) (`replaceShift`) — Replace a shift.
  - [Delete Shift](skills/delete-shift/SKILL.md) (`deleteShift`) — Delete a shift.
  - [List Time Cards](skills/list-time-cards/SKILL.md) (`listTimeCards`) — List time cards in a schedule.
  - [Get Time Card](skills/get-time-card/SKILL.md) (`getTimeCard`) — Get a time card by its ID.
  - [Clock In](skills/clock-in/SKILL.md) (`clockIn`) — Clock in on a time card.
  - [Clock Out](skills/clock-out/SKILL.md) (`clockOut`) — Clock out on a time card.

### Time Off
  - [List Time Off Entries](skills/list-times-off/SKILL.md) (`listTimesOff`) — List time off entries in a schedule.
  - [Create Time Off Entry](skills/create-time-off/SKILL.md) (`createTimeOff`) — Create a time off entry.
  - [Get Time Off Entry](skills/get-time-off/SKILL.md) (`getTimeOff`) — Get a time off entry by its ID.
  - [Replace Time Off Entry](skills/replace-time-off/SKILL.md) (`replaceTimeOff`) — Replace a time off entry.
  - [Delete Time Off Entry](skills/delete-time-off/SKILL.md) (`deleteTimeOff`) — Delete a time off entry.
  - [List Time Off Reasons](skills/list-time-off-reasons/SKILL.md) (`listTimeOffReasons`) — List time off reasons in a schedule.
  - [Create Time Off Reason](skills/create-time-off-reason/SKILL.md) (`createTimeOffReason`) — Create a time off reason.

### Employee Learning
  - [List Learning Providers](skills/list-learning-providers/SKILL.md) (`listLearningProviders`) — List registered learning providers.
  - [Register Learning Provider](skills/create-learning-provider/SKILL.md) (`createLearningProvider`) — Register a new learning provider.
  - [Get Learning Provider](skills/get-learning-provider/SKILL.md) (`getLearningProvider`) — Get a learning provider by its ID.
  - [Update Learning Provider](skills/update-learning-provider/SKILL.md) (`updateLearningProvider`) — Update a learning provider.
  - [Delete Learning Provider](skills/delete-learning-provider/SKILL.md) (`deleteLearningProvider`) — Delete a learning provider.
  - [List Learning Content](skills/list-learning-contents/SKILL.md) (`listLearningContents`) — List learning content from a provider.
  - [Create Learning Content](skills/create-learning-content/SKILL.md) (`createLearningContent`) — Create learning content for a provider.
  - [Get Learning Content](skills/get-learning-content/SKILL.md) (`getLearningContent`) — Get a learning content item by its ID.
  - [Update Learning Content](skills/update-learning-content/SKILL.md) (`updateLearningContent`) — Update learning content.
  - [Delete Learning Content](skills/delete-learning-content/SKILL.md) (`deleteLearningContent`) — Delete learning content.

## Support
Please provide any questions or feedback via GitHub issues, or just email kinlane@naftiko.io with feedback. The goal is to keep iterating upon this sandboxes using existing OpenAPI, Microcks, and Bruno features, offering value out of the box via this forkable capability.


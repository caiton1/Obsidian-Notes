
### Async event request
Used to notify host software of status, error and health information as these events occur
- host software needs to submit one or more of command to controller
- Should not expect command to execute immediately, command completes when there is an event to be reported
- If not yet issued and there is a Async event reporting available, controller will store and wait until next async event request is received


### Format NVM
Low level formatting of NVM media, can be used to change attributes of the NVM media
- May destroy all data and metadata associated with all or specific namespaces associated with command

	
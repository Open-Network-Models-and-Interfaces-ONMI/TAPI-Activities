### [2024‐05‐07 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2024%E2%80%9005%E2%80%9007-TAPI-Meeting-Minutes)

Nigel presents a slide set with the description of the feature / use case
- Distinction between
  + Event
  + State
  + Analogue value
  
- State may be dependent from Event and/or Analogue value change

- It is necessary to determine which information is valuable
  + A lot of measurements and processings are continuously performed by underlying systems,
    + Producing a potentially huge amount of information
      - where only a small subset is relevant for (immediate) communication (notification, streaming)

- There are also cases where a specific "detail", normally not relevant, becomes of interest
- In general there are three types of collected information:
  1) Upfront data, like alarms, which is vital for the system management
  2) Background data, like performance measurements, for post processing
  3) Live measurement, through either
     - Spotlight (e.g. through an OAM Job with a certain duration), or
	 - Snapshot (e.g. through an instantaneous OAM Job)

- In other words, the snapshot is an extremely short spotlight

- Presented a diagram with:
  + Poll
  + Align & Notify
  + Stream
  
- The snapshot could be supported by:
  + Restconf GET request and reply (when a simple processing is required)
  + Restconf GET request and streaming as reply (when a more complex processing is required)
  
The proposal will develop through some amendments / additions to existing Inventory and OAM use cases
  + Impact on the schema could be minimal
  
Andrea shows the power-measurement-pac which augments the photonic media CEP
  + We need to clarify in the RIA that some attributes of an object may imply a complex processing
    - E.g. propagate the request down to the network device, because it is not locally stored/storable in the server controller
    - Possible solution:
      + GET on the object: all attributes are retrieved which are more stable hence locally stored in the server controller
	  + GET on the object with specific filter: the more variable attribute is retrieved, the filter triggering a more complex process on server side
  + Similar consideration for streaming, only the stable attributes are normally streamed
  + Each network management system may identify the stable / unstable attributes according to its capability
  + Agreed that attempting to isolate the unstable parameters by the schema is an unflexible solution
    - what is considered unstable in system A may be considered stable in system B

### [2024‐05‐14 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2024%E2%80%9005%E2%80%9014-TAPI-Meeting-Minutes)

Nigel presents a slide set with the description of the feature / use case
- https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/blob/tapi-team-activities/TAPI-TEAM-ACTIVITIES/ContributionsForDiscussions/otcc2024.ND.002_SpotlightAndSnapshotStreams.pptx
- Spotlight stream, using gNMI/Protobuf format
- The OAM Job driving the snapshot and spotlight measurements
- Outstanding: How to model a property in an entity that can be acquired via snapshot/spotlight but that should not be read on get and should not be notified/streamed normally?
  + Last week we considered the 
    - GET on the object: all attributes are retrieved which are more stable hence locally stored in the server controller
	- GET on the object with specific filter: the more variable attribute is retrieved, the filter triggering a more complex process on server side
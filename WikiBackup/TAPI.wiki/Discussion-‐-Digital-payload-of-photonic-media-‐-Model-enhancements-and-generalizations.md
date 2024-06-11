### [2023‐11‐28 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2023%E2%80%9011%E2%80%9028-TAPI-Meeting-Minutes)

Andrea shows the slides 141 - 160 of the otcc2022.AM.001_TAPI_RIASlides.pptx, available in the contributions
  (https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/tree/tapi-team-activities/TAPI-TEAM-ACTIVITIES/ContributionsForDiscussions)
- Nigel recalls that a generalization of the transponder to transponder connectivity was asked by Ramon a while ago
- So far the transponder to transponder connectivity design is centered on supporting digital OTN payload
  + ODUk or ODUCn Connectivity Service, which provisioning params include all photonic provisioning (transceiver mode, central freq. etc.)
- Discussed to which degree the transponder to transponder connectivity shall include digital payolad details
- Preliminary agreed that the model shall be designed to encompass more flavours / scenarios

### [2024‐02‐06 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2024%E2%80%9002%E2%80%9006-TAPI-Meeting-Minutes)

Andrea indicates that so far the TAPI RIA has foreseen transponder to transponder connectivities in strict conformance to G.709 OTN payload.
- This could be a limitation, given the variety of existing solutions, e.g.
  + OTN but not G.709
  + Non OTN

- Andrea shows some figures with a different organization of NEP/CEP stack:
  1) Introducing a new OTSiMCA CEP.
  2) Either encapsulate the OTU parameters in the ODU CEP (given the fixed 1:1 relationship), or keep the OTU CEP separated.

- Preliminary agreed that the OTSiMCA could or could not be terminated on the regenerators.
  + In case it is terminated, then the OTSiMCA Connectivity Service will list - in case of regens - more OTSiMCA Top Connections.
    - Hence no end to end Top connection for the OTSiMCA Connectivity Service.
  + In case it is not terminated (the regens manage the pass-through) then the OTSiMCA Connectivity Service will have only one e2e Top Connection.

- To be explored whether the new OTSiMCA CS model will be added to or will replace the current one.

### [2024‐02‐20 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2024%E2%80%9002%E2%80%9020-TAPI-Meeting-Minutes)

Andrea recalls that so far the TAPI RIA has foreseen transponder to transponder connectivity config/state model optimized to G.709 OTN payload.
- This could be a limitation, given the variety of existing solutions, e.g.
  + OTN but not G.709
  + Non OTN

- Andrea shows the slide with the requirements for "transponder to transponder" Connectivity Service
  + Text amended according to suggestions from the team

- Discussion to be continued.

### [2024‐03‐26 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2024%E2%80%9003%E2%80%9026-TAPI-Meeting-Minutes)

Andrea shows some new figures regarding the transponder to transponder connectivity
  - General agreement on the approach
  - The management of inverse multiplexing can be attached to the
    + OTU/ODU or OTSiMCA CEP instance, unique client of the NEP which represents the digital payload supported by one or more optical carriers
  - Use dash-dot line for alternative choices in the functional stack
  - Agreed that descriptions - of even multiple cases - anyway reduce the variety of implementations
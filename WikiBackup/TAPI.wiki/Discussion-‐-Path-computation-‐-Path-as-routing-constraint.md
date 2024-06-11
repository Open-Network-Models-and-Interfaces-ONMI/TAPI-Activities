### [2024‐01‐09 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2024%E2%80%9001%E2%80%9009-TAPI-Meeting-Minutes)

Jonathan presents a slideset (reference OIF 2023.436)
  - Highlighted the difference between link and path constraints
    + Path constraints apply to the end to end path
  - Nigel considers "post analysis" scenario:
    + Firstly the paths are calculated based on e.g. some shortest path criteria
    + Secondly the calculated paths are validated against the (optical) constraints
    + Agreed that the "on the fly" path computation could be very complex, although desirable.
  - Nigel asks about the semantic of optical constraints
    + Esther replies that IETF is well advanced on the topic.
    + Post meeting note:
      Andrea asked Sergio - below listed the most relevant references:
      https://datatracker.ietf.org/doc/draft-ietf-teas-yang-path-computation/
      https://datatracker.ietf.org/doc/draft-ietf-ccamp-wdm-tunnel-yang/
      https://datatracker.ietf.org/doc/draft-ietf-ccamp-optical-path-computation-yang/
      https://datatracker.ietf.org/doc/draft-ietf-teas-yang-te/


### [2024‐01‐23 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2024%E2%80%9001%E2%80%9023-TAPI-Meeting-Minutes)

Jonathan announces a contribution regarding path computation use cases. To be reviewed on next call.
- Mentioned that connection and path computation will be key subjects for OFC 2025.

Andrea shows a draft document with a summary of the augments defined in draft-ietf-teas-yang-path-computation-21.txt:
- https://github.com/OpenNetworkingFoundation/TAPI/blob/tapi-team-activities/TAPI-TEAM-ACTIVITIES/ContributionsForDiscussions/ietfCcampTeasPathComp_am23012024.txt
- Next step: start updating the TAPI model, at least the Connectivity Service constraints.
  Regarding TAPI Path Computation, we still miss the related use cases.

- Esther clarifies that the path computation is expected to be performed considering the end of life of network resources.
  + In other words, the computed path shall be fulfilling the specified constraints during the whole network lifecycle.
    Penalties (e.g. increasing crosstalk) shall be calculated in this future proof perspective.

- Jonathan points out that the "gsnr" constraint is not enough.
  + Esther agrees, "gsnr" is a starting point, contributions are welcome.

- Discussion on multi-domain path constraints.
  + General agreement that:
    - Today the ENNI always foresees the O/E/O.
    - The orchestrator (managing more domains) shall be provided with full details regarding topology and impairments,
      otherwise if each domain controller provides only an abstract picture, then there is the risk of cranckback.
    - Gabriele: each domain may make available different (or same but differently evaluated) parameters, leading to sub-optimal solutions.
      Andrea: we are here exactly to minimize the unnecessary differences.
  + Jonathan mentions the need to know the power level of signal coming from the other domain, and that computation shall specify spectrum rather than frequencies.

### [2024‐01‐30 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2024%E2%80%9001%E2%80%9030-TAPI-Meeting-Minutes)

Andrea shows the Photonic Model diagrams regarding the provisioning of the Connectivity Service,
  with the purpose to identify the more appropriate places where to add CCAMP optical path constraints.

- Nigel: in TAPI, the Path is intended as a set of links composing a possible route in the network,
         considering the topological reachability, while the computation of the route of the
         Connectivity Service implies the service feasibility considering all the technology specific constraints,
         hence driving and leveraging all the info available at server controller.

- Esther essentially confirms that CCAMP Path computation is more similar to TAPI Connectivity Service computation,
  with the difference that the CCAMP Path is not necessarily deployed in the network, but can be used for network planning use cases.

- Andrea: we need to develop use cases to progress the TAPI Path Computation - considering CCAMP approach.

- Andrea shows that the 2.5.0 photonic model is using the transceiver profile for both
  + specification of transceiver capabilities / features
  + provisioning of transceiver (at connectivity service provisioning time)
  Agreed that this is not correct, hence Andrea will amend the model to decouple profiles and provisioning management.

- This and some other found issues seem requiring a short term delivery of a 2.5.1 version.


### [2024‐02‐06 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2024%E2%80%9002%E2%80%9006-TAPI-Meeting-Minutes)

Jonathan presents a slide set for the Optical Path Computation and Restoration.
- Since 2003 OIF is interested in network control.
- What is new? The dynamic optical path connection, where optical is analogue technology.
  + Very high rates, no multiplexing, increasingly complex modulation.
- The concept of aggregation (rather than sum) of the optical impairments along the route.
- Listed the candidate metrics of optical impairments.
  + Esther: same approach as GNPy.
- Discussion on photonic ENNI, agreed that multi-operator is difficult to implement, reluctance of publishing internals.
  + For now let's focus on optical path computation within a single domain,
    then will evaluate if the info necessary for multi-domain computation can be published keeping sensitive info hidden.
- Andrea asks Jonathan whether pre-computation of paths has been considered.
  + Jonathan, no because the approach does not scale.
  + Hence the computation & realization is "on the fly", Jonathan has seen restorations concluded in less than one second.


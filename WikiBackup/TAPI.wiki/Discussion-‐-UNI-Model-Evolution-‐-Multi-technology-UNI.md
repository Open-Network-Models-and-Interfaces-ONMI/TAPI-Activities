### [2023‐11‐21 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2023%E2%80%9011%E2%80%9021-TAPI-Meeting-Minutes)

Andrea shows the slides provided by Roshan.
After some discussion, agreed the following way forward:
1) Deprecate DSR and OTN layer protocol names from SIP and NEP at UNI and ENNI.
     - This because DSR and OTN actually represent the supportable service layers, rather than the layer of the (bottom most) SIP/NEP.
2) Recommend in the RIA to use either PHOTONIC_MEDIA or ELECTRICAL_MEDIA (identity to be added) for SIP/NEP at UNI/ENNI.

Nigel clarifies that the NEP referring an Access Port is the logical entity which is nearest to a physical entity.
- For TM Forum MTNM, this is the PTP (Physical Termination Point) entity.
TAPI has evolved by inserting a "PTP" at each layer network, which allows same repeatable pattern at any network slice. 
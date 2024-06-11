### [2023‐11‐14 TAPI Meeting Minutes](https://github.com/Open-Network-Models-and-Interfaces-ONMI/TAPI/wiki/2023%E2%80%9011%E2%80%9014-TAPI-Meeting-Minutes)

Andrea and Nigel recap the discussion with Orange.

The Restconf implementation of OpenDaylight (hence TransportPCE) provides a direct API access to the datastore. While this behavior is in line with Restconf, the TAPI provisioning implies more complex transactions. In general, the data associated to a TAPI provisioning (creation, modification, deletion) represents the intent for such provisioning, which triggers a (potentially very complex) process in the server controller. This process may involve both internal and network modifications, their synchronization, etc.

The decision to deprecate RPCs from TAPI was due:

    the complexity of design and maintenance
    the separation of TAPI data structures dedicated to intent from the data structures dedicated to the mirroring of system state (controllers, network). The POST/PUT/DELETE intents trigger processes which lead to orchestrated changes of the system state, these changes occurring in a variable amount of time, from seconds to hours or even more for e.g. scheduled activities. TAPI model specifies the data structures, TAPI RIAs specify how to use them for a number of Use Cases.

Nigel recalls that at IETF the evolutions ("next") of Netconf, Restconf and Yang are under discussion, references being:

    https://github.com/netconf-wg/restconf-next/issues
    https://github.com/netconf-wg/restconf-next/issues
    https://github.com/netmod-wg/yang-next/issues

Furthermore last week (at IETF 118 Prague) the concept of "candidate intent" has been informally discussed, with the target to add the item to the "next" todo list.

Agreed to add a discussion page re RPCs/Data API/Intent to TAPI
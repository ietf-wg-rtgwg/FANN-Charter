## Overview
Many network applications, including AI/ML training/inference and cloud services, require high bandwidth, low loss, low delay, and low jitter networks that can rapidly adapt to link faults, degradation, congestion, and other such adverse conditions to maintain service continuity and experience. However, existing routing technologies often face limitations in responding to such network conditions, especially in high-scale and high-bandwidth data center (DC) and data center interconnect (DCI) networks.

Network nodes can detect link failures, signal degradation, errors, congestion on output queues, microbursts, and other such adverse local conditions at microseconds to sub-millisecond timescales. These nodes are then able to adjust, when feasible, the traffic flows via local techniques like adaptive load balancing, fast-reroute, and other mechanisms. However, in many DC and DCI network designs, these local techniques are unable to mitigate such events in a timely and efficient manner resulting in diverted traffic flows that introduce latency variations, create congestion in other parts of the network, and affect other traffic flows. This brings about the requirement for a fast notification mechanism whereby a node can signal such locally detected network conditions to other (remote) nodes that are one or more hop away which are then able to apply techniques such as adaptive load balancing or fast-reroute in an efficient and responsive manner.

The Fast Network Notification (FANN) Working Group is chartered to investigate this problem space for the need to convey locally detected adverse conditions (and their recovery) to remote nodes that can then act on them for enabling efficient and responsive traffic flow handling and to develop a comprehensive solution.

## Scope and Work Plan
The WG will begin by documenting the problem space, requirements, and gaps in existing mechanisms, including technologies defined both within and outside the IETF. The WG will then define a framework describing how network notifications are generated, and consumed, including integration with existing technologies (including Layer 2 and Layer 4 techniques and inter-layer dependency with routing at Layer 3). The analysis will include the similarities and differences among the various deployment scenarios that the WG will be considering.

After the WG has completed their work (i.e., after WGLC) on requirements and this framework, the WG will work on the development of a solution to signal adverse network conditions (and their recovery) to remote nodes. These mechanisms may include discovery and registration procedures to identify interested remote nodes. The WG will reuse existing protocols where appropriate and define new protocols or mechanisms when necessary.

The notifications are expected to be event-driven and primarily optimized for fast generation and consumption in the forwarding plane (ideally in hardware) to meet the responsiveness requirements. As a secondary objective, the solution may also support consumption by management systems and routing protocols, provided routing stability is preserved. The solution should look at the use of existing management plane techniques for this secondary objective.

The WG will initially focus on notifications for link failures, signal degradation reported as link errors, and port output queue congestion, while ensuring extensibility for additional conditions in the future.

Although the solution is intended to be generally applicable, the WG will prioritize the requirements of data center (DC) and data center interconnect (DCI) networks, where rapid responsiveness is critical. The WG will balance responsiveness and general applicability in its design of the solution.

The WG will seek publication of protocol specifications (i.e., Proposed Standards documents) only after demonstrating at least two interoperable implementations that utilize hardware-based forwarding, preferably across different network processor implementations.

The WG will also deliver an applicability statement document that provides operational guidance for deployment of the solution in the target deployments and YANG models for management of the solution.

The solution is intended for deployment within private networks under single administrative control. The WG will define mechanisms to identify notification domains and to ensure isolation of notifications within those domains. Appropriate security mechanisms and considerations will be documented as part of the WG deliverables.

## Work Items
The WG is expected to produce the following deliverables:
- A problem statement, requirements, and gap analysis document (using [draft-ietf-rtgwg-net-notif-ps] as a base) to guide the WG work and related deliverables (Informational, not intended for publication).
- A framework document describing the overall architecture and integration with existing protocols and technologies (Informational).
- One or more protocol specifications defining the fast network notification mechanisms, including associated discovery and registration procedures as needed (Proposed Standard).
- An applicability and operational guidance document describing deployment considerations and usage models (Informational).
- YANG modules for configuration and management of the solution (Proposed Standard).

## Collaborations
The WG will coordinate with other relevant IETF working groups for technologies and protocols within their respective areas of responsibility. This includes, but is not limited to, the RTGWG, TEAS, IDR, LSR, SPRING, BFD, IPPM, TSVWG, CCWG, SRV6OPS and NMOP. Any required extensions to existing protocols or technologies will be developed in the appropriate working groups.

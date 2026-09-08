ScLBS — Scalable Self-Certified IoT Authentication
Academic project · Syrian Private University
Faculty of Artificial Intelligence Engineering
Supervised by Dr. Wassim Aljuneide
Overview
ScLBS is an integrated authentication scheme for distributed IoT networks.
Classic approaches (Password / RSA / PKI) impose heavy compute, storage and
communication costs on constrained devices, and depend on a central
certificate authority that becomes a single point of failure. ScLBS removes
the CA entirely using self-certified keys, and uses Federated Learning to
build an adaptive trust score between nodes without sharing raw data.
The system model has three roles: Sensing Nodes (SN) with limited compute,
Reporting Nodes (RN) that aggregate and verify location, and a Base Station
(BS) that collects filtered reports. Authentication runs in three phases —
Initialization, Registration, and Secure Phase.
Key Features
	•	Self-certified keys — no certificate authority; the RN issues and
verifies the public key while the private key never leaves the device
	•	Federated Learning trust evaluation — trust factor per node,
refined collaboratively, no raw data shared
	•	Location-aware two-factor authentication — device identity plus
verified geographic position, confirmed by the highest-trust neighbour
	•	Enhanced ECC (EECC) — 320-bit curve, security based on the hardness
of the EECDLP
	•	B+-tree group key management — O(log n) rekeying on join / leave
Tech Stack
Python · Node-RED · NS-3 · ProVerif
Formal Verification
The protocol is modelled in ProVerif under the Dolev-Yao adversary model.
Verified properties: private-key secrecy (chiSN, chiRN), session-key
secrecy, and authentication correctness
forall x: endAuth(x) => beginAuth(x)).
Six security theorems are proven in the report: session-key secrecy,
Sybil resistance, collusion resistance, correctness of authentication,
forward secrecy and backward secrecy.
To run the model:

proverif proverif/sclbs.pv

Results
Evaluated in NS-3 across 20–100 devices against benchmark group-key
protocols:

|Metric             |ScLBS  |Compared schemes|
|--------------------|-------|----------------|
|Group-formation time|82 ms  |121–148 ms      |
|Rekeying overhead   |920 B  |1,465–1,820 B   |
|Group-key energy    |22.7 mJ|34.2–41.6 mJ    |

Ablation (latency increase when disabled): FL +17%, location +12%,
hierarchy +23%.
Current scope: results assume static nodes, ideal location verification,
and homogeneous device capabilities.
Repository Structure

sclbs.pv                   ProVerif model
ScLBS Presentation.pdf     Slides
report-sclbs.docx          Full report
*.jpeg                     Node-RED implementation screenshots



## Authors

Ghaith Jbili · Hamza Alothman


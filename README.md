# ScLBS — Scalable Self-Certified IoT Authentication

Academic project · Syrian Private University  
Faculty of Artificial Intelligence Engineering  
Supervised by Dr. Wassim Aljuneide

## Overview

ScLBS is an integrated authentication scheme for distributed IoT
networks. Classic approaches (RSA, PKI) are too heavy for constrained
devices and depend on a central certificate authority, which becomes a
single point of failure. ScLBS removes the CA entirely using
self-certified keys, and uses Federated Learning to build an adaptive
trust score between nodes without sharing raw data.

## Key Features

- **Self-certified keys** — no certificate authority, private key never leaves the device
- **Federated Learning trust evaluation** — collaborative, privacy-preserving
- **Location-aware two-factor authentication** — device identity + geographic position
- **Zero-knowledge verification** — public key verified without exposing credentials
- **B+-tree group key management** — O(log n) rekeying on join/leave

## Tech Stack

Python · Node-RED · NS-3 · ProVerif

## Verification & Results

Six security properties formally proven with ProVerif under the
Dolev–Yao adversary model: session-key secrecy, Sybil resistance,
collusion resistance, authentication correctness, forward and backward
secrecy.

Performance evaluated in NS-3 across 20–100 devices, showing
improvements in group-formation time, rekeying overhead and energy
consumption compared to benchmark group-key protocols.

## Repository Structure


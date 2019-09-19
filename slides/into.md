---
marp: true
theme: default
style: |
  # section, code {
  #   background-color: #19445b;
  # }
  # p, h1, h2, h3, h4, li, pre, code, code span, code svg, header, .hljs-string {
  #     color: white;
  #     border: none;
  # }
  # pre, code {
  #     color: white;
  #     background: none;
  # }

header: '**_Virtual Meet-up #1 - Developer introduction_**'
# footer: '![image](https://example.com/image.jpg)'
---

# Catalyst Network

Developer Introduction

###### Created by [@nshcore](https://github.com/nshcore/)

![bg right 50%](https://avatars2.githubusercontent.com/u/46792459?s=200&v=4)

---

# What is the
# <!--fit-->Catalyst Network?

---

# <!--fit--> #NotHotDog

![bg right 50%](./images/not-hot-dog.jpeg "NOT HOT DOG!!!")

---

# Catalyst Network 

* Probabalistic BFT Consensus
* Distributed FileSystem (DFS)
* Distributed Compute System (DCS)
* Distributed DNS
* KVM smart contracts
* Public and Confidential transactions

---

# What is 
# <!--fit-->Probablistic BFT Consensus

---

# <!---fit--->A collabarative process in which nodes collectively vote on global state transitions

---
# Create Transaction
```
                                                                                                                   +--Confidential Entry-------------------+---------------+
+---Protocol Message-------------------------------------+-----------------+                                       |                                       |               |
|                                                        |                 |                                       |  value_commitment                     | M * 32 bytes  |
|   PeerID                                               | 60 bytes        |   +--Public Entry----+-----------+    |                                       |               |
|                                                        |                 |   |                  |           |    +-------------------------------------------------------+
+--------------------------------------------------------------------------+   |  Amount          |  32 bytes |    |                                       |               |
|                                                        |                 |   |                  |           |    |  bit_commitment                       | 32 bytes      |
|   CorrelationId                                        | 16 bytes        |   +------------------------------+    |                                       |               |
|                                                        |                 |   |                  |           |    +-------------------------------------------------------+
+--------------------------------------------------------------------------+   |  To Address      |  20 bytes |    |                                       |               |
|                                                        |                 |   |                  |           |    |  per_bit_blinding_factor_commitment   | 32 bytes      |
|   MessageType                                          | 2 bytes         |   +------------------------------+    |                                       |               |
|                                                        |                 |   |                  |           |    +-------------------------------------------------------+
+--------------------------------------------------------------------------+   |  From Address    |  20 bytes |    |                                       |               |
|                                                        |                 |   |                  |           |    |  poly_commitment_t1                   | 32 bytes      |
|   Signature                                            | 64 bytes        |   +------------------------------+    |                                       |               |
|                                                        |                 |   |                  |           |    +-------------------------------------------------------+
+--------------------------------------------------------------------------+   |  Transaction Fee |  32 bytes |    |                                       |               |
|--Transaction Message-----------------------------------------------------|   |                  |           |    |  poly_commitment_t2                   | 32 bytes      |
||                     |                                 |                ||   +------------------+-----------+    |                                       |               |
||                     |  Public Entries                 | N * 104 bytes  ||                                       +-------------------------------------------------------+
||                     |                                 |                ||   +--Contract Entry--+-----------+    |                                       |               |
||                     |                                 |                ||   |                  |           |    |  proof_of_share_tau                   | 32 bytes      |
||                     +---------------------------------------------------|   |  Amount          |  32 bytes |    |                                       |               |
||                     |                                 |                ||   |                  |           |    +-------------------------------------------------------+
||  Entries (N > 1)    |                                 |                ||   +------------------------------+    |                                       |               |
||                     |  Confidential Entries           | N * (104 bytes ||   |                  |           |    |  proof_of_share_mu                    | 32 bytes      |
||                     |                                 | + CallData)    ||   |  CallData        | Bytes > 0 |    |                                       |               |
||                     |                                 |                ||   |                  |           |    +-------------------------------------------------------+
||                     +---------------------------------------------------|   +------------------------------+    |                                       |               |
||                     |                                 |                ||   |                  |           |    |  aggregated_vector_polynomial_l       | k * 32 bytes  |
||                     |                                 |                ||   |  To Address      |  20 bytes |    |                                       |               |
||                     |  Smart Contract Entries         |  N*736 bytes   ||   |                  |           |    +-------------------------------------------------------+
||                     |                                 |                ||   +------------------------------+    |                                       |               |
||                     |                                 |                ||   |                  |           |    |  aggregated_vector_polynomial_r       | k * 32 bytes  |
|----------------------+---------------------------------------------------|   |  From Address    |  20 bytes |    |                                       |               |
||                                                       |                ||   |                  |           |    +-------------------------------------------------------+
||  Signature                                            |  64 bytes      ||   +------------------------------+    |                                       |               |
||                                                       |                ||   |                  |           |    |  a_prime_0                            | 32 bytes      |
|--------------------------------------------------------------------------|   |  Transaction Fee |  32 bytes |    |                                       |               |
||                                                       |                ||   |                  |           |    +-------------------------------------------------------+
||  Timestamp                                            |  4 bytes       ||   +------------------+-----------+    |                                       |               |
||                                                       |                ||                                       |  b_prime_0                            | 32 bytes      |
|--------------------------------------------------------------------------|                                       |                                       |               |
+--------------------------------------------------------------------------+                                       +---------------------------------------+---------------+

```

---

# Broadcast to network

![bg right 90%](./images/gossip.png)

---

# Nothing too strange yet

---

# Deterministic Mempool

- Highest amount
- Highest fee
- Oldest timestamp
- Signature in alphabetical order

![bg right 50%](./images/deterministic-mempool.png)

---

# Validation

---

# Peers in the validation process have 4 states

1. Passive Node
    - Connected to peer network
2. Reservist Node
    - Awaiting for admission to the validation pool
3. Worker Node
    - A node that is admited to the validation pool
4. Producer Node
    - A subset of worker nodes who can contirbute to production of ledger state updates

---

# Network Constitution
![bg right 100%](./images/network-constitution.png)

---

# Validation pool

![bg 40%](./images/t1.png)

---


# Validation pool

![bg 40%](./images/t2.png)

---

# Validation pool

![bg 40%](./images/t2a.png)

---

# Validation pool

![bg 40%](./images/t3.png)

---

# Validation pool

![bg 40%](./images/t4.png)

---

# Validation pool

![bg 40%](./images/t5.png)

---


![bg 40%](./images/sad-banana.jpg)

---

# 51% Attack Research

![](./images/probability-sum.png)

# <!--fit--> http://github.com/catalyst-network/51-percent-attack-research

![bg right 80%](./images/51-simulation.png)

---

# The Ledger Cycle

- Producers validate common sets of transactions from the mempool

- Each producer compiles a state delta and votes among its peers in the cycle to vote on the most popular delta produced by the set of producers.

---

# The Ledger Cycle

![bg right 100%](./images/ledger-cycle.png)

---

# Consensus Research

# <!--fit--> https://catalystnet.org/consensus-research-paper.pdf

![bg right 100%](./images/1cycle.png)

---

# Architecture

```
+---------------------------+--------------------------+
|                           |                          |
|                           |                          |
|     Catalyst.Modules      |     Custom.Modules.*     |
|                           |                          |
+---------------------------+--------------------------+
|                                                      |
|                                                      |
|     Catalyst.Core.Modules.*                          |
|                                                      |
+------------------------------------------------------+
|                                                      |
|                                                      |
|     Catalyst.Core.Lib                                |
|                                                      |
+--------------------------------------------------------------------------------+----------------------------+
|                                                      |                         |                            |
|                                                      |                         |                            |
|     Protocol.Sdk.C#                                  |     Protocol.Sdk.Js     |     Protocol.Sdk.Java      |
|                                                      |                         |                            |
+------------------------------------------------------+-------------------------+----------------------------+
|                                                                                                             |
|                                                                                                             |
|     Catalyst.Protocol                                                                                       |
|                                                                                                             |
+-------------------------------------------------------------------------------------------------------------+
```

---

# Catalyst.Protocol

* Abstract Protocol Schema Deffinitions.
* Protobuffs Serialisation Format.
* Language Interoperability.

---

# Protocol-sdk-*

* Concrete standardised types across languages
* Auto generated from protobuffs deffinitions
* Building blocks for low level functionality

---

# Catalyst.Core.Lib

Core librarys and helpers for IO, networking and configuration. Low level functionality for nodes and modules

* IO
* P2P
* Cryptography

---

# Catalyst.Core.Modules.*

* Core modules provide spoecific functionality for Catalyst.Node

---

# Catalyst.Modules.*

* Modules provide 'flavour' functionality for nodes
* Use familiar technology
* Extend core functionality

```
+--Catalyst.Core.Module.*----------------------------------------------------------------------------------------------------+
|                                                                                                                            |
|  +-------------+ +-------------+ +---------------+ +---------------+ +---------------+ +---------------+ +---------------+ |
|  |             | |             | |               | |               | |               | |               | |               | |
|  |             | |             | |               | |               | |               | |               | |               | |
|  |             | |             | |               | |               | |               | |               | |               | |
|  |             | |             | |               | |               | |               | |               | |               | |
|  |             | |             | |               | |               | |               | |               | |               | |
|  | KVM         | | Consensus   | | Ledger        | | Mempool       | | KeySigner     | | KeyStore      | | Cryptography  | |
|  |             | |             | |               | |               | |               | |               | |               | |
|  |             | |             | |               | |               | |               | |               | |               | |
|  |             | |             | |               | |               | |               | |               | |               | |
|  |             | |             | |               | |               | |               | |               | |               | |
|  |             | |             | |               | |               | |               | |               | |               | |
|  +-------------+ +-------------+ +---------------+ +---------------+ +---------------+ +---------------+ +---------------+ |
|                                                                                                                            |
+----------------------------------------------------------------------------------------------------------------------------+

+----------------------------------------------------------------------------------------------------------------------------+
|                                                                                                                            |
|   Catalyst.Core.Lib                                                                                                        |
|                                                                                                                            |
+----------------------------------------------------------------------------------------------------------------------------+

```
---

# Custom modules

Custom modules are a great way of providing additional or domain specific functionality to the ledger.

---

# <!--fit--> #NotHotDog

![bg right 75%](./images/its-science.jpg "its science!!!")

---
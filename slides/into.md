---
marp: true
theme: default
style: |
  section, code {
    background-color: #19445b;
  }
  p, h1, h2, h3, h4, li, pre, code, code span, code svg, .hljs-string {
      color: white;
      border: none;
  }
  pre, code {
      color: white;
      background: none;
  }

header: '**_header content_**'
footer: '![image](https://example.com/image.jpg)'
---

# Catalyst Network

Developer Introduction

###### Created by [@nshcore](https://github.com/nshcore/)

![bg right 50%](https://avatars2.githubusercontent.com/u/46792459?s=200&v=4)

---

# <!--fit-->What is Catalyst?

---

# <!--fit--> #NotHotDog

![bg right 50%](./images/not-hot-dog.jpeg "NOT HOT DOG!!!")

---

# Catalyst Core Framework 

* Probabalistic BFT Consensus
* Distributed FileSystem (DFS)
* Distributed Compute System (DCS)
* Distributed DNS
* KVM smart contracts
* Public and Cconfidential transactions

---

# <!---fit--->What is Probablistic BFT

---

# <!---fit--->A collabarative process in which nodes collectively vote on global state transitions

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
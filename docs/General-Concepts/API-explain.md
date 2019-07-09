---
id: api-explain
sidebar_label: GINAR System 
title: GINAR System
---

GINAR system is running on a public blockchain along with a private blockchain of our own. The core idea is to make the system transparent and open-participating while retaining the properties of fairness, tamper-resistance and unpredictability. The system allows anyone who wishes, to verify results and participate in the process of generating them.

![GINAR System](https://github.com/ginarteam/docs/blob/master/docs/General-Concepts/System.png?raw=true)

**GINAR Service** is a bridge between clients who request random numbers and decentralized networks that oversee generating numbers.

**Core Layer** is in charge of generating random numbers. This component is running on a permission blockchain that consists of many nodes distributed throughout the network. Each node in the Core Layer has a **private key SK** and a corresponding **public key PK**.

**Public blockchain** hosts a low-speed, open, multi-participatory RNG protocol to produce fair, verifiable numbers.


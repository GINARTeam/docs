---
id: verification-tool
title: RNG Authenticity Verification
---

## 1. Introduction

GINAR is a service that provides random numbers based on blockchain technology with the following main characteristics: **unpredictability, public-verifiability, tamper-resistance**, and **transparency**. Public-verifiability is the property that enables anyone to check the correctness of random number generation from GINAR. We have APIs available to support authenticity verification.

## 2. How GINAR generate random numbers?

GINAR service generates a random number from the input **Ticket ID**. This Ticket ID contained: 
- Machine ID: The Machine ID which being defined by GINAR customers.
- ETH entropy: The entropy receive from Ethereum blockchain through dRNG smart contract
- Timestamp at receiving
- Serial numbers: Each customer has a set of serial numbers
- User Data: GINAR customers can decide whether or not to send their user data for contributing the ticket ID creation
- Mockup ID: The mockup procedure performed by GINAR system to create a specific ticket ID

After each successful query, a next Ticket ID is created from the previous Ticket ID following recursive formula. GINAR service keeps the hash of the genesis Ticket ID, this value will be published on blockchain for authenticity verification.





To use **GINAR Random Verification Tool**, go to **[GINAR Website](https://www.GINAR.io/)** and navigate to **Verify**, then find **Verification Tool** to start verifying your random number. It will link you to the **[Verification Page](https://blackbox.ginar.io/)**.


## Verification process

-	**Step 1**: Copy your ticket ID and paste to verification windows
-	**Step 2**: Click “Search” to verify your ticket ID. Next, the verified result will show up

> If the random number is incorrect, the tool will notify - **Ticket not found!**

![Invalid](https://github.com/GINARTeam/docs/blob/master/docs/Verification-tool/2.Failed%20Verify.png?raw=true)

> If the random number is correct, the tool will notify – **The result is valid**. There has a list of Eligible Contributors to be showed up. You click to **View Block Information** to check the details of Block Info and JSON Data.

![Valid](https://github.com/GINARTeam/docs/blob/master/docs/Verification-tool/1.Success%20Verified.png?raw=true)



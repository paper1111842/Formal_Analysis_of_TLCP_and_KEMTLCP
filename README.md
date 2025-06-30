# Formal Analysis of TLCP and KEMTLCP
This is the source code repo for the Formal Analysis of TLCP and KEMTLCP, a formal verification tool to analyze the Transport Layer Cryptography Protocol and its Post-quantum Variant. This instruction describes the organization of the source code and how to use it.


## Instructions

### Software Requirements
To run this Code, you need [ProVerif 2.05+](https://prosecco.gforge.inria.fr/personal/bblanche/proverif/).

### File Organization

Source code files:
- tlcp-lib.pv: Generic library with threat model and protocol processes
- OWA_tlcp11.pv: One-way standard authentication process of TLCP with session resumption to analyze security goals
- MuA_tlcp11.pv: Two-way mutual authentication process of TLCP with session resumption to analyze security goals
- PQ_kemtlcp.pv: KEMTLCP Process to analyze security goals


### Verify the security goals
Using the library tlcp-lib.pvl provided above, the `.pv` files corresponding to various processes of the protocol should be run by the command:

```
PROJECTROOTDIR> ./proverif -lib tlcp-lib <filename>
```

### Understanding the results

To understand the results, look in the PV file. Roughly, the "true" queries correspond to security goals like (Forward) Secrecy, Authentication, Replay Prevention, and Integrity.  The "false" queries correspond to queries that we expect to fail; they show that our verification is tight, disabling some of the conditions in our "true" queries would cause them to be false.

In addition, you can also output the attack trace search results in a specified folder using the following code:

```
PROJECTROOTDIR> ./proverif -lib tlcp-lib -html <folderpath> <filename>
```

This can generate result files in various formats (e.g. pdf) including text descriptions and image presentations, such as


![trace1](https://github.com/paper1111842/Formal_Analysis_of_TLCP_and_KEMTLCP/blob/main/trace1.png)

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
You can run './proverif' + '-lib libraryname' + 'filename.pv' to specific which process you want to analyze. 
They use the library tls-lib.pvl provided above.

```
PROJECTROOTDIR> ./proverif -lib tlcp-lib <filename>
```

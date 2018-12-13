# Formal Verification And Full (safe) Semantics For DAOs

## Problem:

## Solution:

## Results:

## Proposed Architecture:

## Genesis Thought:
Browse a DAO safely by: 
1.  going to our tool (website or native app), 
2. paste the DAO's address or ENS name,
3. get a GUI for the DAO where all configuration and functionality of the DAO is present.

To make this possible, we would run the bytecode of the DAO through a semantic generator (locally on the client). The output is every action possible for a DAO and every present configuration. If semantics for some part of the bytecode was not available, it will show a warning ("we can not detect all functionality of this DAO, preceded with caution") and display the code what was not mappable to any known semantic.

To create this tool, we would use something like the K framework with EVM semantics and create building blocks on top of that (grouping of EVM semantics). The building blocks could be coded in a DAO library (the library would also in the process be formally verified).  A JSON schema form definition could accompany each building block (on IPFS), for defining how to interact with the abstraction.

Then we could have the concept of a "safe" DAOs. This would be a DAO that is fully represented by our semantics (our building blocks on top of the K frameworks EVM semantics) and therefore also formally verified.

## Counter Arguments:
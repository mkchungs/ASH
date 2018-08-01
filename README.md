# Audit Secret Hash
Implementation of chunk-level challenge/response according to Vikor Tron's [Smash-Proof Paper](https://ethersphere.github.io/swarm-home/ethersphere/orange-papers/2/smash.pdf). 


To generate the audit hash for later challenge, each 4096 bytes chunk is chopped into 128 segments to form a Merkle Tree. Seed is then added to a random segment j. Aduit Secret Hash is defined as the Merkle Root of the Tree with salted segment j, which can be recovered/validated independently using the published seed. 

This ASH implementaion is made to be compatible with [swarmDB v0.1](https://github.com/wolkdb/swarmdb). Please be aware that it deliberately trims the padded `0`s prior to constructing the Tree, thus the ASH is different than the one specified in the paper. 


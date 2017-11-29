


Here have the working document that documents my understanding of Blockchain & DLT.

How to go forward:
* Go through my whole book and make notes. Dig into the below resources if I get stuck
* Then, go through the whole GLOBAL BLOCKCHAIN BENCHMARKING STUDY 
* Then, go through Vitalic posts and articles (ETH White paper, mauve, medium)
* Then, go into detail in Hyperledger and Corda

My goal is to
* Have a solid understanding of blockchain, in order to see if it is useful for the industry. Have the feeling it might be useless. 
* But at least I can get own business ideas and be an expert
* More concrete questions; use as headers! 
* So have to conclude: is this for cyber punks or a tool in business?

Resources I need to include
* My ethereum book
* Read the whole thing: GLOBAL BLOCKCHAIN BENCHMARKING STUDY Dr Garrick Hileman & Michel Rauchs
* https://medium.com/@VitalikButerin/a-proof-of-stake-design-philosophy-506585978d51
* https://medium.com/@VitalikButerin/the-meaning-of-decentralization-a0c92b76a274
* ETH white and yellow paper
* https://medium.com/@VitalikButerin/zk-snarks-under-the-hood-b33151a013f6
* https://medium.com/@VitalikButerin/exploring-elliptic-curve-pairings-c73c1864e627
* https://medium.com/@VitalikButerin/quadratic-arithmetic-programs-from-zero-to-hero-f6d558cea649
* https://cdn.hackaday.io/files/10879465447136/Mauve%20Paper%20Vitalik.pdf
* file:///C:/Users/herman.a.hellenes/Downloads/casper_economics_basic.pdf
* https://github.com/ethereum/research/blob/master/papers/casper-basics/casper_basics.pdf
* https://www.youtube.com/watch?time_continue=125&v=-oIYqV8q87s

# Introduction to Blockchain
* Here add from the book,  GLOBAL BLOCKCHAIN BENCHMARKING and Vitalik

## Consensus algorithm

## Smart contracts 
We can access a global computer! Cool; but why should we care?

## Private / premissioned Blockchains

# What problem does Blockchain / DLT solve for businesses?
Conclude if Blockchain, DLT, is suited, and why! Corda, Hyperledger


# Introducing Ethereum and Solidity - book notes
Blockchain is a combination of three technologies
* P2P networking: A group of computers can communicate among themselves without relying on a single central authority and therefore not presenting a single point of failure (like BitTorrent)
* Assymetric cryptography. This allows computers to send a message encrypted for spesific recipients such that anyone can verify the sender's authencitym but only indended recipients can read the message contents. In Ethereum and Bitcoins, asymmetric cryptography is used to create a set of credentials for your account, to ensure that only you can transfer your tokens. HERMAN: the latter is right, but not sure if the former sentence is true...
* Cryptographic hashing. A way to generate a small, unique "fingerprint" for any data, allowing quick comparison of large datasets and a secure way to verify that data has not been altered. In Bitcoin and Ethereum, the Merkle tree data structure is used to record the canonical order of transactions, which is then hased into a "fingerprint" that serves as a basis of comparison for computers on the network, and around which they can quickly synchronize.

# Blockchain for business
The security promises of distributed ledgers and private blockchains are only as good as the honesty of the entities validating the transactions. There are no mathematical guarantees behind the irreversibility of transactions in a private blockchain. 

Traditional databases are completely contained within one entity, irrespective of their structure (SQL or no-SQL type databases). This includes read and write access, which is only possible via applications controlled by the entity to which the database belongs [9]. Shared databases, on the other hand, involve read and write access involving multiple entities.

Private blockchains mimic the security process utilized by public blockchains like Bitcoin, but do not involve mathematical guarantees at the validation level or with respect to irreversibility.

At the end of the day, private blockchains provide higher levels of error checking and transaction validity than regular shared databases.

Even though they don’t use proof of work, blocks of transactions are validated using some other forms of consensus mechanism. This can still be chosen to be Byzantine Fault Tolerant (BFT).

The most popular such algorithms include Raft [7] and Juno [8]. These consensus protocols work based on a leader-follower model, wherein for each block a leader is selected who creates the block and adds to the blockchain. There are various ways in which errors and anomalies are then corrected by the system.

(https://medium.com/blockchain-review/private-blockchain-or-database-whats-the-difference-523e7d42edc)
## When NOT to use Blockchain 
Blockchain is not needed when there is no business network:  the existence of a business network is the mandatory test for a blockchain use case.  Quite simply, with no business network means blockchain is an overkill, and probably a distributed database would be a more appropriate (and more mature) solution. (https://www.ibm.com/blogs/insights-on-business/government/ten-things-blockchain-not/)

## Critique
https://freedom-to-tinker.com/2015/09/18/private-blockchain-is-just-a-confusing-name-for-a-shared-database/






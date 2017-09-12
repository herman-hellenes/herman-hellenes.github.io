---
layout: post
title: "Blockchain Resources"
date: 2017-09-11
---

Hey there you beautiful ladies and gentlemen, señoras y señores, damen und herren, 女士们(們) 先生们(們 ! Hope you have a great day. 
I will here just temporarily store my resources on Blockchain. Perhaps I will write my code here at Github too.. Lets see!


### EY
* [Better-working
insurance: moving
blockchain from
concept to reality](http://www.ey.com/Publication/vwLUAssets/ey-better-working-insurance-moving-blockchain-from-concept-to-reality/$FILE/ey-better-working-insurance-moving-blockchain-from-concept-to-reality.pdf). 20-week proof-of-concept project with EY, Guardtime and Maersk. A working blockchain platform that connects every major stakeholder in the insurance value chain. 
  * Challenge: It can
complicate risks in a number of areas. This is because
multiple parties in multiple jurisdictions – from ship
and cargo owners to surveyors and port authorities –
must align around a single insurance contract.
  * Challenge: The great strength of blockchain – its ability to create
a single version of the truth – could also become a
source of systemic risk, if truth becomes falsehood.
There must be clear controls around what data
organizations are storing and what data participants
have permission to use.



* [Blockchain Implications for the insurance industry](http://www.ey.com/Publication/vwLUAssets/EY-blockchain-technology-as-a-platform-for-digitization/$FILE/EY-blockchain-technology-as-a-platform-for-digitization.pdf). Good for understanding and discussing possible use-cases. Not proper projects
  * If we imagine a commercial fire equivalent where a photograph is used as evidence of the cause of the fire, the
blockchain ledger can be used to provide chain of custody for all the evidence related to a single loss event.
Each request is returned a keyless signature which allows a third party to verify the transaction properties (time, identity,
integrity) of the data using the blockchain as a reference.
The keyless signature enables the individual properties and attributes of each transaction (including claims) to be verified
without reliance on trusted parties and manual intervention. There are no keys to be compromised or to revoke; just
mathematical proof of signing time, origin and integrity of the transaction. This, in turn, makes the electronic data tamper
evident and verifiable by anyone, helping to ensure that the historical provenance of the claim can be preserved.




* [Blockchain in insurance: applications and pursuing a path to adoption](http://www.ey.com/Publication/vwLUAssets/EY-blockhain-in-insurance/$FILE/EY-blockhain-in-insurance.pdf). Same as article above, just a bit shorter. Nice to check out anyway. 


* [Blockchain in insurance: applications and pursuing a path to adoption](http://www.ey.com/Publication/vwLUAssets/EY-blockhain-in-insurance/$FILE/EY-blockhain-in-insurance.pdf). Same as article above. Nice to check out anyway. 














### Cool companies

* [Storing data with filecoin](https://filecoin.io/). Raising more than $257M, it is the largest closed token sale so far this year,





![center](/figs/2017-09-11-Blockchain-resources/ICOs-vs-VCs.png)


### Use-cases
* Get a "prediction" platform for trading forwards, futures, whatever derivatives and bonds. Banks can join the platform easily, can do this as an addition to the normal way of doing it.  
  * https://gnosis.pm/ - Use as layer? Hm... Yeah I would think! If this is open source, or could make something "on top of it". OR, just go straight on Etherium 
  * [The National Bank of Belarus to Use Blockchain for Security Bonds Ledger](http://forklog.net/the-national-bank-of-belarus-to-use-blockchain-for-security-bonds-ledger/)
  * [/blockchain-bonds-prepare-for-launch/](http://www.ifre.com/blockchain-bonds-prepare-for-launch/21286417.fullarticle): https://www.blockex.com/. Possible COMPETITOR!!! http://www.ifre.com/blockchain-bonds-prepare-for-launch/21286417.fullarticle (LES HELE DENNE ARTIKLEN)
  * http://www.afr.com/technology/cba-puts-government-bonds-on-a-blockchain-20170123-gtx1ff
  * https://www.thetradenews.com/Asset-Classes/Fixed-income/SGX-to-use-blockchain-for-bond-trading/
  * https://www.coindesk.com/start-hedging-ledgerx-begin-trading-cryptocurrency-derivatives/
  * https://www.coindesk.com/11-trillion-bet-dtcc-clear-derivatives-blockchain-tech/
  * https://www.finextra.com/blogposting/13656/blockchain-and-derivatives-reimagining-the-industry
  * https://news.law.fordham.edu/jcfl/2017/06/23/off-the-chain-a-guide-to-blockchain-derivatives-markets-and-the-implications-on-systemic-risk/
  * https://www.cnbc.com/2016/04/19/barclays-used-blockchain-tech-to-trade-derivatives.html
  * https://www.euromoney.com/article/b12khnth6bgsmv/dtcc-puts-blockchain-at-heart-of-$11-trillion-credit-derivatives-market
  * https://medium.com/@vishakh/a-deeper-look-into-a-financial-derivative-on-the-ethereum-blockchain-47497bd64744
  * https://github.com/vishakh/blockinstruments
  * https://ledgerx.com/category/education/
  * https://augur.net/
  * https://www.cyberscoop.com/dtcc-blockchain-ibm-bank-setttlement-hyperledger/
  * https://www.coindesk.com/world-bank-to-support-blockchain-bonds-trial-in-kenya/
  * http://smartbonds.co/
  * http://www.reuters.com/article/banking-blockchain-bonds/forty-big-banks-test-blockchain-based-bond-trading-system-idUSL8N16A30H
  * https://www.hyperledger.org/


* Og: typ bare selge stocks (og alle mulig derivater og bonds) til VANLIGE stock exchange selskaper. OG egentlig alle selskaper som vil dit. SÅ kan gjøre IPO typ gratis. Uregulert kan kjøpe og selge alle selskaper. Trenger ingen middle man, bare lager noen gode kontrakter på exchangen... HEHE RÅTT.
* Tinglysning - mortgage - state - location - registered - govermental fees - etc etc. EVERYTHING that has to do with real estate and land property. Linked together, so know who owns it, who has to pay etc etc.
* Car register and rental - who owns which car, bought it from who, insurance, etc etc. Very good case for insurance - can "see" some history of the car. 
* Accounting -> kan disrupte hele greia....



### Technologies
So we have different platforms we can use. Most well known are Etherium, Hyperledger Fabric and R3 Corda. They all have their pros and cons, as well as different scope and use-cases.

This article is brilliant for comparing the three, [here](https://medium.com/@philippsandner/comparison-of-ethereum-hyperledger-fabric-and-corda-21c1bb9442f6). Takeaway:  
    * Difference in contracts: It becomes clear that Corda was explicitly designed to account for the highly regulated environment of the financial services industry. Both Fabric and Ethereum lack this feature, no Ricardian Contract there.
    * Difference in currency: Fabric and Corda do not require a build-in cryptocurrency as consensus is not reached via mining. With Fabric, however, it is possible to develop a native currency or a digital token with chaincode.[xvi] With Corda, a creation of digital currencies or tokens is not intended
    * Ethereum’s permissionless mode of operation and its total transparency comes at the cost of performance scalability and privacy. Ethereum’s powerful smart contracts engine makes it a generic platform for literally any kind of application. 
    * Corda is located at the other end. It has been consciously designed as DLT for the financial services industry. Most notably, it takes the highly regulated environment into account by augmenting smart contracts with legal prose.
 
An additional article on Corda, found [here](https://www.gtreview.com/magazine/volume-15issue-3/r3s-corda-uncovered-not-blockchain/). Bit more critic than the one above
* I’m perplexed about what it is. My take is, with some discussion with other people in the industry, that R3 is trying to market Corda as a ledger. I don’t think it’s a ledger. It is a business-to-business messaging protocol that is inspired by bitcoin,” Zaki Manian, co-founder at blockchain-based supply chain ﬁnance company Skuchain, tells GTR. “You have systems for exchanging purchase orders and other information between businesses – they already exist. For example, Swift. What a lot of the experimentation in the blockchain industry has been about is how to run a blockchain system to the side, or on top, of these systems so that they can have stronger properties of data consistency and authentication. That’s been the goal.”


### How to actually code this stuff

* [From Etherium](https://blog.ethereum.org/2016/07/12/build-server-less-applications-mist/). This text is intended at those who have a basic understanding of web technology and how to build a simple javascript and html app, and want to convert these skills into building apps for the Ethereum ecosystem.
* [Getting Started as an Ethereum Web Developer](https://hackernoon.com/getting-started-as-an-ethereum-web-developer-9a2a4ab47baf). Very nice tutorial from crazy Grid+ guy. Also added his [Git repo](https://github.com/alex-miller-0/eth-dev-101) to test this stuff.

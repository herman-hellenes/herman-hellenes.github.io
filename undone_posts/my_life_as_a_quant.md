---
layout: post
title: "My Life As a Quant - Reflections on Physics and Finance by Emanuel Derman"
date: 2018-01-4
comments: true
---

Emanuel Derman is one of the big gurus within Quantitative Finance, both as a practitioner and an academic. Perhaps he is most well know for 
the Black-Derman-Toy model, developed at Goldman Sachs, an important contribution in the world of fixed income instruments. The book however, 
is as the title suggests, a biography centered around Derman's work in finance and a prior physisist. For those of us having the similar 
shift of career, this book is indeed very relatable. Perhaps too much to be honest. It is a bit uninspiring to read pages up and down 
of his hours in the office, on my spare time. That being said, there are some interesting sections that I will highlight here.

##Notes

Derivatives are more intricate than unvarnshed stocks or bonds. Then why do they exist? Because derivatives allow clients such as 
investment banks, money managers, corporations, investors, and speculators to tailor and fine-tune the risk they want to assume or avoid.
An investor who simply buys a share of IBM takes on all the risk of owning it; its value waxes and wanes in direct proportion to IBM's
share price. In contrast, an IBM call option provides potentially unlimited gain (as the share price rises above 100 dollar) but onley limited loss 
(you lose nothing but the cost of the option as the stock price drops below 100 dollars). This asymmetry between upside gain and downside loss is the 
defining characteristic of derivatives.

Dealers are analogous to insurance companies, who are also in the business of managin risk. Just as Allstate must allow for the possibility 
that your house will burn down after they sell you an insurance contract, so an options dealer must take a chance of a rise in the IBM's
stock price when he or she sells you a call option on IBM. Neither Allstate nor the options dealer wants to go broke if the insured-against
scenario comes to pass. Because neither Allstate nor the dealer can foretell the future, they both charge a premium for taking on the risks
that their clients want to aviod.

Allstate's risk strategy is to charge each client a premium such that the total sum they recieve exceeds the estimated clains they will be 
obligated to pay for future conflagrations. An option dealer's risk strategy is different. In an ideal world, he or she would simply
offset the risk that IBM's price will rise bt buying an IBM option similar to the one he or she sold, from someone else and at a 
cheaper price, thereby making a profit. Unfortunately, this is rarely possible. So instead, the dealer *manifactures* a similar option.
This is where the Black-Scholes model enters the picture.

The Black-Sholes model tells us, almost miraculously, how to manifacture an option out of the underlying stock and provides an estimate
of how much it costs us to do so. You hold cash and stock, and it requires that you constant adjust the mixture as the stock price changes.
The Black-Scholes equation tell you that, and its solutions tells the cost of doing this. Thus dealers construct options for their
clients by shares they buy in the market and adjust the mix. Conversely, they can deconstruct an option someone else sells to them by
converting it back into shares of raw stock that they then sell to the market. In this way, dealers mitigate their risk. (Since the Black-Scholes
model is only a model, and since no model in finance is 100 percent correct, it is impossible for them to entirely cancelt their risk.). 
Dealers charge a fee (the option premium) for this construction and deconstruction, just as chefs at fancy restaurants charge you
not only for the raw ingredients but also for the recipes and skills they use.




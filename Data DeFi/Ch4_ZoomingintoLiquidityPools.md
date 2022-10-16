## Zooming into Liquidity Pools

Liquidity pools are at the core of the Ocean Market and allow for automated price discovery of datasets and data services. But how do they work? Let’s dive in.

# The Liquidity Challenge
In traditional financial markets or at your favorite crypto exchange, transactions are based on an order book. To buy a token at a given price,
there must be a seller on the other side willing to match that exact same price. While this mechanism works well when token supply and demand are
high (liquid market), it shows its limitation when supply and demand are low (illiquid market).

# Enter Automated Market Makers (AMMs) and Liquidity Pools
AMMs are a key element of DeFi decentralized exchanges and are like robots that are always ready to buy or sell. At their core,
AMMs are based on smart contracts where a pair of ERC-20 tokens get locked in a liquidity pool. When a user wants to buy or sell their token,
they do not need to wait on a counterparty anymore, the AMM will take their token and swap it for the other token automatically.
The price is dynamically calculated based on a pre-defined ratio between token A and B which has to remain constant.

# Feeding the Liquidity Pools
For AMMs to work, liquidity pools must have some amount of tokens, and that is where liquidity providers (LPs) come into play.
LPs are users which provide their tokens in the pool and can be viewed as shareholders or partners that bought shares of your dataset or service.
In exchange for providing liquidity, they earn a share of transaction fees when:

- traders swap tokens
- buyers consume the data and pay for this consumption
- liquidity providers add or remove tokens from the pool

## Visual of Liquidity Pool Mechanics

![image](https://user-images.githubusercontent.com/110959584/196022233-2e2ac172-9ddb-4b51-833a-b85077e5bed8.png)

(1) Pool initialization. A liquidity pool allows users to swap their tokens. At creation, a pool needs to be initialized with the following parameters:

a ratio between token A and B
an initial amount of liquidity
a transaction fee
Then, as users (including LPs) interact with the liquidity pool, the AMM will strive to maintain the ratio by making sure that the product of the
quantities of the 2 supplied tokens always remains the same.

(2) Token swaps. When users swap their tokens, they influence the price of the tokens within the pool.For example, swapping token A for token B
will reduce token A supply and increase the amount of token B in the pool. This results in an increase of the price of token A and a decrease in the
price of token B. In short, the price of token A and token B is automatically re-calculated. In addition, the pool will also charge a small
transaction fee to the users and distribute it to LPs.

(3) Swap fees. To ensure that AMMs liquidity pools have enough tokens to trade with users, LPs are incentivized to lock-in their tokens in the
pool by receiving transaction fees in exchange. Typical liquidity pools implementations (Uniswap, Curve), require LP to provide liquidity in two
tokens according to the pre-defined ratio.

## Visual of OCEAN<>datatoken AMM Pool Mechanics

![image](https://user-images.githubusercontent.com/110959584/196022178-52b414e9-3fb5-4613-a57f-57e53599c8d1.png)

The liquidity pools implementation in Ocean Protocol differs slightly from implementations mentioned earlier. Ocean Protocol uses a technology
stack (Balancer) which makes it possible to provide liquidity in only one token rather than two. In addition, the OCEAN<>datatoken AMM
pool has a fixed ratio of 70% OCEAN and 30% datatoken.
Let’s use an example to illustrate this new concept.

(1) Publishing a dataset. A data publisher has chosen dynamic pricing when selling their dataset. They set a transaction fee and provide an initial amount of OCEAN.

(2) Minting datatokens. Behind the scenes, an OCEAN<>datatoken pool is created with a 70/30 ratio. Because this ratio has to be maintained, the pool will
mint datatokens out of the total OCEAN initially provided. At this stage, the data publisher owns all shares in the pool (they own all tokens).

(3) Consuming data. A consumer interested in the dataset will pay with their OCEAN. In exchange, they will get a datatoken which they can redeem to get
access to the underlying dataset.

(4) Investing in data. If a liquidity provider believes that datasets are undervalued, they can decide to invest in the dataset in 2 ways:

- Staking: This a key benefit of providing liquidity as LPs will have the opportunity to earn fees from pool transactions.
- LPs provide OCEAN and behind the scenes, the AMM will convert some OCEAN to datatokens and split the total pool shares between the pool owner and the LPs.

Swapping: LPs can choose to add OCEAN to the pool while an equivalent amount in datatokens is withdrawn and stored in their Web3 wallet.
We will discuss this concept in more detail in later chapters.

## Datatoken Price and Market Operations
The type of operations performed against the liquidity pool will affect the price of the datatoken as the AMM will automatically adjust the
price (up or down) to keep the target ratio of 70/30.
To recap:
- staking (adding) OCEAN tokens increases the datatoken price
- unstaking (removing) OCEAN tokens decreases the datatoken price
- minting datatokens (adding datatokens) decreases the datatoken price
- swapping datatokens increases the datatoken price

## Liquidity Provision for Datatokens Provides Signaling on Data Quality
Dynamic pricing serves as a curation signal. LPs are incentivized to stake in pools where they can earn the most transaction fees, earned from any transaction within the pool (e.g.: buying a datatoken, staking/un-staking, swapping OCEAN for datatokens). Knowing this, LPs will direct their liquidity investments towards high quality but undervalued datasets. By locking their OCEAN, LPs are essentially signaling that they believe in the quality of the data. 
Over time, lower quality datasets will have low liquidity, while datasets of higher quality will have high liquidity, and thus visibility.

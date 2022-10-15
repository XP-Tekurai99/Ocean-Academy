# Chapter 3: Creation of a Datatoken on Ocean Market

Creating a datatoken is much easier than one may think. In fact, data publishers may be using one even if it is not made explicit to them
(e.g. in the case of fixed data pricing, where the datatoken is abstracted away), as monetizing a dataset in the Ocean ecosystem will always require a datatoken.

The entire tooling is provided by Ocean Market, making it straightforward for anyone to deploy their own datatoken. Optimizing one’s datatoken is, however,
more challenging, as we will see.

Data publishers creating a datatoken should consider the following before getting started:

- Metadata and tags
- Data availability and access
- Revenue model: Fixed pricing vs. Dynamic pricing
- Dynamic pricing
  - Starting price, or minimum price
  - Amount locked by datatoken creator in liquidity pool
  - Swap fee
- Testing before deploying

# Metadata Helps Potential Buyers Find Your Dataset
The more complete you make the description and specifications of your dataset, the more likely potential buyers will find the data, and eventually buy it.
Ocean Market enables markdown language to make your description look great, and a preview is provided if need be (markdown cheatsheet).
Markdown allows to add style and pictures to make it look professional; this is an important signal of quality for the dataset.


# Make Your Data Accessible.
The data should be accessible through a URL. Files can be hosted anywhere as long as no extra authentication
is needed on the host platform; it could be on AWS, Google Drive, IPFS, your own website, etc. The data is never stored on the blockchain,
only the metadata and the encrypted URL are. As you can see in this example of token creation, no personally identifiable information is stored on the blockchain

In addition to the full dataset, it is strongly encouraged to provide a separate URL pointing to sample data, so that anyone can preview the
data and its structure before making a purchase decision. Watch-out: the URL provided can not be changed later on, so you need to get it right if
you ever want to update your data in the future.

In its current form, only direct data download is deployed on Ocean Protocol, but there will be an opportunity to opt for Compute-to-data when this
is implemented in the Ocean Market (a refresher is available in Ocean 101 chapters 17 and 20).

A timeout can be set, which represents the amount of time the access is valid for, once the data was purchased.

This allows different revenue models: for example, one may create a yearly timeout and update the data provided in the link on a fixed frequency (e.g. daily),
which would replicate a yearly subscription in the Web2 world.
If the access should not be revoked before the data was downloaded, this field should be left to forever.
Get a cool name for the datatoken that you will be creating. It is generated randomly by combining an adjective, a sea creature name and a number.

Tags will help prospective buyers find relevant datasets. Just like with metadata, making good quality tags can make a difference. Add the author name in the field.


Once you have filled-in the entire page and signed the Terms & Conditions, you are ready to create your datatoken. Connect your Web3 wallet and submit,
you will need to approve some operations with your wallet as Ocean smart contracts are deploying your datatoken to Ethereum.


# Now, You can Choose Your Revenue Model.
Just click on “Create Pricing” for the last step of your dataset deployment on the Ocean Marketplace.

Ocean Protocol supports many ways to sell data and data services; anyone can create their own smart contract to interact with Ocean Protocol.

In the Ocean Market, two ways of selling data have been programmed:

Fixed pricing. You set your price for the data in OCEAN. Ocean Market creates a datatoken in the background with a value equal to the dataset
price in OCEAN so that buyers do not have to even know about the datatoken. They pay the amount specified in OCEAN for access.

Dynamic pricing. You let the market define the price with a mechanism derived from Decentralized Finance (DeFi) with liquidity pools.
While you set a base price for the token in OCEAN, the market will organically discover the right price for your data. This can be extremely handy when the
value of the data is not known.

Behind the scenes, a decentralized automated market maker (AMM) is deployed for every dataset. The automated market maker is implemented using Balancer,
an AMM protocol used for price discovery, with the help of a liquidity pool that holds Ocean tokens and datatokens.

The benefit of such a pool is that it can be implemented on a smart contract to offer automated pricing of datasets. Hence, the pricing of datasets becomes
possible without maintenance: no need for a traditional order book or any other centralized component. It operates fully autonomously on the Ethereum Virtual Machine (EVM). This enables individuals and institutions to discover the price of their data through market forces, based on supply and demand. Furthermore the price of the data or data service can react to changes of the underlying asset in real time. If you improve the asset the price can rise immediately.

Selling data with dynamic pricing requires careful parameter choices.

Starting price: what one thinks would be the minimum price for the dataset. It can be totally off, as market forces will drive the price (upward) to an equilibrium.
Ocean token locked: the amount of OCEAN token that the data publisher needs to provide to the liquidity pool that is created. The higher the starting price for the
dataset, the more OCEAN has to be added by data sellers. This is to avoid abuses in Ocean Market. But locking more OCEAN tokens offers other advantages:
It makes liquidity pools larger and more stable, which makes the price for the dataset less volatile.
It ensures that there is enough datatoken supply in the market in the case that many buyers want to purchase your dataset.
Swap fee: the fee collected by the liquidity pool with each transaction. A low fee will encourage data usage but may lead to volatility due to quick speculation, a
high fee will encourage long term liquidity provision, as pool shareholders will be rewarded, but may artificially inflate the price of the dataset
(fees are added to the pool in OCEAN).

Once the token is created, the entire supply of the datatoken resides in the market. Users will have to buy the datatoken from the market in order to access the
data or data service.

You have it all now. Don’t forget to test your deployment on the Rinkeby network first just to be sure. You can ask for some OCEAN token from Ocean Protocol
faucet to that end. Note that the Token address for the Rinkeby Token is different from the mainnet address. In Rinkeby,
add 0x8967bcf84170c91b0d24d4302c2376283b0b3a07 as a custom token to your wallet.

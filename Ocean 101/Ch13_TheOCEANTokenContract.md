# Chapter 13: The OCEAN Token Contract

## Web3 Tools
A rich set of tools has been developed around the Ethereum ecosystem; developer tools like Remix IDE to write Smart Contracts,
libraries like Web3py to interact with the blockchain, apps like Etherscan to explore the blockchain.

## Exploring the OCEAN Token
Look for “OCEAN” on Etherscan and you will find the smart contract of the token.
In Ethereum, Smart Contracts use the same naming convention as wallet addresses; they are referred to by their '0x' 42 hexadecimal characters string.
Tokens on Ethereum are essentially a list of token holder balances that is tracked in the token Smart Contract.

![image](https://user-images.githubusercontent.com/110959584/194822972-952fcba0-5edd-4c27-84ae-34128ecac351.png)

Looking at the OCEAN token Smart Contract you can see that the OCEAN token uses the ERC20 standard.
This means that it is an ERC20 token, which is a widely used standard. The ERC20 token standard imposes a standard set of functions to
interact with it as well as standard naming conventions.

The Ethereum network does not enforce use of these standards, but most developers use them as they increase quality and speed up development.

## ERC Standards
ERC20 is just one standard for tokens, but standards are also available for name registries, library/package formats, and more.
These standards use ERC as a suffix, as they all started as Ethereum Request for Comments.
ERCs started as modification proposals by developers asking for feedback, got tested, and later adopted by the community.
These standards and libraries are open-source and well documented.

## Better User Experience
Because the OCEAN token is an ERC20 token, other apps and Smart Contracts know how to interact with it,
just like they do with other ERC20 tokens. This increases compatibility and enables cross-pollination; the OCEAN Token contributes to the Ethereum ecosystem,
and it benefits from the whole Ethereum ecosystem. Because the OCEAN token contract follows the ERC20 standard,
Etherscan is able to find the Smart Contract by searching for OCEAN. The user does not need to know the '0x' contract address.

## Transparency
Looking at the OCEAN token contract you can see how many addresses hold the token, and you can inspect every single transaction of the token.
You can also view the Smart Contract code under the Contract\Read Contract tab. This information is publicly written on the Ethereum blockchain,
Etherscan is only a tool to access that information which is enhanced with additional off-chain information.
If you do not like Etherscan you can simply switch to another Explorer or build your own; it's that simple.

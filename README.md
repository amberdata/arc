![ARClogoRGBko](https://github.com/amberdata/arc/assets/6354050/0ddbdd18-d340-453a-9ce4-509e1dbd51a3)

# ARC
Open Source Repository for Asset Reference & Classification Data

## What is ARC?

Asset Reference and Classification (ARC) is an institutional-grade security master database for digital assets that aims to provide a transparent and robust approach to the digital asset market to promote effective regulation, alignment, innovation, and risk mitigation. As the first open-source digital asset standard, ARC enables institutions to keep accurate records of highly dynamic digital assets across various dimensions. ARC contains reference and categorization details about a digital asset, such as asset names and addresses across blockchains, exchanges it trades on, spot and derivatives instruments of the asset, instrument contract specifications, and use cases.

## Statistics

| # of Assets | # of Instruments |
|-------------|------------------|
|        4000+|          100,000+|

### Quick Start

ARC is a **dataset** that is split across JSON files in this repository.

We recommend starting in the `packages/schemas` directory to understand the core entities that ARC captures and describes. As a reminder, ARC helps answer the what, where and how of an asset, specifically

1) `packages/schemas/asset.json` helps answer the question *what is the asset?*
2) `packages/schemas/instrument*.json` helps answer the questions *where and how does the asset transact?* i.e. on which exchange does asset *X* have spot instruments.

#### What is the Arc Id?

Each asset in ARC receives a unique identifier known as the Arc Id, which is assigned to the property `assetArcId`. This identifier helps one relate the asset to its associated instruments across the dataset.

The Arc Id is created and maintained by Amberdata and can support **17 trillion+** unique assets.

#### Classification Tags

When enough information exists about an asset, the asset is tagged with descriptors in the `classificationTags` property.

ARC's classification system is designed to meticulously deconstruct the offerings and functionalities of digital assets, empowering users to discern and comprehend their diverse use cases.

ARC adheres to the following principles concerning classification:

- Intuitive: The classifications in ARC reflect general market insight about a digital asset. The terminology used for classification attributes is designed to be easily recognizable and complement established industry norms.

- Usage Context: Digital assets are first classified according to their intended purpose and their underlying protocol, as denoted by the asset creators and the broadly observed behavior of the asset in various markets.

- Non-Hierarchical: Because digital assets can be utilized in ways that are related to or deviate from the intended purpose of the asset and its underlying protocol, ARC allows for flexible, non-hierarchical classification to capture more than the purported primary use case. Since there is no quantitative method to assert the dominant usage patterns of an asset, flexible classification that avoids a strict parent-child or tree-like approach enables an adaptive offering.

- Public Feedback: As ARC is an open-source dataset, feedback from the general public and interested parties will be incorporated to ensure that classification remains timely, accurate, and is not subject to biases.

The dataset currently supports the following tags, which can be **expanded** and **revised** over time

| Tag | Tag Description |
|-----|-----------------|
| Proof-of-Work | Assets that require validation of block transactions where miners are solving computationally expensive cryptographic problems |
| Proof-of-Stake | Assets that require validation of block transactions by participants who offer their holdings of said asset as collateral to validate transactions |
| Stablecoin | Assets that are intended to offer participants in the digital asset ecosystem access to blockchain applications and decentralized protocols without being exposed to volatile price action in digitally native tokens |
| Real World Asset | Assets that are an on-chain tokenized representation of off-chain assets and are pegged to the performance of the underlying off-chain asset |
| Machine Learning & AI |Assets native to protocols that facilitate model training, inference, predictions, and generative artificial intelligence |
| Gaming | Assets native to applications for blockchain-based gaming and their communities. Decentralized gaming applications often include a native token to incentivize players with monetary rewards based on their participation and success in the game |
| Metaverse | Assets native to applications and protocols associated with a loose network of virtual worlds where social connections and interactions are the primary function |
| Advertising | Assets native to applications that facilitate the tokenization of impressions for interacting with ads and marketing campaigns. These tokens correspond with the user’s viewership whereby they are rewarded in the token for their time and attention |
| Content & Streaming | Assets native to applications that support the creation and broadcasting of creative content, such as video, music, or art, and enable social interactions between users and communities. The networks are powered by the asset, allowing creators to communicate and distribute content autonomously |
| Staking | Assets native to decentralized applications that provide the user with yield for locking up their asset(s) to participate in the validation and securing of block transactions |
| Derivatives | Assets native to the operations of an application that facilitates the creation and transfer of derivatives (futures and options etc.) and synthetic assets. These assets are not derivatives themselves but rather enable trading access and liquidity to a derivative/synthetic product that is uniquely offered and distributed by the protocol |
| Liquidity Providers | Assets that represent a share of a user’s liquidity relative to other participants in a liquidity pool. Liquidity Pool, or LP, tokens allow holders to control their share of the underlying pool. These tokens can be redeemed for the underlying shares, exchanged and even used in other applications |
| Prediction Market | Assets native to decentralized applications that are used for speculative trading based on the outcome of future events. Prediction market protocols typically allow users to place bets on probabilities of certain events occurring |
| Yield | Assets native to applications where the primary goal is to generate interest income for users |
| Lending | Assets native to the operations of an automated market maker that primarily provides lending and borrowing services, enabling peer-to-peer loans via liquidity pools. Decentralized lending applications allow users to borrow or lend against other assets, while the other side of the transaction is held and collateralized by the native asset of the lending protocol or other assets in the liquidity pool |
| DEX | Assets native to the operations of an automated market maker for decentralized spot markets, enabling the peer-to-peer transfer of assets through liquidity pools |
| Smart Contract | Assets native to applications or blockchains that allow automatic execution of an agreement between two parties, when the conditions stipulated in the agreement are met. Smart contracts can be standardized or custom computer code that is deployed to the application or network |
| Blockchain Infrastructure | Assets native to applications and ecosystems focused on providing the infrastructure for blockchain networks to scale and be use-case specialized. These infrastructure solutions are colloquially also known as “Layer 0” and can also facilitate interoperability between so-called “app chains” |
| Layer-1 | Assets native to a blockchain in which the network can validate and finalize transactions on its own without another chain |
| Layer-2 | Assets native to a blockchain scaling solution focused on improving throughput, consistency, and cost incurred to process transactions relative to the underlying, parent blockchain. The scaling solution inherits the security of the parent blockchain, colloquially known as “Layer 1” and transactions must still be validated on the parent chain |
| Governance | Assets utilized to collaborate, vote and execute proposals that affect the operations of the applications or user activity |
| Oracles | Assets native to applications that deliver off-chain data to enrich on-chain use cases and products |
| Privacy | Assets native to applications or networks that offer privacy enhancements to facilitate the anonymous transfer of value for on-chain payments. Networks with privacy features can  allow users to self-select when their on-chain data will be publicly available, or encrypted as an unidentifiable and untraceable activity |
| Meme | Assets that are based on or derive value from memes, social commentary and community that supports, engages with and transacts on the asset |
| Remittance | Assets utilized for their velocity in the transfer of monetary value domestically and across borders for payments |
| Transparent | Asset whose blockchain network ledger displays the deposit addresses of both senders and receivers and may reveal wallet balances publicly |
| DeFi | Asset native to decentralized applications that provide the user with economic incentives, trading power, or an on-chain alternative to traditional financial services and products. These tokens often serve as the mechanism to engage with its financial application as well as the reward that is used to collateralize or compensate the user for the financial activity that the protocol offers |
| DePIN | Assets native to decentralized applications that enable the sharing, distribution and maintenance of physical infrastructure for a variety of applications including data storage, energy usage, sensors and wireless connectivity |

##### Classification Tag Limits

Tags are intended to be flexible but not infinite. Assets will have a **maximum of 5** tags to ensure relevancy and discoverability.

## License

ARC is published under the terms of the Apache 2.0 License.

## Roadmap

The following three items will be **perpetual goals** for ARC

1) Expand asset coverage
2) Expand instrument and exchange coverage
3) Expand and revise classification tags

Please check back here for additional details and news regarding the roadmap.

## Contributing

ARC is an open-source dataset and we welcome collaboration from the public to improve and expand this dataset to the benefit of all users interested in digital assets. For specific details on how to contribute, please refer to `CONTRIBUTION.md`.

## Maintainers
Brought to you by

![amberdata_logo_color](https://github.com/amberdata/arc/assets/6354050/12122c01-a588-443e-a869-5d6b7bea96dd)

### Dataset Updates & SLA

Amberdata will update ARC **at most once a day** and at **minimum once a week**. All new data to be added is verified by humans before publishing to this repository.

The once daily updates are published at 02:00 UTC. Amberdata reserves the right to change this publishing time in the future.

## Other Amberdata Products

### amberLens

![amberlens-logo](https://github.com/amberdata/arc/assets/6354050/a24289d5-3921-4a78-abab-bcd4ad542982)

[Checkout](https://intelligence.amberdata.com/) the leading analytics platform for on-chain data.

### AD Derivatives

[Checkout](https://pro.amberdata.io/) the leading digital assets derivatives platform.

### Amberdata API

[Checkout](https://docs.amberdata.io/) the leading institutional grade API for digital assets.
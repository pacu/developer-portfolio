### My journey as a Zcash Dev 

First I started as an iOS Developer contractor for ECC and then as a full-time iOS Engineer, where I built the iOS Zcash SDK (https://github.com/zcash/ZcashLightClientKit/) and the first ECC reference wallet using SwiftUI ([https://github.com/zcash/zcash-ios-wallet](https://github.com/zcash/zcash-ios-wallet)), shipped publicly as NightHawk Wallet by Nighthawk Apps.  I didn’t do this by myself. I had my ECC colleagues who helped me all the way. It is necessary to understand a lot of how Zcash works to effectively develop a mobile SDK that can be a “drop-in” kind of tool for developers around the world. This led me to have a good understanding of the Zcash light-client protocol, and “the protocol” itself. I worked back to back with Kevin Gorham, my Android counterpart, since I started the SDK as a “port” from the Android PoC which also let me actively contribute every now and then to that codebase as well. Later on I would have to onboard other great developers to our codebase. So I did end up learning a lot of Kotlin along the way. 

Wallets are an interdisciplinary work. Inevitably, I ended up picking up some Rust Lang skills which helped me be a more effective contributor all across the tech stack by contributing to the Rust backend: LibRustZcash ([https://github.com/zcash/librustzcash/pulls?q=is%3Apr+is%3Aclosed+author%3Apacu](https://github.com/zcash/librustzcash/pulls?q=is%3Apr+is%3Aclosed+author%3Apacu)). One of my most cherished PRs is this one that implements the principles of autoshielding; I had a great collaboration with ECC’s Core Team to guide me through this implementation which ended up being the backbone for “shielding by default” in our native mobile platforms ([https://github.com/zcash/librustzcash/pull/341](https://github.com/zcash/librustzcash/pull/341)). 

Security and Testing were always priorities for our team. Taylor Hornby and Larry Ruane co-created a set of RPCs in lightwalletd that let developers create a local ZIP-307 compliant synthetic compact blockchain and write integration tests that can reproduce blockchain edge cases. I kind of became the “darksidewalletd guy”. We called this suite “Darksidewalletd Tests” and their first implementation was carried out on ZcashLightClientKit ([https://github.com/zcash/ZcashLightClientKit/tree/main/Tests/DarksideTests](https://github.com/zcash/ZcashLightClientKit/tree/main/Tests/DarksideTests)). This helped our team to develop on solid grounds knowing that our SDK would react properly to chain re-orgs. Working on these tests also had me working a bit in Go Lang ([https://github.com/zcash/lightwalletd/pulls?q=is%3Apr+is%3Aclosed+author%3Apacu](https://github.com/zcash/lightwalletd/pulls?q=is%3Apr+is%3Aclosed+author%3Apacu)) when I caught bugs in Lightwalletd itself.

Going down memory lane, one of my earliest work in tandem with @earthrise was finding a safe native library for BIP-39 for the Swift programming language. We conducted a survey of existing implementations of BIP-39, forked the one that best suited our SWOT analysis and created MnemonicSwift. https://github.com/zcash-hackworks/MnemonicSwift and even got it listed in the Bitcoin wiki page. [https://en.bitcoin.it/wiki/BIP\_0039](https://en.bitcoin.it/wiki/BIP_0039)

### Building a Legacy

One of the goals I always had is to build a legacy. Projects that others can take over to the finish line. This entails setting up code conventions, contributing guidelines, abiding by industry standards, setting up coding guidelines, and more. Carter Jernigan and I worked hard on  
making that possible over the past year. The last wallet project I worked on at ECC is the  
Secant wallet. It has a lot of that. It is being actively developed by ECC and Nighthawk Apps in  
different forks. It was designed to be iterative, fast-paced, testable, rock-solid, and more  
importantly, end-user-facing. We aimed to base Secant on tech stacks that would be not only  
relevant in the present but also future-proof. We developed Secant in the open since day  
one. Anyone following the commits will be able to see its many iterations, different faces, and  
phases. Secant in its two forms, is actively built by great developers in two teams with different  
product plans and design approaches that will get ZEC into the hands of thousands and  
hopefully millions of users across the globe.

### Ecosystem Outreach work

One of the things I enjoyed a lot was working with the different teams on the Zcash Ecosystems. Whenever I was given a chance I tried to reach out to other teams to know about their work, and think about how I could make the SDK more useful to them. In May 2020, the wallet team co-hosted and also participated in the “Protect Privacy” Gitcoin hackathon ([https://bounties.gitcoin.co/hackathon/privacy/prizes/?org=zcash](https://bounties.gitcoin.co/hackathon/privacy/prizes/?org=zcash)). One of the teams participating ended up becoming the Nighthawk Apps team\! They had the bravery and the talent to take the ECC Reference Wallet down to the finish line to be launched at the Apple and Google Stores (and also Fdroid\!). Since then I’ve been collaborating very frequently with Nighthawk Apps and their team. Our work together, ended up creating the “Light-Client Working Group” or “Zcash Mobile Dev Calls” which have been held bi-weekly for quite some time now (see [https://github.com/zcash/lcwg](https://github.com/zcash/lcwg))

Another great partner and supporters of the Zcash cause are the folks at Unstoppable wallet. They have amazing multi-coin native applications for Android and iOS. It took me less than a day to draft a PoC integration to their iOS wallet. That is how modular their code is, pretty awesome. Obviously they took the baton and implemented the whole thing themselves and I helped occasionally as you can see in a few PRs ([https://github.com/horizontalsystems/unstoppable-wallet-ios/pulls?q=is%3Apr+author%3Apacu](https://github.com/horizontalsystems/unstoppable-wallet-ios/pulls?q=is%3Apr+author%3Apacu).

I had the chance to briefly work with Paul and the EDGE wallet team, but to be honest, they mostly did everything and I just provided some guidance and incorporated their feedback into our codebase. They are an awesome team and are fully committed to the values of financial privacy that Zcash embraces. I hope if I get this grant I can collaborate with them more.

One of my latest collaborations was with ZingoLabs, to bring darksidewalletd tests to their Zingo wallet by creating a PoC in Rust on how they could leverage this powerful tool ([https://github.com/zingolabs/zingolib/pulls?q=is%3Apr+is%3Aclosed+author%3Apacu](https://github.com/zingolabs/zingolib/pulls?q=is%3Apr+is%3Aclosed+author%3Apacu)). I use Zingo Lib for some personal projects of mine and for educational purposes when teaching in college. Zancas and team are very engaged with the whole idea of integration tests for wallets and it seems they plan to take it to the next level.

During the end of 2023 and Q1 of 2024 I’ve been actively involved in the Transparent-Source-Only Ecosystem Outreach also known as (Binance’s TEX addresses) collaborating with Binance, ECC, ZCG and Ywallet (Hahn) and reaching out and articulating efforts with the rest of wallets shielded and transparent-only wallets of the ecosystem 

### RFP and ZIP collaboration 

Like many other Zcash developers I contributed to ZIPs and RFPs of great relevance to the Ecosystem like [ZIP-317: Proportional Transfer Fee Mechanism](https://github.com/zcash/zips/blob/main/zip-0317.rst) or [ZIP-316: Unified Addresses and Unified Viewing Keys](https://zips.z.cash/zip-0316) and [ZIP-315: Best Practices for Wallet Handling of Multiple Pools](https://github.com/zcash/zips/pull/607). I also helped draft the [Zcash UniFFI Library RFP](https://forum.zcashcommunity.com/t/rfp-zcash-uniffi-library/41335)**,** reviewed [RFP \- Zcash Lightwalletd Infrastructure Development and Maintenance](https://forum.zcashcommunity.com/t/rfp-zcash-lightwalletd-infrastructure-development-and-maintenance/47080)

### Seminars and talks

Although these appearances were not a part of my job, I participated in many twitter spaces, conferences and podcasts related to Zcash and privacy. 

**Hello decentralization Conference**: In February 2021 I participated in a workshop session at “Hello Decentralization” where I did a “code along” session where attendees could build a Point of Sale proof of concept app with ZcashLightClientKit and Swift UI. The session was called “We accept Zcash\! building a PoS App with Zcash Viewing keys”. The site of the conference unfortunately is down. I could find this link ([https://www.crowdcast.io/e/hello-decentralization/register?navlinks=false\&embed=true](https://www.crowdcast.io/e/hello-decentralization/register?navlinks=false&embed=true)) and the repository with the code-along material can be found here ([https://github.com/zcash-hackworks/we-accept-zcash-ios](https://github.com/zcash-hackworks/we-accept-zcash-ios)). 

**Zcon3**: “The once and future ECC wallet”. In this talk we covered the past, current and future roadmap for ECC Wallet. 

**Zcon4:** 

- [Zcash wallet workshop](https://www.youtube.com/watch?v=mGV_d5IqDvk) with Adi from NightHawk and Joel Valenzuela from Digital Cash podcast  
- Presented speakers and forwarded questions from the audience to them in a few talks as well.

**Podcast Appearances**: “Hacia Afuera” podcast. A podcast about latin american professionals making great contributions from the region to all the world. Link: https://open.spotify.com/episode/5msJJcTCXrnpdV0P1xKvYJ

### **Research and Education**

Unrelated to blockchain but relevant to the tech stack we use here, I taught Introduction to Programming with C from 2009 to 2018 as an assistant professor in different private universities in Buenos Aires. 

Teaching gives people a unique experience where one can learn differently, because “those who teach learn twice”. I like creating documentation, presentations and classes that aim to be appealing and motivating to students.

Back in my undergrad college days I also worked in research and development and published different papers about soft computing and text mining. This helped me polish formal aspects of written English and also technical and scientific writing that definitely helped me grasp the protocol and all the ZIPs Zcash has. 

When I say that I’ve dedicated these last 4 years to Zcash and the privacy space, I really mean it. I graduated from the Software Engineering Master Degree program of the National University of La Plata with a Thesis that studied Privacy Coin mobile wallets and their architecture. I described a framework of software patterns based on reverse engineering requirement analysis of existing non-custodial privacy coin wallet applications. (link in Spanish) [https://doi.org/10.35537/10915/137845](https://doi.org/10.35537/10915/137845)

This work derived into a research paper on wallet software design patterns presented at the [Pattern Languages of Programs conference of 2022](https://hillside.net/plop/2022/) an early draft can be found [here](https://hillside.net/plop/2022/papers/G1_P3.pdf). According to conference chairs, the paper will be listed in the ACM Library soon. 

I’m currently also working as an Assistant Professor in the “Introduction to Blockchain” course at the Faculty of Informatics of the National University where I use tools such as Zingo-cli to explain how Zcash works. 

I’m currently overseeing and writing chapter 6 of **My First Zcash\!** Book which is about Zcash wallets in collaboration with other community members. 

### Zcash Wallet Community Developer

During Zcon4 I started a new journey in my career. I became a ZCG Grantee and was honored with the duty of working as a wallet developer for the Zcash ecosystem. Although some milestones seemed quite ambitious, I achieved all the proposed goals and presented my progress to ZCG synchronously in conference calls and t[hrough the forums to the whole community in this thread](https://forum.zcashcommunity.com/t/grant-updates-zcash-wallet-community-developer/45562/4).

A summary of the achievements:

#### **User Facing Development**

Although all milestones are thought in terms of how to make wallets better, there are some parts of being ZWCD that impact users more directly than others. 

##### **Native support for ZIP-321 Zcash Payment URIs for Android and iOS/MacOS**

I created two distinct Native **Swift** and **Kotlin** Libraries that:

- Generate Payment Request URIs for others to fulfill  
- Parse Payment Request URIs for wallets to fulfill  
- Are fully written in **Swift** or **Kotlin** with not external dependencies like rust or C bindings  
- Composable with other libraries like zcash-{swift|kotlin}-wallet-sdk  
- Has many unit tests and coverage  
- Added 1500 LoCs of Features and Tests to each one of them  
- The libraries are Open Source with MIT license here::   
  - https://github.com/pacu/zcash-kotlin-payment-uri  
  - https://github.com/pacu/zcash-swift-payment-uri/  
- Contributed to find weak points in the ZIP-321 definition and add improvements to its specification.  
  - see [https://github.com/zcash/zips/issues/451](https://github.com/zcash/zips/issues/451)

Remarks:

- The Kotlin variant is a really good candidate to be turned into Kotlin multi-platform supporting javascript and even iOS for kotlin multi platform wallets\!  
- Found a nasty bug in Swift Compiler on Decimal handling. :/ which is, following their tradition, completely known and ignored by Apple 

#### **Developer Tooling**

**FROST UniFFI SDK for GoLang, Swift (and potentially other languages)**  
This SDK wraps FROST 1.0.0 with  UniFFI to user Randomized FROST Reddsa (orchard) with other languages that are not Rust Lang. This is important for getting FROST to other platforms such as infrastructure (lots of Infra in crypto uses GoLang), and Mobile (Swift and Kotlin).   
URL: [https://github.com/pacu/frost-uniffi-sdk](https://github.com/pacu/frost-uniffi-sdk)

**General Purpose, Reusable Darksidewalletd Datasets:**  
“Darksidewalletd” is a development tool that lets developers create synthetic compact blockchains. These blockchains are totally controlled by the devs and can be shaped specifically to exercise specific scenarios for the wallets, such as chain reorgs that can cause transactions being unmined, tx reverted and all sorts for state changes that the wallets need to adjust to in order to keep the users’ funds spendable. I worked with Zingo Labs to ideate and create test scenarios that can help wallet developers benchmark, test and bugfix their wallets. These scenarios are not set in stone. Each one of them has scripts that can be ran to modify them and update them as needed, they can evolve as the protocol evolves.  [https://github.com/zingolabs/darksidewalletd-datasets](https://github.com/zingolabs/darksidewalletd-datasets)

- [151 coinbases](https://github.com/zingolabs/darksidewalletd-datasets/tree/dev/151-coinbases):  This is a darksidewalletd dataset composed of 151 blocks of 1 transparent coinbase to the legacy t-address of zcashd and 150 shielded coinbases to sapling address.  
- [SECOND FLUSH OF ENTHUSIASM](https://github.com/zingolabs/darksidewalletd-datasets/blob/dev/sfoe/README.md): A user gets onboarded into ZEC at a given time (block 1\) and creates a wallet. User forgets about it until a later time it realizes it can accept a Zcash payment instead of fiat, so User intends to receive ZEC.  
- [Advanced ReOrg Tests](https://github.com/zingolabs/darksidewalletd-datasets/blob/dev/advanced-reorg-tests/README.md): This is a set of tests originated as part of integration testing of the [ECC Mobile SDKs](https://github.com/zcash/ZcashLightClientKit/blob/main/Tests/DarksideTests/AdvancedReOrgTests.swift)

**Python API to interact with Zcash node RPCs:**

Part of this work ended up in creating python scripts that could use Zcashd RPCs to handle nodes in Regtest mode. As tests built up, this python starter to take the shape of an API which is expressed in [this python file.](https://github.com/zingolabs/darksidewalletd-datasets/blob/dev/advanced-reorg-tests/Scripts/zcash_rpc.py) 

**Advanced Re Org Test implementation on Zingo-lib**

Zingo Viridians took the darksidewalletd work I had done and took it even further, grouping all the implemented test cases into a rust crate[https://github.com/zingolabs/zingolib/tree/dev/darkside-tests](https://github.com/zingolabs/zingolib/tree/dev/darkside-tests) . 

**Bringing Supporting Regtest/LocalNetwork testing back to Mobile SDKs**

Originally, the mobile SDKs had a suite of tests that allowed us to have a “canary” that would warn developers of regressions when changes were introduced into the codebase, mostly around chain re-orgs and the consistency of the internal state of the wallet SDKs. Due to various types of resource constraints these tests stopped working and were left unmaintained when Spend Before Sync. Given their importance it is one of my goals to bring them back to the place they deserve. It was originally intended to “just enable them back”, but given the experience we gained in the Zingo Lib integration, it was recognized as more beneficial to actually get them to work fully on a the new datasets that were not reliant on mainnet, because the original darksidewalletd tests would only prove that the wallet synced properly sapling blocks of version 4 transactions. This is a more ambitious effort that goes across many repositories and layers of the wallet stack. These changes are still in-flight but yet bring enhancements on their own, like the ability of providing custom checkpoints. 

This is an extract of the last forum update for milestone 5\.

| task | link |
| :---- | :---- |
| CI enhancements for Swift SDK | [https://github.com/zcash/lightwalletd/issues/464](https://github.com/zcash/lightwalletd/issues/464) |
| Librustzcash regtest support (ongoing) | https://github.com/zcash/librustzcash/pull/1054 |
| Custom Checkpoints for Regtest modeOn Zcash Swift SDK | https://github.com/Electric-Coin-Company/zcash-swift-wallet-sdk/pull/1331 |
| Support for Spend Before Sync on  Darksidewallet | https://github.com/zcash/lightwalletd/pull/468/ |

#### **Light Client Working Group**

With great support of @decentralistdan we held 13 meetings of the Light Client Working Group, a venue that gathers Wallet developers together to share their work and tackle problems specific to the Zcash wallet ecosystem, you can see all the notes in [this repository](https://github.com/zcash/lcwg)

**The Reboot**  
LCWG had lost most of its momentum, so we decided it was time for a fresh start. @aquietinvestor, @decentralistdan and I brainstormed a new format to bring the excitement back. We organized the working group in a way that it would reduce the amount of “status updates” and focus on *Work initiatives*. We identified three initiatives we wanted to work on and people volunteered to lead each one of those, while teams would have to commit some resources to carrying them forward:

- LCWG working Initiatives:  
  - ZIP-315 support on the wide wallet ecosystem  
    - Appointed Lead: Pacu (ZWCD)  
    - ZIP-317 Implementation across the ecosystem  
      - Appointed Lead: DecentralistDan (ZF)  
    - Decentralize Core Development, Zcashd, lightwalletd and other tooling  
      - Appointed Lead: Zancas (Zingo Labs)

#### **Code Reviews and small contributions:**

Over the course of the last grant I’ve reviewed almost thirty pull requests from many teams like NightHawk Apps, Zingo Labs and ECC. Most of them were requested directly and others were ad-hoc. I watch many of the core repositories of the Zcash ecosystem and I get PRs and activity feeds in my inbox. Every day I “get to work” I go through my notifications to see what I’ve missed (ZEC has many night owl contributors\!) and things I consider worthy of ZWCD’s attention I’d review and comment if needed. 

#### **Tutorials**

Created a tutorial on [how to run zcashd in regtest mode](https://free2z.cash/pacu/zpage/running-a-zcashd-regtest-node-with-docker) using docker. This info was outdated and scattered around several places, now it’s updated and in a single location.

#### **Community and Ecosystem Activities:**

##### User support

The community part of the grant title was also endured. During the last grant period I worked with other community members to help them in certain circumstances that troubled them. Such as outages in ZecWallet Lite, users having issues with wallets not syncing among others. I have to give a massive shout out to @autotunafish from ZF for being present for every user needing help.

##### Office Hours

Another side of the ZWCD was this concept of office hours where I allocated a fixed amount of hours to meet people that wanted to get some help, assessment or counseling from someone from the Zcash development ecosystem. This kind of thing is often done by “Dev Rel” people in other development ecosystems. 

* **RedDev \<\> ZCWD:** We went over some overall concepts of the ZAVAX bridge. His team is working on implementing the Zcash \<\> AVAX bridge in a similar way the BTC \<\> AVAX bridge was done for V1 and then iterating to build up a more seamless experience for the user. We met recurrently over several weeks brainstorming and revisiting the proposed designed that were recently presented to ZCG as detailed on their last [forum update](https://forum.zcashcommunity.com/t/zcash-elastic-subnet-bridge-on-avalanche/44220/53)  
* **Chainsafe \<\> ZCWD:** Met with Chainsafe Team reps to go over various topics and doubts on their Zcash SDK proposal we channeled their inquiries through the Light Client Working Group and resulted in them presenting a grant for a [Javascript Zcash SDK](https://forum.zcashcommunity.com/t/zcash-sdk-implementation-js-ts-proposal/46158)  
* **My First Zcash:** wrote chapter 6 of the book which is about crypto and Zcash wallets, exchanges, CEXs and DEXs. Also designed exercises for readers to do in order to learn by doing. 
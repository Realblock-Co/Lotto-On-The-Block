# Lotto On The Block - Ethereum powered blockchain lottery

[![N|Solid](https://github.com/cryptolotto/Cryptolotto/blob/master/images/Powered%20by%20ETH.png?raw=true)](https://www.ethereum.org) [![N|Solid](https://github.com/cryptolotto/Cryptolotto/blob/master/images/Play%20Cryptolotto.png?raw=true)](https://cryptolotto.cc)

Lotto On The Block is a blockchain-based, Ethereum powered lottery, which gives to users the most transparent and honest chances of winning.

![Cryptolotto_banner](https://github.com/Cryptolotto/Cryptolotto/blob/master/images/Bitcointalk%20banner.png?raw=true)
# Table of Contents
1. [Overview](#overview)
2. [List of games](#list-of-games)
3. [How to play](#how-to-play)
4. [Explainer video](#explainer-video)
5. [The algorithm of picking a winner](#the-algorithm-of-picking-a-winner)
6. [Features](#features)
7. [Frequently Asked Questions](#frequently-asked-questions)
8. [Contact Support](#contact-support)

# Overview
Lotto On The Block (LOTB) is a powered by Ethereum DApp (decentralized application). The backend code is running on a decentralized peer-to-peer network and is presented by 14 smart contracts and a front-end. Lotto On The Block (LOTB) works autonomously and with no entity controlling the key functions. The LOTB's data and records of operation are cryptographically stored in a public, decentralized Ethereum blockchain network.

The main idea of LOTB is straightforward: people from all over the world contribute equal amounts of ETH to one wallet during the set period of time. When a timer ends, this smart-contract powered wallet automatically sends all received ETH to one randomly chosen wallet-participant.

![Cryptolotto_demo](https://github.com/Cryptolotto/Cryptolotto/blob/master/images/Github%20demo.gif?raw=true)

# List of Games
| Name | Duration | Price |Contract Address |
| ------ | ------ | ------ | ------ |
| [7 days](https://www.cryptolotto.cc/en/7d) | 7 days | 0.01 ETH |[0x118f17f1c67bc53e6341de3f9b6112abf81505f0](https://etherscan.io/address/0x118f17f1c67bc53e6341de3f9b6112abf81505f0)|
| [1 day](https://www.cryptolotto.cc/en/1d) | 1 day | 0.02 ETH |[0x106302aa07955306c31b8e916a16500482016ec2](https://etherscan.io/address/0x106302aa07955306c31b8e916a16500482016ec2)|
| [6 hours](https://www.cryptolotto.cc/en/6h) | 6 hours | 0.03 ETH |[0x51f37f32cd84908f58eb2c5b7e141b61d5774f0a](https://etherscan.io/address/0x51f37f32cd84908f58eb2c5b7e141b61d5774f0a)|
| [1 hour](https://www.cryptolotto.cc/en/1h) | 1 hour | 0.05 ETH |[0x11320d0b29e59da6b1b08a85e9d689ec4ed42e6c](https://etherscan.io/address/0x11320d0b29e59da6b1b08a85e9d689ec4ed42e6c)|
| [10 minutes](https://www.cryptolotto.cc/en/10m)  | 10 minutes | 0.1 ETH |[0xcc208c28644d60fa0eae08c4b19521e27ebcddfa](https://etherscan.io/address/0xcc208c28644d60fa0eae08c4b19521e27ebcddfa)|


# How to play

Please watch our explainer video on [YouTube](https://www.youtube.com/watch?v=PyrtCXVUkTA). We hope it will clear all your questions.

  - **Use an Ethereum**. To start playing, you should have one of these wallets: [Ethereum Wallet](https://github.com/ethereum/mist/releases), [Parity Wallet](https://www.parity.io), [MyEtherWallet](https://www.myetherwallet.com) or [Metamask](https://metamask.io). Top up your wallet with enough amount of ETH first, before you start to play.
  - **Select your Game**. 5 games are running simultaneously. Each game has different duration and entrance cost. Entering the same one game more than once  is allowed. Also, you can join all games at the same time.
  - **Copy the wallet address**. Be sure to send your funds to the right wallet address. Each game has its own unique address presented on the [Home page](https://cryptolotto.cc) as well as on our official Github page.
  - **Send your funds**. Each game has its own price. To join the game, you need to send the right amount of ETH to the given address. If you get everything right, you will find your wallet address in the list of players.
  - **Wait for result**. Join our [Telegram channel](https://t.me/cryptolottoresults) to receive notifications about Jackpot winners. If you are the winner, then you will receive all the Jackpot amount back to your wallet immediately after the end of the game.

# Tutorial 
Please watch a tutorial video on [YouTube](https://www.youtube.com/watch?v=PyrtCXVUkTA). 

# Features
  - **Play safely**. You can join the game safely, even if there are no other players at the time. If by the end of the game no one joins besides you, you will automatically receive your ETH back to your wallet immediately.
  - **Get results**. Recieve instant notifications on your phone by joining our [Telegram](https://www.t.me/lotb). Get useful information about a name of a game, jackpot amount in ETH and USD, timestamp, winner's wallet address and TX hash.
  - **Works worldwide**. Everyone it the world can play the LOTB. There are no borders, limitations or special terms. To start playing, it’s enough to have an Internet access, an Ethereum wallet and ethers. LOTB is not limited to only one country, doesn’t require a special citizenship and is free of any bureaucracy.
  - **Play all games**. In Cryptolotto you can participate in one game unlimited amount of times. Also, you can play in all games simultaneously. It increases chances to win, but remember this not guarantees a win because a winner is always picked randomly. 
  - **MetaMask supported**. Play the game in one click by using [MetaMask](https://metamask.io) wallet. Having Chrome or Firefox browser and MetaMask makes the process of playing in Cryptolotto even more simple and user friendly. No need to copy&paste addresses and ticket prices, just click one button and you will join the game right away!   

# The algorithm of picking a winner

```sh
    }
    
    /**
    * @dev Get random number.
    * @dev Random number calculation depends on block timestamp,
    * @dev difficulty, number and hash.
    *
    * @param min Minimal number.
    * @param max Maximum number.
    * @param time Timestamp.
    * @param difficulty Block difficulty.
    * @param number Block number.
    * @param bHash Block hash.
    */
    function randomNumber(
        uint min,
        uint max,
        uint time,
        uint difficulty,
        uint number,
        bytes32 bHash
    ) 
        public 
        pure 
        returns (uint) 
    {
        min ++;
        max ++;

        uint random = uint(keccak256(
            time * 
            difficulty * 
            number *
            uint(bHash)
        ))%10 + 1;
       
        uint result = uint(keccak256(random))%(min+max)-min;
        
        if (result > max) {
            result = max;
        }
        
        if (result < min) {
            result = min;
        }
        
        result--;

        return result;
    }
```
> Each wallet-participant gets `${uint _number}` when he joins the game. Random number determination depends on current block timestamp, block difficulty, block number and previous block hash. We set determination between min and max values. Additional conditions, in case something goes wrong, are set to prevent contract from sending Jackpot to invalid address.  

# Frequently Asked Questions
Please follow [this link](lotb.xyz/en/faq) to find LOTB FAQs

# Contact Support
If you have any questions about this game please contact us at support@geopay.me


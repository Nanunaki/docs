---
title: cUSD Owner Guide
slug: /celo-owner-guide/cusd
---

If you intend to hold Celo Dollars (cUSD), exchange CELO for cUSD, or send cUSD to others, this guide will help you access your account and manage your funds.

## Prerequisites

This guide assumes:

- You have read [Key Management](/validator-guide/summary) on Celo
- You have installed the [Celo Command Line Interface](../command-line-interface/introduction.md) (Celo CLI)

## Choose a Node

In order to execute the tasks listed below, you will need to point the Celo CLI to a node that is synchronized with the [Mainnet](../getting-started/mainnet). There are two options explained [here](quick-start.md#deployment).

## Create an Account

There are two ways to create an account:

- (Recommended) use [accounts generated by Ledger](ledger.md), if you possess a [Ledger hardware wallet](https://shop.ledger.com/products/ledger-nano-s)
- Use CLI to [generate an account](../getting-started/mainnet/running-a-full-node-in-mainnet#create-an-account-and-get-its-address) -- this approach is less secure and hence not recommended

After creating an account, record its address in environment variables:

```
export CELO_ACCOUNT_ADDRESS=<YOUR-CELO-ACCOUNT-ADDRESS>
```

## Exchange CELO for cUSD

Once you have deposited CELO to your account, you can check your balance:

```
celocli account:balance $CELO_ACCOUNT_ADDRESS
```

You can exchange CELO for cUSD using the following command. Note that the unit of value is CELO Wei (1 CELO = 10^18 CELO Wei).

```
celocli exchange:celo --value <VALUE-TO-EXCHANGE> --from $CELO_ACCOUNT_ADDRESS
```

## Transfer cUSD

When you have sufficient balance, you can send cUSD to other accounts. Note that the unit of value is cUSD Wei (1 cUSD = 10^18 cUSD Wei).

```
celocli transfer:dollars --from $CELO_ACCOUNT_ADDRESS --to <RECIPIENT-ADDRESS> --value <VALUE-TO-TRANSFER>
```

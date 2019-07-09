# CETH Options

## Table of Contents
- [Overview](#Overview)
- [Factory Contract](#Factory)
- [Options Contract](#Options)

## Overview
CETH options use Compound to earn interest on collateral in the contract until contributions are claimed by option writers after expiration.

Suppose Alice wants to write a put for ETH at a 300 DAI strike and an expiration of one month. Put options are simply an obligation to buy an asset at a predefined price, so she deposits 300 DAI into the CETH option contract to enforce her obligation. Her 300 DAI is immediately used to mint cDAI from Compound, now earning Alice interest at the market rate. Alice also has her freshly written put option, so she sells it to a buyer for a premium. Alice is now earning x% from the cDAI and got y% from the put premium, of course, with the caveat that she must buy ETH at 300 DAI at any point before expiration. 

The buyer of the put option, Bob, can sell 1 ETH for 300 DAI to the put option contract at any point before expiration (aka exercising the put option). The put option that Bob bought is an ERC20 token, with all of its implied functionality.

After expiration, Alice claims her assets back from the options contract. She either gets DAI, ETH, or a mix of the two depending on buyers exercise behavior.


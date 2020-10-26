# HushDEX

HushDEX forked from the Subatomic Decentralized App (dapp) and we focus purely
on privacy coin swaps, and specifically, shielded swaps between Zcash Protocol
coins. These are called z-swaps.

## Z-swap example

Alice has 1 ZEC and wants to trade it for 5 HUSH, since she hears HushChat is
pretty awesome and ZEC just goes down in price, always. We represent this in
a diagram like this

    Alice (ZEC) <> Bob (HUSH)

HushDEX is only concerns with Sapling shielded addresses (zaddrs) which start
with `zs1`. Even though ZEC supports Sprout addresses (which start with `zc`),
they cannot be used on HushDEX. Sprout is unsupported on HushDEX.

So Alice must make sure her ZEC is in a Sapling zaddr, and then she can use
HushDEX on her computer, to z-swap with Bob, in a decentralized way, with
no centralized service. The system is not completely trustless, users must
trust the developers and miners on the relevant chains to not do nefarious
things. There is no central authority to decide who gets to do what, it's
peer-to-peer like BitTorrent or Tor.

## Privacy Features of Z-Swaps

  * No KYC
    * We will not feed the identity theft industry any more free data
  * No IP address limiting
    * It is trivial to pay for an IP address from any country in the world
  * Alice's blockchain address never appears in public data
  * Bob's blockchain address never appears in public data
  * Consequently, Alice and Bob's address cannot be searched for on an explorer
  * Since you can't see the address of any transaction, you cannot infer if
    the same address appears as sender or receiver in many transactions.
  * The amount of the transaction, how much ZEC and how much HUSH, is unknown
    * It could be pennies or millions
  * The exchange rate of the transaction never appears on the blockchain
    * The exchange rate will be leaked to the network p2p layer, but it is never
      recorded in blockchain history. If you are not there to record it, it is gone.
    * Realistically, it's simple to run a malicious node which records all exchange rates
      and so we assume an adversary does this
    * Since the exchange rate of ZEC/HUSH is already public data, this is not considered valuable
      information leakage. We are leaking the differential of CEX ZEC/HUSH exchange ratio to
      this DEX's ratio.
    * Adversaries watching all possible public data can infer exchange ratios but no amounts
      or addresses, which is considered a massive blow against blockchain analysis.


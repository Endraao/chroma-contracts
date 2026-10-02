# Chroma — contracts

Smart contracts behind [chromalaunch.fun](https://chromalaunch.fun), a launchpad and trading terminal live on **Robinhood Chain mainnet** (chain id 4663).

## ChromaPons

`src/ChromaPons.sol` — deployed at [`0xC2715457A640E0509Fd38A7ee59b0aB61E15Fc4D`](https://robinhoodchain.blockscout.com/address/0xC2715457A640E0509Fd38A7ee59b0aB61E15Fc4D), source verified on [Sourcify](https://repo.sourcify.dev/4663/0xC2715457A640E0509Fd38A7ee59b0aB61E15Fc4D) (exact match).

- **One-signature launch** (`lancar`): creates the coin through the Pons V2 factory and executes the creator's first buy in the same transaction, so the creator is always first.
- **Anti-bot window**: 60s after launch, protecting early buyers.
- **Trading** (`comprar` / `vender`): buys and sells on the Pons curve with a 0.75% platform fee, of which 0.30% goes to the trader's referrer in the same transaction (no claim step).
- **Launch fee**: 0.0005 ETH.
- Coins launched through Chroma are listed on Pons from block one.

Integrates: Pons V2 Factory `0x7eD598BcEf8bd9Edd8C97A195C6d13f40801EC7e`.

Example: `$CHROMA` (`0x475ab8dd5b1a13a5d18b0b70a1599e3501b0941c`) was launched through this contract — [launch tx](https://robinhoodchain.blockscout.com/tx/0x0fecf202081af682520dd3db31afa84276515c7de684d918e7b9ef07b265583b).

## Tests

11 tests run against a fork of Robinhood Chain mainnet:

```bash
forge install foundry-rs/forge-std
forge test --fork-url https://rpc.mainnet.chain.robinhood.com
```

## Links

- App: https://chromalaunch.fun
- Docs: https://chromalaunch.fun/docs
- Fees: https://chromalaunch.fun/fees
- X: https://x.com/ChromaLaunch
- Telegram: https://t.me/ChromaLaunch

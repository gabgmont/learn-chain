### Chain spec builder

Is a Polkadot SDK utility for generating chain specifications. Refer to the Generate Chain Specs documentation for detailed usage.

Install it by executing the following command:

```sh
cargo install --locked staging-chain-spec-builder@10.0.0
```

This installs the chain-spec-builder binary.
Then Generate chain_spec.json

```sh
chain-spec-builder create -t development \
--relay-chain paseo \
--para-id 1000 \
--runtime ./target/release/wbuild/minimal-template-runtime/minimal_template_runtime.compact.compressed.wasm \
named-preset development
```

### Polkadot Omni Node

Is a white-labeled binary, released as a part of Polkadot SDK that can act as the collator of a parachain in production, with all the related auxiliary functionalities that a normal collator node has: RPC server, archiving state, etc. Moreover, it can also run the wasm blob of the parachain locally for testing and development.

To install it, run the following command:

```sh
cargo install --locked polkadot-omni-node@0.5.0
```

This installs the polkadot-omni-node binary.
Then start node by running

```sh
polkadot-omni-node --chain ./chain_spec.json --dev
```

Explore node at [Substrate Portal](https://polkadot.js.org/apps/#/explorer)
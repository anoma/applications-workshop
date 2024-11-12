# Write & Explore Applications

## Write your first Application

If you [installed Juvix](./2_Install-Juvix.md) on you machine, clone this repo

```sh
git clone https://github.com/anoma/applications-workshop.git
```

and open it in your preferred IDE.

Alternatively, you can use our GitHub Codespace by clicking

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/anoma/applications-workshop?quickstart=1)

or go to [github.com/anoma/applications-workshop](https://github.com/anoma/applications-workshop).

Go through the folders `Excercise_X` and find the assignments as comments inside the `.juvix` files.

| Command                     | Description                                                           |
| :-------------------------- | :-------------------------------------------------------------------- |
| `juvix clean --global`      | Delete your juvix dependencies                                        |
| `juvix clean`               | Delete build artifacts                                                |
| `juvix dependencies update` | Fetch & update the dependencies specified in the `Package.juvix` file |
| `juvix typecheck`           | Check your app for type errors.                                       |
| `juvix format --in-place`   | Format your files                                                     |

Do it all at once with

```sh
juvix clean --global && juvix clean  && juvix dependencies update && juvix typecheck  && juvix format --in-place
```

## Explore the Kudos Token

Kudos is an accounting primitive for Anoma. Kudos intents can embody trust relationships between identities.

### Feature Set

- Identifiers (name, symbol, decimals)
- Originator
  - Can initially create new quantities of this kind/
- Supply
  - Fixed: The total quantity of resources of this kind is fixed. Resources can still be split and merged.
  - Capped: Upper bound on the total quantity. Originator cannot create more than this limit. Owners can burn tokens,
  - Unbound: Originator can inflate the supply.
- Transferability
  - Transferable: Your normal token (ERC-20, NFT)
  - Non-transferable: Soulbound token (SBT)
- Interface
  - mint, burn, transfer, split, merge (no counterparty required)
  - swap intent (counterparty required)

### `Token` Implementation

- Resource Label: [1](https://github.com/anoma/anoma-applib/blob/a6c4993f203d759051ef4a31c0c6c7fde0a9e9a2/Applib/Token/Label.juvix#L8-L16),[2](../HelloWorld/.juvix-build/0.6.8/deps/c4c0b1e74196bd1135c8ea27b48f6756d7ec7aa8f5388511e02d6401d1f1c407/Applib/Token/Label.juvix)
- Resource Logic Function: [1](https://github.com/anoma/anoma-applib/blob/a6c4993f203d759051ef4a31c0c6c7fde0a9e9a2/Applib/Token/Logic.juvix#L13-L23),[2](../HelloWorld/.juvix-build/0.6.8/deps/c4c0b1e74196bd1135c8ea27b48f6756d7ec7aa8f5388511e02d6401d1f1c407/Applib/Token/Logic.juvix)
- Transaction functions (write interface): [1](https://github.com/anoma/anoma-applib/blob/a6c4993f203d759051ef4a31c0c6c7fde0a9e9a2/Applib/Transaction),[2](../HelloWorld/.juvix-build/0.6.8/deps/c4c0b1e74196bd1135c8ea27b48f6756d7ec7aa8f5388511e02d6401d1f1c407/Applib/Transaction)
- Projection functions (read interface): [1](https://github.com/anoma/anoma-applib/blob/a6c4993f203d759051ef4a31c0c6c7fde0a9e9a2/Applib/Projection/TotalQuantity.juvix#L9-L12),[2](../HelloWorld/.juvix-build/0.6.8/deps/c4c0b1e74196bd1135c8ea27b48f6756d7ec7aa8f5388511e02d6401d1f1c407/Applib/Projection/TotalQuantity.juvix)

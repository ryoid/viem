---
head:
  - - meta
    - property: og:title
      content: Client
  - - meta
    - name: description
      content: Setting up your Viem Client with the OP Stack
  - - meta
    - property: og:description
      content: Setting up your Viem Client with the OP Stack
---

# Client

To use the OP Stack functionality of Viem, you must extend your existing (or new) Viem Client with OP Stack Actions.

## Usage

```ts
import { createPublicClient, http } from 'viem'
import { base } from 'viem/chains'
import { l2PublicActions } from 'viem/op-stack' // [!code hl]

const client = createPublicClient({
  chain: base,
  transport: http(),
}).extend(l2PublicActions()) // [!code hl]

const l1Gas = await client.estimateL1Gas({/* ... */})
```

## Decorators

### `l2PublicActions`

A suite of [Public Actions](./actions/estimateL1Gas.md) for **(Layer 2) OP Stack** chains.

```ts
import { l2PublicActions } from 'viem/op-stack'
```
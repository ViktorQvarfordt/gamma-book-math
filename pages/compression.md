---
prerequisites:
  - entropy
---

# Compression

:::definition[Compression]
The number of bits to which a message with $N$ letters can be compressed is $NS_X$. $X$ compressed message has more information (higher entropy) per character.
:::

## Example

If one were to transmit sequences comprising the 4 characters `A`, `B`, `C`, and `D`, a transmitted message might be `ABADDCAB`. Information theory gives a way of calculating the smallest possible amount of information that will convey this. If all 4 letters are equally likely (25%), one can't do better (over a binary channel) than to have 2 bits encode (in binary) each letter: `A` might code as `00`, `B` as `01`, `C` as `10`, and `D` as `11`. If `A` occurs with 70% probability, `B` with 26%, and `C` and `D` with 2% each, one could assign variable length codes, so that receiving a `1` says to look at another bit unless 2 bits of sequential `1`s have already been received. In this case, `A` would be coded as `0` (one bit), `B` as `10`, and `C` and `D` as `110` and `111`, respectively. It is easy to see that 70% of the time only one bit needs to be sent, 26% of the time two bits, and only 4% of the time 3 bits. On average, fewer than 2 bits are required since the entropy is lower (owing to the high prevalence of `A` followed by `B` – together 96% of characters). The calculation of the sum of probability-weighted log probabilities measures and captures this effect.

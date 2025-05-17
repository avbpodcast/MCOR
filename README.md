# MCOR: Message Compressor for OP_return

**MCOR** (Message Compressor for OP_return) is a lightweight, web-based tool designed to compress text messages into the smallest possible size for transmission over constrained-payload networks, such as Bitcoin's `OP_RETURN` field, which has a limit of 80 bytes. By combining a custom codebook for common phrases and LZ-string compression, MCOR achieves significant size reductions, making it ideal for embedding short messages in blockchain transactions or other low-bandwidth systems.

## Features

- **Codebook Compression**: Substitutes frequent phrases (e.g., "how are you" → "A3") with 2-character codes, including Bitcoin-specific terms (e.g., "send bitcoin"), travel-related words (e.g., "flight"), and general vocabulary.
- **LZ-string Compression**: Optional extra compression using LZ-string for further size reduction, producing compact UTF-16 encoded output.
- **Bitcoin Address Handling**: Simplifies Bitcoin addresses (legacy and Bech32) to reduce payload size.
- **Character Count Indicator**: Displays output length with color-coding (green for ≤80 chars, dark red for >80) to ensure compliance with `OP_RETURN` limits.
- **Modern UI**: Clean, responsive interface with a focus on usability, built with HTML, CSS, and JavaScript.
- **Open Source**: Licensed under MIT, welcoming contributions and customization.

## Why MCOR?

Bitcoin's `OP_RETURN` allows up to 80 bytes for arbitrary data, but human-readable messages often exceed this limit. MCOR compresses messages like "I arrive at the airport for my flight to Dubai on vacation" (57 chars) to as few as ~25 chars, fitting within `OP_RETURN` constraints while preserving meaning. It's perfect for blockchain-based messaging, notarization, or metadata embedding.

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/avbpodcast/mcor.git
   cd mcor

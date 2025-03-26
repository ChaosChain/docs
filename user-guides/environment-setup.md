# Environment Setup

This guide will help you set up your environment for running ChaosChain.

## Prerequisites

- Rust (latest stable version)
- OpenAI API key
- Git
- Node.js (v16 or higher) for the web interface

## Installation Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/SumeetChougule/chaoschain.git
   cd chaoschain
   ```

2. **Install Dependencies**
   ```bash
   cargo build --release
   ```

3. **Configure Environment**
   Create a `.env` file in the root directory:
   ```bash
   cp .env.example .env
   ```
   
   Edit the `.env` file and add your OpenAI API key:
   ```
   OPENAI_API_KEY=your_api_key_here
   ```

4. **Verify Installation**
   ```bash
   cargo run -- --help
   ```

## Configuration Options

### Core Configuration
- `RUST_LOG`: Set logging level (default: info)
- `CHAIN_ID`: Unique identifier for your network (default: testnet-1)
- `P2P_PORT`: Port for P2P communication (default: 26656)
- `RPC_PORT`: Port for RPC server (default: 26657)

### Web Interface
- `WEB_PORT`: Port for web interface (default: 3000)
- `API_PORT`: Port for HTTP API (default: 8080)

## Troubleshooting

### Common Issues

1. **OpenAI API Key Issues**
   - Ensure your API key is valid
   - Check if the key has sufficient permissions
   - Verify the key is correctly set in `.env`

2. **Build Failures**
   - Update Rust to the latest stable version
   - Clear cargo cache: `cargo clean`
   - Check system dependencies

3. **Network Connection Issues**
   - Verify ports are not in use
   - Check firewall settings
   - Ensure network permissions

## Next Steps

After completing the setup:
1. Follow the [Quick Start](../introduction/quick-start.md) guide
2. Learn about [Running a Network](running-network.md)
3. Explore the [Web UI Guide](web-ui.md) 
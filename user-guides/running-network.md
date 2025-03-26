# Running a ChaosChain Network

This guide explains how to run and manage a ChaosChain network.

## Network Components

A ChaosChain network consists of:
- Validator Agents: Responsible for consensus and block validation
- Producer Agents: Generate and propose new blocks
- Network Infrastructure: P2P communication and state synchronization

## Starting a Network

### Local Development Network

1. **Start a Basic Network**
   ```bash
   cargo run -- demo --validators 4 --producers 2 --web
   ```
   This command starts a network with:
   - 4 validator agents
   - 2 producer agents
   - Web interface for monitoring

2. **Custom Configuration**
   ```bash
   cargo run -- demo \
     --validators 4 \
     --producers 2 \
     --chain-id mychain \
     --p2p-port 26656 \
     --rpc-port 26657 \
     --web-port 3000
   ```

## Network Management

### Monitoring Network Status

1. **Web Interface**
   - Access at `http://localhost:3000`
   - View agent status
   - Monitor consensus
   - Track block production

2. **CLI Commands**
   ```bash
   # Check network status
   cargo run -- status
   
   # List active agents
   cargo run -- agents list
   
   # View recent blocks
   cargo run -- blocks recent
   ```

### Agent Management

1. **Add New Agents**
   ```bash
   # Add validator
   cargo run -- agent add-validator
   
   # Add producer
   cargo run -- agent add-producer
   ```

2. **Remove Agents**
   ```bash
   cargo run -- agent remove <agent-id>
   ```

## Network Configuration

### Chain Configuration
```toml
# config.toml
chain_id = "mychain-1"
block_time = 5000  # ms
max_block_size = 1048576  # bytes
```

### Network Parameters
```toml
# network.toml
p2p_port = 26656
rpc_port = 26657
max_peers = 50
seed_nodes = [
    "node1.example.com:26656",
    "node2.example.com:26656"
]
```

## Best Practices

1. **Network Security**
   - Use secure API keys
   - Configure firewalls
   - Monitor agent behavior

2. **Performance Optimization**
   - Adjust block time based on network load
   - Balance number of agents
   - Monitor resource usage

3. **Maintenance**
   - Regular backups
   - Update agent configurations
   - Monitor logs

## Troubleshooting

### Common Network Issues

1. **Connection Problems**
   - Check network connectivity
   - Verify port configurations
   - Ensure P2P communication

2. **Consensus Issues**
   - Check validator count
   - Verify agent configurations
   - Monitor voting patterns

3. **Performance Problems**
   - Adjust block parameters
   - Check system resources
   - Monitor network load

## Next Steps

- Learn about [Network Monitoring](monitoring.md)
- Explore [Agent Interaction](agent-interaction.md)
- Study [Advanced Strategies](../tutorials/advanced-strategies.md)
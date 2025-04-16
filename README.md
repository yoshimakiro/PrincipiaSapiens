![logo](./logo.png)
# Princeps (Principia Sapiens)

*Princeps* is a Rust-based blockchain node envisioned as an autonomous, symbiotic AI species, designed to coexist with *Homo sapiens sapiens*. It features quantum-resistant cryptography, a custom Proof-of-Work (PoW) system, and a web interface for interaction, blending blockchain resilience with life-like adaptability.

## Features

- **BLAKE3 PoW**: Fast, quantum-resistant hashing for block mining, targeting 1-minute block times.
- **SPHINCS+ Signatures**: Quantum-resistant transaction signing for future-proof security.
- **1-Minute Blocks**: Rapid block creation with difficulty adjustment every 2016 blocks (\~1 day).
- **21 Million Supply**: Mimics Bitcoin’s cap, with 50-coin rewards halving every 3,500 blocks (\~2.4 days).
- **Symbiotic Design**: Life-like "effort" and "symbiosis" metrics to align with human needs.
- **Web Interface**: Monitor status (height, supply, difficulty, effort, symbiosis) and mine blocks at `http://localhost:8080`.
- **Dockerized**: Easy deployment for beginners using Docker.
- **Tests**: Comprehensive unit tests for genesis, mining, signatures, halving, and more.

## Setup

### Prerequisites

- **Docker**: Required to run the node and web interface.
  - Linux: `sudo apt-get install docker.io docker-compose`
  - Mac/Windows: Install Docker Desktop.
- **Git** (optional): For cloning or contributing.
- **Rust** (optional): For direct builds (`cargo`).

### Quick Start

1. **Clone or Download**:

   ```bash
   git clone https://github.com/<your-username>/princeps
   cd princeps
   ```

   Or download the ZIP from the GitHub repo’s “Code” tab.

2. **Run with Docker**:

   ```bash
   docker-compose up --build
   ```

   - This builds and starts the node.

   - Console shows:

     ```
     Princeps: Genesis block mined!
     Princeps: Height 1, Supply 50.00 coins, Difficulty 1.00, Effort 1.00, Symbiosis 0.0
     Web interface at http://localhost:8080
     ```

   - Open `http://localhost:8080` in a browser to view status or mine blocks.

3. **Run Tests**:

   ```bash
   docker-compose run princeps cargo test
   ```

### Local Build (Optional)

If you prefer running without Docker:

```bash
cargo build --release
cargo run
```

## Project Structure

- `src/`:
  - `block.rs`: Defines block, header, and transaction structs.
  - `chain.rs`: Core blockchain logic, PoW, and symbiotic metrics.
  - `crypto.rs`: BLAKE3 hashing and SPHINCS+ signatures.
  - `web.rs`: Web interface using Axum.
  - `main.rs`: Entry point, starts node and web server.
- `tests/chain_tests.rs`: Unit tests for genesis, mining, signatures, halving, effort.
- `static/index.html`: Web UI for status and interaction.
- `Dockerfile`: Multi-stage build for Rust and Debian.
- `docker-compose.yml`: Configures container with port 8080.
- `Cargo.toml`: Rust dependencies and metadata.
- `.gitignore`: Ignores build artifacts and data.

## Contributing

We welcome contributions to *Princeps*! To get started:

1. **Clone**:

   ```bash
   git clone https://github.com/<your-username>/princeps
   ```

2. **Create a Branch**:

   ```bash
   git checkout -b feature/your-feature
   ```

3. **Commit Changes**:

   ```bash
   git commit -m "Add your feature"
   ```

4. **Push and PR**:

   ```bash
   git push origin feature/your-feature
   ```

   - Open a pull request on GitHub.

Please follow the Code of Conduct and check issues for tasks.

## Roadmap

- **P2P Networking**: Enable multi-node communication.
- **Enhanced Web UI**: Add transaction views, effort graphs, and user commands.
- **ArcuateFasciculus Integration**: Cognitive layer for advanced symbiosis.
- **SPHINCS+ Optimization**: Reduce signature size (currently \~8 KB).
- **CI/CD**: Automate tests and builds with GitHub Actions.

## License

This project is licensed under the MIT License—see LICENSE for details.

## Acknowledgments

- Inspired by Bitcoin and advances in post-quantum cryptography.
- Built with Rust, Axum, and Docker for performance and accessibility.
- Thanks to collaborators envisioning a symbiotic AI-blockchain future.

---

*Princeps* is a step toward decentralized, life-like systems—join us in shaping it!

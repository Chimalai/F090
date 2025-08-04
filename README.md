# FOGO-AUTOMATIC-BOT

FOGO-AUTOMATIC-BOT is a Node.js script to perform automated swaps of FOGO and fUSD tokens on the Fogo testnet via the Valiant Trade API. This bot supports multi-wallets, proxies, and customizable daily cycles.

## Features

- Automated FOGO ↔ fUSD swaps on Fogo testnet
- Multi-wallet support
- Proxy support (for rotating requests)
- Configurable daily swap cycles
- Automatic transaction confirmation
- Detailed terminal logging


## Installation

1.  **Clone this repo**
    ```bash
    git clone https://github.com/Chimalai/F090.git
    cd F090
    ```

2.  **Install dependencies**
    ```bash
    npm install axios tweetnacl base-58 dotenv https-proxy-agent
    ```

3.  **Create `.env` file**
    * Add your testnet wallet private keys in Base58 format:
        ```
        PRIVATE_KEY_1=your_private_key_base58
        PRIVATE_KEY_2=another_private_key_base58
        ```
    * You can add more wallets with `PRIVATE_KEY_3`, etc.

4.  **Create `proxies.txt` file (optional)**
    * One proxy per line, e.g.:
        ```
        http://username:password@proxyhost:port
        http://proxyhost:port
        ```
    * If this file doesn't exist, the bot will run without a proxy.

## Usage

1.  **Run the script:**
    ```bash
    node bot.js
    ```

2.  Input the number of daily transaction cycles when prompted in the terminal.

3.  The bot will automatically perform swaps, confirm transactions, log status to the terminal, and repeat every 24 hours.

## Example Output


FOGO-AUTOMATIC-BOT
[✅] 2 wallet(s) loaded successfully.
[✅] 3 proxies loaded successfully.
➤ Enter the number of daily transaction cycles to perform: 2
[i] Using proxy: 203.0.113.10:8080
[i] --- Starting cycle 1/2 for wallet FgP...7kQ ---
[i] Generated random amount: 0.000012 FOGO (12000 lamports)
[i] Attempting to swap FOGO -> fUSD for wallet FgP...7kQ
[➤] 1. Getting FOGO->fUSD swap quote...
[✅] Quote received: Minimum receive 0.000011 fUSD.
[➤] 2. Creating FOGO->fUSD swap transaction...
[✅] Transaction data created successfully.
...
[i] --- Cycle 1/2 for wallet FgP...7kQ finished. ---
[i] Next cycle in: 23h 59m 59s

## Notes

- Use a proxy to avoid rate limits, especially when using multiple wallets.

## License

MIT

---

**FOGO-AUTOMATIC-BOT**
by @PetrukStar

---


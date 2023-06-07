# global.config.json & testnet-global.config.json

Welcome to the TON Blockchain Configuration Repository. This Repository primarily provides two configuration files in JSON format, `global.config.json` and `testnet-global.config.json`. These files contain the settings for the main and test networks of the TON Blockchain respectively.

- [global.config.json](https://ton-blockchain.github.io/global.config.json) ([Raw](https://raw.githubusercontent.com/ton-blockchain/ton-blockchain.github.io/main/global.config.json)) contains the settings for the TON Blockchain Mainnet.
- [testnet-global.config.json](https://ton-blockchain.github.io/testnet-global.config.json) ([Raw](https://raw.githubusercontent.com/ton-blockchain/ton-blockchain.github.io/main/testnet-global.config.json)) contains the settings for the TON Blockchain Testnet.

## Configuration File Structure

The configuration files are composed of two main sections, `liteservers` and `dht`. Each section contains a list of server or node details.

Simplified explanation of the structure of your `global.config.json` file:

The JSON file comprises of two main sections: `liteservers` and `dht`.

1. `liteservers`: This section contains an array of public servers which can be used to retrieve information about actual state of blockchain: balances, transactions, blocks and network configs. Each server object has three properties:
    - `ip`: This is the IP address of the server, represented as an signed 32bit integer.
    - `port`: This specifies the port number on which the server is operating.
    - `id`: This is an object that represents the server's identification. It has two properties:
        - `@type`: This describes the type of the public key, here it's `pub.ed25519`.
        - `key`: This holds the public key of the server, represented as a base64-encoded string.

2. `dht`: This section defines properties for bootstrap distributed hash table (DHT) servers which can be used for finding peers during first node setup. It has three properties:
    - `a` and `k`: The precise role of these properties is not defined in your provided JSON, but generally, these could be parameters used in the Kademlia DHT (a common DHT variant), where 'k' typically represents the maximum number of contacts stored in a bucket and 'a' could be a related parameter.
    - `static_nodes`: This contains an array of node objects. Each node has multiple properties:
        - `@type`: This represents the type of the node, here it's `dht.node`.
        - `id`: This is similar to the `id` in `liteservers` and holds the identification information for the node.
        - `addr_list`: This is an object that holds a list of addresses for the node. It includes properties such as:
            - `addrs`: An array of address objects, each with properties `@type`, `ip`, and `port`.
            - `version`, `reinit_date`, `priority`, `expire_at`: These could represent versioning and lifecycle data about the addresses.
        - `version`: This might represent the version of the node.
        - `signature`: This might hold a cryptographic signature related to the node, represented as a base64-encoded string.

## Contributions

Feel free to contribute to this project by submitting [issues](https://github.com/ton-blockchain/ton-blockchain.github.io/issues/new) or [pull requests](https://github.com/ton-blockchain/ton-blockchain.github.io/pulls) for improvements to the repository. We appreciate your help and contributions!

## License

This project is licensed under [LICENSE](LICENSE). Please refer to the `LICENSE` file for detailed license information.

Setting up the environment to test Electrum with Testnet5
=
1. Set up a testnet btc1 node with RPC enabled. You'll need to set txindex=1. If you already had a node running without txindex=1, you can add this now and issue -reindex the next time you run it.
2. git clone https://github.com/CoinFabrik/electrumx.git
3. git clone https://github.com/CoinFabrik/electrum.git
4. Install ElectrumX following the instructions.
5. To run ElectrumX, set, then export the following environment variables:
`DAEMON_URL=http://<bitcoin_rpc_user>:<bitcoin_rpc_password>@<bitcoin_rpc_hostname>:<bitcoin_rpc_port>/`
`DB_DIRECTORY=<any_suitable_path>`
`COIN=Bitcoin`
`NET=testnet5`
`TCP_PORT=<electrumx_tcp_port>`
6. Prepare a binary file with all block headers, one after the other, in blockchain order. Set up a minimal HTTP server such that the file is reachable by Electrum at `http://localhost/testnet_headers`.
7. Install Electrum (note: the original Electrum README is at `Electrum.README.rst`) and run it using this command: `electrum --testnet5 --server <electrumx_hostname>:<electrumx_tcp_port>:t`

Now Electrum is ready to use testnet5.

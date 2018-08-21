# TRchain
Blockchain based on Tarantool DB.

# Goal
Tarantool DB is heavily optimized for huge data processing NewSQL and allow build applications inside self, using LuaJit and C languages. Tarantool is a mature and stable project with a fast-growing community. Chain consensus, TCP API peers communication, HTTP API, WASM baed smart contracts can be developed as application-plugin for Tarantool DB. Developers can mostly focus on chain development because DB engine - storage(ledger) already done and supported by the Tarantool dev team and community. The main problem of current blockchain solutions most of them based on embeddable KV storages - LevelDB and RocksDB without any possibility, for example, get transactions by address (for example ETH or BTC derivatives) make queries for data aggregation from the ledger. This doc describe my personal IMHO and ideas how to build blockchain on Tarantool, it's only short overview. 

# Features
* ECDSA: 25519 or Secp256k1. For private chain user can choose.
* Hash function: Blake2s or SHA3. For private chain user can choose.
* Consensus: DPOS - for the public network, POA for a private chain.
* SmartContracts on WASM sandbox. Only for stage 2 of project implementation.
* HTTP Rest Json API.
* User can extend API with personal HTTP API methods using LUA. API methods by defaults provide core functionality for retrieving balances, peer state, txs by address and many more.
* Block every 3sec for private chain can be configurable. Or maybe without blocks only txs (?!?! decentralized ledger ?)
* Max 32 master peers(for POA validators) at the public network.
* Interceptors for transactions (specific permissions).
* Native currency uint64 type with total suplly X.
* Money allocation: minting mechanism.
* P2P messages (chats, notifications...)
* Custom genesis block for private chains. Custom supply, block time, etc.
* Should be simple configuration of peer. Download ant run without jamba-mamba stuff.

# Monitization
Public economic model.

# Competition
Currently exists 2 main chains Ethereum and EOS. Ethereum is slow(POA up too ~1200tps) on public chain 14tx per sec. EOS is future leader but it's only of the embryonic stage (released 1.0 at June of 2018). EOS has one single huge disadvantage it's too centralized and censorship only 21 Master peer. It's not only my personal concern.

# DJV Crypto Token

The DJV Crypto Token is a blockchain-based cryptocurrency implemented in the Motoko programming language. It has been deployed on the Live IC Network, providing users with a secure and decentralized platform for financial transactions.

## Features

- **Blockchain Technology:** DJV is built on a blockchain, ensuring transparent and tamper-proof transaction records.
- **Decentralization:** The DJV Crypto Token operates on a decentralized network, eliminating the need for intermediaries and central authorities.
- **Smart Contract Support:** Smart contracts facilitate the execution of predefined rules and conditions, allowing for automated transactions.
- **Secure Transactions:** DJV ensures secure transactions through cryptographic techniques, protecting user privacy and funds.
- **Live IC Network Deployment:** The DJV Crypto Token has been deployed on the Live IC Network, enabling users to interact with the token and participate in the ecosystem.

## Getting Started

To start using the DJV Crypto Token, follow the steps below:

1. Install a compatible wallet that supports the Internet Computer (IC) network.
2. Obtain DJV tokens through participating in token sales or receiving them from other users.
3. Access the Live IC Network using your wallet.
4. Interact with the DJV token using the provided features, such as sending, receiving, and staking tokens.
5. Explore additional functionalities provided by the DJV ecosystem, including decentralized applications and services.

## Check your Balance

1. Find out your principal id:

```
dfx identity get-principal
```

2. Save it somewhere.

e.g. My principal id is: blah-blah-blah

3. Format and store it in a command line variable:

```
OWNER_PUBLIC_KEY="principal \"$( \dfx identity get-principal )\""
```

4. Check that step 3 worked by printing it out:

```
echo $OWNER_PUBLIC_KEY
```

5. Check the owner's balance:

```
dfx canister call token balanceOf "( $OWNER_PUBLIC_KEY )"
```

## Charge the Canister

1. Check canister ID:

```
dfx canister id token
```

2. Save canister ID into a command line variable:

```
CANISTER_PUBLIC_KEY="principal \"$( \dfx canister id token )\""
```

3. Check canister ID has been successfully saved:

```
echo $CANISTER_PUBLIC_KEY
```

4. Transfer half a billion tokens to the canister Principal ID:

```
dfx canister call token transfer "($CANISTER_PUBLIC_KEY, 500_000_000)"
```

# Deploy the Project to the Live IC Network

1. Create and deploy canisters:

```
dfx deploy --network ic
```

2. Check the live canister ID:

```
dfx canister --network ic id token
```

3. Save the live canister ID to a command line variable:

```
LIVE_CANISTER_KEY="principal \"$( \dfx canister --network ic id token )\""
```

4. Check that it worked:

```
echo $LIVE_CANISTER_KEY
```

5. Transfer some tokens to the live canister:

```
dfx canister --network ic call token transfer "($LIVE_CANISTER_KEY, 50_000_000)"
```

6. Get live canister front-end id:

```
dfx canister --network ic id token_assets
```

7. Copy the id from step 6 and add .raw.ic0.app to the end to form a URL.
   e.g. blah-blah-blah.raw.ic0.app

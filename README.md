```bash
#Create a vanity key pair for mint authority
solana-keygen grind --starts-with bos:1
# use the keypair
solana config set --keypair bos*.json

# use devnet
solana config set --url devnet
# airdrop to the publickey, go to https://faucet.solana.com/
# check balance
solana balance

solana airdrop 5

# create token mint account
solana-keygen grind --starts-with mnt:1

# create token
spl-token create-token --program-id TokenzQdBNbLqP5VEhdkAS6EPFLC1PHnBqCXEpPxuEb \
  --enable-metadata mnt7Sy6d2UDEiUGVsme9Jbm7pswz1ykptRq5GvGk7eD.json

spl-token initialize-metadata mnt7Sy6d2UDEiUGVsme9Jbm7pswz1ykptRq5GvGk7eD 'USDA' 'USDA' https://raw.githubusercontent.com/t7y/solana_mint_setup/refs/heads/main/metadata.json
```

Token can be found [here](https://explorer.solana.com/address/mnt7Sy6d2UDEiUGVsme9Jbm7pswz1ykptRq5GvGk7eD?cluster=devnet)

# Mint tokens
```bash
spl-token create-account mnt7Sy6d2UDEiUGVsme9Jbm7pswz1ykptRq5GvGk7eD

spl-token mint mnt7Sy6d2UDEiUGVsme9Jbm7pswz1ykptRq5GvGk7eD 1000000000
```

# Transfer tokens
```bash
spl-token transfer mnt7Sy6d2UDEiUGVsme9Jbm7pswz1ykptRq5GvGk7eD 100 FwbxtMVYa7kgaxa91PyKRhGYkznxSrNbcmrmncpbjUja --fund-recipient
```

Related resources [here](https://solana.com/developers/guides/getstarted/how-to-create-a-token)
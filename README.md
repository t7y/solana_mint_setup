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

spl-token initialize-metadata mnt7Sy6d2UDEiUGVsme9Jbm7pswz1ykptRq5GvGk7eD 'USDA' 'USDA' https://raw.githubusercontent.com/t7y/solana_mint_setup/f1c79d701cdf7c00ec5b920c08a0b4f5e1c7880b/metadata.json
```
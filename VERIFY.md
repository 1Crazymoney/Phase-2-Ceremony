# Verification of phase-2 ceremony for Railgun

## Install node

First install node with nvm:

````
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash
source ~/.bashrc
nvm install v14.8.0
node --version
````

## Prepare the circuits

````
cd ~
git clone --depth 1 --branch 
git clone --depth 1 --branch v0.0.1-phase-2-ceremony https://github.com/Railgun-Privacy/circuits.git
cd circuits
npm i circom@0.5.38
npm install
````

## Compile the circuits

The compilation may take a while.

##### Small circuit
````
npx circom Small.circom --r1cs
````
##### Large circuit
````
npx circom Large.circom --r1cs
````

## Verify circuits hash
#### Small circuit
````
b2sum Small.r1cs
````

The result must be:

````
82f097195e7bed4ca9a74d5464d100f1778da513eb0c6b70be834661c0ec12e23b65d30b801937c6bd86f0bcb8137e2616aa36beafe262a16bc604b54b589b65
````

##### Large circtuit
````
b2sum Large.r1cs
````

The result must be:

````
8a57c787073bb24e1ed851b9c82b8ac0702d9c784a77570b59fda8a39ac4a295639b1574a8a9eaab98cffcaab9c270164d91fd57e08c9b0e7f79b743e9a75505
````

## Install snarkjs

````bash
npm i snarkjs@0.3.59
````

## Downloading and verifying powers of Tau

First you will need to download powers Of Tau file for phase-1: (pot19.ptau) maintained over [IPFS](https://ipfs.io/ipfs/QmR6agkgFdkHPGGx35UTGkJEjNfB1qJzwYnDcBBB3ixnt2)

To verify phase-1 setup for pot19.ptau, follow this [guide](https://ipfs.io/ipfs/QmYft5k2sY6KJ5V3hkw7FZmHLM7k33uMvwzQy9yC1gt8mF). 

We truncated the final pot-28 to pot-19 since our circuits contain constaints less than 2^19
````
npx snarkjs ptt pot28 
````


Check the blake2b hash of the powers of Tau:
````bash
b2sum pot19.ptau
````

The result must be:

````
bca9d8b04242f175189872c42ceaa21e2951e0f0f272a0cc54fc37193ff6648600eaf1c555c70cdedfaf9fb74927de7aa1d33dc1e2a7f1a50619484989da0887
````


## Verify the final zkey files

##### Small circuit
````
snarkjs zkv small.r1cs pot19.ptau small_final.zkey -v 
````

The circuit hash must be:
````
323539fd42268d6d90ff822b4cede1dd7ac028d8c483078350bc63f7493890ece97c1b8d8dbe25fcab9757dbe9bc6c593d2c6331a20ae546f18fe3a481c6006b
````

##### Large circuit
````
snarkjs zkv large.r1cs pot19.ptau large_final.zkey -v
````

The circuit hash must be:
````
449c7a5644d78d1daa1681052750971a41d575697080945d32e249c5679c819bbb8942d9902bf76e9767759d89f9a19e8eaf22f6c5ef965f1525befc9ed574a4
````

You have to match also the contribution hashes of the participants with attestations they have published.

As far as there is a single attestatation you trust, you can considere the ceremony for this circuit safe.

## Phase2 Random beacon verification

The random beacon of the two circuits is the hash of Ethereum Block 12727000
````
4c742a8b7160d4cc58882d7e7dd11a6234d99e735d2bc12512d6564d1dafddfd
````




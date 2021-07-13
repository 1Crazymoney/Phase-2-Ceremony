# Railgun guide for Phase-2 Trusted Setup Ceremony

This repository contains the transcript of the Phase-2 Ceremony.

This ceremony runs the trusted setup for 2 circuits:

* Small
* Large

Railgun [circuits](https://github.com/Railgun-Privacy/circuits/tree/v0.0.1-phase-2-ceremony), tag `v0.0.1-phase-2-ceremony`, and commit  `e4be8eba3e70394d7c82bc6dfd51fc851715a268`

For verifying the ceremony see: [Verify](VERIFY.md)

## Contributions
All contributions and attestations are maintained over [IPFS](https://ipfs.io/ipfs/QmR6agkgFdkHPGGx35UTGkJEjNfB1qJzwYnDcBBB3ixnt2)
### Small Circuit

| Atestation&nbsp; | Contribution File&nbsp;| Contribution Hash &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; |
|:-----|:------------ |:-------------------------------------------|
| 0000_initial | small_0000.zkey  |`snarkjs zkey new Small.r1cs pot19.ptau small_0000.zkey`
| 0001_hisham | small_0001.zkey   | `a41ca423335eecfd8ee9404a0fecbd479dbd7a1f051ba62d5771fd183504994bba35eaf58acf2e4dc5788b025a7397fc08975c7b2916bb36b988101617ed6d4b`|
| 0002_sponnet | small_0002.zkey | `bed0090714b226cb835282f94e70fa20b9ac6d7fb0be546c6de09367ed2f5c4250b92ee529874319732e976cf7453a10bdaf48f74d041cb68952b77b447e266d`|
| 0003_mesquka | small_0003.zkey  | `71b63e0fda6a7bd30d8be25b53a6338ec97bec51eb33c7a8b596518dcd9ced82dbc06d5e14a0d8616595705fd832885621a9a6ebf83c4a3f7d0f4305699aab16`|
| 0004_wejie | small_0004.zkey    | `ffb11513c5b0d1416cb8975fdd31e13a815d55df328e1880370cd9dadf27c49bae69ea9da99365763bc8ca8b091c6e98df3bc31b516af70c61e79bbbaa0e5ba5`|
| 0005_bertux | small_0005.zkey   | `b110507d61d4f0171380b5fa70d053672e336838b161228a00077d97ef0bee06caffe33ac77bc4ef23575900b28da81cbbc444493613c45230a6782d45fa3c1c`|
| 0006_reuben | small_0006.zkey   | `2783c5ad4f57e714bb83a4c3b9e8e6de77b401dde277a1e9563826198049fbad4093782a50f070d66f53112b3bac6c5764f3f7f0dbac59e3371eb6d92a3cb86b`|
| 0007_riya | small_0007.zkey    | `6b6c8a75d6d9352a89cac764a5e5d06187621b086a791022a6e27de4033d6c37fac5d5fe5be4082774afe48873952ae0ebbf7c2c06b115aa78bf5a2e87a8258f`|
|

#### Beacon Random hash of Ethereum Block 12727000

````
4c742a8b7160d4cc58882d7e7dd11a6234d99e735d2bc12512d6564d1dafddfd
````

###### Applying Beacon

````
snarkjs zkey beacon small_0007.zkey small_final.zkey 4c742a8b7160d4cc58882d7e7dd11a6234d99e735d2bc12512d6564d1dafddfd 10 -n="Ethereum Block 12727000"
042e0379cceddfd35f67457aede6c0a8e8230879b2bd52609cfa0d4d9282908cb997928a0ffb647cb23945218129ad62108108baa776ae52b1f7ce57541c5b8a
````

##### Blake2b hash of small_final.zkey

b2sum:
````
c3bfa798d12c9757027da1282414d9b33fdb783037ec3e2edbdb9b0e6846897d60d51feef6f32c2e659629c31e946d1cccd380e7122f2826167b3bfce59df552
````



### Large Circuit

| Atestation&nbsp; | Contribution File&nbsp;| Contribution Hash &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; |
|:-----|:------------ |:-------------------------------------------|
| 0000_initial | large_0000.zkey    | `snarkjs zkey new Large.r1cs pot19.ptau large_0000.zkey`
| 0001_hisham| large_0001.zkey     | `9fc7e95457d76ee0bcd1a457bb7f8913c146c0e8ac75660077c8443b668b0a4cddd7b0dd493a35756a35ef71a724a11a8f2ac34d3b8034b8c4772c2cbda2b9e2`|
| 0002_sponnet | large_0002.zkey   | `3a12b4d3e30d00cae55682e4b6abb57a6ecf7eac2a90e4892f109fb3a67c9571677a620d4b08029a316642355c925a48eba48efe39c258c18cf9ba46baf3caa8`|
| 0003_mesquka | large_0003.zkey  | `bac1e11250eca570771572298227bc9fa0ed7b50c7b16028976bd63aa2bdf8e679cd32ad1169b86ac30ed8ce8d72d431b3f6409508c5d0f724cd0fa5662f9926`|
| 0004_wejie| large_0004.zkey   |  `cf6c8c5abac9bee596d58a6f3e247502fb9c1255af2dfbc5987a6f2beb9aeeaa456ac8f3fe03305e336c53fd033fd80dd3185a4200921d32f0f92c703114d861`|
| 0005_bertux | large_0005.zkey | `1eb16a73ac0eac00fcb7ed8a15b2af9ae4e3a10d41818f6bf5bfb2be621872eb8b7c38d5fb3b2a501ae79952db0019fb054aaa169891ba812a924386e7044f62`|
| 0006_reuben | large_0006.zkey     |  `f89b9eca5b14abb9809570d0df6d345a1c85f3de79dc272ec0355fd922b0f87fc131c204c347984eb43bfe08cdf353a0f96d6bcac65046c81ab7bbb9b3f1d7ff`|
| 0007_riya | large_0007.zkey   | `4647cae1c7d39322a87fe1c5fae5a698cfe591672372e75a794a71001dc613e45c784c1178dced08025e104ee30bd365a2e865b5f992f60f52b5b3b1f89cfd63`|
|

#### Beacon Random hash of Ethereum Block 12727000

````
4c742a8b7160d4cc58882d7e7dd11a6234d99e735d2bc12512d6564d1dafddfd
````

###### Applying Beacon

````
snarkjs zkey beacon large_0007.zkey large_final.zkey 4c742a8b7160d4cc58882d7e7dd11a6234d99e735d2bc12512d6564d1dafddfd 10 -n="Ethereum Block 12727000"
7b40a5f6ff97f7b05dcb7c99db067b3186a7fa4431868c83505cb139a0e818dde10aa510d6c9b466eb746d15b41a1f77e0514fb8b71c0441d881b78c1b0d597d
````

##### blake2b hash of large_final.zkey

b2sum:
````
2e51c109b9de58646e27d8403e54cdaba5bdc449a2f7c5e7a2d3fdb43ace4d4167634dfb73f56a63d1b37ab8045421178c3761bee8a4805f40724a59186fe2ee
````


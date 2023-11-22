# Diamond EIP-2535 Hardhat Implementation

This is a reference implementation for [EIP-2535 Diamonds](https://github.com/ethereum/EIPs/issues/2535). To learn about other implementations go here: https://github.com/mudgen/diamond


## Installation

1. Clone this repo:
```console
git clone git@github.com:mudgen/diamond-1-hardhat.git
```

2. Install NPM packages:
```console
cd diamond-1-hardhat
npm install
```

## Deployment

```console
npx hardhat run --network avalancheTest scripts/deploy.js
```

### How the scripts/deploy.js script works

```
npx hardhat run --network avalancheTest scripts/deploy.js
DiamondInit deployed: 0x61A5e06b9615b3ad233b4Ebf260eC6fF918d9bcf
Deploying facets
DiamondCutFacet deployed: 0x9f45677b2Cf06d3ae74cf73ca6f220a46E8b13AE
DiamondLoupeFacet deployed: 0x1854EDF3bD67406Bc24d62dC415338c81a8444BA
OwnershipFacet deployed: 0xB48c28d04dbFE3e596b6F4dC29DA714FeD0D155B
Diamond deployed: 0x69793b1405cAD5772b5454A4D22B210AEd3F9271
```

## Upgrade a diamond

3. Create file `Contract/FacetA.sol`
4. Create file  `script/FacetA.js`

```console
npx hardhat run --network avalancheTest scripts/Facet.js
```
5. Verify New Contract

```console
npx hardhat verify --network avalancheTest  0x513B92c9307154bEAb186f1AabA663cBEA2Fe3d9
```

6. Use Daimond Address and Select network hit search button



![alt text](https://www.quicknode.com/guides/assets/images/4-00a7e6f3f611e81b5609bef8074c0e6b.png)

7. click the Upgrade Facet button and click Connect. You will need to input the address of your 
Facet contract (i.e., FacetA) that you previously deployed.

![alt text](https://www.quicknode.com/guides/assets/images/5-b96b2c4e93c35298be5e4cecf697196a.png)

8. After clicking Fetch Facet Info, select the two functions and click Add Facet (you'll need to \
approve the transaction in your wallet).

![alt text](https://www.quicknode.com/guides/assets/images/7-986d3576f75b7ca741d608995f55699d.png)

9. Once your transaction is confirmed, you can move on to the next section, where you will test the 
newly added Facet on your Diamond contract.

10. Now that our Diamond contract has context about our FacetA contract, we can test the setDataA and 
getDataA functions. Navigate back to the homepage of your diamond contract on louper.dev and go to the 
FacetA section and click the Write button and then click Connect. Select the setDataA from the dropdown 
and input the value 0x68656c6c6f206469616d6f6e6473000000000000000000000000000000000000 (which converts 
to "hello diamonds" in decoded string format). Finally, sign the transaction in your MetaMask wallet.

Once your transaction is confirmed, head back over to the homepage of your diamond contract and this time, 
click the Read button under your Facet and select the getDataA function. Click the Read button, and you 
should see your previously set string!

![alt text](https://www.quicknode.com/guides/assets/images/7-986d3576f75b7ca741d608995f55699d.png)


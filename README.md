# Project Title

SimpleBank: A Basic Solidity Smart Contract for Banking Operations

## Description

SimpleBank is a basic Ethereum smart contract written in Solidity. It allows users to deposit and withdraw Ether, check their balances, and includes owner-only functionalities to withdraw all funds. The contract demonstrates the use of 'require()', 'assert()', and 'revert()' statements for error handling and validations.

## Getting Started


### Installing

To set up and run this project, you need the following installed on your machine:

1.Node.js and npm

2.Github

3.Gitpod (for an online development environment)


### Executing program

1.By using gitpod we craete gitpod.yml file in github and then through the URL of that we go to gitpod online development environment.


    image: gitpod/workspace-full

    tasks:
    - init: npm install -g truffle ganache-cli
    command: |
      ganache-cli --chain.chainId 1337 > /workspace/ethereum-dev/ganache-cli.log &
      sleep 5
      truffle compile
      truffle migrate --network development

    ports:
    - port: 8545
      onOpen: open-preview
      visibility: public   


2.Create a "contracts" folder and inside it, create a file named 'SimpleBank.sol' with the provided smart contract code.
3.Create a migrations folder and inside it, create a file named 2_deploy_contracts.js with the following content:
4.Create a truffle-config.js file with the following content:

    module.exports = {
    networks: {
    development: {
      host: "127.0.0.1",
      port: 8545,
      network_id: "*", // Match any network id
     },
    },
    compilers: {
    solc: {
      version: "0.8.0",
      },
     },
    };
    const SimpleBank = artifacts.require("SimpleBank");

    module.exports = function (deployer) {
       deployer.deploy(SimpleBank);
    };


5.Initialize and Run Gitpod:

Commit your changes and push them to your GitHub repository.
Open your GitHub repository in Gitpod by navigating to https://notharley-smartcontract-f0ifhtt1sbs.ws-us114.gitpod.io

6.Watch the Initialization:

Gitpod will automatically initialize the workspace, install dependencies, start Ganache, compile the smart contract, and deploy it.
You can monitor the progress in the terminal.

7.Interact with the Smart Contract:

Once the setup is complete, you can interact with the smart contract using the Truffle console. Open a new terminal in Gitpod and enter the following command:
                                                                            
    truffle console --network development



## Help

If you encounter any issues or need help with the project, feel free to open an issue in the GitHub repository or reach out to the authors.


## Authors

Divij Shukla
divij.shukla2003@gmail.com

## License

This project is licensed under the Smart-Contract License - see the LICENSE.md file for details

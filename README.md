# RivNet: A ZBank Blockchain

![](https://techcrunch.com/wp-content/uploads/2017/10/gettyimages-844081956.jpg?w=1390&crop=1)

To initiate the network, you will need to:

1. Install get and tools. Go to https://geth.ethereum.org/downloads/ and install the latest "Geth & Tools" for your operating system.

2. After installing, you will want to move the new directory to your desired directory. Once moved, you will want to rename the directory to "blockchains-tools."

3. Next, you will navigate to your new blockchain-tools directory through the command line.

4. In the blockchain-tools directory, you will want to create two node accounts by typing "./geth account new --datadir node1" and "./geth account new --datadir node2" respectively. Copy and paste the address and password into another .txt file window, as they will be needed momentarily.

5. With the line "./puppeth" you will navigate through the menu and create a new blockchain with a "Clique (Proof of Authority)" consensus algorithm. 

6. You will want to copy and paste both account addresses to seal on the new blockchain. You will copy and paste as well on accounts to be pre-funded.

7. Choose "no" for pre-funding pre-compiled accounts.

8. Once you have created your blockchain, and find yourself on the main menu, choose "manage existing genesis" option.

9. From there, export genesis configurations. You will only need "rivnet.json", so you can delete "rivnet-harmony.json".

10. Next, you will initialize both nodes with "rivnet.json" using geth.

11. To run the node1, you will type: "./geth --networkid 223 --datadir node1 --syncmode "full" --rpc --unlock "0xf4a8fB0900997EA62c1f2B3d2dCA651DF4398131" --password node1/password.txt --allow-insecure-unlock --mine --minerthreads 1" An explanation of the command line flags follows:

    a. --networkid: Network identifier. Should have been set to "223" when genesis block created.

    b. --datadir: Data directory for the databases and keystore. In this case, node1.

    c. --syncmode: Blockchain sync mode ("fast", "full", or "light") (default: fast).

    d. --rpc: Enable the HTTP-RPC server.

    e. --unlock: Comma separated list of accounts to unlock.

    f. --password: Password file to use for non-interactive password input.

    g. --allow-insecure-unlock: Allow insecure account unlocking when account-related RPCs are expose by http.

    h. --mine: Enable mining.

    j. --minerthreads: Number of CPU threads to use for mining (default: 0).

12. To run node2, you will type: "./geth --networkid 223 --datadir node2 --syncmode "full" --unlock "0xA52B6D4E830055BC50188Ae077134f0ca2980ede" --password node2/password.txt --allow-insecure-unlock --port 30304 --bootnodes "enode://eccbef7d597e4c109c49ebadaf2cd2e0d2c33c481da6f9f4eb60fdf78d13a1132fc6a226397c6a5e10f9cd600dd6e3fbff816ab46d7fa86d37580c3e2400235c@127.0.0.1:30303" --mine --minerthreads 1" An explanation of the command line flags, those different from node1, follows:

    a. --port: Network listening port (default: 30303). Node1 is set to the default, so node2 will be set to port 30304.

    b. --bootnodes: Comma separated node URLs for P2P discovery bootstrap (set v4+v5 instead for light servers)

13. You should now see the two nodes mining blocks!

## MyCrypto:

14. Open MyCrypto and navigate to the "Change Network" button on the left-hand column.

15. Click on "Add Custom Node" and fill in the fields as follows:

    a. Node Name: RivNet

    b. Network: Custom

    c. Network Name: RivNet

    d. Currency: ETH

    e. Chain ID: 223

    f. URL: http://127.0.0.1:8545

16. Click "Save & Use Custom Node"

17. Click "Keystore File," then "SELECT WALLET FILE," then navigate to the keystone file for node1 in the node1 directory. Input the password you set when creating node1, which should be in the password.txt file in the node1 directory.

18. Put the node2 address in the "To Address" field, select an amount and transaction fee and click "Send Transaction."

19. Congrats! You have successfully sent a transaction on the RivNet blockchain!
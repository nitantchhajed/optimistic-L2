# optimistic-L2
Making L2 chain, Optimistic/zkRollup


The Rollup contract functionalities -

-Deposit funds into the layer 2 chain
-Withdraw funds from the layer 2 chain
-Batch and submit a group of layer 2 transactions to the Ethereum mainchain
-Verify and apply the results of a batch of layer 2 transactions
-verify the batch data using a fraud-proof mechanism
-Submit a fraud-proof to the mainchain, challenging a previous batch
-Verify and process a fraud-proof submitted by a user

---------------------------------------------------------------------------------------------------------------------------------------------------------------
The deposit contract is responsible for maintaining the guaranteed gas market, charging deposits for gas to be used on L2, and ensuring that the total amount of guaranteed gas in a single L1 block does not exceed the L2 block gas limit.

The deposit contract handles two special cases:

A contract creation deposit, which is indicated by setting the isCreation flag to true. In the event that the to address is non-zero, the contract will revert.
A call from a contract account, in which case the from value is transformed to its L2 alias.

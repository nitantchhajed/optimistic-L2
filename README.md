# optimistic-L2
Trying to make L2 chain, Optimistic/zkRollup


The deposit contract is responsible for maintaining the guaranteed gas market, charging deposits for gas to be used on L2, and ensuring that the total amount of guaranteed gas in a single L1 block does not exceed the L2 block gas limit.

The deposit contract handles two special cases:

A contract creation deposit, which is indicated by setting the isCreation flag to true. In the event that the to address is non-zero, the contract will revert.
A call from a contract account, in which case the from value is transformed to its L2 alias.

## Ethproof_Beginner Project 

The Tokening contract is a smart contract designed to manage a basic token system for Chandigarh University. In this system, tokens are represented as "Chandigarh University" tokens, abbreviated as "B.Tech." This contract allows for the creation (minting) and destruction (burning) of tokens while maintaining essential token-related information.

**Key Features:**

Token Details: The contract stores crucial details about the token, including its name ("Chandigarh University"), its abbreviation ("B.Tech"), and the total supply of tokens. These details are publicly accessible for transparency.

Mint Function: The contract provides a minting function that enables authorized users to generate new tokens. When invoked, the mint function increases the total supply of tokens and allocates the specified number of tokens to the target address. This feature allows for the controlled expansion of the token supply.

Burn Function: Conversely, the contract offers a burning function to reduce the number of tokens in circulation. When called, the burn function deducts tokens from the sender's balance and decreases the total supply of tokens. Importantly, this operation is conditional on the sender having a sufficient token balance, ensuring that tokens are only burned by their rightful owners.

## Code Explanations

The contract starts by declaring three state variables: tokenName, tokenSymbol, and totalSupply. These variables hold critical information about the token. tokenName represents the name of the token, which, in this case, is "Chandigarh University." tokenSymbol is an abbreviation or symbol for the token, here specified as "B.Tech." Finally, totalSupply keeps track of the total number of tokens in circulation. These variables are declared as public, making them readable from outside the contract for transparency.

#### Balances Mapping:
The contract features a mapping named balances that associates Ethereum addresses with their respective token balances. Users can query the balance of any address using the balances mapping, and it's publicly accessible. The balances mapping is essential for tracking who owns how many tokens within the token system.

#### Mint Function:
The mint function allows for the creation of new tokens and increasing the total token supply. When a user calls this function, they specify two parameters: _to (the target address where new tokens will be sent) and _value (the amount of tokens to mint). Inside the function, a require statement checks that _to is not an invalid address, ensuring the minting operation is secure. Afterward, it increases the total supply by the specified _value and adds these tokens to the balance of the _to address. This functionality facilitates controlled token issuance.

#### Burn Function:
Conversely, the burn function allows for the destruction of tokens, effectively reducing the total token supply. To initiate a burn, users need to provide _value, specifying the number of tokens they want to destroy. Before proceeding, the function includes a require statement to ensure that the sender (message sender) has a sufficient balance of tokens to burn, thus preventing unauthorized or excessive token destruction. If the balance check passes, the function deducts the specified _value tokens from the sender's balance and reduces the total supply accordingly.

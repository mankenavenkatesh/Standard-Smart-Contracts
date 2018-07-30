

ERC-20 defines a common list of rules for Ethereum tokens to follow within the larger Ethereum ecosystem, allowing developers to accurately predict interaction between tokens. These rules include how the tokens are transferred between addresses and how data within each token is accessed


```
The ERC-20 token has the following method-related functions:

The specific wording of the function is followed by a clarification of what it does, in [brackets]

1. totalSupply [Get the total token supply]
2. balanceOf(address _owner) constant returns (uint256 balance) [Get the account balance of another account with address _owner]
3. transfer(address _to, uint256 _value) returns (bool success) [Send _value amount of tokens to address _to]
4. transferFrom(address _from, address _to, uint256 _value) returns (bool success)[Send _value amount of tokens from address _from to address _to]
5. approve(address _spender, uint256 _value) returns (bool success) [Allow _spender to withdraw from your account, multiple times, up to the _value amount. If this function is called again it overwrites the current allowance with _value]
6. allowance(address _owner, address _spender) constant returns (uint256 remaining) [Returns the amount which _spender is still allowed to withdraw from _owner]

Events format:

Transfer(address indexed _from, address indexed _to, uint256 _value). [Triggered when tokens are transferred.]
Approval(address indexed _owner, address indexed _spender, uint256 _value)[Triggered whenever approve(address _spender, uint256 _value) is called.]

```
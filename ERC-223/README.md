The ERC20 Token standard was a good starting point for setting up token development best practices, but it also had some flaws. While any well coded contract will have a fallback function that prevents the user from sending ether to a contract without going through the workflow, no such thing was in place for tokens transfers. This resulted in funds getting lost forever.

```
Thankfully a user named Dexaran (an ETC developer) came up with a keen solution using some inline Assembly. He updated the transfer function to check if the address the tokens are being sent to is a contract address. 

function transfer(address to, uint value, bytes data) {
        uint codeLength;
        assembly {
            codeLength := extcodesize(_to)
        }
        balances[msg.sender] = balances[msg.sender].sub(_value);
        balances[_to] = balances[_to].add(_value);
        if(codeLength>0) {
            // Require proper transaction handling.
            ERC223Receiver receiver = ERC223Receiver(_to);
            receiver.tokenFallback(msg.sender, _value, _data);
        }
    }
```

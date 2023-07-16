// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;
contract GoldCoin {

    string public tokenName = "Agapito";
    string public tokenAbbrv = "Hampaslupa";
    uint public totalSupply = 6;

    mapping(address => uint) public balances;

    function mint(address recipient, uint value) public {
        totalSupply += value;
        balances[recipient] += value;

    }

    function burn(address sender, uint value) public {
        require(balances[sender] >= value, "insufficient balance for burning.");
        totalSupply -= value;
        balances[sender] -= value;
    }
}

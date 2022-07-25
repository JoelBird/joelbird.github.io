## Creating Payment Splitter Smart Contract

- Go to Remix.Ethereum.org
- Create new file in contracts folder called "paymentSplitter"
- Copy and paste OpenZepplin's payment splitter contract code from the following link into your paymentSplitter file:
https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/finance/PaymentSplitter.sol

![1](/assets/images/1.PNG)

- Copy constructor and paste at bottom of contract
- replace "constructor" with "function _addPayees"
- replace "payable with "public onlyOwner"

![2](/assets/images/2.PNG)

- Go back to the constructor we copied near the top of the file and make it as the following image:

![3](/assets/images/3.PNG)

- Add event "payeesCleared"

![4](/assets/images/4.PNG)

- Add "clearPayees" function to bottom of file:

![5](/assets/images/5.PNG)
```
 function _clearPayees() public onlyOwner {
        for (uint256 i = 0; i < _payees.length; i++) {
            address thing = _payees[i];
            delete _shares[thing];
        }
        delete _payees;
        delete _totalShares;
        emit PayeesCleared();
    }
```

## Creating Payment Splitter Smart Contract

- Go to Remix.Ethereum.org
- Create new file in contracts folder called "paymentSplitter"
- Copy and paste OpenZepplin's payment splitter contract code from the following link into your paymentSplitter file:
https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/finance/PaymentSplitter.sol

![1](/assets/images/1.PNG)

- Create "addPayees" function at bottom of file:

```
function _addPayees(address[] memory payees, uint256[] memory shares_) public onlyOwner  {
            require(payees.length == shares_.length, "PaymentSplitter: payees and shares length mismatch");
            require(payees.length > 0, "PaymentSplitter: no payees");

            for (uint256 i = 0; i < payees.length; i++) {
                _addPayee(payees[i], shares_[i]);
            }
        }
```

![2](/assets/images/2.PNG)

- Replace constructor near top of file with following code:

    ```
    constructor() payable {
 
    }
    ```

![3](/assets/images/3.PNG)

- Add event "payeesCleared"

```
event PayeesCleared();
```

![4](/assets/images/4.PNG)

- Add "clearPayees" function to bottom of file:

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
![5](/assets/images/5.PNG)

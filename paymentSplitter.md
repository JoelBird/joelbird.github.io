
- Go to [Remix IDE](Remix.Ethereum.org)
- Create new file in contracts folder called "paymentSplitter"
- Copy and paste OpenZepplin's payment splitter contract code from the following link into your paymentSplitter file:
[OpenZepplin's Payment Splitter](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/finance/PaymentSplitter.sol)

![1](/assets/images/1.PNG)

- Replace import statements at top of file with the following:

```
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/Context.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/Address.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/utils/SafeERC20.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/access/Ownable.sol";
```

- Replace the circled line with the following:

```
contract PaymentSplitter is Context, Ownable {
```

![6](/assets/images/6.PNG)



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

- Add event "payeesCleared" near top of file

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

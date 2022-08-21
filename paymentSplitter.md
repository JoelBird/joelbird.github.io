
## Notes:

- This guide is to make transparent the changes made to the contract developed by OpenZepplin so that you can create it yourself, you can contact me at OpenProje@gmail.com to create the contract for you and I'll transfer ownership to you if you'd prefer

- Changes are required to allow project owner to add and clear payees at any point and to reserve access of certain functions for contract creator(Project Owner)

- A metamask account is required with 0.01 MATIC(0.008315 US Dollar) in the account to deploy the smart contract to the MATIC Mainnet

- This contract should be deployed with MATIC/Polygon because Ethereum is too expensive(117 US Dollar)

- I created this guide using polygon testnet for demonstrative purposes, the process is exactly the same for polygon mainnet which you will be using

---

## Steps:

- Go to [Remix IDE](https://remix.ethereum.org/#optimize=false&runs=200&evmVersion=null)
- Create new file in contracts folder called "paymentSplitter"
- Copy and paste OpenZepplin's payment splitter contract code from the following link into your paymentSplitter file:\
[OpenZepplin's Payment Splitter](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/finance/PaymentSplitter.sol)

![1](/assets/paymentSplitterImages/1.PNG)

---

- Replace import statements at top of file with the following:

```
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/Context.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/Address.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/token/ERC20/utils/SafeERC20.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/access/Ownable.sol";
```

![6](/assets/paymentSplitterImages/6.PNG)

---

- Replace the underlined with the following:

```
contract PaymentSplitter is Context, Ownable {
```

![5](/assets/paymentSplitterImages/5.PNG)

---

- Create "addPayees" function at bottom of file(Before last curly bracket):

```
function _addPayees(address[] memory payees, uint256[] memory shares_) public onlyOwner  {
            require(payees.length == shares_.length, "PaymentSplitter: payees and shares length mismatch");
            require(payees.length > 0, "PaymentSplitter: no payees");

            for (uint256 i = 0; i < payees.length; i++) {
                _addPayee(payees[i], shares_[i]);
            }
        }
```

![2](/assets/paymentSplitterImages/2.PNG)

---

- Replace constructor near top of file with following:

    ```
    constructor() payable {
 
    }
    ```

![3](/assets/paymentSplitterImages/3.PNG)

---

- Add event "payeesCleared" near top of file

```
event PayeesCleared();
```

![4](/assets/paymentSplitterImages/4.PNG)

---

- Add "clearPayees" function to bottom of file(Before last curly bracket):

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

![7](/assets/paymentSplitterImages/7.PNG)

---

- Go to plugin manager tab, search and activate flattener plugin:

![13](/assets/paymentSplitterImages/13.PNG)

---

- In the flattener plugin tab, flatten paymentSplitter and save paymentSplitter_flat

![34](/assets/paymentSplitterImages/34.PNG)

---

- Add following text to top of paymentSplitter_flat if missing

```
// SPDX-License-Identifier: MIT
```

![14](/assets/paymentSplitterImages/14.PNG)

---

- Ensure your compiler and contract is set to the following and click "Compile and run script":

![15](/assets/paymentSplitterImages/15.PNG)

---

- Ensure your Metamask wallet network is set to Matic Mainnet:

![16](/assets/paymentSplitterImages/16.PNG)

---

- On "Deploy and run transactions" tab, set environment to "injected provider", ensure contract is "paymentSplitter_flat" and click "deploy"

![17](/assets/paymentSplitterImages/17.PNG)

---

- confirm the message box that appears, Metamask will pop up asking you to confirm transaction, click "confirm"

![18](/assets/paymentSplitterImages/18.PNG)

---

- In metamask, open the contract deployment transaction, and click "View on block explorer":

![19](/assets/paymentSplitterImages/19.PNG)
![20](/assets/paymentSplitterImages/20.PNG)

---

- Click the contract address link:

![21](/assets/paymentSplitterImages/21.PNG)

---

- Click "Verify and Publish" on "contract" tab:

![22](/assets/paymentSplitterImages/22.PNG)

---

- Make the fields in circle the same:

![23](/assets/paymentSplitterImages/23.PNG)

---

- Copy-paste all the code from the "paymentSplitter_flat.sol" file into the "Enter the Solidity contract code below" field, click "Im not a robot", do the captcha and click "Verify and publish"

![24](/assets/paymentSplitterImages/24.PNG)

---

- Click the underlined link:

![25](/assets/paymentSplitterImages/25.PNG)

---

- convert all money earned from the project to matic tokens and send to the contract address:

![33](/assets/paymentSplitterImages/33.PNG)

- Click "Contract" > Click "Write Contract" > Click "Connect to Web3" > Click "Metamask" and follow through:

![26](/assets/paymentSplitterImages/26.PNG)

---

- Use the following slash command in your discord server to generate the payees and shares arrays for your server:

```
/generate_payees_and_shares
```

![one](/assets/paymentSplitterImages/one.PNG)

- Paste the Shares Array into the "shares" field of the addpayees function and paste the Address Array into the "Payees" field of the addPayees function and click "Write" and confirm the transaction in metamask:

![29](/assets/paymentSplitterImages/29.PNG)

---

- Contributors can use the *release* function with their inserted metamask wallet address to receive their MATIC, you should use the *clear payees* command before adding new payees and you can transfer ownership of the contract if you wish:

![30](/assets/paymentSplitterImages/30.PNG)

---

- On the "Read" tab, you can see the contract owner's address, see a payee account by index, and see how much is releasable to a contributor:

![31](/assets/paymentSplitterImages/31.PNG)

---

- See how much matic an account has released, how many shares an account has, total matic released and total shares posessed:

![32](/assets/paymentSplitterImages/32.PNG)

*Congratulations! You've created your paymentSplitter smart contract on polygon.*



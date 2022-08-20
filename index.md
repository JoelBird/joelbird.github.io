---
layout: default
title: "Home"
---
## What is OpenProj?

OpenProj helps projects on discord open their work to the community, allowing members to participate in the projects development and get rewarded with shares of that project.

---

## OpenProj integration into discord server
## Initial Setup:

Please ensure all earnings from your project go to a project wallet address that is seperate from all other income streams or holdings. The project earnings should be isolated in it's own address and not merged with any other value.

If your project is an NFT project, we highly advise following our guide on setting up NFT royalties for your contract, this will ensure sustained project income and encourage long term project development and growth from your contributors:
[NFT Royalties Guide](https://joelbird.github.io/nftRoyalties/)

- Invite our OpenProj bot to your server:
[Invite Url](https://discordapp.com/api/oauth2/authorize?client_id=961725997789630524&scope=bot&permissions=395405552656)
- Our bot will create the OpenProj category, the required channels and the OpenProjManager role

---

## Creating Tasks:

- The first message in a tasks-channel will define all the tasks that you are inviting members to complete.
- For a member to add and remove tasks they must have the OpenProjManager role of that server.
- Create tasks with the **add_task** slash command in your discord server:

```
/add_task
```
![1](/assets/images/1.PNG)

*These commands must be used so that the "tasks" message is created by our bot, this is necessary as the bot will be updating the tasks message frequently and must be the author of the message to do so.*

**Task Information:**

**Task Title:** Title of the task\
**Shares:** A number from 1 - 100 that describes the difficulty of the task and is also the amount shares a contributor will receive on completion of the task\
**Task Description:** Describe what the task entails\
**Thread Count:** Specify how many threads can be created to contribute towards/complete a task\
**Thread Links:** The bot will create links to the threads that members create
**Task Creator:** The member that created this task

---

## How a member completes/contributes to a task:

- Members can create a thread to attempt completion/contribution of a task
- The creator of this thread is held responsible for the task
- The thread creator may require other members to assist in contribution/completion of the task. The thread creator uses the **split** command to allocate a percentage of received shares to contributors in that thread.
- When the thread creator has judged that the task is sufficiently completed/contributed towards, they will use the **split** command in their thread, allocating shares to all assisting members for their contribution:

```
/split
```

![2](/assets/images/2.PNG)

They will then archive the thread, awaiting evaluation. 

---

## Set Owner Shares Percent

- A member with the OpenprojManager role must set the percentage of shares the project owner will possess using the **set_owner_shares_percent** command, if contributors collectively accumulate 100 shares and the owner set their shares percent to 50%, the owner will have 100 shares as well. The owner will always have the percent of shares set with this command:

```
/set_owner_shares_percent
```

---

## Setting Owner Wallet address

- A member with the OpenprojManager role must use the **set_owner_wallet_address** command, their wallet earnings according to the amount set with the "Set Owner Shares Percent" command will be released to this account:

```
/set_owner_wallet_address
```

---

## Evaluating a task contribution/completion:

- At the end of the month time period, members with the OpenProjManager role will evaluate all task contributions/completions of every task-channel and distribute the share amounts, they will distribute the shares as a percentage of the threads contribution towards completing the task and according to the thread creators' Split allocations:

```
/distribute
```

![3](/assets/images/3.PNG)

**Diagram Of Flow:**

![6](/assets/images/6.PNG)

---

## Generate Payees And Shares

- After all threads have been evaluated and shares distributed, the owner should use the **generate_payees_and_shares** command. The bot will send 2 arrays, the first array contains the share amounts and the second array contains the ethereum addresses for those amounts:

```
/generate_payees_and_shares
```

- These lists are inserted into the **_addPayees** function of the payment splitter smart contract:

![4](/assets/images/4.PNG)

- You can request for me to create this contract for you at OpenProje@gmail.com or find the guide on how to create this smart contract here:

[Payment Splitter Guide](https://joelbird.github.io/paymentSplitter/)

- Send the funds from the project wallet to the created smart contract's address
- Contributors can now release their allocated earnings from the smart contract by inserting their wallet address into the **release** function:

![5](/assets/images/5.PNG)

---

## Openproj will always have 5% of shares

- Openproj will always possess 5% of shares, according to the same logic as the **set_owner_shares_percent** command

---

## Set Wallet address

- Members must add their wallet address with the below command, members that fail to add their address will forfeit their earnings to everyone that did add their address:
```
/set_wallet_address
```

---

You can delete and create the following channels in the OpenProj category anytime, our bot will populate the necessary info on creation:\
marketing-tasks\
coding-tasks\
other-tasks\
info\
chat\
commands\
request-task\

*When creating these channels, please ensure spelling is the same as demonstrated above, this is necessary for our bot*

---

## Server Duplication

- For every discord server that has integrated with OpenProj, it's task channels and task channel's contents will be duplicated and kept up to date by our bot on the OpenProj server, making it accesible to members looking to contribute to a project.

OpenProj Server:
[Invite Url](https://discord.gg/sUGsVayRaD)

---

## OpenProjBot Slash Commands

**Add task to channel (Must have OpenProjManager role)**
```
/add_task
```
**Remove task from channel (Must have OpenProjManager role)**
```
/remove_task
```
**Set split for assisting members (Sent in thread)**
```
/split
```
**Distribute shares to task completers/contributors (Sent in thread) (Must have OpenProjManager role)**
```
/distribute
```
**Set Owner Shares Percent (Must have OpenProjManager role)**
```
/set_owner_shares_percent
```
**Set Owner Wallet Address (Must have OpenProjManager role)**
```
/set_owner_wallet_address
```
**Set Contributor Wallet Address**
```
/set_wallet_address
```
**Check Shares**
```
/shares
```
**Generate Payees And Shares**
```
/generate_payees_and_shares
```

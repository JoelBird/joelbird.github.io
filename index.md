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

Now create the task-channels you will be working with. Task-channels are different areas of development your project wishes to open to the public, inviting their support. Task-channels can be of the following categories:\
marketing-tasks\
coding-tasks\
other-tasks

*When creating these channels, please ensure spelling is the same as demonstrated above, this is necessary for our bot*

---

## Creating Tasks:

- The first message in a tasks-channel will define all the tasks that you are inviting members to complete.
- For a member to create and update tasks they must have the OpenProjManager role of that server.
- Create tasks with the following format inserted as a message in a task-channel:

```
Update Tasks(**tasks**)
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
- The thread creator may require other members to assist in contribution/completion of the task. The thread creator uses the Split command to allocate a percentage of received shares to contributors in that thread.
- When the thread creator has judged that the task is sufficiently completed/contributed towards, they will create their final messages in the thread, allocating the shares to all assisting members for their contribution:

```
(Split: @member **amount**)
```

![2](/assets/images/2.PNG)

They will then archive the thread, awaiting evaluation. 

---

## Evaluating a task contribution/completion:

- At the end of the month time period, members with the OpenProjManager role will evaluate all task contributions/completions of every task-channel and distribute the share amounts, they will distribute the shares as a percentage of the threads contribution towards completing the task and according to the thread creators' Split allocations:

```
(Distribute: @member **amount**)
```

![3](/assets/images/3.PNG)

**Diagram Of Flow:**

![6](/assets/images/6.PNG)

---

## Generate Payees And Shares

- After all threads have been evaluated and shares distributed, the owner should use the "Generate Payees And Shares" command. The bot will send 2 arrays, the first array contains the share amounts and the second array contains the ethereum addresses' for those amounts.

- These lists are inserted into the "_addPayees" function of the payment splitter smart contract:

![4](/assets/images/4.PNG)

- You can request for me to create this contract for you at OpenProje@gmail.com or find the guide on how to create this smart contract here:

[Payment Splitter Guide](https://joelbird.github.io/paymentSplitter/)

- Send the funds from the project wallet to the created smart contract's address
- Contributors can now release their allocated earnings from the smart contract by inserting their wallet address into the "release" function:

![5](/assets/images/5.PNG)

---

## Set Owner Shares Percent

- The server owner should set the percentage of shares the project owner will possess using the "Set Owner Shares percent" command, if contributors collectively accumulate 100 shares and the owner set their shares percent to 50%, the owner will have 100 shares as well. The owner will always have the percent of shares set with this command:

```
(Set Owner Shares Percent: **percentage**)
```

---

## Setting Owner Wallet address

- The server owner must use the "Set Owner Wallet address" command, their wallet earnings according to the amount set with the "Set Owner Shares Percent" command will be released to this account:

```
(Set Owner Wallet Address: **wallet address**)
```

---

## Openproj will always have 6% of shares

- Openproj will always possess 6% of shares, according to the same logic as the "Set Owner Shares percent" command

---

## Set Wallet address

- Members must add their wallet address with the below command, members that fail to add their address will forfeit their earnings to everyone that did add their address:
```
(Set Wallet Address: **wallet address**)
```

---

## Server Duplication

- For every discord server that has integrated with OpenProj, it's task channels and task channel's contents will be duplicated and kept up to date by our bot on the OpenProj server, making it accesible to members looking to contribute to a project

OpenProj Server:
[Invite Url](https://discord.gg/sUGsVayRaD)

---

## OpenProj-Discord Commands

- These commands are sent as a message in a Discord server that has invited our OpenProj bot
- Our OpenProj bot will message you with command errors or information requested from a command


**Create channel tasks (Sent in task channel) (Must have OpenprojManager role)**
```
(Create Tasks: **tasks**)
```
**Update channel tasks (Sent in task channel) (Must have OpenprojManager role)**
```
(Update Tasks: **tasks**)
```
*This command will delete the tasks already there and replace them with the new task information*

**Set Split for assisting members (Sent in thread)**
```
(Split: @member **percentage**)
```
**Distribute shares to task completers/contributors (Sent in thread) (Must have OpenprojManager role)**
```
(Distribute: @member **amount**)
```
**Set Owner Shares Percent (Sent in chat/commands channel) (Must be server owner)**
```
(Set Owner Shares Percent: **percentage**)
```
**Set Owner Wallet Address (Sent in chat/commands channel) (Must be server owner)**
```
(Set Owner Wallet Address: **wallet address**)
```
**Set Contributor Wallet Address (Sent in chat/commands channel)**
```
(Set Wallet Address: **wallet address**)
```
**Check shares (Sent in chat/commands channel)**
```
(Shares: **server name**)
```
**Generate Payees And Shares (Sent in chat/commands channel)**
```
(Generate Payees And Shares: **server name**)
```

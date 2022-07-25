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
(LINKKKK))

- Invite our OpenProj bot to your server:
[Invite Url](https://discordapp.com/api/oauth2/authorize?client_id=961725997789630524&scope=bot&permissions=17179962368)
- Create a category called "OpenProj" within your discord server - Capitalised "O" and capitalised "P"
- Create the following channels in the OpenProj category:\
info\
chat\
commands

Now create the task-channels. Task-channels are different areas of development your project wishes to open to the public, inviting their support. Task-channels can be of the following categories:\
marketing-tasks\
coding-tasks\
other-tasks

*When creating these channels, please ensure spelling is the same as demonstrated above, this is necessary for our bot*

---

## Creating Tasks:

- The first message in a tasks-channel will define all the tasks that you are inviting members to complete.
- You must create a distributor role within your server, call it: (name of server)Distributor - no spaces, server name spelt as spelt on server, distributor with capitalised "D"\
![9](/assets/9.PNG)
- For a member to create and update tasks they must have the distributor role of that server.\
- Create tasks with the following format inserted as a message in your discord server:

```
Create Tasks(**tasks**)
```
![10](/assets/10.PNG)

*These commands must be used so that the "tasks" message is created by our bot, this is necessary as the bot will be updating the tasks message frequently and must be the author of the message to do so.*

**Task Information:**

**Task Title:** Title of the task\
**Task Level:** A number from 1 - 100 that describes the difficulty of the task and is also the amount shares a contributor will receive on completion of the task\
**Task Description:** Describe what the task entails\
**Thread Count:** Specify how many threads can be created to contribute towards/complete a task\
**Thread Links:** The bot will create links to the threads that members create

![11](/assets/11.PNG)

---

## How a member completes/contributes to a task:

- Members can create a thread to attempt completion/contribution of a task
- The creator of this thread is held responsible for the task
- The thread creator may require other members to assist in contribution/completion of the task. The thread creator uses the Split command to allocate a percentage of received shares to contributors in that thread.

![12](/assets/12.PNG)

When the thread creator has judged that the task is sufficiently completed/contributed towards, they will create their final messages in the thread, allocating the shares to all assisting members for their contribution:

```
(Split: @member **amount**)
```

![13](/assets/13.PNG)

They will then archive the thread, awaiting evaluation. 

---

## Evaluating a task contribution/completion:

- At the end of the month time period, members with the distributor role will evaluate all task contributions/completions of every task channel and distribute the share amounts, they will distribute the shares as a percentage of the threads contribution towards completing the task and according to the thread creators' Split allocations:

```
(Distribute: @member **amount**)
```

![14](/assets/14.PNG)

![8](/assets/8.PNG)

---

## Generate Payees And Shares

- After all threads have been evaluated and shares distributed, the owner should use the "Generate Payees And Shares" command. The bot will send 2 arrays, the first array contains the share amounts and the second array contains the ethereum addresses' for those amounts.

- These lists are inserted into the "_addPayees" function of the payment splitter smart contract:

(IMAGEE)

- You can request for me to create this contract for you at OpenProje@gmail.com or find the guide on how to create this smart contract here:
(LINK)))

- Send the funds from the project wallet to the created smart contract's address
- Contributors can now release their allocated earnings from the smart contract by inserting their wallet address into the "release" function:
(IMAGEEEE))))

---

## Set Owner Shares Percent

- The server owner should set the percentage of shares the project owner will possess using the "Set Owner Shares percent" command, if contributors collectively accumulate 100 shares and the owner set their shares percent to 50%, the owner will have 100 shares as well. The owner will always have the percent of shares set with this command:

```
(Set Owner Shares Percent: **percentage**)
```

---

## Setting Owner Ethereum address

- The server owner must use the "Set Owner Ethereum address" command, their ethereum earnings according to the amount set with the "Set Owner Shares Percent" command will be released to this account:

```
(Set Owner Ethereum Address: **ethereum address**)
```

---

## Openproj will always have 5% of shares

- Openproj will always possess 5% of shares, according to the same logic as the "Set Owner Shares percent" command

---

## Set Ethereum address

- Members must add their ethereum wallet address with the below command, members that fail to add their address will forfeit their earnings to everyone that did add their address:
```
(Set Ethereum Address: **ethereum address**)
```

---

## Server Duplication

- For every discord server that has integrated with OpenProj, it's task channels and task channel's contents will be duplicated and kept up to date by our bot on the OpenProj server, making it accesible to members looking to contribute to a project

OpenProj Server:
https://discord.gg/8D4seJb4

---

## OpenProj-Discord Commands

- These commands are sent as a message in a Discord server that has invited our OpenProj bot
- Our OpenProj bot will message you with command errors or information requested from a command


**Create channel tasks (Sent in task channel) (Must have distributor role)**
```
(Create Tasks: **tasks**)
```

**Update channel tasks (Sent in task channel) (Must have distributor role)**
```
(Update Tasks: **tasks**)
```
*This command will delete the tasks already there and replace them with the new task information*

**Set Split for assisting members (Sent in thread)**
```
(Split: @member **percentage**)
```
**Distribute shares to task completers/contributors (Sent in thread) (Must have distributor role)**
```
(Distribute: @member **amount**)
```
**Set Owner Shares Percent (Sent in chat/commands channel) (Must be server owner)**
```
(Set Owner Shares Percent: **percentage**)
```
**Set Owner Ethereum Address (Sent in chat/commands channel) (Must be server owner)**
```
(Set Owner Ethereum Address: **ethereum address**)
```
**Set my Ethereum Address (Sent in chat/commands channel)**
```
(Set Ethereum Address: **ethereum address**)
```
**Check shares (Sent in chat/commands channel)**
```
(Shares: **server name**)
```
**Generate Payees And Shares (Sent in chat/commands channel)**
```
(Generate Payees And Shares: **server name**)
```

---
layout: default
title: "Home"
---

## What is OpenProj?

OpenProj helps projects on discord open their work to the community, allowing members to participate in the projects development and get rewarded with tokens belonging to that project.

The tokens received can be exchanged for the project's products, held in anticipation of future value growth, and in the future, exchanged for their dollar value.

## OpenProj integration into discord server
## Initial Setup:

1. Invite our OpenProj bot to your server:
[Invite Url](https://discordapp.com/api/oauth2/authorize?client_id=961725997789630524&scope=bot&permissions=66560)
2. Create a category called "OpenProj" within your discord server - Capitalised "O" and capitalised "P"
3. Create the following channels in the OpenProj category:\
info
chat
commands

Now create the tasks channels. Task channels are different areas of development your project wishes to open to the public, inviting their support. Task channels can be of the following categories:\
marketing-tasks\
coding-tasks\
other-tasks

*When creating these channels, please ensure spelling is the same as demonstrated above, this is necessary for our bot*

## Creating Operation Tasks:

- The first message in the channel will define all the tasks of this operation that you are inviting members to complete.
- You must create a distributor role within your server, call it: (name of server)Distributor | no spaces, first letter of each word capitalised:
![9](/assets/9.PNG)
- For a member to create and update tasks they must have the distributor role of that server.\
4. Create tasks with the following format inserted as a message in your discord server:

```
Create Tasks(insert tasks)
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
(Split: @member amount)
```

![13](/assets/13.PNG)

They will then archive the thread, awaiting evaluation. 

---

## Evaluating a task contribution/completion:

- At the end of the month time period, members with the distributor role will evaluate all task contributions/completions of every task channel and distribute the share amounts, they will distribute the shares as a percentage of the threads contribution towards completing the task and according to the thread creators' split allocations:

![14](/assets/14.PNG)

![8](/assets/8.PNG)

---

## Server Duplication

- For every discord server that has integrated with OpenProj, it's task channels and task channels contents will be duplicated and kept up to date by our bot on the OpenProj server, making it accesible to members looking to contribute to a project

---

## OpenProj-Discord Commands

- These commands are sent as a message in a Discord server that has invited our OpenProj bot
- Our OpenProj bot will message you with command errors or information requested from a command


**Create server tasks (Sent in task channel) (Must have distributor role):**
```
(Create Tasks: (insert tasks) )
```

**Update server tasks (Sent in task channel) (Must have distributor role)**
```
(Update Tasks: (insert tasks) )
```
*This command will delete the tasks already there and replace them with the new task information*

**Set Split for assisting members (Sent in thread)**
```
(Split: @member percentage)
```
**Distribute shares to task completers/contributors (Sent in thread) (Must have distributor role)**
```
(Distribute: @member amount)
```
**Set Owner Shares Percent (Sent in chat/commands channel) (Must be server owner)**
```
(Set Owner Shares Percent: percentage)
```
**Set Owner Ethereum Address (Sent in chat/commands channel) (Must be server owner)**
```
(Set Owner Ethereum Address: ethereum address)
```
**Set my Ethereum Address (Sent in chat/commands channel)**
```
(Set Ethereum Address: ethereum address)
```
**Check shares (Sent in chat/commands channel)**
```
(Shares: server name)
```
**Generate Payees And Shares (Sent in chat/commands channel)**
```
(Generate Payees And Shares: server name)
```

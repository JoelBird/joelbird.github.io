---
layout: default
title: "Home"
---


#### OpenProj integration into discord server:

#### Initial Setup:

- Invite our OpenProj bot with ... permissions 
- Create a category called "OpenProj" 
- Create channels within the "OpenProj" category, each channel is a different area of development your project wishes to open to the public, inviting their support

These channels that we call "Operations" can be of the following categories: 

Design
Marketing
Coding
Other Contributory tasks

The channel name should correspond with one of the categories mentioned above.

#### Creating Operation Tasks:

The first message in the channel will define all the tasks of this operation which you will invite members to complete.

- you can create tasks with the following format inserted as a message in your discord server:

```
Create Tasks(insert tasks)
```

- You can update tasks with the following format inserted as a message in your discord server:

```
Update Tasks(insert tasks)
```

The "Update Tasks" command replaces the tasks already present

These commands must be used so that the "tasks" message is created by our bot, this is necessary as the bot will be updating the tasks message frequently and must be the author of the message to do so.

**Task Information:**

**Task Title:** Title of the task
**Token Allocation:** Will be rewarded to members on completion/contribution of the task
**Task Description:** Describe what the task entails
**Minimum-(operation)-tokens-earned-last-month:** Specify minimum tokens of this operation member must have acquired last month to contribute to the task.
**Thread Count:** Specify how many threads can be created to contribute towards/complete a task
**Thread Links:** The bot will create links to the threads members create

![[1.PNG]]

---

#### How a member completes/contributes to a task:

- Members can create a thread to attempt completion/contribution of a task
- The creator of this thread is held responsible for the task
- The thread creator may require other members to assist in contribution/completion of the task. The thread creator can compensate the assisting members through method of **compensation** and **scaling**:

**Compensation** is a defined amount of tokens the thread creator will send the assisting members before ending/archiving the thread. This will come from the thread creator. It is a method of ensuring compensation of assisting members regardless of how many tokens is received on evaluation. This is specifed as the first item in the thread title in brackets.

**Scaling** is a method of paying assisting members based on a percentage of how much they may earn for their contribution/completion. This will come from the servers distributor account. This is specifed in the thread title in brackets with a percentage preceding the amount. The amount is the percentage the thread creator is willing to allocate to contributing members, the rest reserved for the thread creator.

These 2 methods can be applied by thread creator together or individually. The thread creator will define this amount and/percentage in the thread title:


(fix problem when screenshot)

When the thread creator has judged that the task is sufficiently completed/contributed towards, they will create a final message in the thread distributing tokens to all assisting members for their contribution:

```
(Distribute: @member value/percentage)
```

(ScREENEHSOT_)

They will then archive the thread, awaiting evaluation. 


---

#### Evaluating a task contribution/completion:

- At the end of the month time period, members with the distributor role will evaluate all task contributions/completions of every operation and distribute the allocated token amounts, they will distribute the tokens as a percentage of the threads contribution towards completing the task and according to the thread creators' scaling allocations:

![[2.PNG]]

(Add screneshdsdo)

---

#### Contributor Rating

- Tokens earned by task completers/contributors within an operation will contribute to their (operation)-tokens-earned. A contributor can be evaluated on their quality of contribution within an operation based on the operation-tokens-received-last-month. 

- Members looking to assist thread creators will decide which thread creator to support based on scaling according to high (operation)-tokens-received-last-month, or compensatory, to ensure compensation regardless of ablity of thread creator to contribute to operation goals. 

---

#### Server Duplication

- Every operation and it's contents on your server will be duplicated and kept up to date by our bot on the OpenProj server, making it accesible to members looking to contribute to a project. 



---
#### OpenProj-Discord Commands
- These commands are sent as a message in a Discord server that has invited our OpenProj bot
- Our OpenProj bot will message you with command errors or information requested from a command


**Creating server tasks (Must have distributor role):**

```
(Create Tasks: (insert tasks) )
```

**Update Server Tasks (Must have distributor role):**

```
(Update Tasks: (insert tasks) )
```

This command will delete the tasks already there and replace them with the new task information

**Check tokens balance:**

```
(My Balance)
```

**Send tokens to another member:**

```
(Send: @member value)
```

___

# Creating a Dash DGBB Proposal

This guide will walk you through the proceess of creating a dash proposal. It is adapted from the [documentation on dash.org](https://dashpay.atlassian.net/wiki/display/DOC/Using+Decentralized+Governance%3A+Proposals,+Voting,+and+Budgets).  Dash proposals are intended for submission to the dash mastenode 'distributed governance by blockchain' (DGBB) network.

### Understanding Proposals

Describe what is necessary at the protocol level, why it is okay to use any website to host your proposal.

### Step-by-step Guide

#### 1. Join dash's community github organization

Describe overall step

1. Post your github username or an email address on the main project page to join the community
2. Wait to be added to the community organization

#### 2. create new repo
3. Sign in to Github and go to https://github.com/dashcommunity
4. Click the **plus icon** in the top, right-hand corner of the page
5. Select **dashcommunity** in the *Owner* field
6. Enter a name in the *Repository* field
7. Check the *Initialize this repository with a README* box
8. Click **Create repository** button

#### 3. Initialize a proposal

Describe overall step

1. Navigate to the repository you created in step 2 (if needed)
2. Click on the **Settings** tab
3. Scroll down to the *GitHub Pages* module
4. Click **Launch automatic page generator** button
5. Play around with editing the populated document, experimenting with the markdown menu features
6. Make some minor edits and click **Continue to layouts** (we'll come back later for further edits)
7. Choose a themes for your proposal (`minimal` is recommended)
8. Review, make changes if desired by clicking **edit**, and click **Publish** when finished
9  Note the message above ("Your project page has been created at...")
9. Open a browser and go to the URL Github made for you

#### 4. Populate your proposal with a template and customize

Describe overall step

1. Navigate to the repository you created in the step 1 (if needed)
2. Click on the **Settings** tab
2. ...


#### 1. Prepare the required data

Describe overall step

1. Create a text file to store proposal data
2. ...


#### 2. Create a document detailing your proposal 

Describe overall step

1. Open https://github.com/dashcommunity in a web browser
2. Create a new repository
2. ...


#### 3. Submit your proposal to the network

Describe overall step

1. Open Dash-Qt
2. ...


##### From dash.org documentation...

Preparation
Anyone can submit a Proposal for a small fee.
Choose a proposal name
Proposal names are limited to 20 characters.
Choose a unique proposal name to to prevent voter confusion.
The currently active proposals can be found by running 'mnbudget show' in the debug window or by visiting https://www.dashwhale.org/budget
Choose your payment amount and cycle duration.
The payment amount is fixed. You cannot vary your payment across cycles.
For instance: request 100 dash for 6 cycles to receive a total of 600 dash.
Write your proposal webpage/forum post
Explain your project.
Introduce yourself. Include your qualifications, experience and contact information for questions.
Estimate and outline the project requirements, progress milestones, and deliverables.
Continued funding may depend on reaching your stated goals.
The more detail the better. This page is your marketing and sales pitch.
Justify your funding request
Explain how the funds will be used. Detail your expenses and profit.
Shorten your proposal webpage/forum post url
Use a url shortening service such as: https://goo.gl/ or https://tinyurl.com/
Select your funding cycle start block
Choose a block far enough in the future to allow time for your proposal to be discussed and gain support. 
Allow at least one cycle (calendar month) for most proposals.
Consider longer incubation periods for larger funding requests.
Generate and backup your funding address
create a new address using one of:
the wallet interface "file -> receiving addresses... -> New button"
the debug console command 'getnewaddress'
create a backup of this new private key using one of:
the wallet interface "file -> backup wallet"
save to different media (usb key or second hard drive) -- in case of primary hard drive failure
the debug console command 'dumpprivkey <payment address>'
the output of the above command is called a WIF (Wallet Import Format) and is an unprotected private key
possession of the WIF means possession of the funds -- protect it accordingly
carefully write it down or
store it in an encrypted container
Structure
The following information is required to create a proposal:
proposal-name -- a unique label, 20 characters or less
url -- a proposer-created webpage or forum post containing detailed proposal information
payment-count -- how many cycles the proposal is requesting payment
block-start -- the requested start of proposal payments
dash-address -- the address to receive proposal payments
monthly-payment-dash -- the requested payment amount
Persistence
Proposals become active one day after submission.
Proposals will remain visible on the network until they are either disapproved or the proposal's last payment-cycle is reached.
Approval occurs when yes votes minus no votes equals 10% or more of the total available votes.
Disapproval occurs when no votes minus yes votes equals 10% or more of the total available votes.
The total available votes is the count of online and responding masternodes and can be seen by running the command 'masternode count' in any wallet debug window. A graph of the total masternode count can be found at http://178.254.18.153/~pub/masternode_count.png
Submitting
To prevent mistakes and loss of collateral funds, make sure you've completed all the tasks in the checklist below before submitting your proposal to the network.
Proposal Checklist
proposal name
is 20 characters or less in length
does not match any currently active proposal names
url
is a shortened url and retrieves proposal page
proposal page
contains enough information for voters to decide their vote
payment amount
is reasonable compensation for project scope
payment count
is appropriate compensation for project duration
payment address
is backed up
payment start block
is far enough in the future to allow for discussion and to gather voting support
Commands
Once prepared, submitting the proposal to the network requires running the following two commands.
The first command (prepare) will create your collateral transaction.
The collateral transaction must mature (reach six confirmations (about 20 minutes)) before running the second command.
The second command (submit) publishes your proposal for voting.
mnbudget prepare
This command will destroy 5 dash in preparation to submit the proposal.  Once run, you may not make any changes without incurring another 5 dash fee.
Insert your own values and run this command via the debug window or dash-cli to submit:
       mnbudget prepare proposal-name url payment-count block-start dash-address monthly-payment-dash false
Example: mnbudget prepare mar-12-2015-bakesale http://goo.gl/XjUFZV 1 415400 XmoocowYfrPKUR6p6M5aJZdVntQe71irCX 10 false
It will return the transaction id of the collateral for the now-prepared proposal. Use this transaction id in the following command. You may not use this collateral transaction for any proposal other than this. No proposal values may be changed between these two commands.
mnbudget submit
After the collateral transaction reaches six (6) confirmations, you may run this command to publish your proposal for voting.
Insert your own values and run this command via the debug window or dash-cli to submit.
Hint: hit up-arrow and change prepare to submit, then replace the 'false' at the end with the transaction id. 
       mnbudget submit proposal-name url payment-count block-start dash-address monthly-payment-dash mnbudget-prepare-transaction-id
Example: mnbudget submit mar-12-2015-bakesale http://goo.gl/XjUFZV 1 415400 XmoocowYfrPKUR6p6M5aJZdVntQe71irCX 10 e734430e1c283fe236abb6c5a2fb272f1b9d4fc6a60421507973c6c451119039
It will return the proposal hash, which other nodes will use to vote on it. Sample output: a2b29778ae82e45a973a94309ffa6aa2e2388b8f95b39ab3739f0078835f0491 
See Masternode Budget API for more details and example invocations.
Next steps
Once you have completed submitting your proposal to the network, it's time to get the word out.
Use social media to announce your proposal and contact community members to begin a discussion and gather voter support.
Project Proposal and Status UpdateTemplates
Project Proposal Template: Dash Project Proposal Template v1.0.docx
Project Status Update Template: Dash Project Status Update Template v1.0.docx

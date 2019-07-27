# Secure-Electronic-Voting \\ Microsoft codefundo++

Proposing a model consists of a app and two blockchains, one for maintaing a *distributive ledger* of vote cast and other for *verification, authentication* and *maintainance* of Voter IDs which also serve the purpose of electoral list.

### Problems addressed

* Preparation of *Electoral Rolls*
* Verification of individuals to allow voting
* Applying for/correction in *Voter IDs*
* Usage of *fake Voter IDs*
* Exclusion of *eligible voters*
* Unable to vote due to *reachability*
* Accusation related to *EVM Hacking*
* Maintainance of *EVMs*
* *Votes Counting* Period after Close of Poll

### Datasets used

* Aadhaar Cards
* Voter IDs

### Working of the purposed model 

* User login to the application is verified through *unique identification number* like Aadhaar(from UIDAI database), college ID etc.     which are backed by strong and discreet identification like *OTP, biometric or retina scans*.

  - ***Benefits:*** 
    - ***Verification throught his mode will remove deceitful participation.***

* For each user, a *public* and *private keypair* is generated (only on first login, remains same for future transaction) where public key act as a *sender/reciever public address* on the blockchain networks. The public key (not private key) generated is stored against the corresponding Aadhar in the Aadhar database maintained by govt. User can create new keypair, the same is updated in the database.

  - ***Benefits:*** 
    - ***Ensuring user privacy on the network.***
    
* Each account already present/created is updated with **one vote credit** only, before the election day.

* App can perform 2 types of *transactions* :
  - Cast a vote
  - Apply for a new or correction in Voter ID

* To apply for new/correction in Voter ID,
  - user will provide necessary details required for Voter ID that are encrypted using receiver's (i.e. Voter ID verification authorities) public key and along with other details(timestamp, Voter ID status etc.) are digitally signatured using sender's private key creating a new transaction towards verification authorities.
  - once the sender is verified, and transaction is added to blockchain using the appropiate *consensus mechanism*. The application for a Voter ID can be accessed by the authorities using their private key.
  - Aadhar details  of the sender are securely accessed from the database using his/her public key to verify the application for Voter ID.
  - Once verified, a new transaction is made by authorities towards concerned person in similar fashion, encrypting the new Voter ID using public key of the applicant.
  - Since all the transactions of applications of Voter IDs are recorded in blockchain, Voter ID details in the last transaction corresponding to user's public key are taken into account.
  
  - ***Benefits:***
    - ***Resolves the issue of fake/multiple voter ids since only the Voter ID details in the last transaction are taken into condideration.***
    - ***People can apply for a new/updated Voter ID online.***
    - ***If any Indian Citizen turns 18+ (which can verified using Aadhar) their Voter ID can be created and using his/her public key same can be updated in the ledger.***
    - ***People can see all their previous records of applications for new/updated Voter IDs.***
    - ***Authorites can revoke a person's voting rights by generating a new transaction (keeping other details same in VoterID of the person except the field 'Voter ID status' as true) towards him/her.***
    - ***Because of all the above benefits this ledger successfully serves the purpose of Electoral Roll.***
    - ***The problem of exclusion of eligible voters is also resolved.***
    
* For each candidate party, a account is created (by authorities/EC) and their public key is linked to the button corresponding to their logo in app.
  
* When a vote cast occurs,
  - the transaction(votes) will be directed to *only one public key (corresponding to the voted party ).* 
  - the transaction is generated containing details such as *public key of voter/reciever(i.e. Election Comission), voted party, timestamp* etc. which is *digitally signatured* using *private key* of voter.
  - **eligibility of the voter** is verified using the Voter ID ledger (generated above).
  - If eligible, transaction is verified using public key of the voter and added to blockchain using appropiate *consensus mechanism*.
  
  - ***Benefits***
    - ***Storing of votes as transaction in the blockchain resolves the issues related to EVM Hacking.***
    - ***Utilization of resources expended for maintainance of EVMs earlier.***
    - ***Concerned authority can use the account created for each party for real-time counting.***
    - ***Multiple voting are verified and removed during transaction verification before adding to blockchain.***
    
 * Booth camps can be set-up in rural areas to cater large population facing difficulty with modernized election process.

- ***Other Benefits:*** 
   - Citizen can vote online from anywhere due to availability of Electoral Roll in form of secure online ledger and Aadhar verification

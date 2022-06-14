# quest-submissions

## Chapter One ##

### Day One ###

#### 1. Explain what the Blockchain is in your own words. You can read this to help you, but you don't have to: https://www.investopedia.com/terms/b/blockchain.asp ####

A blockchain is an open, immutable, peer-to-peer network. It is most commonly thought of in conjunction with cryptocurrency and NFTs; however, the technology is also being utilized for other purposes such as IoT devices.

#### 2. Explain what a Smart Contract is. You can read this to help you, but you don't have to: https://www.ibm.com/topics/smart-contracts ####

Smart contracts are code deployed to the blockchain to help developers and users Read/Write information on a particular blockchain. They are powerful but brittle.

A smart contract is similar to a global static OOP class. There are a few important distinctions, such as how smart contracts are instantiated and stored on the blockchain. Once a smart contract is deployed, the information is there forever. The contract information and methods can be made inaccessible if the contract is designed with a "self destruct" catch in mind.

#### 3. Explain the difference between a script and a transaction. ####

In the context of Cadence & the Flow Blockchain: Scripts have read access and are free. Transactions have read/write access and require someone to pay a gas fee.

### Day Two ###

#### 1. What are the 5 Cadence Programming Language Pillars? ####

1. Safety and Security
2. Clarity
3. Approachability
4. Developer Experience
5. Resource Oriented Programming

#### 2. In your opinion, even without knowing anything about the Blockchain or coding, why could the 5 Pillars be useful (you don't have to answer this for #5)? ####

Safety and Security is crucial for several aspects. From a developer standpoint, I find it beneficial to have rules in place to prevent me from making mistakes. It's why I prefer Typescript over vanilla JS. Using a language with a "built in linter" prevents me from making mistakes. It forces me to design with more thought and purposefulness, which in turn leads to stronger and more secure code. From a user standpoint -- the blockchain has a ton of publicly accessible information. Few people would enjoy losing funds or privacy due to a security breach. 

In regards to 2-4. That's why I jumped on the Cadence train. Plutus was hard. Setting up the environment took a ton of storage and memory. Haskell is secure, but it is completely different from every other language that I know. Cadence has a similar feel to other languages with which I am already familiar. The learning curve doesn't seem too intense. Even though the playground is buggy -- it's significantly more user friendly than some other blockchain playgrounds. Having an easy developer onboarding process makes it easy for me to spend more time making mistakes in development instead of trying to figure out how to setup the environment. 

Resource Oriented Programming will be useful because it adds to #1. I find it pretty similar to OOP -- but with some added attention on how something is being instantiated, moved, and deleted. Resource Oriented Programming is an interesting innovation; I'm not sure we've seen the "true best practices" for this type of design. I think more innovation is coming. Maybe at a conference or hackathon, and certainly from someone much smarter than me!

## Chapter 2 ##

### Day One ###

#### 1. Deploy a contract to account 0x03 called "JacobTucker". Inside that contract, declare a constant variable named is, and make it have type String. Initialize it to "the best" when your contract gets deployed. ####

<img width="1678" alt="Chapter2_Day1_Question1" src="https://user-images.githubusercontent.com/46829117/173191315-b0591b16-5cd1-4eef-982d-380b0fbb74a6.png">

#### 2. Check that your variable is actually equals "the best" by executing a script to read that variable. Include a screenshot of the output. ####

<img width="1680" alt="Chapter2_Day1_Question2" src="https://user-images.githubusercontent.com/46829117/173191327-aa71cab9-0146-4f48-b646-f497c53c58e4.png">

### Day Two ###

#### 1. Explain why we wouldn't call changeGreeting in a script. ####

chaingeGreeting is modifying the state on blockchain. This behavior is reserved for transactions on the Flow blockchain. 

#### 2. What does the AuthAccount mean in the prepare phase of the transaction? ####

In the context of the "prepare phase" of the transaction, AuthAccount is an account that is signing (approving) the transaction. AuthAccount is one of two types of accounts. Full permissions to the AuthAccount allows someone to access storage, public keys, and code.

#### 3. What is the difference between the prepare phase and the execute phase in the transaction? ####

They are supposed to handle different logic for the transaction. The prepare phase should be dedicated to handling logic that requires the use of AuthAccount. The execute phase should handle all of the "main" logic. The execute phase can access PublicAccount -- which has limited read access of an Account. One example explaining the difference would be a token transfer. The withdrawal should be in the prepare phase because it requires access to account storage. Account storage is accessed using AuthAccount. The deposit should be used in the execute phase.

There are two other phases (pre/post) for conditional checks that can be included as well.

#### 4. Add two new things inside your contract: ####

<img width="1672" alt="Chapter2Question4_contract" src="https://user-images.githubusercontent.com/46829117/173686701-7add5fb7-bd1f-4956-b5e5-872bf01d31a3.png">
<img width="1680" alt="Chapter2Question4_transaction" src="https://user-images.githubusercontent.com/46829117/173686739-c8c38bdd-c000-491e-88f3-a6b694d11617.png">
<img width="1677" alt="Chapter2Question4_script1" src="https://user-images.githubusercontent.com/46829117/173686752-c8a89e17-2d80-4a90-b65b-8eb594246efe.png">
<img width="1680" alt="Chapter2Question4_script2" src="https://user-images.githubusercontent.com/46829117/173686763-5aa0e175-0f2e-41c5-9479-0719ac5e159b.png">

### Day Three ###

#### 1. In a script, initialize an array (that has length == 3) of your favourite people, represented as Strings, and log it. ####
<img width="1678" alt="Chapter2Day3Question1" src="https://user-images.githubusercontent.com/46829117/173687948-2c9b2fcf-d4d2-478e-889a-a4492e51bea4.png">

#### 2. In a script, initialize a dictionary that maps the Strings Facebook, Instagram, Twitter, YouTube, Reddit, and LinkedIn to a UInt64 that represents the order in which you use them from most to least. For example, YouTube --> 1, Reddit --> 2, etc. If you've never used one before, map it to 0! ####

#### 3. Explain what the force unwrap operator ! does, with an example different from the one I showed you (you can just change the type). ####

#### 4. Using this picture below, explain...What the error message means, Why we're getting this error, How to fix it ####

![image](https://user-images.githubusercontent.com/46829117/173687560-3577c594-b2b3-4697-b932-012834413451.png)


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


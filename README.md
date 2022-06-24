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
<img width="1678" alt="Chapter2Day3Question2" src="https://user-images.githubusercontent.com/46829117/174126781-ef323bb9-6e2d-4d45-9f0f-4aff3e6f48a6.png">

#### 3. Explain what the force unwrap operator ! does, with an example different from the one I showed you (you can just change the type). ####
In essence, the force-unwrap operator "!" strips away the "optional" wrapper and exposes what is underneath. If the Optional was empty, then it contains nil. If it contains nil, then the force unwrap will panic. If it is not nil then it will provide whatever type was underneath. For example: 

```
var favNumber: Int? = 6
var unwrappedFavNumber: Int = favNumber! // The "?" at the end of "Int?" is gone. This means the Optional has been removed and the type is *just* Int.

var leastFavNumber: Int? = nil
var unwrappedLeastFavNumber: Int = leastFavNumber! // PANICS! The program will abort because "Int" cannot be of type "nil". Without the optional wrapper, the compiler won't be able to process unwrappedLeastFavNumber.
```
#### 4. Using this picture below, explain...What the error message means, Why we're getting this error, How to fix it ####

![image](https://user-images.githubusercontent.com/46829117/173687560-3577c594-b2b3-4697-b932-012834413451.png)

1. This error message means that the compiler expected the method to return a type of "String" but the method is actually returning a type of Optional<String> (an Optional containing String).
  
2. We are getting this error because we declared a return type of String and are returning an Optional.
  
3. We can fix this in three different ways. First, we could declare the return type as `String?` instead of `String`. Alternatively, we could force unwrap `thing[0x03]` by writing `thing[0x03]!`. Another option would be to add a panic catch at the end. See "Third Option" for an explanation of this fix.

```
//First option:
pub fun main(): String? {
    let thing: {Address: String} = {0x01: "One", 0x02: "Two", 0x03: "Three"}
    return thing[0x03]
}

//Second option:
pub fun main(): String {
    let thing: {Address: String} = {0x01: "One", 0x02: "Two", 0x03: "Three"}
    return thing[0x03]!
}
//Third option:
pub fun main(): String {
    let thing: {Address: String} = {0x01: "One", 0x02: "Two", 0x03: "Three"}
    return thing[0x03] ?? panic("Does not exist. Loser!")
}
```
### Day Four ###

#### 1. Deploy a new contract that has a Struct of your choosing inside of it (must be different than Profile). ####
See code block below.
#### 2. Create a dictionary or array that contains the Struct you defined. ####
See code block below.
#### 3. Create a function to add to that array/dictionary. ####
```
pub contract ChapterTwoDayFour {
  
  pub var countries: {Address: Country}

  pub struct Country {
      pub let name: String
      pub let population: UInt64
      pub let gdp: UFix64
      pub let type: CountryTier
      pub let account: Address

      init(name: String, population: UInt64, gdp: UFix64, type: CountryTier, account: Address) {
        self.name = name
        self.population = population
        self.gdp = gdp
        self.type = type
        self.account = account
      }
  }

  pub enum CountryTier: UInt8 {
    pub case first
    pub case second
    pub case third
  }

  pub fun addCountry(name: String, population: UInt64, gdp: UFix64, type: CountryTier, account: Address) {
      let country = Country(name: name, population: population, gdp: gdp, type: type, account: account)
      self.countries[account] = country
  }

  init() {
    self.countries = {}
  }

}
```
#### 4. Add a transaction to call that function in step 3. ####
```
import ChapterTwoDayFour from 0x01

transaction(name: String, population: UInt64, gdp: UFix64, account: Address) {

  prepare(acct: AuthAccount) {}

  //I couldn't figure out how to get enumerations to work in the playground so I hardcoded it.
  execute {
      ChapterTwoDayFour.addCountry(name: name, population: population, gdp: gdp, type: ChapterTwoDayFour.CountryTier.first, account: account)
      log("Country Added")
  }
}
```
#### 5. Add a script to read the Struct you defined. ####
```
import ChapterTwoDayFour from 0x01

pub fun main(account: Address): ChapterTwoDayFour.Country {
  return ChapterTwoDayFour.countries[account] ?? panic("There's nothing here bud")
}
```

## Chapter Three ##

### Day One ###

#### 1. In words, list 3 reasons why structs are different from resources. ####
* Structs can be instantiated outside of the contract, and in a similar way to other variables/classes. Resources can only be instantiated using the `create` command, which must be declared in the contract (usually within a method inside a controlled role). Resources cannot be instantiated outside of the contract.
* Structs are meant to be copied, they are value types whereas Resources are moved. Resources are linear types and must be used exactly once.
* Structs are useful for representing information in a logical way but the information doesn't contain value or require ownership or transfer. 
#### 2. Describe a situation where a resource might be better to use than a struct. ####
I want to start issuing college diplomas on the blockchain. In order to do that I would need to create a strict NFT (maybe even use the new Soulbond token standard). I wouldn't want anyone to be able to create and hand these out; I would want this to be secure. I would also only want to issue one official diploma per individual. In this case, a Resource would be better than a Struct. However, a Struct would be preferred for storing general information about the students, departments, professors, etc.
#### 3. What is the keyword to make a new resource? ####
`create`
#### 4. Can a resource be created in a script or transaction (assuming there isn't a public function to create one)? ####
No.
#### 5. What is the type of the resource below? ####
```
pub resource Jacob {

}
```
I'm not exactly sure what this question is asking, so I'm going to throw out a few answers and hope one sticks.

Resources are a composite type. 

@Jacob

Resources are of composite type "Resource". Brando has electrolytes. It's what plants crave. Plants crave electrolytes. Brando has electrolytes.
#### 6. Let's play the "I Spy" game from when we were kids. I Spy 4 things wrong with this code. Please fix them. ####
```
pub contract Test {

    // Hint: There's nothing wrong here ;)
    pub resource Jacob {
        pub let rocks: Bool
        init() {
            self.rocks = true
        }
    }

    pub fun createJacob(): Jacob { // there is 1 here
        let myJacob = Jacob() // there are 2 here
        return myJacob // there is 1 here
    }
}
```

Fixed method below:

```
    pub fun createJacob(): @Jacob { 
        let myJacob <- create Jacob()
        return <- myJacob
    }
```
### Day Two ###

#### 1. Write your own smart contract that contains two state variables: an array of resources, and a dictionary of resources. Add functions to remove and add to each of them. They must be different from the examples above. ####

```
pub contract Pantheon {

  pub var listOfGods: @[God]

  pub fun addNewGod(god: @God) {
    self.listOfGods.append(<- god)
  }

  pub fun removeGodByIndex(index: Int): @God {
    return <- self.listOfGods.remove(at: index)
  }

  pub resource God {
    pub let name: String
    pub var powers: @{PowerType: Power}

    init(name: String) {
      self.name = name
      self.powers <- {}
    }

    pub fun addNewPower(power: @Power) {
        let key = power.powerType
        
        let oldPower <- self.powers[key] <- power
        destroy oldPower
    }

    pub fun removePowerByType(powerType: PowerType): @Power {
      let power <- self.powers.remove(key: powerType) ?? panic("Could not find a power of that type.")
      return <- power
    }

    destroy() {
      destroy <- self.powers
    }

  }

  pub resource Power {
      pub let name: String
      pub let description: String
      pub let powerType: PowerType

      init(name: String, description: String, powerType: PowerType) {
        self.name = name
        self.description = description
        self.powerType = powerType
      }
  }

  pub enum PowerType: UInt8 {
    pub case offense
    pub case deffense
    pub case special
  }

  init() {
    self.listOfGods <- []
  }

}
```

### Day Three ###

#### 1. Define your own contract that stores a dictionary of resources. Add a function to get a reference to one of the resources in the dictionary.####

```
pub contract Quest {

    pub var dic: @{UInt64: QuestResource}

    pub resource QuestResource {

        pub let name: String

        init(name: String) {
            self.name = name
        }
    }

    pub fun getReference(key: UInt64): &QuestResource {
        return (&self.dic[key] as &QuestResource?) ?? panic("Nothing here bruv")
    }

    init() {
        self.dic <- {
            1: <- create QuestResource(name: "John"),
            2: <- create QuestResource(name: "Jacob"),
            3: <- create QuestResource(name: "Jingleheimerschmidtt")
        }
    }
}
```

#### 2. Create a script that reads information from that resource using the reference from the function you defined in part 1. ####
```
//Create a script that reads information from that resource using the reference from the function you defined in part 1.
import Quest from 0x01

pub fun main(): String {
  let ref = Quest.getReference(key: 1)
  return ref.name // returns John
}
```
#### 3. Explain, in your own words, why references can be useful in Cadence. ####
References are useful because they let us interact with Resources without having to move them. The whole point of Resources is that they need to be secure. Requiring a dev to code movement of a Resource everytime someone needed to execute a READ would not only be tedious, but dangerous. Humans are prone to errors. As secure as Cadence is -- this design has the potential to invite bugs. References not only promote security and more elegent design patterns in the codebase, but also convenience for the engineers.

### Day Four ###

#### 1. Explain, in your own words, the 2 things resource interfaces can be used for (we went over both in today's content) ####

1. Interfaces allow devs to create templates that can be used throughout the codebase.
2. Templates promote security through limiting exposure and promoting consistency of implementation among the engineers.
              
#### 2. Define your own contract. Make your own resource interface and a resource that implements the interface. Create 2 functions. In the 1st function, show an example of not restricting the type of the resource and accessing its content. In the 2nd function, show an example of restricting the type of the resource and NOT being able to access its content. ####

```
/*2. Define your own contract. Make your own resource interface and a resource that implements the interface. 
Create 2 functions. In the 1st function, show an example of not restricting the type of the resource 
and accessing its content.
 In the 2nd function, show an example of restricting the type of the resource and NOT being 
 able to access its content.
*/

pub contract Space {

    pub resource interface Mandatory {
        pub name: String
    }

    pub resource Rocket: Mandatory {
        pub let name: String
        pub var thrusters: UInt64

        pub fun causeAccident() {
            if (self.thrusters > 0) {
                self.thrusters = self.thrusters - 1
                log("Oh damn we're down to ".concat(self.thrusters.toString()).concat(" thrusters!"))
            } else {
                panic("Shit we're gonna explode")
            }
            
        }

        init(name: String) {
            self.name = name
            self.thrusters = 2
        }
    }

    //Not Restricted
    pub fun successDamageRocket() {
        let newRocket: @Rocket <- create Rocket(name: "Jacob")
        newRocket.causeAccident()
        newRocket.causeAccident()
        destroy  newRocket
    }

    //Restricted
    pub fun failDamageRocket() {
        let newRocket: @Rocket{Mandatory} <- create Rocket(name: "Jacob")
        // newRocket.causeAccident() // This will not work due to restricted type
        destroy newRocket

    }
}
```

#### 3. How would we fix this code? ####

```
              pub contract Stuff {

    pub struct interface ITest {
      pub var greeting: String
      pub var favouriteFruit: String
    }

    // ERROR:
    // `structure Stuff.Test does not conform 
    // to structure interface Stuff.ITest`
    pub struct Test: ITest {
      pub var greeting: String

      pub fun changeGreeting(newGreeting: String): String {
        self.greeting = newGreeting
        return self.greeting // returns the new greeting
      }

      init() {
        self.greeting = "Hello!"
      }
    }

    pub fun fixThis() {
      let test: Test{ITest} = Test()
      let newGreeting = test.changeGreeting(newGreeting: "Bonjour!") // ERROR HERE: `member of restricted type is not accessible: changeGreeting`
      log(newGreeting)
    }
}
```

The working refactored code is below:

```
pub contract Stuff {

    pub struct interface ITest {
      pub var greeting: String
      pub var favoriteFruit: String
    }

    pub struct Test: ITest {
      pub var greeting: String
      pub var favoriteFruit: String

      pub fun changeGreeting(newGreeting: String): String {
        self.greeting = newGreeting
        return self.greeting // returns the new greeting
      }

      init() {
        self.greeting = "Hello!"
        self.favoriteFruit = "Starfruit"
      }
    }

    pub fun fixThis() {
      let test: Test = Test()
      let newGreeting = test.changeGreeting(newGreeting: "Bonjour!")
      log(newGreeting)
    }
}
```
              
### Day Five ###

### Question One: For today's quest, you will be looking at a contract and a script. You will be looking at 4 variables (a, b, c, d) and 3 functions (publicFunc, contractFunc, privateFunc) defined in SomeContract. In each AREA (1, 2, 3, and 4), I want you to do the following: for each variable (a, b, c, and d), tell me in which areas they can be read (read scope) and which areas they can be modified (write scope). For each function (publicFunc, contractFunc, and privateFunc), simply tell me where they can be called. ###

```
access(all) contract SomeContract {
    pub var testStruct: SomeStruct

    pub struct SomeStruct {

        //
        // 4 Variables
        //

        pub(set) var a: String

        pub var b: String

        access(contract) var c: String

        access(self) var d: String

        //
        // 3 Functions
        //

        pub fun publicFunc() {}

        access(contract) fun contractFunc() {}

        access(self) fun privateFunc() {}


        pub fun structFunc() {
            /**************/
            /*** AREA 1 ***/
            /**************/
        }

        init() {
            self.a = "a"
            self.b = "b"
            self.c = "c"
            self.d = "d"
        }
    }

    pub resource SomeResource {
        pub var e: Int

        pub fun resourceFunc() {
            /**************/
            /*** AREA 2 ***/
            /**************/
        }

        init() {
            self.e = 17
        }
    }

    pub fun createSomeResource(): @SomeResource {
        return <- create SomeResource()
    }

    pub fun questsAreFun() {
        /**************/
        /*** AREA 3 ****/
        /**************/
    }

    init() {
        self.testStruct = SomeStruct()
    }
}
```
This is a script that imports the contract above:
```
import SomeContract from 0x01

pub fun main() {
  /**************/
  /*** AREA 4 ***/
  /**************/
}
```
##### A Scope #####
Read: Everywhere (1,2,3,4)
Write: Everywhere (1,2,3,4)
##### B Scope #####
Read: Everywhere (1,2,3,4)
Write: Contract & Inner (1). If we wanted to alter it elsewhere we would need to include a setter function in the struct.
##### C Scope #####
Read: Current, inner, containing contract (1,2,3,4)
Write: Current, inner (1)
##### D Scope #####
Read: Current, inner (1)
Write: Current, inner (1)
##### publicFunc Scope #####
Everywhere. Transactions, scripts, what have you. (1,2,3,4)
##### contractFunc Scope #####
Within the current contract (Current, inner, containing contract). (1,2,3)
##### privateFunc Scope #####
Current/Inner. (1)

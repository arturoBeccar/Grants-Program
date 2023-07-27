# Blacksmith CoinFabrik
- **Team Name:** CoinFabrik (Nektra S.A)
- **Payment Address:** 0xf488039EDe6B38D7689fDCC6A9FC2dd0EF39D54e (USDC)
- **[Level](https://github.com/w3f/Grants-Program/tree/master#level_slider-levels):** 3

## Project Overview :page_facing_up:

### Overview

Blacksmith 1: Flattening the Anvil

CoinFabrik has successfully accomplished two previous grant milestones for the development of Scout, an open source bug-detection tool for ink! targetted to developers and smart contract auditors.

We have completed a [Proof of Concept](https://github.com/CoinFabrik/web3-grant ) and a [Prototype](https://github.com/CoinFabrik/scout ).

During these iterations, we encountered certain challenges, especially while developing fuzzing detectors. These challenges included limited integration tests and differences with the ink! E2E testing environment. Specifically, we faced difficulties when working with functions related to cross contract calls, storage, gas usage, and delegatecall.

With this grant, our objective is to conduct a comprehensive analysis to identify any other missing functionalities in integration tests, and to propose and develop new testing features based on our findings.


### Project Details

As mentioned before, we have already identified a number of E2E functionalities that are not present in integration tests. For example:
- A different implementation of storage in integration testing.
- Inability to perform delegatecall in integration tests. 
- Inability to perform contract-to-contract calls in integration tests.
- Gas consumption is not integrated.
- Inconsistencies.

This analysis is not exhaustive, as it simply highlights some difficulties encountered while performing another task. Therefore, as you will see later on, our proposal is to begin the work by conducting a more comprehensive and focused analysis.

Furthermore, we have not been able to thoroughly analyze the complexity or feasibility of generating the necessary tests. The analysis we just mentioned will allow us to better understand which improvements will truly be possible to develop.


### Ecosystem Fit

Having a comprehensive set of tests would bring numerous benefits to the entire community, including improved reliability, code quality, and rapid feedback loops.

For our work on [Scout](https://github.com/CoinFabrik/scout), this would help us in building fuzzing detectors, as we use integration tests during their development as they are quicker than E2E tests.

## Team :busts_in_silhouette:

### Team members

- Ariel Wassbein, Head of Research.
- Diego Kelyacoubian, Head of Program Management.
- Valeria Caracciolo, Business Development.
- CoinFabrik's development and auditing team.


### Contact

- **Contact Name:** Valeria Caracciolo
- **Contact Email:** valeria.caracciolo@coinfabrik.com
- **Website:** https://www.coinfabrik.com/ 

### Legal Structure

- **Registered Address:** Dr. Emilio Ravignani 2394, C1425 CABA, Argentina.
- **Registered Legal Entity:** Nektra S.A.

### Team's experience
We are a research and development company specialized in Web3, with a strong background in cybersecurity. Founded in 2014, we have worked on over 200 blockchain-related projects, EVM based and also for Solana, Algorand, and Polkadot. Beyond development, we offer security audits through a dedicated in-house team of senior cybersecurity professionals, currently working on code in Substrate, Solidity, Clarity, Rust, and TEAL.

Our team has an academic background in computer science and mathematics, with work experience focused on cybersecurity and software development, including academic publications, patents turned into products, and conference presentations. Furthermore, we have an ongoing collaboration on knowledge transfer and open-source projects with the University of Buenos Aires.

As well, CoinFabrik has been providing Quality Assurance as a service to development teams, accumulating valuable expertise in the field for a considerable period of time. Our clients highly appreciate this service, and as a result, we are eager to expand our capabilities to the ink! ecosystem.

### Team Code Repos

- https://github.com/CoinFabrik
- https://github.com/CoinFabrik/scout
- https://github.com/CoinFabrik/web3-grant

### Team LinkedIn Profiles (if available)

- https://www.linkedin.com/in/arielwaissbein/
- https://www.linkedin.com/in/diego-kelyacoubian-5417613/ 
- https://www.linkedin.com/in/valeriacaracciolo/  


## Development Status :open_book:

Since this application is the result of some previous work, we have already identified some improvements in integration tests, with different levels of complexity:
- Alice and Bob's addresses should match: Feasible.
- The storage in the integration environment should have the same limitations as in the blockchain environment (end-to-end): Feasible.
- Delegate call: Ability to use delegate call in integration tests: Complex, yet feasible.
- Contract-to-contract calls: To be evaluated.
- Gas usage: To be evaluated.


We briefly validated the idea of the analysis and development described in this application with Sam Ruberti from the ink! Ecosystem and David Hawig from Web3 Foundation, who encouraged us to apply for this grant.

## Development Roadmap :nut_and_bolt:

### Overview

- **Total Estimated Duration:** 6 weeks
- **Full-Time Equivalent (FTE):**  2.5 FTE
(0.25 Project Manager,
0.25 Tech Lead,
1 Full time Sr. Rust Developer,
1 Full Time SemiSr. Rust Developer)
- **Total Costs:**  U$D


### Milestone 1: Analysis
- **Estimated duration:** 2 weeks
- **FTE:**  2.75
- **Costs:** 

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | MIT
| 0b. | Documentation | Create a comprehensive report that compares the functionalities of Integration tests and E2E (End-to-End) tests. The report should focus on identifying what can be accomplished in E2E tests but not in Integration tests, as well as any inconsistencies found. If applicable, we will provide suggestions that are not covered by either test type.
| 0c. | Testing and Testing Guide | No tests will be produced at this stage.
| 0d. | Docker | Does not apply at this stage.
| 0e. | Article | We will prepare a summary report and publish it on our blog https://blog.coinfabrik.com/ 
 **1** | Analyze | Study and compare Integration Tests and E2E (End-to-End) tests in ink!.
 **2** | Evaluate | Assign a complexity level (ranging from 1 to 3, with 1 being the least complex and 3 being the most complex) to each finding.
 **3** | Estimate | Indicate which tests shall be developed during the Milestone #2 (see below) delivery. If the allocated four weeks for Milestone #2 prove to be insufficient, we may consider requesting an extension for this grant.


### Milestone 2: Execution
- **Estimated duration:** 4 weeks
- **FTE:** 2.75
- **Costs:** 

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| 0a. | License | MIT
| 0b. | Documentation | We will provide an update to the Milestone #1 report, including the current status of all identified use cases.
| 0c. | Testing and Testing Guide | We will develop the missing or improvable functionalities identified in Milestone #1, and submit a pull request to the corresponding Parity repository. We will also provide a Testing Guide with documentation and examples on how to use the developed new functionalities.
| 0d. | Docker | Does not apply at this stage.
| 0e. | Article | We will update the summary report with the progress of the development and publish it on our blog at https://blog.coinfabrik.com/.
 **1** | Develop | Build the necessary improvements and missing tests for the identified use cases outlined in Milestone #1.
 **2** | Analyze and Estimate | Consider the development of additional tests throughout the duration of this milestone or subsequent milestones.


## Future Plans

Once we are content with the development of the identified use case, our subsequent task is to commence researching a testing automation solution, along with its associated tools, within the framework of ink! smart contracts.

Additionally, in a separate direction, we will be seeking funding to finalize a beta release of the bug-detection tool [Scout](https://coinfabrik.github.io/scout/ ), which will undoubtedly benefit from the culmination of this work.
## Referral Program (optional) :moneybag: 

## Additional Information :heavy_plus_sign:

**How did you hear about the Grants Program?** Richard Casey from Parity brought this program to our attention, and we have already successfully delivered two applications as a result.

During our inquiries for this application, we briefly consulted Sam Ruberti from the ink! Team and David Hawig from the Web3 Foundation. Their encouragement motivated us to proceed with this presentation.


# Tom Tutone T3A1-Workbook

- Due 18.8.24 (3 weeks)
- [https://ait.instructure.com/courses/5200/assignments/56761]

Sources:

- consider if people in the industry would trust it e.g./ AWS data

## Q1. Provide an overview and description of a standard source control process for a large project /6

- large project, multiple people, use other git features
- Provides an extensive overview and description of a standard source control process

- ![Git function diagram](https://homes.cs.washington.edu/~mernst/advice/version-control-ops-local-vs-remote.svg)
- practice conflict resolution [Git conflict resolution tutorial](https://rawgit.com/mernst/git-conflict-tutorial/master/git-conflict-resolution.html)

When working on a large-scale project, backing up the project and having it easily accessible to team members is a fundamental consideration. Source control software, such as Git and Mecurial, is the industry standard for programmers to share and work on projects concurrently. These tools monitor changes in a project's files, integrate them into a defined "main" collection and provide tools for updating or regressing this collection so that team members can access the project's most current, stable files.

In a standard large-scale project using source control software, it is mandatory that team members agree upon a protocol for saving changes to the main files. This includes designating standardised naming and commenting conventions, rules for the scope of each change and how the team will manage conflicting opinions and edits. In the context of Git, a team must decide where the project will be hosted, how each commit message needs to be structured, protocol for updating code that multiple users concurrently depend on, such as an initialisation module, and designating when changes should be merged to the main branch. To manage these challenges, there are a variety of commonly used best practices a large project can use.

Using branches allows team members to copy the main files of a project and edit them separately without affecting other branches. Teams typically create branches with a distinct intention in mind such as fixing a bug or implementing a feature. When this development is finished, the individual can then create a pull request which proposes the changes to the main branch so that they can be reviewed and integrated when all team members, or a designated manager, confirm that they are ready. Branches allow for clean, auditable updates to the project's main files as, when the branch is integrated, it will be committed with a clear scope, message and date (Ernst, 2024a). Notably, it is typically recommended that branches are squashed before they are committed because merging the branch to the main branch is the key notable moment and commit message rather than the branch's gradual changing (Ernst, 2024b). It is also important that branches remain within scope so that they do not create merge conflicts for other branches.

Team members must make sure not to edit code that multiple branches are dependent on without first creating a new branch as, when each branch is eventually submitted, there will be a collection of core documents, all distinct and raising merge issues. Merge issues are challenging to solve as they can break different branches work and, if they are not confronted until later, will be doubly challenging due to time stress (Ernst, 2024a). For this reason, team members need to communicate clearly about what they are editing and make sure their branches are all focused. For the same reason, it is crucial that in-progress branches pull from the main branch daily or more frequently depending on the project's update frequency. Team members must ensure they are working on the most up-to-date, main branch code as this will allow them prevent merge conflicts before they become too embedded into their updates. Finally, when commencing a branch, such as a bug fix patch, it is great practice to generate tests before work begins. Creating tests which currently fail but will resolve once the changes are implemented gradually ensures the project's robustness, archives the project's development and helps lock-in a branch's scope. When the branch is integrated, its intented impact can be clearly tracked in the tests and these features can be preserved in future branches easily (Ernst, 2024b).

### References

Ernst, M. (2024a) _[How to create and review a GitHub pull request](https://homes.cs.washington.edu/~mernst/advice/github-pull-request.html)_, Computer Science & Engineering University of Washington Community Website, accessed 27 July 2024.

Ernst, M. (2024b) _[Version control concepts and best practices](https://homes.cs.washington.edu/~mernst/advice/version-control.html)_, Computer Science & Engineering University of Washington Community Website, accessed 22 July 2024.

## Q2. What are the most important aspects of quality software? /6

- conceptual, good lists that outline it, reference
- List discuss and demonstrate 6 software quality characteristics

When designing software, a project typically involves by considering an issue, understanding why it occurs and generating a tool to solve it. Its apparent that the tool needs to function in its developmental context but, creating quality software requires a more robust solution that can work in varied contexts over a longer period of time. Boehm's (1976) software quality model and the ISO's (International Organization for Standardization) 25010 publication (ISO 25000, 2022) provide frameworks for describing and designing quality software.

Both Boehm and the ISO describe the importance of a software being portable. Portablility refers to a software's ability to function on varied machines with varied hardware specifications. When designing a tool, developer's must consider the contexts they are designing within and the capability of their development hardware. It is little use to potential users if their computers or internet connections cannot operate a program without it causing an error due to freezing or timeout. Developer's must consider their target users and the tools they will already have access to.

Notably, Boehm describes how portability often works in opposition to efficiency as a program can be optimised for a particular system but function worse on other systems (Boehm, 1976). Efficiency in quality software describes utilising the available resources for that software to run. This can refer to processing power but also refers to other resources which aid the software's function. A common example of efficiency is designing web applications for desktops versus mobiles. Efficiency in this context refers not only to processing power but also efficiency in communicating information and utilising the screen space by making a responsive layout. Quality software considers the tools available in the different contexts that the software will be used in and maximises them.

Portability also complements flexibility and the ability for a software to be scaled (ISO 25000, 2022). Software developers need to consider how their tools will be implemented into workflows and how much data they may need to handle. Quality software can be used across systems, installed easily and handle varying data loads.

Both models also emphasise interaction capability (ISO 25000, 2022) and the ease of use of software. ISO furthers usability and describes that a quality software must be reasonable to learn as well. Usability is a fundamental concern of software design as the tool, in essence, does not work if individuals cannot use it. Learnability is an important consideration however, as it accentuates the need to understand user contexts. Understanding who will use a tool allows developers to tune the interface or functionality so that it is logical to users.

One point of difference between the two models is that the ISO 25010 describes security as a neccessity of quality software (ISO 25000, 2022) whereas Boehm's does not. This can likely be attributed to an increased emphasis on data privacy in the internet age. When designing software, developers must consider the risks that the tool generates for users including system vulnerabilities and the storage of their data. It is essential that users are guaranteed confidentiality when using a software as privacy is as much of a resource to consider for users as time and financial costs. Security also encompasses data integrity and user confirmation that saved data is consistent and reliable. Software must implement reliable data storage and access to be considered effective.

Finally, both models value maintainability and the ease that software can be updated. At a coding level, maintainability means producing code that is clearly modularised and formatted so that bugs can be fixed cleanly and without large overhauls. At the user level, maintainability requires users to be able to install updates easily or update their own processes using the app logically.

Creating quality software requires clear planning and considerate implementation so that tools function as intended in varied, future-proof contexts. Developers must strive to create portable, efficient, flexible, useable, maintainable and secure software and, to do so, must consider the different contexts that the software will be used in.

### References

ISO 25000 (2022) _[ISO/IEC 25010](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010)_, ISO 25000 website, accessed 27 July 2024.

Boehm, B. W., Brown, J. R. and Lipow, M., (1976). ‘Quantitative Evaluation of Software Quality’, _Proceedings of the 2nd international conference on Software engineering_, pp. 592-605. DOI: 10.5555/800253.807736.

## Q3. Outline a standard high level structure for a MERN stack application and explain the components /6

- REACT, express data, Mongo, Node, how the techs work together to make the app
- Shows almost flawless understanding of the high level structure of the app

## Q4. A team is about to engage in a project, developing a website for a small business. What knowledge and skills would they need in order to develop the project? /6

- technical, soft skills too
- Effectively describes a range of skills and knowledge required by IT workers to complete a quality web development project

## Q5. With reference to one of your own projects, discuss what knowledge or skills were required to complete your project, and to overcome challenges /6

- assignments, side projects
- challenges you overcame extrapolated
- Effectively describes a range of skills and knowledge used to complete a project.

## Q6. With reference to one of your own projects, evaluate how effective your knowledge and skills were for this project, and suggest changes or improvements for future projects of a similar nature /6

- here's what I would do differently
- Evaluates effectiveness of knowledge and skills accurately, providing examples, and providing an insightful improvement on each skill

## Q7. Explain control flow, using an example from the JavaScript programming language /6

- if statements
- Provides a thorough explanation of control flow in programming

## Q8. Explain type coercion, using examples from the JavaScript programming language /6

- quirks that are unique to JS
- Provides a thorough explanation of control flow in programming

## Q9. Explain data types, using examples from the JavaScript programming language /6

- types, unique to JS, show what the concept is and how to use it
- Provides a thorough explanation of data types in programming

## Q10. Explain how arrays can be manipulated in JavaScript, using examples from the JavaScript programming language /6

- explain a concept, how to use it
- Demonstrates an extensive ability to manipulate arrays
- .filter, .map, .sort

## Q11. Explain how objects can be manipulated in JavaScript, using examples from the JavaScript programming language /6

- Demonstrates an extensive ability to manipulate objects

## Q12. Explain how JSON can be manipulated in JavaScript, using examples from the JavaScript programming language /6

- Demonstrates an extensive ability to manipulate JSON

Amazon Web Services (2024) _[What is SQL?](https://aws.amazon.com/what-is/sql/)_, AWS website, accessed 24 May 2024.

Hanlon, M., Dooley, R., Mock, S., Dahan, M., Nuthulapati, P. & Hurley, P. (2011). _Benefits of NoSQL databases for portals & science gateways_. DOI: [10.1145/2016741.2016780](https://doi.org/10.1145/2016741.2016780).

PostgreSQL Documentation (n.d.) _[13.1 Introduction: Chapter 13 Concurrency Control](https://www.postgresql.org/docs/16/mvcc-intro.html)_, PostgreSQL website, accessed 6 June 2024.

---------------------------------------------------SUBMISSION---------------------------------------------------

- submit as .pdf
- naming convention: LukeSkywalker_T2A2-A.pdf

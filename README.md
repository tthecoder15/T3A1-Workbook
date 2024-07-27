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

---------------------------------------------------SUBMISSION---------------------------------------------------

- submit as .pdf
- naming convention: LukeSkywalker_T2A2-A.pdf

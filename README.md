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

The MERN stack is a popular collection of technologies which can be used to create a dynamic web application. MERN stands for MongoDB, Express, React JS and Node.js, four tools which all use Javascript syntax and complimentarily fill the roles required to generate webpages, handle interactions with them and serve and store their data.

React JS is the front-end component of the MERN stack and is a web framework used to create fast-loading, responsive webpages. React uses JSX, a Javascript syntax extension which hybridises JS with HTML so that users can easily describe stateful webpages. React uses component-based design where the different elements of a website are modularised to be reused like building blocks and pieced together to create a webpage. React is powerful thanks to its underlying virtual DOM technologies. The virtual DOM is a recreation of the DOM (Document Object Model) which describes the elements of a webpage as a JS object. React creates an exact replica of the DOM as it is rendered as well as a new copy whenever the webpage is to be changed. The two iterations are compared to identify where the changes take place so that the true DOM can be updated compartmentally to reflect the changes (GeeksforGeeks, 2024). This is different to the true DOM which requires an entire reload when the page changes and this allows React display pages more efficiently.

Express is a Node package used to create APIs and handle routing configuration, facilitating the connection and interaction between a web application's front-end and back-end. Using Express, a developer is able to define routers which describe how a webpage will handle and respond to the different HTTP request types at defined URIs. Express allows for the use of middleware to handle requests and manipulate any data they are sent with or lack. A typical middleware used in Express is a converts a request's body into JSON, so that it can be sanitised and forwarded to a database or verified for correctness. Express is particularly effective for developer's because its syntax and router objects allow for DRY, reuseable code elements which speeds up development (GeeksforGeeks, 2023).

Node.js is a runtime environment which allows the Express scripting of a web application to run. Express is built using Javascript which was designed to be executed by web browsers. Node provides an alternative way to run JS scripts so that the webpage and server-side logic can be executed concurrently and written in the same language. In addition, Node.js is open-sourced and has a large developmental community that generates packages to extend server-side capabilities.

Finally, MongoDB is the database layer of the MERN stack. MongoDB is a NoSQL database that can be interacted with using Javascript syntax. MongoDB databases can be run locally or using MongoDB Inc.'s cloud services. MongoDB is particularly valued due to its flexible data structures which allow developers to define, store and query instances without the strict formatting required by SQL databases (GeeksforGeeks, 2023). In the MERN stack, MongoDB is used to store the data that populates a page and to record users' posted data.

In combination, the React layer provides the tools to create webpages for users to interact with, the Express layer handles the user's interactions by requesting the appropriate resources, Node.js allows Express to execute and offers additional capabilities and MongoDB stores data for the user to interact with. Besides effective performance, the key element that makes the MERN stack popular is its consistent use of Javascript eliminating script conversions and allowing developers to easily learn the software syntax (MongoDB, n.d. & Kadam et. al., 2023).

### References

GeeksforGeeks (2023) _[MERN Stack](https://www.geeksforgeeks.org/mern-stack/)_, GeeksforGeeks website, accessed 27 July 2024.

GeeksforGeeks (2024) _[ReactJS Virtual DOM](https://www.geeksforgeeks.org/reactjs-virtual-dom/)_, GeeksforGeeks website, accessed 28 July 2024.

Kadam, Y., Goplani, A, Mattoo, S., Gupta, S. K., Amrutkar, D., Dhanke, J. (2023). 'Introduction to MERN Stack & Comparison with Previous Technologies', _European Chemical Bulletin_ 12(4), pp. 14382-14386. DOI: 10.48047/ecb/2023.12.si4.1300.

MongoDB (n.d.) _[Mern Stack Explained](https://www.mongodb.com/resources/languages/mern-stack-tutorial)_, MongoDB website, accessed 27 July 2024.

## Q4. A team is about to engage in a project, developing a website for a small business. What knowledge and skills would they need in order to develop the project? /6

- technical, soft skills too
- Effectively describes a range of skills and knowledge required by IT workers to complete a quality web development project

To design and create a website for a business, a development team needs a specific understanding of the business' requirements. Considering Boehm's (1976) model for quality software, a website should be designed considering the contexts that it will be engaged with. Firstly, the development team must understand what functionality the website needs to have to aid the business. By extension, the team needs to understand the typical website user so that the website can be designed to suit their hardware and interface requirements. For example, a general practice business will likely need to feature contact information, service offerings and information about the clinic's doctors. In addition, the business may require additional functionality such as an online booking system implemented with dynamic webpages and form submissions, or, the company may want to keep these systems on site for simplicity. By extension, depending on the clinic's customers or location, the typical user may have limited website literacy and may require a simpler user interface, or the business may want a sophisticated and sleek interface to attract a different customer type. These requirements should be considered to ensure the website fulfills Boehm's recommendations for usability and portability across devices. The team also needs to understand the company's maintenance plans following the websites creation to ensure that it is appropriately future-proofed. If the business does not plan on updating the site frequently, the team needs to ensure the layout and functionality is robust as web technologies advance, a consideration that would shape the entire design process. It is key that a team understands the contexts that their website will be used in to successfully design and implement it.

There are distinct technical skills a development team requires to create a website using a particular technology stack. In many contexts, the MERN stack provides all of the tools required to make an approptiate small business' website. To use the MERN stack, the design team must know how to use Javascript as well as the specific syntax of MongoDB, Express, React JS and how to configure and use Node.js. Besides these defined skills, there are complementary understandings the team must apply to use these tools. When designing the back-end and routing for the website, the team members must implement RESTful practices so that the website functions in a stable and maintainable way. This includes defining routes that are logical and delivering data in a consistent way. Notably, creating a RESTful API requires a reliable database and consistant storage structure. Because MongoDB is a NoSQL database, the development team has full control over how instances are recorded which allows for quick initialisation but can also permit messy formatting. For these reasons, the development team must have a technical knowledge of the MERN stack but also a conceptual knowledge of how to design the website's database and backend to be consistent and maintainable.

In addition to project understanding and technical knowledge, the team members require project management and planning skills. In many contemporary projects, Agile methodologies are used to set goals, manage deadlines and respond to project challenges as they arise. Adopting Agile techniques including using Kanban boards to visually communicate progress and prioritise tasks, scheduling daily stand-ups and feedback sessions and dedicating resources based on team agreement are all beneficial practices that will bolster a teams productivity (Moe, et. all, 2014). Whilst a development team does not need to know Agile project management specifically, the team requires a structured division of work to ensure all tasks can be completed on schedule. In a technical context, project management requires a team to develop and enforce source control habits. Using Git or an alternative software, team members must know how to back-up and share their work and how to archive their progress with succinct commit messages and pull requests.

When creating a website, a development team requires technical and conceptual skills to handle the design, programming and project management elements of the task.

### References

Boehm, B. W., Brown, J. R. and Lipow, M., (1976). ‘Quantitative Evaluation of Software Quality’, _Proceedings of the 2nd international conference on Software engineering_, pp. 592-605. DOI: 10.5555/800253.807736.

Brede Moe, N., Dingsøyr, T., Dyba, T. (2014) 'Agile Project Management', in Ruhe, G., Wohlin, C. (eds.) _Software Project Management in a Changing World_. Berlin: Springer-Verlag, pp. 277-300.

## Q5. With reference to one of your own projects, discuss what knowledge or skills were required to complete your project, and to overcome challenges /6

- assignments, side projects
- challenges you overcame extrapolated
- Effectively describes a range of skills and knowledge used to complete a project

Designing and creating a web server API using Flask and Postgres was a project that required distinct technical and conceptual skills. The project featured these tools as well as SQLAlchemy and marshmallow and was designed as parent-teacher communication tool that allowed each side to make comments about students, parents to enter contact information for their child's attendances and endpoints for teachers to access this contact information.

A core challenge creating the application was designing the database efficiently to allow for RESTful endpoints. When I began this process, I found it challenging to identify what data needed to be stored and how to best structure the tables. Specifically, the task of normalising the data was daunting. To handle this macro challenge, I decided to break down the task down into its technical and conceptual elements. First, I found it helpful to research similar API tools that childcare businesses used to facilitate their data and communication. After collecting references, I identified the features that my application needed by reading reviews and imagining use cases. This allowed me to identify improvements I could incorporate into my API such as improving the security of the app by reducing the amount of input data required. To refine the tables, I completed additional research into ERD diagrams and compared my work to industry examples. This allowed me to develop my understanding of ERD design and normalise the database, step-by-step, in a way that prevented technical challenges in the implementation stages. In addition, I continued to review the table design as I designed the API's endpoints which helped identify flaws which I was able to fix such as using a merge table to link contact, children and attendance data in a distinct table to prevent duplicate data.

In addition, to the database design skills that the project required, the task required me to improve my ability using models and schemas. Connecting the Flask routes to the database was simple to implement yet, as I continued programming, I found that my models allowed users to input flawed data which would raise errors. marshmallow's validation tools proved a powerful and convenient way to prevent these errors but, when I began the project, I only had a rudimentary understanding of how they could be applied. In particular, there were input routes where I wanted users to have to choose from one of three values. In this instance, I was able to refer to the reference documentation and find the OneOf() validator which was perfect for the situation. In addition, I had trouble handling datatype errors which would arise when POST requests were submitted with formatting errors but were not particularly descriptive when printed to the console. Again, I referred to SQLAlchemy and marshmallow's documentation and online forums to identify the issue and brainstorm solutions. Two notable examples were when submitting a phone number beginning with a zero, Python would disregard the zero which, in turn, would raise a marshmallow validator error. This was challenging to identify but, after logging the data at each stage, I was able find the error and convert the number input to a string and add the zero knowing that marshmallow could interpret numbers or strings. The other example was submitting a boolean value for an "is_admin" attribute. The request body would inconsistently be interpretted and it took lengthy troubleshooting to recognise the error would arise when the boolean was submitted without being wrapped in appostrophes. Each of these issues required patient research and a more through understanding of Flask, marshmallow and SQLAlchemy behaviours. Preventing these issues at the API level makes the project more robust and easy to incorporate into a front-end application.

Designing and creating a server API required technical knowledge of how to use a Flask, PostgreSQL, SQLAlchemy and marshmallow tech stack as well as the ability to troubleshoot errors in a pragmatic way. In addition, a key challenge of creating a successful API is designing the database in a considered way. With each challenge, I was able to overcome the problem with research and patience.

### References



## Q6. With reference to one of your own projects, evaluate how effective your knowledge and skills were for this project, and suggest changes or improvements for future projects of a similar nature /6

- here's what I would do differently
- Evaluates effectiveness of knowledge and skills accurately, providing examples, and providing an insightful improvement on each skill

- when developing a Python CLI app, I required a variety of technical knowledge to create the functionality that I wanted
- the app works by presenting the user a string of text describing a mystery object, a pokemon card
- the user can then choose between more hints or geuss
- the application features a scoreboard which uses CSV
- the app presents data from a JSON file and features modularised, reusable code to allow for two game modes and scoreboards
- Agile project management, didn't know how to do it, had to adjust my methodology as I went
- Particular challenge due to time management, the app was more complex than I realised
- testing skills would be better

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
